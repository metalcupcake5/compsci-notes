## 8/16/21 - Intro to Java
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
System.out.println("He screamed, \"Oh no! A Zoom bomber!\""); // this
System.out.println("He screamed, "Oh no! A Zoom bomber!""); // not this
```
- To print a backslash, type it twice: `\\`
- `\n` inserts a newline(return character)
- `\t` inserts a tab
- not in AP Java Subset, may be tested in class