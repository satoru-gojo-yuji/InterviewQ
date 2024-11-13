Ahembda bad Why string is immutable String s = "Hi" s="hellow"

String
@reposirey why we use what is abstaract class and interfce discribe your porject microservices advanatge of functinaol interface abstact class why we use if we have interface
what are the languagest did you use in your project

RBI  
How to add the new entity in jpa and Java 
 String me vowels kese print karaye 

 public class VowelPrinter {
    public static void main(String[] args) {
        String input = "Hello World"; // यहाँ अपनी स्ट्रिंग डालें
        printVowels(input);
    }

    public static void printVowels(String str) {
        for (int i = 0; i < str.length(); i++) {
            char ch = Character.toLowerCase(str.charAt(i)); // छोटे अक्षरों में कन्वर्ट करना ताकि कैपिटल लेटर्स भी कवर हो जाएं
            if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
                System.out.print(ch + " ");
            }
        }
    }
}

  JAP annotation  
  Angular host  
  How to add new functionality in your current project  
  Project related questions

TCS 

Rest contreoller and controller.

ANS - 
@Controller
Purpose: It is used to define a standard web controller that can handle HTTP requests and return views.
Return Type: Methods annotated with @Controller typically return ModelAndView or a view name as a String, which is resolved to an actual view (like a JSP or Thymeleaf template).
Usage: Commonly used in traditional web applications where server-side rendered views are returned to the client.
Example:
java
Copy code
@Controller
public class MyController {
    @GetMapping("/hello")
    public String sayHello(Model model) {
        model.addAttribute("message", "Hello, World!");
        return "hello"; // This is the name of the view (e.g., hello.jsp or hello.html)
    }
}
@RestController
Purpose: It is a specialized version of @Controller used to create RESTful web services. It simplifies the creation of RESTful APIs by eliminating the need to annotate every @RequestMapping method with @ResponseBody.
Return Type: Methods in a @RestController return data directly (usually JSON or XML) instead of a view. The returned data is automatically serialized into the appropriate format (typically JSON).
Usage: Commonly used in RESTful web services where the focus is on returning data rather than views.
Example:
java
Copy code
@RestController
public class MyRestController {
    @GetMapping("/hello")
    public String sayHello() {
        return "Hello, World!"; // This will be returned as a plain text response (or JSON/XML if it's an object)
    }
}

Annotation:

@Controller: General-purpose controller for handling web requests and returning views.
@RestController: Specialized controller for RESTful services that combines @Controller and @ResponseBody.
Response Handling:

@Controller: Methods return views, with model data passed along for rendering on the server side.
@RestController: Methods return objects that are serialized directly into HTTP response bodies (usually JSON).
View Resolution:

@Controller: Returns a view name, and the view resolver resolves it to a concrete view.
@RestController: Directly returns data, bypassing view resolution

JPA and why we JPA hibernet.

Encapsulation real life example related fro your project.



Interface logical questuon.

inheritance logical exceuor.

Springbootannotation.

@SpringBootApplication

This is the main annotation that marks a configuration class that declares one or more @Bean methods and also triggers auto-configuration and component scanning. It is a combination of three annotations:
@Configuration: Indicates that the class can be used by the Spring IoC container as a source of bean definitions.
@EnableAutoConfiguration: Enables Spring Boot's auto-configuration feature.
@ComponentScan: Enables component scanning, allowing Spring to find and register beans automatically.

MySQL logical qeustuon.

HTML Css JS Anguler to craret the login pager how to versify the user enter data through Js.

Vector and arry list logicla questuon.

1. Synchronization
Vector: It is synchronized, meaning it is thread-safe and can be used in a multi-threaded environment without external synchronization. Each operation on a Vector is thread-safe, which can lead to performance overhead due to the locking mechanism.
ArrayList: It is not synchronized, making it not thread-safe. If multiple threads access an ArrayList concurrently, and at least one of the threads modifies it, it must be externally synchronized.

2. Performance
Vector: Because of its synchronized nature, it generally has lower performance compared to ArrayList when accessed from multiple threads.
ArrayList: It is faster for single-threaded operations because it does not have the overhead of synchronization.
3. Growth Rate
Vector: When a Vector runs out of space, it doubles its size. This can lead to less frequent resizing but may waste memory.
ArrayList: When an ArrayList runs out of space, it increases its size by 50% (1.5 times the old capacity). This often results in better memory utilization.
4. Legacy vs. Modern Collection
Vector: It is part of the original Java 1.0 and is considered a legacy class. It can be replaced by more modern collection classes like ArrayList.
ArrayList: Introduced in Java 2 (Java 1.2), it is part of the Java Collections Framework and is generally preferred for new implementations.
5. Iterators
Vector: It provides a legacy enumeration method and also has a method to return an Iterator.
ArrayList: It provides a more modern iterator which is fail-fast, meaning it throws a ConcurrentModificationException if the list is structurally modified while iterating.

treemap and hashmap diff.

1. Ordering
TreeMap: It maintains a sorted order of its keys. By default, it sorts the keys according to their natural ordering (e.g., numerical order for numbers, alphabetical order for strings). You can also provide a custom comparator to control the sorting order.
HashMap: It does not maintain any order of its keys. The order of the keys is based on the hash code of the keys and can change when new key-value pairs are added.

2. Performance
TreeMap: The operations such as insertion, deletion, and retrieval take O(log n) time due to the underlying Red-Black tree structure used to maintain order.
HashMap: These operations generally take O(1) time on average due to its hash table implementation. However, in cases of hash collisions, performance can degrade to O(n) in the worst case.

3. Null Keys and Values
TreeMap: It does not allow null keys. You can have null values, but not null keys. Attempting to add a null key will throw a NullPointerException.
HashMap: It allows one null key and multiple null values. This means you can store a key with a null value without issues.

4. Thread Safety
Both TreeMap and HashMap are not synchronized, meaning they are not thread-safe. If you need to use them in a multi-threaded environment, you should either wrap them using Collections.synchronizedMap() or use ConcurrentHashMap.

5. Use Cases
TreeMap: Use when you need a sorted map (e.g., if you need to retrieve keys in a sorted order or perform range queries).
HashMap: Use when you need fast access to elements and do not require the keys to be sorted.

finaly why we use ralred project / data base close

what is indexing in SQL

To create an immutable class in Java, follow these principles:

Declare the class as final: This prevents other classes from subclassing it.

Make all fields private and final: Fields must be private to prevent direct access, and final to ensure they can't be changed after construction.
Provide no setters: Don't provide any methods that can modify the fields.

Initialize fields only via constructor: The only way to set the values of the fields should be through the constructor.

Return deep copies of mutable fields: If your class contains mutable objects (like arrays, collections, or custom objects), return deep copies in getter methods to prevent the caller from modifying the original object.

public final class Employee {
    
    // Fields are private and final
    private final String name;
    private final int age;
    private final Address address;  // Mutable object

    // Constructor initializes all fields
    public Employee(String name, int age, Address address) {
        this.name = name;
        this.age = age;
        // Create a deep copy of the Address to ensure immutability
        this.address = new Address(address.getCity(), address.getZipCode());
    }

    // Only getters are provided, no setters
    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    // Return a deep copy of the mutable field (Address) to ensure immutability
    public Address getAddress() {
        return new Address(address.getCity(), address.getZipCode());
    }
}



KPMG 
Find the very first non-repeating character in a string array

Input: String [] strArr={"apple","aappllee","","aabbcde","kettle"};
Output: Character [] chArr={'a','0','\u0000','c','k'};




