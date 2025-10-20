
# Java `final` Keyword – Interview Notes

## What is `final`?
- A modifier used to restrict usage.
- Can be applied to **variables**, **methods**, and **classes**.
- Promotes immutability, security, and clarity.

---

## 1. Final Variables

### Instance Variable
- Must be initialized once (at declaration or in constructor).
- Cannot be reassigned.

```java
final int x = 10;
x = 20; // ❌ Compile-time error
```

### Static Final Variable
- Used for constants.
- Initialized in a static block.

```java
static final int MAX = 100;
```

### Local Final Variable
- Declared inside methods.
- Cannot be reassigned.

```java
void show() {
    final int temp = 5;
    temp = 10; // ❌ Error
}
```

### Blank Final Variable
- Declared but not initialized.
- Must be initialized in constructor or instance block.

```java
final int id;
Student(int i) {
    id = i;
}
```

---

## 2. Final Method Parameters
- Prevents reassignment inside method body.

```java
void show(final int num) {
    num = num + 1; // ❌ Error
}
```

---

## 3. Final Methods
- Can be inherited but **cannot be overridden**.

```java
class A {
    final void display() { }
}

class B extends A {
    void display() { } // ❌ Error
}
```

---

## 4. Final Classes
- Cannot be extended.

```java
final class A { }

class B extends A { } // ❌ Error
```

---

## 5. Final Object & Array References
- Reference cannot change.
- Contents can change (if mutable).

```java
final int[] nums = {1, 2, 3};
nums[0] = 99;       // ✅ Allowed
nums = new int[5];  // ❌ Error
```

---

## 6. Final vs Immutable
- `final` prevents reassignment.
- Immutability means internal state cannot change (e.g., `String` class).

---

## 7. Key Benefits
- Improves performance (JVM optimizations).
- Enables safe multithreading.
- Supports design clarity and intent.

---
