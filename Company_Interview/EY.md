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







