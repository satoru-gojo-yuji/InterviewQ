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







