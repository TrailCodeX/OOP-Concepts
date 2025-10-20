
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

Happy coding!
```

Let me know if you'd like this turned into flashcards or bundled with your other notes!