Given an array of random numbers, push all the zeroes of a given array to the end of the array. For example, if the given array is {1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0}, it should be changed to {1, 9, 8, 4, 2, 7, 6, 0, 0, 0, 0}. The order of all other elements should be same.
Expected time complexity is O(n) and extra space is O(1).

 public static void main(String[] args) {
        int[] arr={1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0};
  int n =arr.length;
        System.out.println(n);
        int c =0;
        for(int i=0 ; i<n ; i++) {
            if (arr[i] != 0)
                arr[c++] = arr[i];
        }
        System.out.println(c);
            while (c < n)
            {
                arr[c++] = 0;
        }
        for(int i=0 ; i<n ; i++)
            System.out.println(arr[i]);
    }
}


Second method : 


public class LastZero2 {

    public static void main(String[] args) {

        int[] arr = {1, 4, 0, 3, 0, 4, 6, 0, 5, 6, 0};

        int last = 0;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] != 0) {
                int temp = arr[i];
                arr[i] = arr[last];
                arr[last] = temp;
                last++;
            }
        }
        for(int a : arr)
        {
            System.out.println(a);
        }
    }
}

12. diff. abstract class and interface real life 


1) Abstract class can have abstract and non-abstract methods.

Interface can have only abstract methods. Since Java 8, it can have default and static methods also.

2) Abstract class doesn't support multiple inheritance.

Interface supports multiple inheritance.

3) Abstract class can have final, non-final, static and non-static variables.

Interface has only static and final variables.

4) Abstract class can provide the implementation of interface.

Interface can't provide the implementation of abstract class.

5) The abstract keyword is used to declare abstract class.

The interface keyword is used to declare interface.

6) An abstract class can extend another Java class and implement multiple Java interfaces.

An interface can extend another Java interface only.

7) An abstract class can be extended using keyword "extends".

An interface can be implemented using keyword "implements".

8) A Java abstract class can have class members like private, protected, etc.

Members of a Java interface are public by default.

9)Example:

public abstract class Shape{
public abstract void draw();
}
Example:
public interface Drawable{
void draw();
}


what are the new fatuer of java 8 
diff map and flatmap 

map()
Purpose: The map() method is used to apply a function to each element of a stream or collection and returns a new stream or collection where each element is transformed according to the function. 
Return Type: It returns a stream (or collection) where each element is a direct mapping (1-to-1 transformation) from the input to the output.
Does Not Flatten: It doesn't flatten the structure. If the function you apply returns a collection or stream, map() will create a stream of collections or streams (nested structure).

map() operation produces a single value for each value of input Stream and hence it is also called One-To-One mapping.


flatMap()
Purpose: The flatMap() method is used to transform and flatten a stream of elements. It’s particularly useful when each element itself is a collection or stream, and you want to combine these sub-streams or collections into a single continuous stream (flattening the structure).
Return Type: It returns a flat stream by replacing each element with the contents of the mapped stream or collection.
Flattens the Structure: If the mapping function returns a collection or stream, flatMap() will "flatten" these into a single stream of elements.

map() does only mapping, but flatMap() performs mapping as well as flattening. Flattening means transforming data from Stream<Stream<T>> to Stream<T>. This is the main difference between map() and flatMap()

List<List<String>> nestedList = Arrays.asList(
    Arrays.asList("A", "B"),
    Arrays.asList("C", "D"),
    Arrays.asList("E", "F")
);

List<String> flatResult = nestedList.stream()
                                    .flatMap(list -> list.stream())  // Flattens the lists
                                    .collect(Collectors.toList());

System.out.println(flatResult);  // Output: [A, B, C, D, E, F]

Map()	flatMap()
It processes stream of values.	
It processes stream of stream of values.
It does only mapping.	
It performs mapping as well as flattening.
It’s mapper function produces single value for each input value.	
It’s mapper function produces multiple values for each input value.
It is a One-To-One mapping.	
It is a One-To-Many mapping.
Data Transformation : From Stream<T> to Stream<R>	
Data Transformation : From Stream<Stream<T> to Stream<R>
Use this method when the mapper function is producing a single value for each input value.	
Use this method when the mapper function is producing multiple values for each input value.


anonoumus arry and inter class 
and announomus class 
Date API new feture for in java 8 

Java 8 introduced a new and improved Date and Time API under the package java.time. The new API addresses many issues with the old java.util.Date and java.util.Calendar classes, providing a more readable, flexible, and immutable way to work with dates and times.

Here are the key new features of the Java 8 Date and Time API:

1. Immutable and Thread-safe Classes
Unlike java.util.Date and java.util.Calendar, which are mutable and not thread-safe, the new java.time classes are immutable and thread-safe. This improves the reliability and safety of your code in concurrent environments.
2. Main Classes in java.time Package
LocalDate: Represents a date (year, month, day) without time and time zone.
LocalTime: Represents a time (hours, minutes, seconds, nanoseconds) without a date and time zone.
LocalDateTime: Represents both date and time, but without a time zone.
ZonedDateTime: Represents date and time with a time zone.
Instant: Represents a timestamp (date and time) as an instantaneous point on the timeline (seconds and nanoseconds from the Unix epoch).
Duration: Represents the amount of time (in seconds, nanoseconds).
Period: Represents a date-based amount of time (years, months, days).

Infosys

1. Transiant Kayword

In Java, the transient keyword is used to indicate that a field should not be serialized when an object is converted to a byte stream. Serialization is the process of converting an object into a format that can be easily stored or transmitted (for example, saving to a file or sending over a network). During serialization, all non-transient fields of the object are saved, but fields marked as transient are skipped.

Why Use the transient Keyword? 
There are several reasons why you might not want certain fields to be serialized: 

Sensitive Data: You might have sensitive information (like passwords, security keys, etc.) in an object that you don’t want to store or transmit when serializing. 
Temporary Fields: Some fields might be temporary, such as caches or other calculated values that don’t need to be saved.
Non-Serializable Objects: If a field holds an object that is not serializable itself, marking it as transient avoids serialization errors.

2. Diamond problem

Talking about Multiple inheritance is when a child class is inherits the properties from more than one parents and the methods for the parents are same (Method name and parameters are exactly the same) then child gets confused about which method will be called. This problem in Java is called the Diamond problem.

// Java Program to demonstrate 
// Diamond Problem 
import java.io.*; 

// Parent Class1 
class Parent1 { 
	void fun() { System.out.println("Parent1"); } 
} 

// Parent Class2 
class Parent2 { 
	void fun() { System.out.println("Parent2"); } 
} 

// Inherting the Properties from 
// Both the classes 
class test extends Parent1, Parent2 { 
	// main function 
	public static void main(String[] args) 
	{ 
		test t = new test(); 
		t.fun(); 
	} 
}

Solution of Diamond Problem in Java
Although Diamond Problem is a serious issue but we can create a solution for it which is Interface. Interface are created by using interface keyword. It contains all methods by default as abstract we don’t need to declared as abstract ,compiler will do it implicitly. We can’t instantiate interface for this we have to use a class which will implement the interface and will write the definitions of its all functions.
// Java Programs to illustrate 
// use of Interface to solve 
// Diamond Problem 
import java.io.*; 

// Interfaces Declared 
interface Parent1 { 
	void fun(); 
} 

// Interfaces Declared 
interface Parent2 { 
	void fun(); 
} 

// Inheritance using Interfaces 
class test implements Parent1, Parent2 { 
	public void fun() 
	{ 
		System.out.println("fun function"); 
	} 
} 

// Driver Class 
class test1 { 
	// main function 
	public static void main(String[] args) 
	{ 
		test t = new test(); 
		t.fun(); 
	} 
}


3. String immutable 

In summary, String immutability in Java provides benefits in terms of security, thread safety, performance, and code simplicity. By preventing changes to string objects after they are created, Java helps ensure consistent behavior and reduces the risk of bugs and security vulnerabilities in applications.

