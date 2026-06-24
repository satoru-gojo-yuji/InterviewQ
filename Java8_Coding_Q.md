 String s ="Java is a good Java"

  String[] g = s.split("");     // ["j","a","v","a"] 
  String[] d =s.split("\\s+")   // ["Java","is","a","good","Java"] 


Arrays.stream(g) // Convert into String of arry into stream

===========================================================================================================================

If map = {"a"=3, "b"=1, "c"=1}

Then map.entrySet() returns:

java
Copy
Edit
[("a"=3), ("b"=1), ("c"=1)]

**"\\s+"	Regular expression (regex) that matches one or more whitespace characters
""	Replacement string — in this case, an empty string, so the whitespaces are removed**

**Yes, entrySet() is used when you want to iterate over the map and need access to both key and value.**

**Why & Where Do We Use Function.identity()?
It is often used in grouping, mapping, or transforming streams, when you don't need to change the values, and just want to use them as they are.**

**What is groupingBy()?
Collectors.groupingBy() is a collector that is used to group elements of a stream based on a classification function (i.e., a rule to categorize them).**

It returns a Map<K, List<V> by default — grouping elements under a key.


Code 

Q1. Find first non-repeated character in a string?


 String s = "Java and I".replaceAll("\\s+","").toLowercase();

 Map<String, Long> g =Arrays.strema(s.split("")).collect(Collectors.groupingBy(Function.identity(), LinkedHasmpa::new , Collectors.counting()));


 String F = g.entrySet().stream().filter(entry -> entry.getValues()== 1).map(entry -> entry.getKey()).findFirst().get();

 sout(F);

 Q2. How do you extract duplicate elements from an array?

         List<Integer> listOfIntegers = Arrays.asList(111, 222, 333, 111, 555, 333, 777, 222);


         Set<Interger> S = new HasSet<>();

         List<Interger> D =listofInterger.stream().filter(f -> !S.add(f)).collect(Collectors.toList());

Dry Run Set---
Element from List	Is in Set?	Added to Set?	Passes Filter (duplicate)?
111	❌ No	✅ Yes	❌ No (it's new)
222	❌ No	✅ Yes	❌ No
333	❌ No	✅ Yes	❌ No
111	✅ Yes	❌ No	✅ Yes (duplicate)



Q3.  Count frequency of characters


Approch 1. Using chars /  

chars -  In Java, calling .chars() on a String returns an IntStream of the Unicode code points (integer values) of each character in the string.
         Character: A => Unicode: 65  
         Character: b => Unicode: 98  
         Character: 1 => Unicode: 49

.mapToObj(c -> (char) c) - This converts each Unicode integer (from .chars()) into a Character object.

So, each int (Unicode code point) is converted to a single character.         
   a
   b
   c


String s = "Abhishek Pal";

 s =s.replcaseAll("\\s+","").toLovercase();

 Map<Charecters, Long> g =s.chars().maptoObj(c->(char)c).stream().collect(Collectors.groupingBy(Function.identity(), LinkedHasMap::new,Collectors.counting()));

 g.entrySet().stream().forEach(e -> sout(e.getValues()+" "+e.getKey()));


 Approch 2.  Using split


 String s ="Java is a good Java"

  String[] g = s.split("");     // ["j","a","v","a"] 
  String[] d =s.split("\\s+")   // ["Java","is","a","good","Java"] 


Arrays.stream(g) // Convert into String of arry into stream

  Map<String,Long> D = Arrays.stream(s.toLowerCase().split(""))
                .collect(Collectors.groupingBy(Function.identity(),Collectors.counting()));

        D.entrySet().stream().filter(d -> d.getValue() == 1).forEach(e -> System.out.println(e.getKey()+" "+e.getValue()));
    }

    

If the interviewer asks "Find the longest common prefix in Core Java (without Streams)", this is the most common solution:

public class LongestCommonPrefix {

    public static String findCommonPrefix(String[] strs) {

        if (strs == null || strs.length == 0) {
            return "";
        }

        String prefix = strs[0];

        for (int i = 1; i < strs.length; i++) {

            while (!strs[i].startsWith(prefix)) {

                prefix = prefix.substring(0, prefix.length() - 1);  //  remove the last index 

                if (prefix.isEmpty()) {
                    return "";
                }
            }
        }

        return prefix;
    }

    public static void main(String[] args) {

        String[] strs = {"flower", "flow", "flight"};

        System.out.println(findCommonPrefix(strs));
    }
}
Output
fl


Find First Non-Repeated Character

string s="AbhishekPal"

