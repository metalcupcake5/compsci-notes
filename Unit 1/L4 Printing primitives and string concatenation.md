## 8/24/21 - Printing Primitives and String Concatenation
#### using print statements in new ways
- Apart from string literals, print statements can also display other data types
```java
System.out.println(5); // prints 5
```
- Can also display the value of a variable
```java
System.out.println(x); // prints x, whether its a primitive or a STring
```
- You can make the compiler evalue a mathmatical expression and print the result
```java
System.out.println(x*y);
```

#### string concatenation
- A primitive that gets concatenated to a String becomes part of the String
```java
String boast = "I'm #" + 5 % 4;
```
- The easiest way to convert an int to a String is to concatenate it to an empty String
```java
int count = 1;
String stringyCount = "" + count; // result is "1"
```

#### printing a combination of strings/number values
```java
int currentHP = 10;
int maxHP = 20;
System.out.print(“HP: “ + currentHP + “/” + maxHP); // prints "HP 10/20"
```

#### priority of concatenation
- string concatenation has the same priority as numerical addition
```java
String string = 1 + 4 + "banana" + 3 + 2;
// string is "5banana32"
```