4. Pass failed in collection
5. How to pass data from one application to another application

Choosing the Right Approach:
REST APIs: Best for synchronous communication over HTTP.
Messaging (RabbitMQ, Kafka): Ideal for asynchronous communication.
Database Sharing: Suitable for applications that interact with a shared database.
File Sharing: Good for simple, low-latency communication between applications.
RPC (gRPC): Great for high-performance, remote method invocations.

6. How to read the application.property file

In a Spring Boot application, you can read properties from the application.properties (or application.yml) file using various methods, including using the @Value annotation, @ConfigurationProperties annotation, or by directly injecting the Environment object. Here are the approaches:

You can read a single property from the application.properties file using the @Value annotation. 

The @ConfigurationProperties annotation is more useful for grouping related properties into a POJO (Plain Old Java Object). It can bind hierarchical properties to a class.

You can use the Environment object to access properties dynamically at runtime. The Environment object is part of the Spring framework and can be autowired into any Spring component.

7. How many way we can do the overload method 

8. diff. comparable and comparator 

Comparable Interface
Purpose: Used to define the natural ordering of objects.
Method to implement: compareTo(T o)
Location of comparison logic: Inside the class whose objects are being compared.
Usage: A class implements Comparable to define how its objects should be compared to each other.
Single sorting sequence: When implemented, objects of the class can be sorted in only one way (natural ordering).


public class Employee implements Comparable<Employee> {
    private int id;
    private String name;
    
    public Employee(int id, String name) {
        this.id = id;
        this.name = name;
    }
    
    @Override
    public int compareTo(Employee other) {
        return this.id - other.id; // Compare based on id
    }
}

Comparator Interface
Purpose: Used to define external/customized sorting.
Method to implement: compare(T o1, T o2)
Location of comparison logic: In a separate class or as an anonymous class or lambda expression. This keeps sorting logic outside the object being sorted.
Multiple sorting sequences: You can define multiple comparators for different sorting criteria.

class Sortbyroll implements Comparator<Student> {

    // Method
    // Sorting in ascending order of roll number
    public int compare(Student a, Student b)
    {

        return a.rollno - b.rollno;
    }
}
9. fail pass in collection 

Fail-Fast Iterators:
Definition: Fail-Fast iterators immediately throw a ConcurrentModificationException if the collection is structurally modified after the iterator is created, except through the iterator's own methods (like remove).
Behavior:
If one thread modifies the collection (e.g., adding/removing elements) while another thread is iterating over it, the iterator detects this and throws an exception.
Structural modifications are changes like inserting or deleting elements, but not updates to the existing elements.
Examples:
Iterators from collections like ArrayList, HashMap, LinkedList, and HashSet are Fail-Fast.
Internal Working:
Fail-Fast iterators use a mechanism called the modCount (modification count). Every time a structural modification is made to the collection, the modCount is updated. The iterator checks if the modCount has changed since the iterator was created, and if so, it throws a ConcurrentModificationException.


Fail-Safe Iterators:
Definition: Fail-Safe iterators do not throw an exception if the collection is modified during iteration. Instead, they work on a copy of the collection and do not reflect changes made to the original collection during iteration.
Behavior:
These iterators are generally used in concurrent environments where the collection might be modified while iterating.
Since they operate on a copy, modifications made to the original collection after the iterator is created will not affect the iterator's behavior.
Examples:
Collections from the java.util.concurrent package like ConcurrentHashMap, CopyOnWriteArrayList, and CopyOnWriteArraySet use Fail-Safe iterators.
Internal Working:
Fail-Safe iterators work by iterating over a clone (snapshot) of the collection rather than the original collection, ensuring that the iteration is not impacted by structural modifications.

| Fail-Fast Iterators      |	Fail-Safe Iterators |
Fail-Fast iterators doesn’t allow modifications of a collection while iterating over it.	
Fail-Safe iterators allow modifications of a collection while iterating over it.
These iterators throw ConcurrentModificationException if a collection is modified while iterating over it.	
These iterators don’t throw any exceptions if a collection is modified while iterating over it.
They use original collection to traverse over the elements of the collection.	
They use copy of the original collection to traverse over the elements of the collection.
These iterators don’t require extra memory.	These iterators require extra memory to clone the collection.
Ex : Iterators returned by ArrayList, Vector, HashMap.	
Ex : Iterator returned by ConcurrentHashMap.

10. how to make singloeton 
11.  Singlton desing pattern 


The Singleton design pattern is a creational design pattern that ensures a class has only one instance, and provides a global point of access to that instance. In Java, we use the Singleton design pattern for several reasons:
When to use Singleton:

Logger Classes: Singleton pattern is often used in logger classes to ensure that only one instance of the logger is created, and all log messages are written to the same log file.

Configuration Classes: Singleton pattern can be used in configuration classes to ensure that only one instance of the configuration is created, and all parts of the application access the same configuration.

Database Connection: Singleton pattern can be used to ensure that only one instance of the database connection is created, and all parts of the application access the same connection.

public class Singleton {
    private static Singleton instance;
    private Singleton() {}
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}


12. Factory desing pattern 

Factory Design Pattern in Java: Why and When to Use It

The Factory design pattern is a creational design pattern that provides a way to create objects without exposing the creation logic to the client and refer to a newly created object using a common interface. In Java, we use the Factory design pattern for several reasons:

Object Creation Complexity: Factory pattern is useful when the object creation process is complex and involves multiple steps or dependencies.

Multiple Object Types: Factory pattern is useful when there are multiple types of objects that need to be created, and the client code needs to be decoupled from the specific object type.

Dynamic Object Creation: Factory pattern is useful when the type of object to be created is determined at runtime.

public abstract class Animal {
    public abstract void sound();
}

public class Dog extends Animal {
    public void sound() {
        System.out.println("Woof!");
    }
}

public class Cat extends Animal {
    public void sound() {
        System.out.println("Meow!");
    }
}

public class AnimalFactory {
    public static Animal createAnimal(String type) {
        if (type.equals("dog")) {
            return new Dog();
        } else if (type.equals("cat")) {
            return new Cat();
        } else {
            return null;
        }
    }
}

public class Client {
    public static void main(String[] args) {
        Animal animal = AnimalFactory.createAnimal("dog");
        animal.sound(); // Output: Woof!
    }
}


12. Iterator Vs ListIterator


Iterator:
Definition: An interface that provides a way to traverse through elements in a collection, one at a time.

Applicable to: Any collection (e.g., List, Set, Map, etc.) that implements the Iterable interface.

Traversal Direction: Supports only forward traversal.

Cannot iterate backward.
Can remove elements but cannot modify or add elements during iteration.
Can be used with all collections like List, Set, Map, but provides limited functionality.


 ListIterator:
Definition: A specialized sub-interface of Iterator, designed specifically for lists. It provides additional methods to traverse a list in both directions and modify elements during iteration.

Applicable to: Only List types (e.g., ArrayList, LinkedList, etc.).

Traversal Direction: Supports both forward and backward traversal.


Can traverse in both forward and reverse directions.
Allows modifying the list during iteration (e.g., adding or replacing elements).
Provides the index of the elements being iterated, which is not possible with a regular Iterator.

Saint Goblin 
1. What is the defult patcher in servelet 

The DispatcherServlet is a core component of the Spring MVC framework. It is a front controller that manages all incoming HTTP requests and routes them to appropriate handlers (such as controllers) within a Spring MVC web application.

Key Responsibilities of the DispatcherServlet:
Request Handling:

The DispatcherServlet acts as the entry point for all HTTP requests in a Spring MVC application.
It receives incoming requests and then delegates the processing of these requests to appropriate controller methods, view resolvers, and other components like interceptors, exception handlers, etc.
Front Controller Pattern:

