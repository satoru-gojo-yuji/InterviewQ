Ahembda bad Why string is immutable String s = "Hi" s="hellow"

String
@reposirey why we use what is abstaract class and interfce discribe your porject microservices advanatge of functinaol interface abstact class why we use if we have interface
what are the languagest did you use in your project

RBI  
How to add the new entity in jpa and Java 
 String me vowels kese print karaye 
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

Spring boot annotation.

MySQL logical qeustuon.

HTML Css JS Anguler to craret the login pager how to versify the user enter data through Js.

Vector and arry list logicla questuon.

treemap and hashmap diff.

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

diff. abstract class and interface real life 
what are the new fatuer of java 8 
diff map and flatmap 
anonoumus arry and inter class 
and announomus class 
Date API new feture for in java 8 

Infosys

1. Transiant Kayword 
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
4. Pass failed in collection
5. How to pass data from one application to another application
6. How to read the application.property file

In a Spring Boot application, you can read properties from the application.properties (or application.yml) file using various methods, including using the @Value annotation, @ConfigurationProperties annotation, or by directly injecting the Environment object. Here are the approaches:

You can read a single property from the application.properties file using the @Value annotation. 

The @ConfigurationProperties annotation is more useful for grouping related properties into a POJO (Plain Old Java Object). It can bind hierarchical properties to a class.

You can use the Environment object to access properties dynamically at runtime. The Environment object is part of the Spring framework and can be autowired into any Spring component.

7. How many way we can do the overload method 
8. diff. comparable and comparator 
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
1. What is the defult patch in servelet
2. How to write a code for immutable object 
3. Serialization and deserialization  and what is serialization id 
4. diff arry list and linklist 
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
10. throw and throws 
11. Globle exception
12. Exception and error 
13. compile and runtime error 
14. different bean
15. 1 to many relationship implements
16. Singleton design pattern 
17. 1 emp has many address

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


11. Can we overriding static methods   

No We can not override the static methods.
12. Patch and put



NTT DATA
1. How to handle the multiple requests in spring boot.
2. Controller and restcontroller

3. Globale exceptions.
4. Microservices how to communicate with 2 microservices and.
5. Saga design pattern
5.  to remove memory leaked.
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
9. How to push your code in perticular feature repo 
10. And how to build that. 
11. Arrylist and linkedlist.
12. Map flatmap difference
13. Intermediate and terminal operations 
14. Authentication and Automations
15. How to secure your rest API
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












