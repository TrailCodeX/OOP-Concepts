# 📘 Java Basics Summary

## 🧰 Java Development Environment
- **JDK (Java Development Kit):** Includes compiler, interpreter, and tools for development and execution.
- **JRE (Java Runtime Environment):** Used to run Java programs; includes JVM.
- **JVM (Java Virtual Machine):** Executes bytecode line by line; built into both JDK and JRE.

---

## 🧑‍💻 Writing and Running Java Programs
1. Use any IDE (e.g., Notepad, Eclipse).
2. Save file with `.java` extension.
3. Compile: `javac MyProgram.java`
4. Run: `java MyProgram`

---

## ✍️ Java Coding Standards
- Use camelCase for variables.
- Names should be self-explanatory and pronounceable.
- Common temp variables: `i`, `j`, `k`, `c`, `d`, `e`.

---

## 📦 Java Data Types

| Type     | Size     | Range                              | Default |
|----------|----------|-------------------------------------|---------|
| byte     | 8 bits   | -128 to 127                         | 0       |
| short    | 16 bits  | -32,768 to 32,767                   | 0       |
| int      | 32 bits  | -2^31 to 2^31-1                     | 0       |
| long     | 64 bits  | -2^63 to 2^63-1                     | 0L      |
| float    | 32 bits  | ±1.4×10^-45 to ±3.4×10^38           | 0.0f    |
| double   | 64 bits  | ±4.9×10^-324 to ±1.8×10^308         | 0.0     |
| char     | 16 bits  | 0 to 65,535                         | '\u0000'|
| boolean  | ~1 bit   | true or false                       | false   |

- **Reference Types:** Objects, arrays, interfaces.
- **String:** Immutable, supported via `java.lang.String`.

---

## 📥 Input Handling with Scanner

    ```java
    Scanner sc = new Scanner(System.in);
    int rollNo = sc.nextInt();
    sc.nextLine(); // to consume leftover newline
    String name = sc.nextLine();


# Java Type Casting & Conversion Notes

## Primitive Data Types in Java

Java has 8 primitive types. Each has a default value and specific size:

| Type     | Size     | Description            | Default Value |
|----------|----------|------------------------|---------------|
| byte     | 8 bits   | Signed integer         | 0             |
| short    | 16 bits  | Signed integer         | 0             |
| char     | 16 bits  | Unsigned Unicode char  | '\u0000'      |
| int      | 32 bits  | Signed integer         | 0             |
| long     | 64 bits  | Signed integer         | 0L            |
| float    | 32 bits  | Decimal number         | 0.0f          |
| double   | 64 bits  | Decimal number         | 0.0d          |
| boolean  | ~1 bit   | true or false          | false         |

## Primitive Casting

### Implicit Casting (Widening)
- Automatically done by compiler.
- Converts smaller type to larger type.

    ```java
    int numOne = 50;
    double numTwo = numOne; // int to double
    ```

### Explicit Casting (Narrowing)
- Manually done using cast operator.
- Converts larger type to smaller type.
- May cause data loss.

    ```java
    double numOne = 50.75;
    int numTwo = (int) numOne; // double to int
    ```

## Derived Casting (Inheritance-Based)

### Upcasting
- Subclass to Superclass
- Implicit and safe

    ```java
    Employee emp = new Manager(); // Manager is treated as Employee
    ```

### Downcasting
- Superclass to Subclass
- Explicit and risky (may cause ClassCastException)

    ```java
    Manager mgr = (Manager) emp; // Only safe if emp is actually a Manager
    ```

## Wrapper Classes

Java provides wrapper classes to use primitives as objects:

| Primitive | Wrapper     |
|-----------|-------------|
| boolean   | Boolean     |
| byte      | Byte        |
| char      | Character   |
| short     | Short       |
| int       | Integer     |
| long      | Long        |
| float     | Float       |
| double    | Double      |

## Autoboxing and Unboxing

### Autoboxing: primitive to wrapper
    
    ```java
    Integer balance = 100; // int to Integer
    ```

### Unboxing: wrapper to primitive

    ```java
    int total = balance; // Integer to int
    ```

### Benefits
- Interchangeability between primitives and objects.
- Reduces need for explicit casting.
- Enables use in collections and expressions.

## Example: Derived Casting with Inheritance

    ```java
    class Employee {
        void doTask() {
            System.out.println("As per designation");
        }
    }
    
    class Manager extends Employee {
        void doTask() {
            System.out.println("Manage the office");
        }
    }
    
    class Accountant extends Employee {
        void doTask() {
            System.out.println("Manage Accounts");
        }
    }
    
    public class DerivedCastingExample {
        public static void main(String[] args) {
            Employee employeeOne = new Manager();     // Upcasting
            Employee employeeTwo = new Accountant();  // Upcasting
    
            employeeOne.doTask();  // Output: Manage the office
            employeeTwo.doTask();  // Output: Manage Accounts
    
            Manager manager = (Manager) employeeOne;  // Downcasting
            manager.doTask();      // Output: Manage the office
    
            try {
                Accountant accountant = (Accountant) employeeOne; // Unsafe downcasting
                accountant.doTask();
            } catch (ClassCastException e) {
                System.out.println("ClassCastException: " + e.getMessage());
            }
        }
    }