The DispatcherServlet implements the Front Controller design pattern, meaning it centralizes request processing by handling requests and responses, routing them to the right places in the application.
Routing Requests:

It uses Handler Mappings to determine which method or controller should handle the incoming request, based on the URL, HTTP method (e.g., GET, POST), and other factors.
For instance, if a request comes to /login, the DispatcherServlet will look for the corresponding controller method mapped to this URL and pass the request to it.
Processing Flow:

It works together with controllers, view resolvers, and model objects to generate responses (HTML, JSON, etc.).
After receiving a request, the DispatcherServlet coordinates with:
Controller: Handles the business logic and processing.
Model: Holds the data that will be passed to the view.
View Resolver: Responsible for resolving view names (like .jsp or .html files).
Exception Resolver: Handles any exceptions during the request.
Configurable:

You can configure the DispatcherServlet with a variety of features such as interceptors, custom error handling, and more.
It is the main servlet configured in a Spring Boot or Spring MVC application, which you can customize in application.properties or Java-based configurations.

2. How to write a code for immutable object 

To write an immutable String class in Java, you need to ensure that once an object of this class is created, it cannot be modified. While Java already provides an immutable String class, you can create your own custom immutable string class by following these guidelines:

Key Principles of Immutability:

1. Mark the class as final:  This prevents the class from being subclassed and modified.
2. Make all fields private and final:  To ensure fields are assigned only once and cannot be modified.
3. Do not provide any setter methods:  Mutator methods would allow modification after creation, violating immutability.
4. If returning mutable objects, return a copy, not the original object.

Code : 

public final class MyString {

    // Final private variable to hold the string value
    private final String value;

    // Constructor to initialize the value
    public MyString(String value) {
        // Make a defensive copy to ensure immutability (though String is already immutable)
        this.value = value != null ? value : ""; // Ensures it's never null
    }

    // Getter method that returns the string value
    public String getValue() {
        return value;
    }

    // Method to get the length of the string
    public int length() {
        return value.length();
    }

    // Method to get a character at a specific index
    public char charAt(int index) {
        return value.charAt(index);
    }

    // Method to concatenate two MyString objects
    public MyString concat(MyString other) {
        if (other == null) {
            return this;
        }
        return new MyString(this.value + other.value);
    }

    // Method to check equality with another MyString object
    @Override
    public boolean equals(Object obj) {
        if (this == obj) {
            return true;
        }
        if (obj instanceof MyString) {
            MyString other = (MyString) obj;
            return this.value.equals(other.value);
        }
        return false;
    }

    // Override the hashCode method
    @Override
    public int hashCode() {
        return value.hashCode();
    }

    // Override the toString method
    @Override
    public String toString() {
        return value;
    }
}


3. Serialization and deserialization  and what is serialization id 
Serialization	Deserialization
Converts an object into a byte stream or a storable/transferable format.
Converts a byte stream or data format back into an object.
Usually for storage or network transmission.
Typically used when retrieving or using the object.
Example output: File, JSON, XML, or byte stream.
Example output: Reconstructed object or data.

4. diff arry list and linklist 

ArrayList	LinkedList

1. ArrayList is an index based data structure where each element is associated with an index.
|Elements in the LinkedList are called as nodes, where each node consists of three things – Reference to previous element, Actual value of the element and Reference to next element.|

2. 	Insertions and Removals in the middle of the ArrayList are very slow. Because after each insertion and removal, elements need to be shifted.|
Insertions and Removals from any position in the LinkedList are faster than the ArrayList. Because there is no need to shift the elements after every insertion and removal. Only references of previous and next elements are to be changed.|

3. Insertion and removal operations in ArrayList are of order O(n).	
|Insertion and removal in LinkedList are of order O(1).

4. Retrieval(Searching or getting an element)	Retrieval of elements in the ArrayList is faster than the LinkedList . Because all elements in ArrayList are index based.	
Retrieval of elements in LinkedList is very slow compared to ArrayList. Because to retrieve an element, you have to traverse from beginning or end (Whichever is closer to that element) to reach that element.

5. Retrieval operation in ArrayList is of order of O(1).	
Retrieval operation in LinkedList is of order of O(n).

6. Random Access	ArrayList is of type Random Access. i.e elements can be accessed randomly.	
LinkedList is not of type Random Access. i.e elements can not be accessed randomly. you have to traverse from beginning or end to reach a particular element.

7. ArrayList can not be used as a Stack or Queue.
LinkedList, once defined, can be used as ArrayList, Stack, Queue, Singly Linked List and Doubly Linked List.

8. ArrayList requires less memory compared to LinkedList. Because ArrayList holds only actual data and it’s index.	
LinkedList requires more memory compared to ArrayList. Because, each node in LinkedList holds data and reference to next and previous elements.

9. When To Use	If your application does more retrieval than the insertions and deletions, then use ArrayList.	
If your application does more insertions and deletions than the retrieval, then use LinkedList.

5. what is the default end point of URL
6. Fouction on project 
7. java 8 new feature and date api 
8. Angular 


Tech Mahindra 
1. What is agile 
2. what is SDLC
3. what is class loader
4. class path and variable diff
5. Vector and arrtlist
6. what is multi threading
7. what is arrylist


1. Java 8 feature 
2. @transition 
3. how you implement security 
4. how you developer auth token 
5. jwt 
6. final keyword - class , var , method 
7. functional interface 
8. Exception handling
9. if error is occure multiple times how to handle it. 

Global Error Handling with @ControllerAdvice
Global Exception Handling: Use @ControllerAdvice to catch errors globally and handle them in a uniform manner.
Retry Mechanism: Use Spring Retry for retrying failed operations.
Circuit Breaker: Use Resilience4j or Hystrix to stop calling a failing service after repeated failures.
Logging and Monitoring: Log repeated errors and set up monitoring to detect and fix recurring issues.
Rate Limiting: Prevent too many error messages from overwhelming the system.
Graceful Degradation: Handle failures in a way that maintains the user experience, such as showing fallback content.

10. throw and throws 
11. Globle exception
12. Exception and error 
13. compile and runtime error 
14. different bean
15. 1 to many relationship implements
16. Singleton design pattern 
17. 1 emp has many address


Questuon : 
1. Why string is immutable 
2. Internet working of hashmap 
3. What is hashing tecnicke 
4. Write the code to count the frequency of arry 
5. What is lambda express 
6. Write the code in lambda expression 
7. What is functional interface 
8. Why we use @springbootapplication annotation 
9. Why we use spring boot 
10. How to change the port number in spring boot
11. Method overriding and method overloading Inheritance in java
12. Can we overriding the static method

Question :
Why string is immutable 
Internet working of hashmap 
What is hashing tecnicke 
Write the code to count the frequency of arry 
What is lambda express 
Write the code in lambda expression 
What is functional interface 
Why we use @springbootapplication annotation 

What @SpringBootApplication Includes:
It is a combination of the following three annotations:

@EnableAutoConfiguration:
Tells Spring Boot to automatically configure the application based on the libraries on the classpath. For example, if Spring Boot detects a web application, it will automatically configure an embedded web server like Tomcat or Jetty.
@ComponentScan:
Tells Spring to scan the current package and its sub-packages for components, configurations, and services. It allows Spring to automatically detect classes annotated with @Component, @Service, @Repository, and @Controller (among others).
@Configuration:
Marks the class as a source of bean definitions for the application context. Essentially, it indicates that the class can contain @Bean definitions.

1. Why we use spring boot 
2. How to change the port number in spring boot

server.port=8081

