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


KPMG 
Find the very first non-repeating character in a string array

Input: String [] strArr={"apple","aappllee","","aabbcde","kettle"};
Output: Character [] chArr={'a','0','\u0000','c','k'};


Given an array of random numbers, push all the zeroes of a given array to the end of the array. For example, if the given array is {1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0}, it should be changed to {1, 9, 8, 4, 2, 7, 6, 0, 0, 0, 0}. The order of all other elements should be same.
Expected time complexity is O(n) and extra space is O(1).

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


