1. How do you optimize a Spring Boot application that takes 3 minutes to start?
2. How do you handle millions of records from another API?
3.How do you implement caching using Redis?
4. How do you secure REST APIs with JWT?
5. How do you implement rate limiting?
6. How do you achieve zero-downtime deployment?
7. How do you implement distributed transactions?
8. How do you troubleshoot memory leaks in Spring Boot?
9. How do you handle database connection pool exhaustion?
10. How do you improve API performance? 
11. how you will check hashaMap contians the same key if hash colition happen 
12. How to handle huge no of request is coming from the client side to yuor APi

Xorient - 
Client round - MasterCard
Cassandra - 

location entity -

id - 
name 
naid - BH19 
country - 

Optional<String> name =
Optional.ofNullable(null);
 
System.out.println(
name.orElse("Default"));  /

String s1 = "Java";
String s2 = "Java";
 
System.out.println(s1 == s2); //  java - s1,s2 


t1 t2 =

sleep(5000) ;

++ 


public class Test {
    public static void main(String[] args) {
        String value = getValue();  // Ac
        Optional<String> optional = Optional.ofNullable(value);// Acturl 
 
        System.out.println(optional.orElse(""));  //  optional.orElseGet(() -> getDefault());
    }
 
    static String getValue() {
        return "Actual";
    }
 
    static String getDefault() {
        System.out.println("Default method called");
        return "Default";
    }
}

Input:
s = "abcabcbb"  //
 
Output:
3

int n =s.length();
int maxlenght = 0;
int left = 0

set<Character> s1 = new hasSet<>();

for(int right = 0 ; right < n ; right++)
{
while(s1.contians(s.chartAt(right))
{
s.remove(s.charAt(left));
left++p;
}

s1.add(s.chatAt(right));
maxLenght  = Math.max(maxlength, right - left + 1);

}
retrun maxlenght;


LRUCache(int capacity)
 
int get(int key)
 
void put(int key, int value)


Input:
"swiss"    - 
 
Output:
'w'
``

chars().mapToOBj(c-> (Char)c).collect(Collectors.groupingBy(Funtion,identity() LinnkedHasmap::new 
, Collectores.counting())).entrySet().stream().filter(e -> e.getValue() == 1).findFirest().get();

`````````````````````````````````````````````````````````````````````````

Map<String,Long> d = new HasMap<>();

d.add("Abhishek", 1);  //
d.add(



 Map<String, Long> result = d.entrySet().stream().sorted(Map.Entry.comparingByValue())
collect(Collectors.toMap(Map.Entry::getKey,Map.Entry::getValue
(r1,r2) -> r1, LinkedHasMap::new)); 

sourt(result)

````````````````````````````````````````````````````````````````

Find Employees Joined in Last 30 Days

input list em;;

java 8

e.stream().filter(e -> e.getjoiningDate().isAfter(LocalDate.now()
.minsDay(30)).collect(Collectors.toList());

`````````````````````````````````````````````````````````

Table - emp
id - 1
name - Abhishek 
salary - 750000
mangerid - 2

id - 2
name - abhi
salary - 50000
mangerid - 4

print - em id and name em salary more then manger 

Select e.id, e.name 
From em e 
Join em m
on e.manger_id= m.id
where e.salary > m.salary;

```````````````````````````````````````````````````````````````````


  int sum =IntStream.rangeClosed(1, 10)
        .filter( n -> n%2 == 0).sum();
        
        System.out.println(sum);

````````````````````````````````````````````````````````
/*String s ="Committee"; // t   // C - 1 , m -2

        Map<Character,Long> D =s.chars().mapToObj(c -> (char)c)
                .collect(Collectors.groupingBy(Function.identity(), LinkedHashMap:: new,
                        Collectors.counting()));

        Character result =D.entrySet().stream().filter(e -> e.getValue() > 1).skip(1).map(Map.Entry::getKey).findFirst().orelse(null);

        System.out.println(result);*/

````````````````````````````````````````````````````````````````````````

list {"Mango","Apple","Banana","Mango","Apple"}

Gorup as per length and 

output Map<5,


Map<Interger,List<String>> r =
s.stream().collect(Collectors.groupingBy(String::length) // 
5 

s.stream().map(String::toLowercase).collect(Collectors
.groupingBy(Funtion.identity, Collectors.counting()))

s = "madam" -
s1 ="";
for(int i=0; i<s.length()

List<Integer> digits = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
        
        for (int digit : digits) {
            if (digit == 2) {
                digits.remove(Integer.valueOf(digit));
            }
        }

Employee e1 = new Employee(1, "John");
map. Put(e1,10);
e1.setName("Jane");
map.get(e1);