# Java Interface & Multiple Inheritance Notes

## Interface Basics
- Declared using `interface` keyword.
- Contains only `public abstract` methods and `public static final` constants.
- Cannot be instantiated.
- Implemented by classes using `implements`.


    ```java
    interface PaymentMethod {
        void checkout(double amount, String paymentAPI);
    }


Important Points
 ➢ Abstract class gives reusable logic.
     Eg.Related subclasses
 ➢ Interface gives flexible type handling.
     Eg.Multiple Unrelated Classes

The rulebook for interface says,
   • An interface is 100% abstract class and has only abstract methods.
   • Class can implement any number of interfaces.
 Multiple Inheritance in Java 
    1. Aclass can implements multiple interfaces.
    2. Aninterface can extends multiple interfaces.

Marker/Tagging Interfaces:
 An interface with no methods is known as marker or tagged interface.
 Why marker interface used: 
It provides some useful information to JVM/compiler so that JVM/compiler performs some 
special operations on it. It is used for better readability of code.  Example: Serializable, 
Clonnable etc.

      ```java
       public interface InterfaceName {
       }
       
# Java Methods Notes

## What is a Method?
- A block of code that performs a specific task.
- Improves modularity and reusability.
- Can be called multiple times from different places.

---

## Method Syntax
    ```java
    returnType methodName(parameters) {
        // method body
    }

# Java Static vs Non-Static Methods

## 1. What is a Method?
- A block of code that performs a specific task.
- Improves modularity and reusability.


## 2. Static Method

### Characteristics
- Belongs to the class, not an instance.
- Can be called without creating an object.
- Can only access static members directly.

### Syntax
    ```java
    class Demo {
        static void greet() {
            System.out.println("Hello from static method");
        }
    }
    Demo.greet(); // calling without object
    ```

---

## 3. Non-Static Method

### Characteristics
- Belongs to an object of the class.
- Requires object creation to call.
- Can access both static and non-static members.

### Syntax
      ```java
      class Demo {
          void greet() {
              System.out.println("Hello from non-static method");
          }
      }
      Demo obj = new Demo();
      obj.greet(); // calling with object


## 4. Comparison Table

| Feature              | Static Method                  | Non-Static Method             |
|----------------------|--------------------------------|-------------------------------|
| Belongs to           | Class                          | Object                        |
| Invocation           | `ClassName.method()`           | `object.method()`             |
| Access to members    | Only static                    | Static + non-static           |
| Use case             | Utility, shared logic          | Instance-specific behavior    |

---


# Java main() Method Breakdown

## Method Signature
    ```java
    public static void main(String[] args)
    ```

### Keyword Breakdown

