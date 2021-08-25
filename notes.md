# 8/16/21
#### IDE: Integrated Development Environment
- An app, software program, website, where you can write/run a program
    - repl.it and BlueJ used in class
    - IDE is required to run a program, not needed to write the program
- Most important feature: compiler
    - Takes code from a programming language, translates into binary
#### the main method
- IDE starts with the main method in java
    - Executes code in the main method in order, one at a time
```java
public static void main(String[] args)
```
- In repl.it, main method must be placed in class called Main
    - not true for all of java

#### comments
- Single line: double slash `//`
- Multi-line: slash star `/* */`
- compiler ingores comments
- important if other people read your code; explain what you are doing

#### semicolons/whitespace
- Statements in java ends with semicolons
- Java does not care about whitespace
    - Many statements can be on one line
    - One statement can be several lines long
    - Any amount of whitespace is treated as the same thing
- Best practice is one statement per line

#### printing
- Cause a java program to display lines of text
- AP Java Subset expects
```java
System.out.print();
System.out.println();
```
- `println` inserts a return after the text, print does not

#### escape sequences
- When the argument you pass into a print method is exactly what you want to display, you put it in quotation marks; this is called a string literal
```java
System.out.println(“Hello World!”); // “Hello World!” Is the string literal
```
- If you are printing a string with quotation marks, escape them
    - Use `\` before quotation marks
```java
System.out.println("He screamed, \"Oh no! A Zoom bomber!\"");  // this
System.out.println("He screamed, "Oh no! A Zoom bomber!""); // not this
```
- To print a backslash, type it twice: `\\`
- `\n` inserts a newline(return character)
- `\t` inserts a tab
    - not in AP Java Subset, may be tested in class




# 8/18/21 - Variable
#### what's a variable?
- A memory slot that keeps track of data
- Value my be overwritten as needed

#### data types
- When creating a variable, __must__ specify type
- Type cannot be overwritten; assigning a different type of data to it will cause an error
    - Called static typing
- Eight simple "primitive data types" in java
    - AP Java subset: int, double, char
    - Not useful: byte, short, long, float

#### int
- an integer
- smallest: `-2^32`, largest: `2^32`
- Primitives byte, short, and long are alternate versions of int.
    - Long has a larger range of possible values
    - Short has a smaller range
    - Byte has the smallest range

#### double
- Represents a floating-point number; a number that is allowed to have a decimal component
- Float: alternate version of double that has a smaller range of possible values/less precision
- Imprecision can result when computer does arithmetic involving doubles

#### Boolean
- Represents one of two states: true or false
- Smallest data type in terms of memory allocation

#### char
- Represents a single lexicographical character(letter/number/symbol)
- Sometimes more convenient to use than strings, but string can do anything char can
    - will not be tested, not in AP Java subset

#### data types
- Eight simple “primitive data types” in Java
- All other data types are classes
    - Technically called reference types
- Some classes are built-in to java+available by default
- Many classes are built-in and available by importing
- Java allows you to make your own classes

#### string
- Most important built-in class in java
- The String is the type that can store a string literal

#### identifiers
- Any part of a program the programmer gives a name to
- May only contain letters, numbers, underscores, dollar signs
    - may not begin with a number
- May not match reserved words like int, static, class
- Important conventions for how to capitalize identifiers depending on what they identify

| Type of Identifier | Capitalization | Single-word Example |
| ------------------ | -------------- | ------------------- |
| variables/methods  | camelCase      | count               |
| classes            | UpperCamelCase | String              |
| ???                | ALL_CAPS       | PI                  |

#### declaring and initializing
- Creating a new variable is called a declaration
- You must specify data type when declaring a variable
```java
int count;
```
- Giving a variable a value is called assignment
    - Assigning a value for the first time is initializing
```java
count = 1;
```
- You are allowed to initialize a variable in the same line that you use to declare it
```java
int count = 1;
```

#### common errors
- Must declare a variable(specify its data type) before it can be used
- Must not re-declare a variable(by specifying its data type a second time)




# 8/20/21 - Arithmetic
#### copying variable values
- The contents of a variable can also be assign to a variable
```java
int x = 5;
int y = x; // x is now 5
```
- When it is done with primitive data types, the value of x is copied into y
- You can assign the result of an expression to a variable

#### meth
- `+` for addition
- `-` for subtraction
- `*` for multiplication
- `/` for division
- `%` for modulus
- addition/subtraction/multiplication work in the way you’d expect
- With doubles, division works the way you would expect
- PEMDAS is in full effect

#### dividing ints
- When dividing ints, decimals in the quotient are discarded
- The modulus operation (%) find the remainder of the division expression
```java
int y = 20 % 3; // y is 2; 20/3 has a remainder of 2
double x = 3 / 2; // x is 1; 3 and 2 are integers so it is still int division
double z = 3.0 / 2; // zy is 1.5; you must have at least one floating point value to do proper division
```

#### widening
- If arithmetic involves a combination of ints/doubles, or result of int operation is assigned to a double, the final result is a double
- Named widening

#### casting
- The opposite of widening is not true
- If you need to assign a double to an int, you must cast it
```java
int z = (int) (3.0 / 2.0);
```
- When a double is cast to an int the decimal is truncated
    - Only the part before the decimal point is kept



# 8/24/21 - Printing Primitives and String Concatenation
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



# 8/24/21 - Errors
## run time vs compile-time

#### compile-time vs run-time errors
- compile-time
    - we classify errors depending on when they become apparent: when the code compiles, or when the code runs
    - compile-time errors are caught by the compiler before the program runs. the compiler is onlyr eally able to detect errors that are the result of you typing something that doesn't make sense in Java, so we also call these syntax errors
- run-time errors
    - run-time errors are caught when the program runs. since the compiler has already caught syntax errors by then, the only possible errors are caused by writing a program that doesn't make sense, so these are also called logic errors
    - very serious run-time errors cause the program to crash and terminate with an Exception. Most run-time errors just make the program do something different from what you intended.
        - bugs!