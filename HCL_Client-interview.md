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