3. Method overriding and method overloading 
4. Inheritance in java
5. Can we overriding the static method
6. Hibernate important interface user hibernate 
7. Direct in hibernet easy load and get load 
8. Ioc container type 
9. Beans factory and applications contexest 
10. Session factory 
11. Hibernet cache 
12. Lazy and eager loading 
13. Get and load method hibernet 
15. Architectural of hibernate 
16. State of hibernet 
17. Loging factory
18. Swagger api documentation 
Provide karte hai front end walo ko 
Put and patch
19. Concutsnt hashmap and hash table






 Q.  Can we overriding the static method

 Ans: No we can not override the static method in java beac. for static mehtod is related for compile time 
     but in overriding we can perform run time only.   we called as a method hiding. 

     package CodingQ;

 class Static {

    public static void m() {
        System.out.println("appp");
    }

}
class s extends Static {
    public static void m() {
        System.out.println("apppch");
    }
}


public  class ABH
    {
        public static void main(String[] args) {

            Static s =new s();
            s.m();
        }
    }



Code:  Counting frequencies of array elements

class GFG
{
 
    static void countFreq(int arr[], int n)
    {
        Map<Integer, Integer> mp = new HashMap<>();
 
        // Traverse through array elements and
        // count frequencies
        for (int i = 0; i < n; i++)
        {
            if (mp.containsKey(arr[i])) 
            {
                mp.put(arr[i], mp.get(arr[i]) + 1);
            } 
            else
            {
                mp.put(arr[i], 1);
            }
        }
        // Traverse through map and print frequencies
        for (Map.Entry<Integer, Integer> entry : mp.entrySet())
        {
            System.out.println(entry.getKey() + " " + entry.getValue());
        }
    }
 
    // Driver code
    public static void main(String args[]) 
    {
        int arr[] = {10, 20, 20, 10, 10, 20, 5, 20};
        int n = arr.length;
        countFreq(arr, n);
    }
}

HashMap get() Method in Java

The java.util.HashMap.get() method of HashMap class is used to retrieve or fetch the value mapped by a particular key mentioned in the parameter. It returns NULL when the map contains no such mapping for the key.

The java.util.HashMap.containsKey() 
method is used to check whether a particular key is being mapped into the HashMap or not. It takes the key element as a parameter and returns True if that element is mapped in the map.

The java.util.Map.entrySet()
 method in Java is used to create a set out of the same elements contained in the map. It basically returns a set view of the map or we can create a new set and store the map elements into them.

 https://www.geeksforgeeks.org/map-entryset-method-in-java-with-examples/?ref=header_ind

Wissen 
1. what is map'
2. hashmap
3. it internal working
4. how to implemetns linklist property
5. merge tow arry
6. post method 
7. SOLID Property 
8. transction 
9. Spring mvc and sb 
10. how to make classs imutable 
11. server side paging 
12. isolation level 
13. map interface.



Banck Intervieeww 

1. What is the diff SB and MVC 
2. What is the tranjaction annotaion 
3. how to communicate with two microservices 
4. how to remove the string repitaed charecter and replcae with some special charecter 

Code 

import java.util.HashSet;
import java.util.Set;

public class RemoveRepeatedCharacters {

    public static void main(String[] args) {
        String input = "aabbccdaeffg";
        char specialChar = '\\';

        String result = removeRepeatedCharacters(input, specialChar);
        System.out.println("Modified String: " + result);
    }

    private static String removeRepeatedCharacters(String input, char specialChar) {
        StringBuilder result = new StringBuilder();
        Set<Character> seen = new HashSet<>();

        for (int i = 0; i < input.length(); i++) {
            char c = input.charAt(i);
            if (seen.contains(c)) {
                result.append(specialChar);
            } else {
                result.append(c);
                seen.add(c);
            }
        }

        return result.toString();
    }
}


5. diff list and set 
6. what is linklist 
7. what is microservices 
8. controller and rest controller 
9. why we use cruedrepositery instent of JPArepositery diff 
10. what si ency. and dcryption. 
11. what is achuater


Mumbai Company
1. What is the difference between MVC and Spring boot 
2. Singleton and static class design pattern 
3. Link list and arry list 
4. Interface and abstract class 
5. JPA and orm tool
6. System.out.println 

System is a utility class, out is a PrintStream object, and println() is a method that prints various types of data followed by a newline.

7. Springspacuter



Comany  Init Kolkata 
1. What is Dispatch servlet 
2. Arrylist and lindlist 
3. Linkedhasset and treehasset 
4. Restcontroller and controller 
5. Frequency count code 
import java.util.HashMap;
import java.util.Map;

public class CharFrequencyCount {
    public static void main(String[] args) {
        // Input string
        String str = "Abhishek";

        // Convert string to lowercase to make the frequency count case-insensitive
        str = str.toLowerCase();

        // Map to store the frequency of each character
        Map<Character, Integer> frequencyMap = new HashMap<>();

        // Loop through the string using charAt() to count the frequency of each character
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);  // Get the character at index i
            frequencyMap.put(ch, frequencyMap.getOrDefault(ch, 0) + 1);
        }

        // Print the frequency of each character
        for (Map.Entry<Character, Integer> entry : frequencyMap.entrySet()) {
            System.out.println("Character: " + entry.getKey() + ", Frequency: " + entry.getValue());
        }
    }
}

6. Https code 200 201 202
7. JPA hibernate differacne 
8. How to connect two database in Spring boot


You need to create separate DataSource beans for each database in a configuration class.

DataSource
EntityManagerFactory (userEntityManager)
TransactionManager (userTransactionManager)

import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.boot.context.properties.ConfigurationProperties;
import org.springframework.boot.jdbc.DataSourceBuilder;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.jdbc.datasource.DataSourceTransactionManager;
import org.springframework.orm.jpa.JpaTransactionManager;
import org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean;

import javax.sql.DataSource;

@Configuration
public class DataSourceConfig {

    // First DataSource configuration
    @Bean(name = "firstDataSource")
    @ConfigurationProperties(prefix = "spring.datasource")
    public DataSource firstDataSource() {
        return DataSourceBuilder.create().build();
    }

    // Second DataSource configuration
    @Bean(name = "secondDataSource")
    @ConfigurationProperties(prefix = "second.datasource")
    public DataSource secondDataSource() {
        return DataSourceBuilder.create().build();
    }

    // EntityManagerFactory and TransactionManager for the first DB (for JPA)
    @Bean(name = "firstEntityManagerFactory")
    public LocalContainerEntityManagerFactoryBean firstEntityManagerFactory(
        @Qualifier("firstDataSource") DataSource dataSource) {
        return new LocalContainerEntityManagerFactoryBean();
    }

    @Bean(name = "firstTransactionManager")
    public JpaTransactionManager firstTransactionManager(
        @Qualifier("firstEntityManagerFactory") LocalContainerEntityManagerFactoryBean firstEntityManagerFactory) {
        return new JpaTransactionManager(firstEntityManagerFactory.getObject());
    }

    // EntityManagerFactory and TransactionManager for the second DB (for JPA)
    @Bean(name = "secondEntityManagerFactory")
    public LocalContainerEntityManagerFactoryBean secondEntityManagerFactory(
        @Qualifier("secondDataSource") DataSource dataSource) {
        return new LocalContainerEntityManagerFactoryBean();
    }

    @Bean(name = "secondTransactionManager")
    public JpaTransactionManager secondTransactionManager(
        @Qualifier("secondEntityManagerFactory") LocalContainerEntityManagerFactoryBean secondEntityManagerFactory) {
        return new JpaTransactionManager(secondEntityManagerFactory.getObject());
    }
}

You need to create separate DataSource beans for each database in a configuration class.