| Keyword         | Meaning                                                                 |
|----------------|-------------------------------------------------------------------------|
| `public`        | Access modifier — makes the method visible to all classes (JVM included). |
| `static`        | Allows JVM to call `main()` without creating an object of the class.     |
| `void`          | Indicates that the method does not return any value.                    |
| `main()`        | Special method name recognized by JVM as the entry point of the program. |
| `String[] args` | Array of strings — stores command-line arguments passed to the program.  |

---

### Example
    ```java
    public class Demo {
        public static void main(String[] args) {
            System.out.println("Hello, Java!");
        }
    }

# Java OOPs, Class, Object & Constructor Notes

## 1. OOPs Concepts
Object-Oriented Programming (OOP) simplifies development and maintenance using:

- **Object**
- **Class**
- **Data Abstraction**
- **Encapsulation**
- **Inheritance**
- **Polymorphism**
- **Dynamic Binding**

---

## 2. Class & Object

### Class
- User-defined datatype.
- Blueprint for creating objects.
- Contains data members and methods.

### Object
- Instance of a class.
- Created using `new` keyword.
  
    ```java
    ClassName obj = new ClassName();
    ```

---

## 3. Data Abstraction
- Hides internal implementation, shows only essential features.
- Achieved using abstract classes and interfaces.

## 4. Encapsulation
- Binds data and methods together.
- Restricts access using access modifiers.
- Enables **data hiding**.

---

## 5. Inheritance
- One class acquires properties of another.
    ```java
    class Child extends Parent { }
    ```

## 6. Polymorphism
- One interface, multiple implementations.
- Types:
  - Compile-time (method overloading)
  - Runtime (method overriding)

## 7. Dynamic Binding
- Method call resolved at runtime.
- Enables runtime polymorphism.

---

## 8. Constructor

### Definition
- Special method used to initialize object state.
- Automatically called when an object is created.
- Same name as the class.
- No return type (not even `void`).

### Types
- **Default Constructor**
  - No parameters.
  - Created automatically if none defined.
- **Parameterized Constructor**
  - Accepts arguments to initialize object.

### Syntax

      ```java
      class Employee {
          int empNo;
          String empName;
      
          Employee() {
              empNo = 0;
              empName = null;
          }
      
          Employee(int id, String name) {
              empNo = id;
              empName = name;
          }
      }
    



## 9. Copy Constructor
- Creates a new object by copying another.
  
```java
class Admin {
    int empRoll;
    String empName;

    Admin(Admin a) {
        empRoll = a.empRoll;
        empName = a.empName;
    }
}
```

---

## 10. Constructor vs Method

| Feature         | Constructor                      | Method                          |
|----------------|-----------------------------------|----------------------------------|
| Name            | Same as class                    | Any valid identifier             |
| Invocation      | Implicit (object creation)       | Explicit (method call)           |
| Return type     | None                             | Must have a return type          |
| Purpose         | Initialize object state          | Define object behavior           |

---

## 11. instanceof Operator

Used to check object type before casting:
    ```java
    if (person instanceof Employee) {
        Employee emp = (Employee) person;
    }
    ```



## Memory Allocation During Object Creation

### Example
  ```java
  class Employee {
      int id;
      String name;
  
      Employee(int i, String n) {
          id = i;
          name = n;
      }
  }

Employee emp = new Employee(101, "Sherin");
```

### Memory Breakdown

| Memory Area     | What Happens                                 |
|-----------------|----------------------------------------------|
| **Heap**        | Object `emp` is created and fields are stored |
| **Stack**       | Reference `emp` is stored                     |
| **Method Area** | Constructor code is loaded once per class     |

- Constructor initializes fields in **heap memory**.
- Reference variable lives in **stack memory**.
- Class-level code (constructor definition) resides in **method area**.

---

## 3. Constructor Types

### Default Constructor
```java
Employee() {
    id = 0;
    name = null;
}
```

### Parameterized Constructor
```java
Employee(int i, String n) {
    id = i;
    name = n;
}
```

