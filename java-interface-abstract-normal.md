# Java Interfaces vs. Abstract Classes vs Normal Classes

| Feature              | Interface                                                                           | Abstract Class                                                            | Normal Class (Concrete Class)                          |
| -------------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------ |
| **Definition**       | A reference type for defining methods without implementation                        | A class that cannot be instantiated and is meant to be subclassed         | A fully implementable class that can be instantiated   |
| **Methods**          | Only abstract, default, and static methods (default and static from Java 8 onwards) | Can have abstract and concrete methods                                    | Only concrete methods                                  |
| **Fields**           | Cannot have instance fields; only static final constants                            | Can have instance fields                                                  | Can have instance fields                               |
| **Constructors**     | Cannot have constructors                                                            | Can have constructors                                                     | Can have constructors                                  |
| **Instantiation**    | Cannot be instantiated                                                              | Cannot be instantiated                                                    | Can be instantiated                                    |
| **Inheritance**      | Supports multiple inheritance (a class can implement multiple interfaces)           | Single inheritance (a class can extend only one abstract class)           | Single inheritance (a class can extend only one class) |
| **Access Modifiers** | Methods are implicitly public; fields are implicitly public, static, and final      | Methods can have any access modifier; fields can have any access modifier | Methods and fields can have any access modifier        |
| **Use Case**         | Define a contract for what a class can do without implementation details            | Share code among closely related classes and provide a base class         | Define a full implementation of a class                |

### Example Code

**Interface Example:**

```java
public interface Drivable {
    void drive();
    default void defaultMethod() {
        System.out.println("Default method in interface");
    }
    static void staticMethod() {
        System.out.println("Static method in interface");
    }
}
```

**Abstract Class Example:**

```java
public abstract class Vehicle {
    private String model;
    public Vehicle(String model) {
        this.model = model;
    }
    public abstract void start();
    public void stop() {
        System.out.println("Vehicle is stopping");
    }
}
```

**Concrete Class Example:**

```java
public class Car {
    private String model;
    public Car(String model) {
        this.model = model;
    }
    public void start() {
        System.out.println("Car is starting");
    }
    public void stop() {
        System.out.println("Car is stopping");
    }
}
```

### Key Takeaways

- **Interfaces** are for defining a contract with abstract methods, default methods, and static methods.
- **Abstract classes** are for sharing code among related classes and can include both abstract and concrete methods.
- **Normal classes** are fully implementable and instantiable, serving as complete blueprints for objects.
