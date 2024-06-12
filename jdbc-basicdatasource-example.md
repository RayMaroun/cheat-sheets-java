# JDBC and BasicDataSource Detailed Example

This example will guide you through setting up a simple Java application to interact with the Sakila database using JDBC, BasicDataSource, and a DataManager class.

## Step-by-Step Instructions

### Step 1: Setup the Environment

1. **Ensure the Sakila Database is Installed:**

   - The Sakila database should already be installed on your MySQL server.

2. **Project Setup:**

   - Create a new Java project in your IDE.
   - Add the necessary dependencies to your project. If using Maven, add the following dependencies to your `pom.xml`:

   ```xml
   <dependencies>
       <!-- JDBC MySQL Connector -->
       <dependency>
           <groupId>mysql</groupId>
           <artifactId>mysql-connector-java</artifactId>
           <version>8.0.33</version>
       </dependency>
       <!-- Apache Commons DBCP -->
       <dependency>
           <groupId>org.apache.commons</groupId>
           <artifactId>commons-dbcp2</artifactId>
           <version>2.11.0</version>
       </dependency>
   </dependencies>
   ```

   The `mysql-connector-java` dependency allows Java to communicate with the MySQL database, while `commons-dbcp2` provides database connection pooling, which helps manage database connections efficiently.

### Step 2: Organize Packages

To keep our project organized, we will create different packages for different purposes.

- Create the following packages in your project:
  - `com.pluralsight.manager`
  - `com.pluralsight.models`
  - `com.pluralsight.main`

### Step 3: Create the Actor Model Class

In the `com.pluralsight.models` package, create the `Actor` class:

```java
package com.pluralsight.models;

public class Actor {
    private int actorId;
    private String firstName;
    private String lastName;

    // Constructor
    public Actor(int actorId, String firstName, String lastName) {
        this.actorId = actorId;
        this.firstName = firstName;
        this.lastName = lastName;
    }

    // Getters
    public int getActorId() {
        return actorId;
    }

    public String getFirstName() {
        return firstName;
    }

    public String getLastName() {
        return lastName;
    }
}
```

**Explanation:**

- The `Actor` class is a simple model class that represents an actor from the database.
- It has three fields: `actorId`, `firstName`, and `lastName`, which correspond to the columns in the `actor` table in the Sakila database.
- The constructor initializes these fields, and the getter methods allow us to retrieve their values.

### Step 4: Create the DataManager Class

In the `com.pluralsight.manager` package, create the `DataManager` class:

```java
package com.pluralsight.manager;

import com.pluralsight.models.Actor;

import javax.sql.DataSource;
import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public class DataManager {
    private DataSource dataSource;

    // Constructor that receives a DataSource
    public DataManager(DataSource dataSource) {
        this.dataSource = dataSource;
    }

    // Method to fetch actor by ID
    public Actor getActorById(int actorId) throws SQLException {
        String query = "SELECT * FROM actor WHERE actor_id = ?";
        try (Connection connection = dataSource.getConnection();
             PreparedStatement statement = connection.prepareStatement(query)) {

            // Set the parameter for the query
            statement.setInt(1, actorId);
            ResultSet resultSet = statement.executeQuery();

            // Check if we got any results
            if (resultSet.next()) {
                // Extract the information from the result set
                int id = resultSet.getInt("actor_id");
                String firstName = resultSet.getString("first_name");
                String lastName = resultSet.getString("last_name");

                // Create an Actor object with the extracted information
                return new Actor(id, firstName, lastName);
            } else {
                // Handle case where no actor was found
                System.out.println("No actor found with ID: " + actorId);
                return null;
            }
        }
    }

    // Method to fetch all actors
    public List<Actor> getAllActors() throws SQLException {
        String query = "SELECT * FROM actor";
        List<Actor> actors = new ArrayList<>();
        try (Connection connection = dataSource.getConnection();
             PreparedStatement statement = connection.prepareStatement(query);
             ResultSet resultSet = statement.executeQuery()) {

            // Iterate through the result set and create Actor objects
            while (resultSet.next()) {
                int id = resultSet.getInt("actor_id");
                String firstName = resultSet.getString("first_name");
                String lastName = resultSet.getString("last_name");
                actors.add(new Actor(id, firstName, lastName));
            }
        }
        return actors;
    }

    // Method to fetch actors by last name
    public List<Actor> getActorsByLastName(String lastName) throws SQLException {
        String query = "SELECT * FROM actor WHERE last_name = ?";
        List<Actor> actors = new ArrayList<>();
        try (Connection connection = dataSource.getConnection();
             PreparedStatement statement = connection.prepareStatement(query)) {

            // Set the parameter for the query
            statement.setString(1, lastName);
            ResultSet resultSet = statement.executeQuery();

            // Iterate through the result set and create Actor objects
            while (resultSet.next()) {
                int id = resultSet.getInt("actor_id");
                String firstName = resultSet.getString("first_name");
                String lastNameResult = resultSet.getString("last_name");
                actors.add(new Actor(id, firstName, lastNameResult));
            }
        }
        return actors;
    }
}
```