Use @Primary to mark one of the data sources as the default one.
Define separate EntityManager factories for each DataSource.
If you're using JPA, you need to annotate the repositories with @EnableJpaRepositories and specify which EntityManager to use.


1. Different between throw and throws 
2. What is bad request In rest apis
3. Arrylist and lindlist 
4. What is Class loader 

In Java, ClassLoader is a part of the Java Runtime Environment (JRE) that dynamically loads Java classes into the Java Virtual Machine (JVM) during runtime. A class loader is responsible for locating, loading, and linking class files (usually .class files) as needed.


1. Bootstrap ClassLoader
Purpose: Loads the core Java classes (like those in java.lang, java.util, etc.) from the rt.jar or its equivalent.
Written in: Native code (typically C or C++).
Parent of: The Extension ClassLoader.

2. Extension (Platform) ClassLoader
Purpose: Loads classes from the ext directory (<JAVA_HOME>/lib/ext) or other locations configured by the system property java.ext.dirs.
Parent of: The Application ClassLoader.

3. Application (System) ClassLoader
Purpose: Loads classes from the classpath (CLASSPATH environment variable or -classpath option) defined by the user.
Default: Loads the classes of your Java application.
Example: All classes in your src folder or JAR files that you package.

5. Finally and finalize difference


Finally : 
finally is a block which is used for exception handling along with try and catch blocks. finally block is always executed whether exception is raised or not and raised exception is handled or not. Most of time, this block is used to close the resources like database connection, I/O resources etc. 

finalize() Method :
 This method is called by  garbage collector thread before an object is removed from the memory. finalize() method is used to perform some clean up operations on an object before it is removed from the memory.
6. Outer join and interjoin 
7. Restcontroller and controller different 
8. Why we use default and static method in interface 
9. Numberformeate exceptions and one more  InputMismatchException

 NumberFormatException
The NumberFormatException typically occurs when using methods like Integer.parseInt(), Double.parseDouble(), or similar methods from the wrapper classes, and the string being parsed does not represent a valid number.

public class Main {
    public static void main(String[] args) {
        try {
            String invalidNumber = "abc";
            int number = Integer.parseInt(invalidNumber); // This will throw NumberFormatException
        } catch (NumberFormatException e) {
            System.out.println("Invalid number format: " + e.getMessage());
        }
    }
}

The string "abc" is not a valid integer, so Integer.parseInt() throws a NumberFormatException.

Trying to convert a non-numeric string into a number (e.g., "abc" to an integer).
Trying to convert a string with inappropriate characters (e.g., "$100" or "123abc").
Converting an empty string ("") to a number.
Trying to convert a string that represents a number larger than the maximum value for that numeric type.

INputMismatch 

The InputMismatchException in Java is thrown by the Scanner class when the input provided does not match the expected type. It occurs when the program is expecting a particular type of input (like an integer or a double), but the user enters something that doesn't match that type.

This exception is part of the java.util package.
It's a runtime exception, meaning it’s unchecked, and the program doesn’t have to declare or catch it explicitly.
The Scanner class methods, such as nextInt(), nextDouble(), etc., can throw this exception if the input does not match the expected type.

import java.util.Scanner;
import java.util.InputMismatchException;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter an integer: ");
        
        try {
            int number = scanner.nextInt();  // Expects an integer input
            System.out.println("You entered: " + number);
        } catch (InputMismatchException e) {
            System.out.println("Error: Input is not a valid integer. Please enter a number.");
        }
    }
}



10. Can we overloading and overload construocter 


Constructor is a block of code that allows you to create an object of class and has same name as class with no explicit return type.

Whenever a class (child class) extends another class (parent class), the sub class inherits state and behavior in the form of variables and methods from its super class but it does not inherit constructor of super class because of following reasons:

Constructors are special and have same name as class name. So if constructors were inherited in child class then child class would contain a parent class constructor which is against the constraint that constructor should have same name as class name. For example see the below code:


If we define Parent class constructor inside Child class it will give compile time error for return type and consider it a method. But for print method it does not give any compile time error and consider it a overriding method.

Now suppose if constructors can be inherited then it will be impossible to achieving encapsulation. Because by using a super class’s constructor we can access/initialize private members of a class.
A constructor cannot be called as a method. It is called when object of the class is created so it does not make sense of creating child class object using parent class constructor notation. i.e. Child c = new Parent();
A parent class constructor is not inherited in child class and this is why super() is added automatically in child class constructor if there is no explicit call to super or this.


Constructor Overloading: Yes, it's allowed. You can have multiple constructors with different parameter lists in the same class.

Constructor Overriding: No, it's not allowed. Constructors are not inherited in Java, so they cannot be overridden. However, you can call superclass constructors using super() from the subclass.


11. Can we overriding static methods   

No We can not override the static methods.
12. Patch and put



NTT DATA
1. How to handle the multiple requests in spring boot.

Summary of Techniques for Handling Multiple Requests in Spring Boot:
Default (Synchronous): Each request is handled one at a time by a single thread.
Asynchronous Processing: Use @Async and CompletableFuture for non-blocking processing, enabling concurrent request handling.
ExecutorService: Use a custom ExecutorService for managing multiple threads manually.
Request Queuing: Queue tasks using a BlockingQueue to manage high numbers of requests.
Rate Limiting: Implement rate limiting using libraries like Bucket4j to control the number of requests.
WebSockets: Use WebSockets for real-time applications that require handling multiple simultaneous connections.


2. Controller and restcontroller

3. Globale exceptions.

Using @ControllerAdvice for Global Exception Handling
@ControllerAdvice is a specialized @Component that allows you to handle exceptions globally in Spring Boot. It can be applied to methods within the class that handle exceptions for the entire application, or specific controllers.

Steps to implement:
Create a class with the @ControllerAdvice annotation.
Define exception handler methods inside the class using @ExceptionHandler.
Customize the response, such as the status code, message, or any other details, for each type of exception.

@ControllerAdvice: This annotation defines a global exception handler class that will handle exceptions thrown in any controller.
@ExceptionHandler: This annotation specifies the method to handle specific types of exceptions. In this example, we handle ResourceNotFoundException and RuntimeException.
ResponseEntity: This is used to customize the response sent back to the client (including HTTP status code and body content).
@ResponseStatus: Specifies the HTTP status code to return for the exception.

4. Microservices how to communicate with 2 microservices and.
5. Saga design pattern
5. how to remove memory leaked.
6. @Qualifer and primary.

Use @Primary to designate the default bean when multiple beans of the same type are present.

Use @Qualifier when you want to specify a particular bean explicitly.

7. Throw and throws 

throw Keyword
The throw keyword is used to explicitly throw an exception from a method or any block of code.
You can use it to throw both checked and unchecked exceptions.
When throw is used, it creates an instance of the exception class and passes it up the call stack to be handled by an appropriate catch block or propagated further.

throws Keyword
The throws keyword is used in a method signature to declare that the method might throw one or more exceptions. It informs the caller of the method that the exceptions must be handled or propagated further.
It is typically used for checked exceptions, which need to be handled explicitly.

8. How to create our own exception 

Throw your custom exception where needed (e.g., in service or controller methods).
Handle the exception globally or locally using @ExceptionHandler or @ControllerAdvice.

9. How to push your code in perticular feature repo 
10. And how to build that. 
11. Arrylist and linkedlist.
12. Map flatmap difference
13. Intermediate and terminal operations 
14. Authentication and Automations
15. How to secure your rest API

Using Spring Boot, you can integrate Bucket4j or Resilience4j to implement rate-limiting. 

Summary of Best Practices:
Use Authentication (JWT or OAuth 2.0) to secure API endpoints.
Always use HTTPS to encrypt communication between clients and APIs.
Rate Limit API Requests to prevent abuse and overloading.
Validate and Sanitize Input to avoid SQL injection, XSS, and other vulnerabilities.
Enable CSRF Protection where necessary.
Implement Role-based Access Control (RBAC) for fine-grained access management.
Centralize Security with an API Gateway for better manageability.

