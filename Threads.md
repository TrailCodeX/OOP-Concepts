
# Java Threads – Short Interview Notes

## What is a Thread?
- A lightweight subprocess.
- Smallest unit of execution in Java.
- Enables **multitasking** and **parallelism**.

---

## Ways to Create a Thread

  ### 1. Extending `Thread` Class
    ```java
    class MyThread extends Thread {
        public void run() {
            System.out.println("Running thread");
        }
    }
    ```
  
  ### 2. Implementing `Runnable` Interface
    ```java
    class MyRunnable implements Runnable {
        public void run() {
            System.out.println("Running thread");
        }
    }
    ```
  
  ---

## Thread Lifecycle

| State           | Description                                  |
|-----------------|----------------------------------------------|
| New             | Thread created but not started               |
| Runnable        | Ready to run, waiting for CPU                |
| Running         | Actively executing                           |
| Blocked/Waiting | Paused due to I/O or synchronization         |
| Timed Waiting   | Paused for a specific time (`sleep`, `join`) |
| Terminated      | Finished execution or crashed                |

---

## Key Methods

| Method         | Purpose                                      |
|----------------|----------------------------------------------|
| `start()`      | Starts thread and calls `run()`              |
| `run()`        | Contains thread logic                        |
| `sleep(ms)`    | Pauses thread for given milliseconds         |
| `join()`       | Waits for another thread to finish           |
| `interrupt()`  | Interrupts a sleeping or waiting thread      |
| `isAlive()`    | Checks if thread is still running            |

---

## Thread Priorities
  
  - Range: `1` (MIN) to `10` (MAX)
  - Default: `5` (NORM)
  ```java
  thread.setPriority(10);
  ```
  
  ---

## Daemon Threads
  - Background threads (e.g., garbage collector)
  ```java
  thread.setDaemon(true);
  ```

---

## Multithreading Benefits
  - Better CPU utilization
  - Faster execution
  - Responsive applications
  
  ---
Here’s a concise, GitHub-ready Markdown summary based on your **Multitasking and Multithreading** page — perfect for interview prep:

---


# Multitasking & Multithreading 

## 1. What is Multitasking?
- Executing multiple tasks simultaneously.
- Improves CPU utilization.

### Types of Multitasking
| Type                     | Description                                 |
|--------------------------|---------------------------------------------|
| **Process-based**        | Multiple processes run independently        |
| **Thread-based**         | Multiple threads run within a single process|

---

## 2. Process-based Multitasking
- Each process has its own memory space.
- Heavyweight and slower context switching.
- High communication cost.

---

## 3. Thread-based Multitasking
- Threads share memory space.
- Lightweight and faster context switching.
- Low communication cost.

---

## 4. Java Multithreading
- Running multiple threads simultaneously.
- Threads are lightweight sub-processes.
- Common in games, animations, etc.

### Benefits
- Saves memory
- Faster context switching
- Non-blocking user experience

---

## 5. Synchronization
- Controls access to shared resources.
- Prevents thread interference.

### Types
- **Process Synchronization**
- **Thread Synchronization**

#### Thread Synchronization Techniques
- Synchronized Method
- Synchronized Block
- Static Synchronization

---

## 6. Mutual Exclusion
- Ensures only one thread accesses shared data at a time.

### Example
  ```java
  synchronized void printTable(int n) {
      for(int i=1; i<=5; i++) {
          System.out.println(n * i);
          Thread.sleep(400);
      }
  }
```

---

## 7. Concept of Lock
- Every object has an internal lock (monitor).
- A thread must acquire the lock before accessing shared data.

---

## 8. Static Synchronization
- Applies lock at the class level.
- Prevents interference across multiple object instances.

### Example
  ```java
  synchronized static void printTable(int n) {
      for(int i=1; i<=10; i++) {
          System.out.println(n * i);
          Thread.sleep(400);
      }
  }
```


## 9. Inter-thread Communication
- Threads cooperate using `wait()`, `notify()`, `notifyAll()`.

---

## How to Create a Thread Pool in Java
   The java.util.concurrent package provides several classes that can be used for this purpose, 
  including the Executors class and the ThreadPoolExecutor class.
   The java.util.concurrent package defines three executor interfaces:
       1. Executor, a simple interface that supports launching new tasks.
       2. ExecutorService, a subinterface of Executor, which adds features that help manage the life 
      cycle, both of the individual tasks and of the executor itself.
       3. ScheduledExecutorService, a subinterface of ExecutorService, supports future and/or 
      periodic execution of tasks
       

---
