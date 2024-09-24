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
10. how to make singloeton 


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