16. Session factory why we use
17. memory leake in java 8 feature 

A Memory Leak is a situation where there are objects present in the heap that are no longer used, but the garbage collector is unable to remove them from memory, and therefore, they’re unnecessarily maintained.

In Java, the memory leak is a situation when the garbage collector does not recognize the unused objects and they remain in the memory indefinitely that reduces the amount of memory allocated to the application. Because the unused objects still being referenced that may lead to OutOfMemoryError

A memory leak is bad because it blocks memory resources and degrades system performance over time. If not dealt with, the application will eventually exhaust its resources, finally terminating with a fatal java.lang.OutOfMemoryError.

Reasons :

1. Using Unwanted Object Reference: These are the object references that are no longer needed. The garbage collector is failed to reclaim the memory because another object still refers to that unwanted object.

2. Using Long-live Static Objects: Using static objects also leads to a memory leak. Because they live in the memory till the application's life span.

3. Failure to Clean-up Native System Resources: Native system resources allocated by a function external to Java. It is written in C and C++. JNI APIs are used to embed native libraries in the Java code.

4. Bugs in the Third-party Libraries: Bugs in AWT and Java Swing packages are another cause of memory leak.

Preventing Memory Leak
While writing code, remember the following points that prevent the memory leak in Java.

Do not create unnecessary objects.
Avoid String Concatenation.
Use String Builder.
Do not store a massive amount of data in the session.
Time out the session when no longer used.
Do not use the System.gc() method.
Avoid the use of static objects. Because they live for the entire life of the application, by default. So, it is better to set the reference to null, explicitly.
Always close the ResultSet, Statements, and Connection objects in the finally block.


Detecting Memory Leak
Detecting memory leaks is a difficult task. To simplify the task, there are many tools available that perform static analysis and detect memory leaks:

JProbe
AppPerfect
Visual VM
Jprofiler
YourKit
GCeasy
JRockit


Fixing Memory Leak
There are the following solutions to the memory leak problem:

Using JVM Tools: There are many tools available that optimizes the code and show the memory status.

Using Heap Dump: It is a technique that is the solution to the memory leak problem. It is a snapshot of all objects that reside in the memory at a certain time. It also optimizes memory usage in a Java application. It is stored in binary format in hprof

Using Eclipse Memory Leak Warnings: If you are using the Eclipse framework to develop a Java application, eclipse regularly shows the waring and errors whenever it encounters any causes of memory leak.


13.  Arrange the input string in the alphabetical order of their occurrence . and also remove the duplicate characters.
        Sample output - ABDEHIKNORSTVWY*/

        /*String inputString = " ABHISHEK INTERVIEW TODAY";

public class A {

    public static void main(String[] args) {

        String inputString = "ABHISHEK INTERVIEW TODAY";
        String result = inputString.replaceAll("\\s+", "") // remove spaces
                .chars()               // get stream of characters
                .distinct()            // remove duplicates
                .sorted()              // sort characters
                .mapToObj(c -> String.valueOf((char)c)) // convert back to String
                .collect(Collectors.joining()); // join the characters into a string

        System.out.println(result); // Output: ABDEHIKNORSTVWY
    }



Techbulls

1. Siglton and Factory pattern
2. Frequnecy count code 

  String s ="MADAM";

        HashMap<Character, Integer> r =new HashMap<>();

        for(char c : s.toCharArray())
        {
            r.put(c , r.getOrDefault(c,0) + 1);
        }

        for(Map.Entry<Character,Integer> entery : r.entrySet())
        {
            System.out.print(entery.getKey()+  " -  "  +entery.getValue());
        }

3.  why we use default method in functiona interface
4.  5 any spring boot annotation 
5. diff. bean and compnent // service and componet 
6.  SQl 

Table Name:  EMPLOYEE 
Columns : emp_id, emp_name , emp_dept
Write a Query to print below Output :
EmpCount   |   EmpDept 
 10                 |    Maths
 50                 |    Physics 
 20                 |    Chemistry


Select cout(*) as empcourt,
emp_dept
from Employee group by emp_dept 

7. Take a list of integers , remove duplicates and sort in natural order

/*  List<Integer> sorted = Arrays.asList(5,6,5,6,7,8,5,8);

       List<Integer> R =sorted.stream().distinct().sorted().collect(Collectors.toList());

        System.out.println(R);*/

8. Fequency count 
       String s ="MADAM";

        HashMap<Character, Integer> r =new HashMap<>();

        for(char c : s.toCharArray())
        {
            r.put(c , r.getOrDefault(c,0) + 1);
        }

        for(Map.Entry<Character,Integer> entery : r.entrySet())
        {
            System.out.print(entery.getKey()+  " -  "  +entery.getValue());
        }

9. Can we overload and override the main method
 
 we can overload the main method - 
 but we can not override the main method 


Congnizent 
1. inside singelton if dependency is added inside this bean , we are invoking several calls to outer bean , how many instances of outer and inner bean will be created
2. What is eventlistner in hibernet.
3. How to sort the list based on  empty age and name.

import java.util.ArrayList;
import java.util.Comparator;
import java.util.List;

public class Employee {
    private String name;
    private int age; // Use primitive int since null handling is not needed

    public Employee(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    @Override
    public String toString() {
        return "Employee{name='" + name + "', age=" + age + "}";
    }

    public static void main(String[] args) {
        List<Employee> employees = new ArrayList<>();
        employees.add(new Employee("Alice", 30));
        employees.add(new Employee("Bob", 28));
        employees.add(new Employee("Charlie", 25));
        employees.add(new Employee("Diana", 30));
        employees.add(new Employee("Eve", 28));

        // Sort by age, then by name
        employees.sort(
            Comparator.comparingInt(Employee::getAge) // Sort by age
                      .thenComparing(Employee::getName) // Then by name
        );

        // Print the sorted list
        employees.forEach(System.out::println);
    }
}

4. Different type to bean scope 

1. Singleton (Default Scope)

Only one instance of the bean is created per Spring container.
This instance is shared across the entire application, meaning any request for the bean will return the same instance.
It's the default scope when you define a bean in Spring without specifying a scope.
java
Copy code
@Bean
@Scope("singleton")
public MyBean myBean() {
    return new MyBean();
}
2. Prototype

A new instance of the bean is created each time it's requested from the Spring container.
Useful when each user or component needs its own unique instance.
The container does not manage the complete lifecycle of a prototype bean, only its instantiation.
java
Copy code
@Bean
@Scope("prototype")
public MyBean myBean() {
    return new MyBean();
}
3. Request (Web Application Scope)

Creates a new bean instance for each HTTP request in a web application.
The bean is valid only within the scope of a single HTTP request and is destroyed at the end of the request.
java
Copy code
@Bean
@Scope("request")
public MyBean myBean() {
    return new MyBean();
}
4. Session (Web Application Scope)

Creates a new bean instance for each HTTP session in a web application.
The bean is stored in the session scope and lasts as long as the HTTP session.
java
Copy code
@Bean
@Scope("session")
public MyBean myBean() {
    return new MyBean();
}
5. Application (Web Application Scope)

A single instance of the bean is created for the entire lifecycle of the ServletContext.
Similar to singleton scope but specific to web applications, where the bean’s lifecycle matches the application’s lifecycle.
java
Copy code
@Bean
@Scope("application")
public MyBean myBean() {
    return new MyBean();
}
6. WebSocket (WebSocket Scope)

This scope is specific to WebSocket communication.
A new instance is created for each WebSocket session.
java
Copy code
@Bean
@Scope("websocket")
public MyBean myBean() {
    return new MyBean();
}
Note: The web-related scopes (request, session, application, websocket) are only available in a web-aware Spring ApplicationContext, such as a Spring MVC application.

Each scope has its own specific use cases, and choosing the right one depends on how you want the bean to behave in terms of its lifecycle and accessibility across different components in the application.


5. What is default bean scope

In Spring, the default bean scope is singleton. This means that by default, Spring creates only one instance of a bean per Spring IoC container, and this single instance is shared across the entire application context. When a bean is defined with the singleton scope, any request for that bean will return the same instance.

6. How to configure hibernet in spring boot 
7. What input is needed to create the session factory.

hibernate.dialect: This tells Hibernate which SQL dialect to use for the database (e.g., org.hibernate.dialect.MySQLDialect).
hibernate.hbm2ddl.auto: This setting controls the schema management strategy (update, create, create-drop, validate, or none).
hibernate.show_sql: Whether to show SQL queries in the console (true or false).
hibernate.format_sql: Whether to format SQL output (true or false)

import org.hibernate.SessionFactory;
import org.hibernate.cfg.Configuration;

public class HibernateUtil {
    private static SessionFactory sessionFactory;

