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

Why string is immutable 
Internet working of hashmap 
What is hashing tecnicke 
Write the code to count the frequency of arry 
What is lambda express 
Write the code in lambda expression 
What is functional interface 
Why we use @springbootapplication annotation 
Why we use spring boot 
How to change the port number in spring boot
Method overriding and method overloading 
Inheritance in java
Can we overriding the static method
Hibernate important interface user hibernate 
Direct in hibernet easy load and get load 
Ioc container type 
Beans factory and applications contexest 
Session factory 
Hibernet cache 
Lazy and eager loading 
Get and load method hibernet 
Architectural of hibernate 
State of hibernet 
Loging factory
Swagger api documentation 
Provide karte hai front end walo ko 
Put and patch
Concutsnt hashmap and hash table






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