### Copy Constructor
```java
Employee(Employee e) {
    id = e.id;
    name = e.name;
}
```

---

## 4. Key Points

- Constructor is invoked during object creation.
- Fields initialized by constructor are stored in heap.
- Constructor logic is shared across all instances (loaded once).
- If no constructor is defined, Java provides a default one.


# Java Variable Types Notes

## 1. Types of Variables

Java defines three main types of variables:

### 1. Local Variable
  - Declared inside a method, constructor, or block.
  - No access modifiers allowed.
  - Scope is limited to the block where it's declared.
  
    ```java
    void display() {
        int y = 5; // local variable
        System.out.println("y = " + y);
    }

### 2. Instance Variable
  - Declared inside a class but outside any method or block.
  - Associated with object instances.
  - Can use access modifiers.
  - Accessed via object reference.

    ```java
    class Student {
        int rollNo;           // instance variable
        private String name;  // instance variable with access modifier
    }


---

### 3. Static Variable
  - Declared inside a class using the `static` keyword.
  - Shared across all instances.
  - Associated with the class, not objects.
  - Accessed using `ClassName.variableName`.
  
    ```java
    class Student {
        static String school = "Rajagiri"; // static variable
    }
    ```

---

## 2. Example Class
    
    ```java
    class Student {
        int rollNo;                         // instance variable
        private String name;                // instance variable
        static String school = "Rajagiri";   // static variable
    
        Student() {
            rollNo = 123;
            name = "Bini";
        }
    
        public void display() {
            int y = 5;                       // local variable
            System.out.println("Local y = " + y);
            System.out.println("RollNo = " + rollNo);
            System.out.println("Name = " + name);
            System.out.println("School = " + school);
        }
    }
```

---

## 3. Accessing Variables

    ```java
    public class VariablesInClass {
        public static void main(String[] args) {
            Student.school = "Naipunya"; // static variable via class name
            System.out.println("School = " + Student.school);
    
            Student obj = new Student(); // object creation
            System.out.println("RollNo = " + obj.rollNo); // instance variable
            System.out.println("Name = " + obj.name);     // instance variable
            obj.display(); // method call
        }
    }
```

Memory division in a java program execution
 In a java program execution memory is divided into three parts:
 ➢ Stack: Stack is used to local variables of the methods.
 ➢ Heap: Heap is used to store objects.
 ➢ Class Area: Class area is used to store static data members


# Java Inheritance Notes

## What is Inheritance?
- Mechanism where one class acquires properties and behaviors of another.
- Promotes **code reusability** and supports **IS-A** relationship.
- Implemented using the `extends` keyword.

---

## Types of Inheritance in Java

### 1. Single Inheritance
- One subclass inherits from one superclass.
      ```java
      class A { }
      class B extends A { }
      ```

### 2. Multilevel Inheritance
- A class inherits from a derived class.
      ```java
      class A { }
      class B extends A { }
      class C extends B { }
      ```

### 3. Hierarchical Inheritance
- Multiple classes inherit from a single superclass.
      ```java
      class A { }
      class B extends A { }
      class C extends A { }
      ```

### 4. Multiple Inheritance (Not Supported in Java)
- One class inherits from more than one class.
- Java avoids this to prevent ambiguity (Diamond Problem).
      ```java
      // Not allowed in Java
      class C extends A, B { }
      ```

### 5. Hybrid Inheritance
  - Combination of multiple and multilevel inheritance.
  - Achievable using interfaces.
  
        ```java
        interface A { void methodA(); }
        interface B { void methodB(); }
        
        class C implements A, B {
            public void methodA() { }
            public void methodB() { }
        }
        ```

---

## Why Java Doesn’t Support Multiple Class Inheritance?

### Diamond Problem
- Ambiguity arises when two parent classes have the same method.
- JVM can't decide which method to inherit.

---

## Real-Life Analogy
- A child inherits traits from parents.
- In software, a subclass inherits fields and methods from its superclass.