s.chars().maptoObj(c->(char)c).collect(Collectors.groupingBy(Function.identity(),LindkedhashMap::new,Collectors.counting())
.entrySet().stream().filter(e -> e.getValue() == 1)map(Map.Entery::getKey).Findfirst().get().


Find Duplicate Elements

List<Integer> d = Arrays.asList(1,2,3,4,5,64,5,6);

set<Integer> s = new hasSet<>();

d.stream().filter(e-> !s.add(e)).for(System.out::Print);


Find Second Highest Number
List<Integer> numbers = Arrays.asList(10,20,50,40,30);


n.stream().sorted(comparator.reverseOrder()).
    skip(1).findFirst()


Find Highest Paid Employee in Each Department

e.stream().collect(Collectors.groupingBy(e-> e.getDepartment(),Collectors.maxBy(Comparator.comparing(e-> e.getSalary());


String sentence = "java spring java kafka spring";


Map<String,Integer> result = Arrays.stream(split(" ").collect(Collectors.groupingBy(Function.identity(),Collectors.counting());



String[] strs = {"flower", "flow", "flight"};

String s = Arrays.stream().reduce((s1,s2) -> {
      int i = 0
  while(i < s1.lenght() && i <s2.lenght() && s1.charAt(i) == s2.charAt(i))
{
 i++ ;
}
return s1.subString(0,i);
}); 

sout(s);

Approach 2: Using Loop

int[] arr1 = {1, 2, 3};
int[] arr2 = {4, 5, 6};

int[] merged = new int[arr1.length + arr2.length];

int index = 0;

for (int num : arr1) {
    merged[index++] = num;
}

for (int num : arr2) {
    merged[index++] = num;
}

System.out.println(Arrays.toString(merged));

Approach 3: Java 8 Streams
int[] arr1 = {1, 2, 3};
int[] arr2 = {4, 5, 6};

int[] merged = IntStream.concat(
                    Arrays.stream(arr1),
                    Arrays.stream(arr2))
                .toArray();

System.out.println(Arrays.toString(merged));

Output:

[1, 2, 3, 4, 5, 6]
````````````````````````````````````````````````````````````````````````````````````````````````
class Main {
    public static void main(String[] args) {
      
        
        String  s ="AbhishekPallll";  // h = 2
        // duplicat and and consonet and 
        
    Map<Character,Long> resul =s.toLowerCase().chars().mapToObj(c ->(char)c)
            .filter(Character::isLetter).filter(e -> "aeiou".indexOf(e) == -1)
            .collect(Collectors.groupingBy(Function.identity(),Collectors.counting()));
            
            resul.entrySet().stream().filter(e -> e.getValue() > 1).
            forEach(e -> System.out.print(e.getKey()+" "+e.getValue()));
            
    }

``````````````````````````````````````````````````````````````````````
Given a string, print each character along with:

Number of occurrences
Index positions where it appears
Type of character (Alphabet, Number, or Special Character)

Input:

String s = "abhsiketest2345@gmail.com";

Expected Output (Sample):

a 2 [0, 15] Character
b 1 [1] Character
h 1 [2] Character
2 1 [11] Number
@ 1 [14] Special Character
import java.util.*;
import java.util.stream.*;

public class Main {
    public static void main(String[] args) {

        String s = "abhsiketest2345@gmail.com";

        Map<Character, List<Integer>> map =
                IntStream.range(0, s.length())
                        .boxed()
                        .collect(Collectors.groupingBy(
                                i -> s.charAt(i),
                                LinkedHashMap::new,
                                Collectors.toList()));

        map.forEach((ch, indexes) -> {

            String type;

            if (Character.isLetter(ch))
                type = "Character";
            else if (Character.isDigit(ch))
                type = "Number";
            else
                type = "Special Character";

            System.out.println(
                    ch + " " +
                    indexes.size() + " " +
                    indexes + " " +
                    type);
        });
    }
}

import java.util.*;

public class Main {
    public static void main(String[] args) {

        String s = "abhsiketest2345@gmail.com";

        Map<Character, List<Integer>> map = new LinkedHashMap<>();

        for (int i = 0; i < s.length(); i++) {

            char ch = s.charAt(i);

            if (!map.containsKey(ch)) {
                map.put(ch, new ArrayList<>());
            }

            map.get(ch).add(i);
        }

        for (Map.Entry<Character, List<Integer>> entry : map.entrySet()) {

            char ch = entry.getKey();
            List<Integer> indexes = entry.getValue();

            String type;

            if (Character.isLetter(ch)) {
                type = "Character";
            } else if (Character.isDigit(ch)) {
                type = "Number";
            } else {
                type = "Special Character";
            }

            System.out.println(
                    ch + " " +
                    indexes.size() + " " +
                    indexes + " " +
                    type
            );
        }
    }
}

`````````````````````````````````````````````````````````````````````````````````````````````````````````````````
Solution 2 (Recommended for Interviews)

Using Set gives better performance.

import java.util.*;
import java.util.stream.*;

public class Main {
    public static void main(String[] args) {

        int[] arr1 = {1, 2, 3, 4, 5};
        int[] arr2 = {3, 4, 5, 6, 7};

        Set<Integer> set = Arrays.stream(arr2)
                                 .boxed()
                                 .collect(Collectors.toSet());

        Arrays.stream(arr1)
              .filter(set::contains)
              .forEach(System.out::println);
    }
}

Output:

3
4
5
````````````````````````````````````````````````````````````

int [][] a ={{1,1,1}, {2,2,2}};
        int [][] b = {{3,3},{2,2},{1,1}};
        
        
        if(a[0].length != b.length)
        {
            System.out.print("Multiplication not possible");
        }else
        {
           System.out.print("Multiplication possible");
        }
        
int result[][] = new int[a.length][b[0].length];

for(int i=0; i<a.length; i++)
{
    for(int j=0; j<b[0].length; j++)
    {
        for(int k=0 ; k<a[0].length ; k++)
        {
            result[i][j] += a[i][k] * b[k][j] ;
        }
    }
}

for(int i=0 ; i<result.length; i++)
{
    for(int j = 0;  j<result[0].length; j++)
    {
      System.out.print(result[i][j] + " ");
    }
    System.out.println();
}



