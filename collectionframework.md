# Java Collection Framework 

## 1. What Is the Collection Framework?
- The Java Collection Framework is a set of interfaces, classes, and algorithms for storing and manipulating groups of objects.
- Part of `java.util` package.
- Includes interfaces, classes, and utility methods.
  
- Interfaces: List, Set, Queue, Map, etc.
- Implementations: ArrayList, HashSet, LinkedList, HashMap, etc.
- Algorithms: Sorting, searching, shuffling, etc.

  
Collection: Interface that represents a group of objects (root of List, Set, Queue).

Collections: Utility class with static methods like sort(), reverse(), shuffle().


---

## 2. Core Interfaces & Their Implementations

| Interface | Description                     | Common Classes                  |
|-----------|----------------------------------|----------------------------------|
| `List`    | Ordered, allows duplicates       | `ArrayList`, `LinkedList`, `Vector` |
| `Set`     | Unordered, no duplicates         | `HashSet`, `LinkedHashSet`, `TreeSet` |
| `Queue`   | FIFO structure                   | `PriorityQueue`, `ArrayDeque`   |
| `Deque`   | Double-ended queue               | `ArrayDeque`, `LinkedList`      |
| `Map`     | Key-value pairs (not a Collection) | `HashMap`, `TreeMap`, `LinkedHashMap` |

---

## 3. Key Methods by Type

### List (e.g., `ArrayList`)
Ordered collection that allows duplicates.
Elements can be accessed by index.
      ```java
      list.add("A");
      list.get(0);
      list.remove("A");
      list.size();
      ```

### Set (e.g., `HashSet`)

Unordered collection that does not allow duplicates.
No index-based access.

    ```java
    set.add("A");
    set.contains("A");
    set.remove("A");
    ```

### Queue (e.g., `PriorityQueue`)
Follows FIFO (First-In-First-Out).
Used for scheduling and buffering.
    ```java
    queue.offer("A");
    queue.poll();
    queue.peek();
    ```

### Map (e.g., `HashMap`)

Key-Value Pairs
Not part of Collection interface.
Stores data as key-value pairs.
Keys must be unique.
    ```java
    map.put("key", "value");
    map.get("key");
    map.remove("key");
    map.containsKey("key");
    ```

---

## 4. Differences Between List, Set, and Map

| Feature       | List            | Set             | Map                     |
|---------------|------------------|------------------|--------------------------|
| Order         | Maintains order  | No guaranteed order | Sorted (TreeMap) or unordered |
| Duplicates    | Allowed          | Not allowed      | Keys: unique, Values: allowed |
| Access        | By index         | By element       | By key                   |

---

## 5. Utility Class: `Collections`

    - Static methods for sorting, reversing, shuffling, etc.
    ```java
    Collections.sort(list);
    Collections.reverse(list);
    Collections.shuffle(list);
    ```

---

## 6. Comparator vs Comparable

| Feature       | Comparable                  | Comparator                  |
|---------------|-----------------------------|-----------------------------|
| Location      | Inside class                | Outside class               |
| Method        | `compareTo()`               | `compare()`                 |
| Sorting Type  | Natural                     | Custom                      |

### Example – Comparable
```java
class Student implements Comparable<Student> {
    public int compareTo(Student s) {
        return this.id - s.id;
    }
}
```

### Example – Comparator
```java
class NameComparator implements Comparator<Student> {
    public int compare(Student s1, Student s2) {
        return s1.name.compareTo(s2.name);
    }
}
```

