Key Java 17 Features

1. Sealed Classes (Final Feature)

Restrict which classes can extend or implement a class/interface. This helps model closed hierarchies safely.

public sealed class Shape
    permits Circle, Rectangle, Triangle {
}

final class Circle extends Shape {}
final class Rectangle extends Shape {}
final class Triangle extends Shape {}

Benefits:

Better control over inheritance
Improved maintainability
Works well with pattern matching




2. Pattern Matching for switch (Preview)

Allows type patterns in switch statements and expressions, reducing instanceof checks and casts.

static String format(Object obj) {
    return switch (obj) {
        case String s -> "String: " + s;
        case Integer i -> "Integer: " + i;
        case null -> "Null";
        default -> "Unknown";
    };
}

Ex :

public String sendNotification(Object notification) {

    return switch (notification) {

        case EmailNotification email ->
                "Email sent to " + email.getEmail();

        case SmsNotification sms ->
                "SMS sent to " + sms.getMobile();

        case PushNotification push ->
                "Push sent to " + push.getDeviceId();

        default ->
                "Unsupported notification";
    };
}

```````````````````````````````````````````````````````````````

3. Records (Java 16)
public record Person(String name, int age) {}

Automatically generates:

Constructor
Getters
equals()
hashCode()
toString()


Spring Boot Request DTO
public record CreateUserRequest(
        String firstName,
        String lastName,
        String email) {
}

Controller:

@PostMapping("/users")
public ResponseEntity<String> createUser(
        @RequestBody CreateUserRequest request) {

    return ResponseEntity.ok(
            "User Created: " + request.email());
}




````````````````````````````````````````````````````````````

4. Pattern Matching for instanceof (Java 16)
if (obj instanceof String s) {
    System.out.println(s.length());
}

No explicit cast required.

Exa :

public void handleException(Exception ex) {

    if (ex instanceof ResourceNotFoundException rnfe) {
        log.error("Resource Not Found: {}", rnfe.getMessage());

    } else if (ex instanceof ValidationException ve) {
        log.error("Validation Error: {}", ve.getMessage());
    }
}

``````````````````````````````````````````````````````

5. Enhanced Random Number Generators

Introduces new random number generator interfaces and algorithms for better flexibility and performance.

RandomGenerator generator = RandomGenerator.getDefault();
int value = generator.nextInt(100);


Multithreading in Java


Creating Threads in Java
1. By Extending Thread Class
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start(); // Starts a new thread
    }
}


2. By Implementing Runnable Interface (Recommended)
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Runnable thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}

Key Concepts in Java Multithreading
Thread: Smallest unit of execution.
Concurrency: Multiple tasks making progress simultaneously.
Synchronization: Prevents race conditions.
Deadlock: Two or more threads waiting indefinitely for each other.
Thread Pool: Reusable collection of worker threads.
ExecutorService: Preferred API for managing threads.
Best Practices

✔ Prefer Runnable, Callable, and ExecutorService over extending Thread.
✔ Minimize shared mutable data.
✔ Use synchronization carefully.
✔ Use concurrent collections (ConcurrentHashMap, CopyOnWriteArrayList) when needed.
✔ Always shut down executors with shutdown().


import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class Main {

    public static void main(String[] args) {

        ExecutorService executor =
                Executors.newFixedThreadPool(3);

        for(int i=1; i<=10; i++) {

            int taskId = i;

            executor.submit(() -> {
                System.out.println(
                        "Task " + taskId +
                        " executed by " +
                        Thread.currentThread().getName());
            });
        }

        executor.shutdown();
    }
}

11. What is Volatile?

Ensures visibility across threads.

volatile boolean flag = true;

Changes made by one thread become visible to others immediately.

12. Difference between volatile and synchronized?
volatile	synchronized
Visibility	Visibility + Mutual Exclusion
No locking	Uses lock
Faster	Slower