---

## Benefits of Inheritance
- Code reusability
- Runtime polymorphism
- Logical hierarchy

---


# Java Abstract Class & Method – Short Notes

## Abstract Class
- Declared using `abstract` keyword.
- Cannot be instantiated.
- May contain abstract and non-abstract methods.
- Used to define a common base with partial implementation.

### Syntax
    ```java
    abstract class Shape {
        abstract void draw(); // abstract method
        void display() {
            System.out.println("Displaying shape");
        }
    }
    ```

---

## Abstract Method
- Declared without a body.
- Must be implemented by subclass.
- Only allowed inside abstract classes or interfaces.

    ### Syntax
    ```java
    abstract void draw();
    ```

---

## Key Points

| Feature              | Abstract Class             | Abstract Method               |
|----------------------|----------------------------|-------------------------------|
| Purpose              | Base for subclasses        | Enforce method implementation |
| Body                 | May have method bodies     | No body                       |
| Access Modifier      | Can use modifiers          | Must be `public` or `protected` |
| Instantiation        | Not allowed                | N/A                           |

---

        ## Example
        ```java
        abstract class Animal {
            abstract void sound();
        }
        
        class Dog extends Animal {
            void sound() {
                System.out.println("Bark");
            }
        }
    ```


# Java Access Modifiers – Simple Interview Notes

## What Are Access Modifiers?
- Control the visibility/scope of classes, methods, and variables.
- Help enforce encapsulation and security.

---

## Types of Access Modifiers

| Modifier   | Scope Within Class | Same Package | Subclass (Other Package) | Other Packages |
|------------|--------------------|--------------|---------------------------|----------------|
| `private`  | ✅                 | ❌           | ❌                        | ❌             |
| _default_  | ✅                 | ✅           | ❌                        | ❌             |
| `protected`| ✅                 | ✅           | ✅                        | ❌             |
| `public`   | ✅                 | ✅           | ✅                        | ✅             |

---

## Modifier Summary

### `private`
- Accessible only within the same class.
- Used for sensitive data.

### _default_ (no modifier)
- Accessible within the same package.
- Also called package-private.

### `protected`
- Accessible within the same package and subclasses in other packages.

### `public`
- Accessible from anywhere.

---

## Example
    ```java
    public class Demo {
        private int a;         // private
        int b;                 // default
        protected int c;       // protected
        public int d;          // public
    }

---


# Java API & Packages – Interview Notes

## 1. What is a Package?
- A namespace that organizes related classes and interfaces.
- Helps avoid name conflicts and improves code maintainability.
- Acts like a folder in a file system.

### Types of Packages
- **Built-in Packages:** Provided by Java API (e.g., `java.util`, `java.io`)
- **User-defined Packages:** Created by developers to organize custom classes

### Syntax
    ```java
    package mypackage;
    class MyClass { }
    ```

### Importing Packages
    ```java
    import java.util.Scanner;       // single class
    import java.util.*;             // entire package
    ```

---

## 2. What is Java API?
- **API (Application Programming Interface):** A collection of prewritten classes and interfaces.
- Part of the Java Development Kit (JDK).
- Provides tools for input/output, networking, data structures, GUI, etc.

### Common Java API Packages

| Package       | Purpose                              |
|---------------|---------------------------------------|
| `java.lang`   | Core language classes (String, Math)  |
| `java.util`   | Data structures, collections, date    |
| `java.io`     | Input/output streams and files        |
| `java.net`    | Networking (sockets, URLs)            |
| `java.awt`    | GUI components                        |
| `javax.swing` | Advanced GUI (buttons, frames)        |

---

## 3. Benefits of Using Packages & API
- Code reusability
- Easier maintenance
- Logical grouping
- Controlled access
- Faster development using built-in tools

---

## 4. Example
```java
import java.util.Scanner;

public class Example {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter name:");
        String name = sc.nextLine();
        System.out.println("Hello, " + name);
    }
}
```

