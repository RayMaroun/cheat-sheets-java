# Classes in Java

A class is a blueprint for creating objects in Java. It defines the properties and behavior of objects that belong to that class.

## Attributes

Attributes, also known as fields or properties, are the variables that define the state of an object. They represent the data that an object contains. For example, a Person class may have attributes like name, age, and gender.

## Constructors

Constructors are special methods that are used to create objects of a class. They initialize the attributes of an object when it is created. A constructor has the same name as the class and no return type. For example:

```java
public class Person {
String name;
int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

}
```

## Creating a Class

To create a class in Java, you need to use the class keyword followed by the name of the class. For example:

```java
public class Person {
// attributes and methods go here
}
```

## Creating an Object

To create an object of a class in Java, you need to use the new keyword followed by the name of the class and parentheses. For example:

```java
Person person1 = new Person("John", 30);
```

This creates a new Person object with the name "John" and age 30.

## Getters and Setters

Getters and setters are methods that allow you to access and modify the attributes of an object, respectively. They are used to ensure that the attributes are accessed and modified in a controlled way. For example:

```java
public class Person {
private String name;
private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

}
```

The private keyword is used to make sure that the attributes can only be accessed or modified through the getters and setters.

## Overloading Methods

Method overloading is the process of defining multiple methods with the same name but different parameters. Java uses the number and types of the parameters to determine which method to call. For example:

```java
public class Calculator {
public int add(int a, int b) {
return a + b;
}

    public double add(double a, double b) {
        return a + b;
    }

}
```

## Overloading Constructors

Constructor overloading is the process of defining multiple constructors with different parameters. Java uses the number and types of the parameters to determine which constructor to call. For example:

```java
public class Person {
private String name;
private int age;

    public Person() {
        this.name = "Unknown";
        this.age = 0;
    }

    public Person(String name) {
        this.name = name;
        this.age = 0;
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

}
```

The first constructor creates a Person object with the name "Unknown" and age 0. The second constructor creates a Person object with the specified name and age 0. The third constructor creates a Person object with the specified name and age.