    static {
        try {
            Configuration configuration = new Configuration();

            // Database connection properties
            configuration.setProperty("hibernate.connection.url", "jdbc:mysql://localhost:3306/mydb");
            configuration.setProperty("hibernate.connection.username", "root");
            configuration.setProperty("hibernate.connection.password", "password");
            configuration.setProperty("hibernate.connection.driver_class", "com.mysql.cj.jdbc.Driver");

            // Hibernate properties
            configuration.setProperty("hibernate.dialect", "org.hibernate.dialect.MySQLDialect");
            configuration.setProperty("hibernate.hbm2ddl.auto", "update");
            configuration.setProperty("hibernate.show_sql", "true");
            configuration.setProperty("hibernate.format_sql", "true");

            // Adding annotated entity classes
            configuration.addAnnotatedClass(Customer.class);

            // Build the SessionFactory
            sessionFactory = configuration.buildSessionFactory();
        } catch (Exception e) {
            e.printStackTrace();
            throw new ExceptionInInitializerError("SessionFactory creation failed");
        }
    }

    public static SessionFactory getSessionFactory() {
        return sessionFactory;
    }
}

8. HIBERNATE generates some query how bean log it.
9. Copareble and comparato different.
10. CQRS design pattern. 
11. Saga design pattern.
12. Different between restfull and rest APIs



Condnizent Clien roeund 
1. How to convert get name is active user and to convert in uppercase 
 Optional<String> activeUserNameUpper = users.stream()
                .filter(User::isActive) // Filter active users
                .map(User::getName)     // Get the name of active users
                .findFirst()            // Take the first active user
                .map(String::toUpperCase); // Convert the name to uppercase

        // Print the uppercase name of the active user if found
        activeUserNameUpper.ifPresent(name -> System.out.println("Active user name in uppercase: " + name));

2. Frequncy count 

S = "abhishek" ;
Map<Charecter, Integer> t = new HashMap<>();
s.chars().maptoObj( e -> (char) e).collect(Collectors.groupingBy(Function.identity(), Collectors.countign());

3. How to print the values like 
input s = "abhishek Pal"

out put = "AAHHISEKLB" ;

4. Kafka 
5. how to communicate with thired party api and interservice communication 
6. API gate way 

An API Gateway is an essential component in a microservices architecture that acts as a single entry point for all client requests to interact with multiple services. Its primary role is to manage, route, and secure client requests, simplifying how clients access services within a distributed system.

7. Why we use function.identity in java 8 
8. Saga pattern 

The Saga pattern is a widely used approach for handling distributed transactions in a microservices architecture. Since each microservice is designed to operate independently and manage its own data, traditional ACID transactions are not feasible across services. The Saga pattern breaks a large, distributed transaction into a sequence of smaller, independent transactions managed within each service.

Key Concepts of the Saga Pattern
Distributed Transaction: A single transaction spread across multiple services.
Saga: A sequence of transactions (operations) where each operation is a local transaction within a service.
Compensation: If a transaction in the sequence fails, the Saga pattern ensures any previous changes are undone to maintain consistency.


Two Main Saga Implementation Approaches

Choreography: Each service involved in the saga is responsible for knowing when to start the next step in the transaction process or when to trigger a compensating action.

Orchestration: A central controller (or orchestrator) manages the entire saga sequence, deciding the order of steps and handling rollbacks if necessary.

1. Choreography-Based Saga
In the choreography approach, each service publishes and listens to events. When one service completes a step in the saga, it publishes an event that triggers the next step in another service.

How It Works
Event-Driven: Services communicate by publishing and subscribing to events.
Decentralized: There is no central orchestrator; each service knows what to do upon receiving specific events.
Compensation: If a failure occurs, services emit compensating events to undo the previous actions.
Pros and Cons
Pros:

Loose Coupling: Services are loosely coupled because they only listen to and emit events.
Scalable: It scales well since there is no central dependency.
Cons:

Complexity: Can become challenging to manage as the number of services and events grows.
Difficult to Debug: Tracing the saga flow and debugging issues across multiple services can be difficult.
Example Workflow (Choreography)
Let’s say you have an order placement flow:

Order Service: Places the order and publishes an OrderCreated event.
Inventory Service: Listens to the OrderCreated event, reserves the items, and publishes an InventoryReserved event.
Payment Service: Listens to the InventoryReserved event, processes payment, and publishes a PaymentCompleted event.
Shipping Service: Listens to the PaymentCompleted event and ships the order.
If any service fails, previous services will need to publish compensating events to undo previous steps.


2. Orchestration-Based Saga
In the orchestration approach, a central orchestrator (Saga Orchestrator) manages and coordinates the sequence of steps in the saga.

How It Works
Central Controller: The orchestrator service decides the order of execution for each step in the saga.
Direct Communication: The orchestrator calls each service in a defined sequence.
Compensation: The orchestrator initiates compensating transactions in the event of a failure.
Pros and Cons
Pros:

Centralized Logic: The workflow logic is centralized, making it easier to manage and change.
Clear Execution Flow: Easier to trace, debug, and maintain due to centralized control.
Cons:

Single Point of Failure: The orchestrator can become a single point of failure.
Higher Coupling: Services are more tightly coupled to the orchestrator.
Example Workflow (Orchestration)
Using the same order placement flow:

Orchestrator Service: Starts the saga by calling the Order Service to create the order.
Order Service: Creates the order and returns success to the orchestrator.
Orchestrator Service: Calls the Inventory Service to reserve items.
Inventory Service: Reserves items and returns success.
Orchestrator Service: Calls the Payment Service to process payment.
If any step fails, the orchestrator triggers compensating transactions, like canceling the order or releasing reserved inventory.


Mphasisi

1. What is covariant return type in java 
2. Different between singleton in java class and singleton design pattern 
3. How to convert json to DTO and other formats 
4. Hwo to create the restapi without using restcontroller annotations 
5. Hwo to write the code filter epm name lastname and first name using core java 
6. What stream is using internal to iterat 
7. Internal working of @enableautoconfiguration
8. Different between map and maptoint in java 8


Produst 

1. Different between fail fast and fail 
2. Comparable and comparator 
3. Arrylist and lindlist 
4. Saga pattern 
5. @component 
6. Palindrome code
7. Find first duplicate values
8. Checked exception and unchecked exception example 
9. @component @service @repositery 
10. @traditional
11. Try chatch can run code without  catch 
12. Fina finally finalized the method difference
13. How many ways we can handle exception












