# 🧭 Java Interview Preparation Notes

A structured roadmap to revise **Core Java**, **OOP**, **Collections**, and **Interview Questions** — ideal for placements and technical interviews.

---

## 🧩 1. Core Java Concepts

### ✅ OOP Principles

- **Encapsulation**: Wrapping data and methods into a single unit (class). Use private fields and public getters/setters.
  ```java
  class Person {
      private String name;
      public String getName() { return name; }
      public void setName(String name) { this.name = name; }
  }

Inheritance: Enables a class to inherit properties and behaviors from another class using extends
 
     ```java
    class Animal {
        void sound() { System.out.println("Generic sound"); }
    }
    class Dog extends Animal {
        void sound() { System.out.println("Bark"); }
    }

Polymorphism:
Compile-time (Method Overloading):

     ```java
    class Calculator {
        int add(int a, int b) { return a + b; }
        double add(double a, double b) { return a + b; }
    }
Runtime (Method Overriding):

     ```java
    class Shape {
        void draw() { System.out.println("Drawing shape"); }
    }
    class Circle extends Shape {
        void draw() { System.out.println("Drawing circle"); }
    }
Abstraction: Hiding internal details and showing only essential features. Achieved using abstract classes or interfaces.

    ```java
    abstract class Vehicle {
        abstract void start();
    }
    class Car extends Vehicle {
        void start() { System.out.println("Car starts"); }
    }


| Concept | Description | Example |
|----------|--------------|----------|
| **Encapsulation** | Wrapping data (variables) and code (methods) together as a single unit | Using `private` variables with getters and setters |
| **Inheritance** | Acquiring properties and methods from another class | `class Dog extends Animal` |
| **Polymorphism** | One interface, many implementations | Method overriding in subclasses |
| **Abstraction** | Hiding implementation details, showing only essentials | Using `abstract` classes or `interfaces` |



🔹 Constructors & Overloading
-Constructors initialize objects.
-Overloading allows multiple constructors with different parameter lists.

    ```java
    class Book {
        String title;
        Book() {
            title = "Unknown"; 
            }
        Book(String t) {
        title = t; 
        }
    }

Access Modifiers

Modifier	Scope
public	Accessible everywhere
private	Accessible only within the class
protected	Accessible within package and subclasses
default	Accessible within the same package

Static vs Instance
Static: Belongs to the class, shared across all instances.

Instance: Belongs to the object, unique per instance.

    try {
        // risky code
    } catch (Exception e) {
        // handle exception
    } finally {
        // always executes
    }


2. 📦 Java Collections Framework
🔹 List, Set, Map, Queue


🔹 Iterators vs For-each
Iterator: Explicit control, supports remove().

For-each: Cleaner syntax, read-only iteration.



🔹 Comparable vs Comparator
Comparable: Natural ordering via compareTo(), implemented in the class.

Comparator: Custom ordering via compare(), implemented externally.


3. 🚀 Java 8+ Features
🔹 Lambda Expressions

        Runnable r = () -> System.out.println("Hello");
Streams API

        List<String> names = Arrays.asList("A", "B", "C");
        names.stream().filter(n -> n.startsWith("A")).forEach(System.out::println);
Functional Interfaces
Interfaces with a single abstract method.

Examples: Runnable, Callable, Predicate, Function

4. 🧵 Multithreading & Concurrency
🔹 Thread Lifecycle
New → Runnable → Running → Blocked/Waiting → Terminated

🔹 Runnable vs Callable
Runnable: No return value, no checked exceptions.

Callable: Returns a value, can throw checked exceptions.

Synchronization and Locks
java
synchronized void method() {
    // thread-safe code
}
Alternatives: ReentrantLock, AtomicInteger, volatile


5. 🧠 Memory Management
🔹 Stack vs Heap
Stack: Stores method calls and local variables.

Heap: Stores objects and class instances.

🔹 Garbage Collection
Automatic cleanup of unreachable objects.


---

### ✨ Author
**Merin Magi Telson**  
_M.C.A. Student | Java Developer in Training 