**Explanation:**

- The `DataManager` class is responsible for interacting with the database.
- It has a constructor that takes a `DataSource` object, which manages the database connections.
- The `getActorById` method retrieves an actor by their ID. It uses a SQL `SELECT` query with a `WHERE` clause to find the actor by their ID. If the actor is found, it extracts their information and creates an `Actor` object. If not, it prints a message and returns `null`.
- The `getAllActors` method retrieves all actors from the database. It uses a SQL `SELECT` query to get all rows from the `actor` table, iterates through the result set, and creates `Actor` objects for each row.
- The `getActorsByLastName` method retrieves actors by their last name. It uses a SQL `SELECT` query with a `WHERE` clause to find actors with the specified last name. It then iterates through the result set and creates `Actor` objects.

### Step 5: Create the Main Application Class

In the `com.pluralsight.main` package, create the `MainApp` class:

```java
package com.pluralsight.main;

import com.pluralsight.manager.DataManager;
import com.pluralsight.models.Actor;
import org.apache.commons.dbcp2.BasicDataSource;

import java.sql.SQLException;
import java.util.List;
import java.util.Scanner;

public class MainApp {
    public static void main(String[] args) {
        // Ensure that username and password are provided as program arguments
        if (args.length != 2) {
            System.out.println("Please provide database username and password as program arguments.");
            return;
        }

        String dbUsername = args[0];
        String dbPassword = args[1];

        // Create the BasicDataSource
        BasicDataSource dataSource = new BasicDataSource();
        dataSource.setUrl("jdbc:mysql://localhost:3306/sakila");
        dataSource.setUsername(dbUsername);
        dataSource.setPassword(dbPassword);

        // Create DataManager with the DataSource
        DataManager dataManager = new DataManager(dataSource);

        Scanner scanner = new Scanner(System.in);

        // Menu for user to choose an operation
        while (true) {
            System.out.println("\nChoose an operation:");
            System.out.println("1. Get actor by ID");
            System.out.println("2. Get all actors");
            System.out.println("3. Get actors by last name");
            System.out.println("4. Exit");
            int choice = scanner.nextInt();

            try {
                switch (choice) {
                    case 1:
                        // Get actor by ID
                        System.out.print("Enter actor ID: ");
                        int actorId = scanner.nextInt();
                        Actor actor = dataManager.getActorById(actorId);
                        if (actor != null) {
                            System.out.println("Actor ID: " + actor.getActorId());
                            System.out.println("First Name: " + actor.getFirstName());
                            System.out.println("Last Name: " + actor.getLastName());
                        }
                        break;

                    case 2:
                        // Get all actors
                        List<Actor> allActors = dataManager.getAllActors();
                        System.out.println("All actors:");
                        for (Actor a : allActors) {
                            System.out.println(a.getFirstName() + " " + a.getLastName());
                        }
                        break;

                    case 3:
                        // Get actors by last name
                        System.out.print("Enter last name: ");
                        scanner.nextLine(); // Consume newline left-over
                        String lastName = scanner.nextLine();
                        List<Actor> actorsByLastName = dataManager.getActorsByLastName(lastName);
                        if (actorsByLastName.isEmpty()) {
                            System.out.println("No actors found with last name: " + lastName);
                        } else {
                            System.out.println("Actors with last name " + lastName + ":");
                            for (Actor a : actorsByLastName) {
                                System.out.println(a.getFirstName() + " " + a.getLastName());
                            }
                        }
                        break;

                    case 4:
                        // Exit
                        System.out.println("Exiting...");
                        return;

                    default:
                        System.out.println("Invalid choice. Please try again.");
                }
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
    }
}
```

**Explanation:**

- The `MainApp` class is the entry point of the application.
- It ensures that the username and password for the database are provided as command-line arguments.
- It creates a `BasicDataSource` object with the database connection details.
- It creates a `DataManager` instance with the `BasicDataSource`.
- It presents a menu to the user to choose an operation:
  - **Get actor by ID:** Prompts the user for an actor ID, calls `getActorById`, and displays the actor details.
  - **Get all actors:** Calls `getAllActors` and displays the list of all actors.
  - **Get actors by last name:** Prompts the user for a last name, calls `getActorsByLastName`, and displays the list of actors with that last name.
  - **Exit:** Exits the application.
