## Java Inheritance Cheat Sheet

### 1. Normal Parent and Child Classes (Inheritance)

#### Definition

- **Parent Class**: Also known as a superclass, it's a class whose properties and methods are inherited by another class.
- **Child Class**: Also known as a subclass, it inherits properties and methods from the parent class.

#### Example

```java
class Parent {
    void display() {
        System.out.println("Parent display");
    }
}

class Child extends Parent {
    void displayChild() {
        System.out.println("Child display");
    }
}
```

#### Analogy

- Think of it like a family tree. The child inherits traits (methods and properties) from the parent.

#### Use Case

- **Reusable Code**: Allows for code reuse by inheriting common functionality from a parent class. For example, a `Vehicle` class might have methods like `startEngine()` or `stop()`, and subclasses like `Car` and `Motorbike` can inherit these methods without rewriting them.
- **Polymorphism**: Enables polymorphism, where a subclass can be treated as an instance of the parent class, enhancing flexibility. For example, a method that accepts a `Vehicle` object can work with any subclass of `Vehicle`.

---

### 2. Abstract Classes

#### Definition

- An abstract class cannot be instantiated and may contain abstract methods (without a body). It's used to provide a base for subclasses to build upon.

#### Example

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square extends Shape {
    void draw() {
        System.out.println("Drawing Square");
    }
}
```

#### Analogy

- Think of an abstract class like a blueprint. You can't build a house (i.e., instantiate) just from a blueprint, but it guides the construction of actual houses (subclasses).

#### Use Case

- **Common Template**: Serves as a template for subclasses. An abstract class `DatabaseConnection` might define a method `connect()` but not implement it, letting subclasses like `MySQLConnection` or `OracleConnection` provide specific implementations.
- **Control Over Inheritance**: Allows for more control over inheritance. Abstract classes can dictate the structure (methods) that all subclasses must follow, ensuring consistency.

---

### 3. Interfaces

#### Definition

- An interface is a completely abstract class with only abstract methods. It is used to define behaviors that can be implemented by any class, regardless of its position in the class hierarchy.

#### Example

```java
interface Drawable {
    void draw();
}

class Rectangle implements Drawable {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

class Triangle implements Drawable {
    public void draw() {
        System.out.println("Drawing Triangle");
    }
}
```

#### Analogy

- An interface is like a contract. Any class that "signs" (implements) this contract agrees to provide specific behavior (methods).

#### Use Case

- **Multiple Inheritance**: In Java, a class can implement multiple interfaces, allowing for a form of multiple inheritance. For instance, a `SmartPhone` class can implement interfaces like `Camera`, `GPS`, and `MediaPlayer`, incorporating functionalities from all these interfaces.
- **Decoupling Code**: Interfaces help in decoupling code as changes in the interface implementation do not affect the classes that implement the interface, as long as the method signatures remain the same.

---

### Key Differences

- **Inheritance (Parent/Child Classes)**:

  - Establishes a direct relationship between classes (an "is-a" relationship).
  - Subclasses inherit both behavior and state (methods and properties) from the parent class.
  - Subclasses can override inherited methods to provide specific functionality.

- **Abstract Class**:

  - Cannot be instantiated; serves as a conceptual foundation.
  - Can have both abstract methods (without implementation) and regular methods with implementation.
  - Useful when various subclasses share common methods or fields but require unique implementations of some other methods.

- **Interface**:
  - Cannot have any implementation; it's purely a contract for what methods a class should implement.
  - A class can implement multiple interfaces, facilitating a form of multiple inheritance.
  - Promotes loose coupling, making code more modular and adaptable to change.

---

### Comparing Use Cases: When to Use Each

#### 1. Inheritance (Parent/Child Classes)

- **Best for Hierarchical Relationships**: Use when there's a clear hierarchical relationship (like `Animal` -> `Dog`, `Cat`). It's the most natural way to represent real-world inheritance.
- **Concrete Implementations**: Ideal when subclasses should inherit concrete methods and properties from a parent class.
- **Simple Extension of Functionality**: When extending a class to add or modify functionalities without changing the existing code structure.

#### 2. Abstract Classes

- **Common Blueprint with Partial Implementation**: Best when you have a common blueprint (like `Shape`) but need to enforce certain common behaviors (methods) across all subclasses.
- **Shared State or Functionality**: When different subclasses share some common methods or fields but also need unique implementations for other methods.
- **Control Over Inheritance**: If you need to control how subclasses are implemented to a certain extent, abstract classes provide a mix of enforced structure and flexibility.

#### 3. Interfaces

- **Multiple Inheritance and Loose Coupling**: Ideal when a class needs to inherit from multiple sources. Interfaces allow for a form of multiple inheritance and are great for defining capabilities like `Flyable`, `Readable`.
- **Contract for Behavior without Implementation**: Use when you need to define a contract (set of methods) that can be implemented by any class, regardless of where it sits in the class hierarchy.
- **Decoupling and Flexibility**: When you want to decouple the definition of what to do from the actual implementation. Interfaces are perfect for situations where you want to specify that certain classes must have specific methods, but the details of how these methods are implemented are left to the classes.

#### General Guidelines

- **Inheritance** is more straightforward but can lead to tightly coupled code if overused.
- **Abstract Classes** offer a middle ground, providing a concrete foundation but also flexibility for subclasses.
- **Interfaces** are the most flexible and promote loose coupling, making them ideal for defining capabilities and behaviors that can span across unrelated class hierarchies.

By understanding these specific use cases and guidelines, you can make more informed decisions about when to use each of these concepts in your Java programming.
