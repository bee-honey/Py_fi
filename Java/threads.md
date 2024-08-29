In Java, there are several ways to create and manage threads. Below are the most common methods:

### 1. **Extending the `Thread` Class**
   - You can create a thread by extending the `Thread` class and overriding its `run()` method. This approach is straightforward but limits you to single inheritance (since Java doesn’t support multiple inheritance).

```java
class MyThread extends Thread {
    @Override
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start(); // Starts the thread
    }
}
```

### 2. **Implementing the `Runnable` Interface**
   - Implementing the `Runnable` interface is a more flexible way to create threads, as it allows your class to implement other interfaces or extend another class. You need to pass an instance of the `Runnable` implementation to a `Thread` object.

```java
class MyRunnable implements Runnable {
    @Override
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        MyRunnable myRunnable = new MyRunnable();
        Thread thread = new Thread(myRunnable);
        thread.start(); // Starts the thread
    }
}
```

### 3. **Using Anonymous Classes**
   - You can create a thread using an anonymous class that implements `Runnable`.

```java
public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new Runnable() {
            @Override
            public void run() {
                System.out.println("Thread is running...");
            }
        });
        thread.start(); // Starts the thread
    }
}
```

### 4. **Using Lambda Expressions (Java 8+)**
   - In Java 8 and later, you can use lambda expressions to create threads in a more concise manner. This is particularly useful for short tasks.

```java
public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(() -> System.out.println("Thread is running..."));
        thread.start(); // Starts the thread
    }
}
```

### 5. **Using the `ExecutorService` Framework**
   - The `ExecutorService` framework, part of the `java.util.concurrent` package, provides a more powerful way to manage threads, especially when dealing with multiple threads or a thread pool.

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class Main {
    public static void main(String[] args) {
        ExecutorService executorService = Executors.newFixedThreadPool(2);

        executorService.execute(() -> System.out.println("Thread 1 is running..."));
        executorService.execute(() -> System.out.println("Thread 2 is running..."));

        executorService.shutdown(); // Gracefully shut down the executor service
    }
}
```

### 6. **Using `Callable` and `Future` (with `ExecutorService`)**
   - `Callable` is similar to `Runnable` but can return a result and throw a checked exception. The `Future` object can be used to retrieve the result or check if the task is completed.

```java
import java.util.concurrent.Callable;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

public class Main {
    public static void main(String[] args) throws Exception {
        ExecutorService executorService = Executors.newSingleThreadExecutor();

        Callable<String> callable = () -> {
            return "Task's result";
        };

        Future<String> future = executorService.submit(callable);
        System.out.println("Result: " + future.get()); // Outputs: Task's result

        executorService.shutdown();
    }
}
```

### 7. **Creating a Daemon Thread**
   - A daemon thread is a background thread that does not prevent the JVM from exiting when the program finishes. To create a daemon thread, you can set the thread to daemon mode before starting it.

```java
class MyRunnable implements Runnable {
    @Override
    public void run() {
        while (true) {
            System.out.println("Daemon thread running...");
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.setDaemon(true); // Set the thread as a daemon thread
        thread.start(); // Starts the daemon thread

        System.out.println("Main thread finished");
        // Daemon thread will stop when the main thread finishes
    }
}
```

### Summary:
- **Extending `Thread`**: Simple but less flexible.
- **Implementing `Runnable`**: More flexible, better for reusability.
- **Anonymous Classes and Lambdas**: Concise and useful for short tasks.
- **`ExecutorService` Framework**: Best for managing multiple threads, thread pools, and more complex concurrency scenarios.
- **`Callable` and `Future`**: Useful when you need a return value from a task.
- **Daemon Threads**: Background threads that automatically stop when no other non-daemon threads are running.

Each of these methods has its use cases depending on the complexity of your task, the need for flexibility, and the requirement for managing multiple threads.