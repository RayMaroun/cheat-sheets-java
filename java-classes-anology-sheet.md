## Classes in Java

**Analogy: A Blueprint for a Car**  
Think of a class as a blueprint for making cars. The blueprint outlines what features (attributes) a car has (like a make, model, and color) and what it can do (methods, such as drive or honk). Just like how a blueprint provides instructions for building a car, a class in Java provides instructions for creating objects.

## Attributes

**Analogy: A Car’s Characteristics**  
Attributes (also called fields or properties) are the data stored inside an object. If we’re talking about a car, attributes might include the car’s make, model, color, and year. These characteristics define the car’s state at any given time.

## Constructors

**Analogy: Manufacturing a Car**  
When a new car is manufactured, it’s assembled with specific parts and features. Similarly, a constructor in Java is a special method that runs when an object is created. It sets up initial values for attributes (like assigning the make and model to the car) so that the new object has its own state right away.

## Creating a Class

**Analogy: Defining the Blueprints for a New Car Model**  
Creating a class in Java is like designing a new model of car on paper. You decide what characteristics (attributes) the car will have (e.g., make, model, color) and what actions (methods) the car can perform (e.g., startEngine(), drive(), stopEngine()).

Example:

```java
public class Car {
    // Attributes
    private String make;
    private String model;
    private int year;

    // Constructor
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Methods
    public void startEngine() {
        System.out.println("Engine started!");
    }

    public void drive() {
        System.out.println("The car is now driving.");
    }
}
```

## Creating an Object

**Analogy: Assembling a Specific Car**  
When you create an object from a class, it’s like taking the car blueprint and actually building one specific car. That car (object) will have its own unique set of attribute values (e.g., “Toyota,” “Corolla,” 2025).

Example:

```java
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Toyota", "Corolla", 2025);
        myCar.startEngine();
        myCar.drive();
    }
}
```

## Getters and Setters

**Analogy: Accessing and Changing Car Details Safely**  
Getters and setters control how attributes are read and updated. Imagine you’re a mechanic checking a car’s details or updating its parts. The “getter” methods let you read details (like the car’s year), and the “setter” methods let you change details (like repainting the car a different color) in a controlled way.

Example:

```java
public class Car {
    private String make;
    private String model;
    private int year;

    // Constructor
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Getter for year
    public int getYear() {
        return year;
    }

    // Setter for year
    public void setYear(int year) {
        this.year = year;
    }

    // ...
}
```

## Overloading Methods

**Analogy: Different Ways to Drive a Car**  
You might have one “drive” method that just starts driving at a default speed, and another “drive” method that allows you to set a specific speed. They do similar things (driving), but the parameters differ. This is called method overloading.

Example:

```java
public void drive() {
    System.out.println("Driving at a default speed.");
}

public void drive(int speed) {
    System.out.println("Driving at " + speed + " km/h.");
}
```

## Overloading Constructors

**Analogy: Buying a Car with Different Options**  
A car can come with standard features, or you can upgrade for more customization. In Java, you can have multiple constructors with different sets of parameters, letting you create objects in various configurations.

**Example:**

```java
public class Car {
    private String make;
    private String model;
    private int year;
    private String color;

    // Overloaded constructor #1 (standard options)
    public Car(String make, String model) {
        this(make, model, 2025, "Black");
    }

    // Overloaded constructor #2 (custom options)
    public Car(String make, String model, int year, String color) {
        this.make = make;
        this.model = model;
        this.year = year;
        this.color = color;
    }

    // ...
}
```

Here, **Constructor #1** sets some default values (year and color), simulating a standard package. **Constructor #2** provides more flexibility, simulating a premium package where a buyer can choose the year and color.
