Unit 1
======

## 8/16/21
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




## 8/18/21 - Variable
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




## 8/20/21 - Arithmetic
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




## 8/24/21 - Errors
### run time vs compile-time

#### compile-time vs run-time errors
- compile-time
    - we classify errors depending on when they become apparent: when the code compiles, or when the code runs
    - compile-time errors are caught by the compiler before the program runs. the compiler is onlyr eally able to detect errors that are the result of you typing something that doesn't make sense in Java, so we also call these syntax errors
- run-time errors
    - run-time errors are caught when the program runs. since the compiler has already caught syntax errors by then, the only possible errors are caused by writing a program that doesn't make sense, so these are also called logic errors
    - very serious run-time errors cause the program to crash and terminate with an Exception. Most run-time errors just make the program do something different from what you intended.
        - bugs!




## 8/26/21 - Updating the values of variables
#### updating a variable
- assuming that x and y have been initialized, the following lines of code are all valid
```java
x = 5 + 7;
x = 7*y;
x = x + 2;
```
- if the last one confuses you, realize that the computer evaluates the right side of the equation and stores the result in the variable on the left. the new value of x is the old value of x plus 2. We're just increasing x by 2

#### shortcut assignment operators
- when an arithmetic operator is combined with `=`, it's a shortcut to update x by the amount on the right hand side

| the shortcut | means the same thing as |
| ------------ | ----------------------- |
| `x += y;`    | `x = x + y`             |
| `x -= y;`    | `x = x - y`             |
| `x *= y;`    | `x = x * y`             |
| `x /= y;`    | `x = x / y`             |
| `x %= y;`    | `x = x % y`             |
- these are helpful when you understand the logic behind them
```java
x -= 2; //decrease x by 2
x *= 3; //triple the value of x
x += y; //increase x by y
```

#### even shorter shortcuts
##### because programmers are lazy
- increasing or decreasing the value of a variable by 1 happens to be so helpful, it has its own shortcut.
```java
x++; //increment x by 1
x--; //decrement x by 1
```
- __IMPORTANT__: only use the shortcut as its own line of code, not inside a print statement




## 8/26/21 - Overflow, underflow, and floating-point imprecision
### the real reason there aren't any level 1 Pokemon and Red and Blue

#### an int in memory
- the designers of Java allocated 32 bits of memory to each `int`: an `int` can represent 2^32 different numbers
- half of them were used to represent negative numbers, half of them for positive

#### overflow and underflow
- if an int holding the maximum value of 2147483647 is increased by one, its value "wraps around" to the minimum value of -2147483647. this is called __overflow__

#### glitches from overflow and underflow
- many video games in the 1990s had glitches caused by overflow and underflow, before programmers became better at guarding against it

#### floating-point imprecision
- any arithmetic involving doubles may result in a slight rounding error




Unit 2
======

## 8/30/21 - Objects, methods, and the `String` class
### references, instantiation, and return types

#### what's an object?
- we know that to create a variable, we msut declare it by specifying its data type
- for primitives, assigning a value is very simple, and we have been practicing how to do it
```java
int x = 7;
double y = y.;
boolean isBreathing = true;
```
- a class-type variable has much more information to remember than a primitive. (compare data in `Ellipse` to `int`)
- we dont need to only create the variable, by declaring it-we also have to create the data, by instantiating it
- data is called an object. a class-type variable holds a reference to an object
```java
Square wall = new Square();
```

#### instantiating objects
- use the `new` keyword to instantiate an object, followed by the class name and a pair of parentheses
```java
Square wall = new Square();
```
- __Strings are an exception.__ Can be created like primitives - this is a shortcut to make them easier to use. You may also instantiate them formally like other objects
    - following lines are equivalent
```java
String greeting = "Hello";
String greeting = new String("Hello");
```

#### what's a method?
- an important feature of objects that is *not* true about primitives is: we can call methods on objects
- a __method__ is a subroutine of code; a sequence of statements in Java
- *usually* a method calculates a value and __returns__ it. The data type of the value it returns in the method's __return type__
- we call a method using __dot notation__ on a variable with a reference to the object
```java
greeting.length()
```

#### String methods: `length()`
##### `length(int)`
- return type: `int`
- the `length()` method computes and returns the number of characters in the String
```java
String greeting = "Hello";
greeting.length(); // returns 5
```

#### using return values
- when a method calculates a value, it returns it, and the return value can be used just like any other raw/calculated value
```java
String greeting = "Hello";
int x = 2 + 3; // x is now 5
int y = greeting.length(); // y is now 5

System.out.println(x); // prints 5
System.out.println(greeting.length()); // prints 5
```

#### parameters and arguments
- some methods have __parameters__, which are data types it asks for inside its parentheses
- when you call a method, the value you place inside the parentheses to satisfy the paremter is called an __argument__
- anything you've put into a print statement is an argument
```java
System.out.println(x); // x is the argument
```

#### String methods: `indexOf()`
##### `indexOf(String)`
- parameter: `String`
- return type: `int`
- the `indexOf()` method accepts a String as an argument and returns the location of the argument inside the String.
```java
String command = "Attack!";
                //0123456

command.indexOf("A");    // returns 0
command.indexOf("k");    // returns 5
command.indexOf("tack"); // returns 2
```
- the method will return the first occurrence if there are multiple
- the method will return `-1` if the argument is not found
```java
String command = "Attack!";
                //0123456

command.indexOf("t");   // returns 1, not 2
command.indexOf("g");   // returns -1; not found
```




## Method overloading and more String methods

#### method overloading
- two different methods from the same class can have the same identifier as long as their parameter lsits are different
    - generally they shouldn't be totally different methods; if they have the same name, they should do similar things. But in theory, they could be
- called __method overloading__

#### String methods: `substring()`(version 1)
##### `substring(int)`
- parameter: `int`
- return type: `String`
- the `substring()` method returns a copy of the String starting from the index specified by the argument
```java
String command = "Attack!";
                //0123456

command.substring(2);   // returns "tack!"
command.substring(6);   // returns "!"
command.substring(0);   // returns the whole String ("Attack!")
```
- if the argument is equal to its length, the method returns the empty string
- if the argument is greater than its length or less than 0, the method crashes with a `StringIndexOutOfBoundsException`
    - runtime error
```java
String command = "Attack!";
                //0123456

command.substring(7);   // returns ""
command.substring(10);  // ERROR
command.substring(-1);  // ERROR
```

#### String methods: `substring()`(version 2)
##### `substring(int, int)`
- parameters: `int`, `int`
- return type: `String`
- the two parameter `substring()` method returns a copy of the String starting from the index specified by the first arugment (inclusive) and ending at the index specified by the second argument (exclusive)
```java
"Attack!".substring(2,6);   // returns "tack"
            // the character at 2, "t", is included
            // the character at 6, "!", is excluded
```
- notice that the length of the returned String is equal to the difference of the arugments (6 - 2 = 4, `tack` has 4 letters)

#### String methods: `toUpperCase()`
##### `toUpperCase()`
- parameters: none
- return type: `String`
- returns a version of the String with all alphabetic characters converted to uppercase
```java
String catThoughts = "Must attack shoelace!";

catThoughts.toUpperCase();
// returns "MUST ATTACK SHOELACE!"
```

#### String methods: `toLowerCase()`
##### `toLowerCase()`
- parameters: none
- return type: `String`
- returns a version of the String with all alphabetic characters converted to lowercase
```java
"sTOp YElling aT ME".toLowerCase();
// returns "stop yelling at me"
```

#### common misconception
- `.toUpperCase()` and `.toLowerCase()` __do not alter the original String__! They only return a *copy* with certain properties applied
```java
String catThoughts = "Must attack shoelace!";
STring aggressiveCatThoughts = catThoughts.toUpperCase();
/* aggressiveCatThoughts now contains the all caps version, but catThoughts has not changed */
```
- the String class does not contain any methods that alter the original String(other classes do). Because of this, we say that Strings are __immutable__
- you can replace a String with a different one, but calling a method on a String does not itself change the original
```java
greeting = greeting.toUpperCase();
// greeting is replaced by its all caps version
```




## `static` methods and the Main class
### `.abs()`, `.sqrt()`, `.pow()`, `.min()`, `.max()`


#### `static` methods
- we know that we can call methods on an object... as long as they are not `static` methods
- for `static` methods, we can still call them using dot notation, but we call them on a *class* instead of on an object
```java
Math.abs(-1);
```

#### the `Math` class
- a built-in class that is full of useful `static` methods and we don't have to instantiate a `Math` object to be able to use them
    - (in fact, the class was designed so that you can't instantiate it)

#### Math methods: `abs()` (version 1)
##### `abs(int)`
- parameter: `int`
- return type: `int`
- returns the absolute value of the argument
```java
Math.abs(1);  // returns 1
Math.abs(0);  // returns 0
Math.abs(-1); // returns 1
```

#### Math methods: `abs()` (version 2)
##### `abs(double)`
- parameter: `double`
- return type: `double`
- returns the absolute value of the argument
```java
Math.abs(1.0);  // returns 1.0
Math.abs(0.0);  // returns 0.0
Math.abs(-1.0); // returns 1.0
```

#### Math methods: `sqrt()`
##### `sqrt(double)`
- parameter: `double`
- return type: `double`
- returns the square root of the argument
    - while the method always returns a `double`, you can use an `int` as the parameter because of widening
```java
Math.sqrt(9.0); // returns 3.0
Math.sqrt(9);   // returns 3.0
```
*there is a `cbrt()` too, but it is not part of ap java subset*

#### Math methods: `pow()`
##### `pow(double, double)`
- parameters: `double`, `double`
- return type: `double`
- returns the first argumetn raised to the power of the second argument
    - because it converts everything to a `double`, it is common to simply multiply something by itself in order to square it, etc
```java
Math.pow(3,2); // returns 9.0 (3^2)
Math.pow(2,5); // returns 32.0 (2^5)
```

#### Math methods: `min()`
##### `min(int, int/double, double)`
- parameters: `int`, `int` or `double`, `double`
- return type: `int` or `double`
- returns the smaller argument
```java
Math.min(4.0, 16.0); // returns 4.0
Math.min(-75, -45);  // returns -75
```

#### Math methods: `max()`
##### `max(int, int/double, double)`
- parameters: `int`, `int` or `double`, `double`
- return type: `int` or `double`
- returns the larger argument
```java
Math.max(4.0, 16.0); // returns 16.0
Math.max(-75, -45);  // returns -45
```



## learning to write methods!
### switching from the User hat to the Designer hat

#### hats
- programmers have to keep two different perspectives in mind when they write code. these two perspectives are like wearing two different hats: the "user" hat and the "designer" hat

#### thinking of code as the user
- so far, we've only worn the User hat
- to __use__ a class, generally speaking, we instantiate an object of that class
```java
Square wall = new Square();
```
- to __use__ a method, we call the method on an object(or on its class if it is a `static` method)
```java
wall.changeColor("gray");
```

#### thinking of code as the designer
- wehn we design a class or method, we have to keep in mind how they will be used
- we write classes thinking about how they will function as objects
- when we write methods, we need to think about what arguments we need to ask for from the user, and how to compute the return value correctly

#### structure of writing a method
- this is a very simple method that takes an int as an argument and returns twice its value
- methods have two parts: a __header__ and a __body__. The header and body together form the __definition__ of the method
```java
public static int doubleValue(int input)//header
{                       // 
    return 2 * input;   //  body
}                       // 
```

#### the body
- the body of a mehod is where the "code" goes (where the Java statements that end in semicolons go)
- when a method is called, the computer stops whatever it was doing and executes the lines of code in the body of that method one by one
```java
public static int doubleValue(int input)
{                       // 
    return 2 * input;   //  body
}                       // 
```

#### return statements
- if a method is supposed to return a value, it must end with a __return statement__ ( or else you'll get a compile-time error).
- a return statement consists of the reserved word `return` and then the value you're returning
```java
return 2 * input;
```
- you can return any expression, including
    - raw values(`return 1`)
    - mathematical expressions(`return 3 - 2;`)
    - the value of a variable(` return x;`)
    - the return value of another method call(`return "H".length()`)

#### method headers
- 5 parts:
    1. access modifier
    2. static / non-static
    3. return type
    4. method name (identifier)
    5. parameter list
```java
public static int doubleValue(int input)
// ^1  ^2     ^3  ^4           ^5
```

#### method headers: access modifiers
- the only __access modifier__ we know so far is `public`
- you need to include it, dont worry about what it does yet
```java
public static int doubleValue(int input)
// ^
```

#### method headers: `static`
- if a method isn't `static`, nothing goes here
- we will start off writing `static` methods first because they are simpler
```java
public static int doubleValue(int input)
//     ^
```

#### method headers: return type
- indicates what the data type of the method's return value will be
- if a method does not return a value, it uses the special return type `void` to indicate this
```java
public static int doubleValue(int input)
//            ^
```

#### method headers: name
- by convention, we use camelCase just like with variables
```java
public static int doubleValue(int input)
//                ^
```

#### method headers: parameter lsit
- in parentheses, the __parameter list__ has a list of variable declarations separated by commas. These varaibles are called __parameter variables__
- the data types of the parameters variables match the data types of the arguments that are expected to be used to satisfy the parameters
```java
public static int doubleValue(int input)
//                             ^
```
- using `Math.pow()` as an example
```java
Math.pow(3.0, 4.0); 
// calling the method, as a user

public static double pow(double base, double exponent)
// what the method header would look like, if we could see it
```
- the parameter variables are initialized to the arguments that are passed in. they can then be used in the body of the method
    - in this case, base is initialized to 3.0, and exponent is initialized to 4.0

#### writing multiple methods in a class
- in a class that has a main method, there can be other methods, too

#### calling methods
- normally, we call methods with dot notation, either on a variable holding a reference to an object (non-static methods) or on the class name (static methods)
- however, if you call a method that is written in the same class you are already in, you don't need dot notation! Simply use `methodName()`
- you can use your main method to test out the other methods you've written




## `Math.random()`

#### Math methods: `random()`
##### `Math.random()`
- parameters: none
- return type: `double`
- returns a psuedorandomly generated `double` between the values of 0.0, inclusive, and 1.0, exclusive
```java
Math.random();
```

#### does this seem helpful?
- it seems significantly more helpful to return an `int` within a range than to return a `double` in the range [0.0, 1.0)
- how can we use the output of Math.random() to select a whole number within a range?

#### randomly generating an integer
```java
(int) (Math.random() * 7);
```
- multiplying the range [0.0, 1.0) by 7 results in the range [0.0, 7.0). When this is cast to an int, because of how truncation works, the result will be between 0 and 6(inclusive)
    - *notice how 7 is the number we multiplied by, and there are seven possible results*
- find a random number between 4 and 10
```java
(int) (Math.random() * 7) + 4;
```
- add 4 to the result of the previous example, so the outcomes are between 4 and 10 (inclusive)
- formula to generate an `int` within a range
# important
```java
(int) (Math.random() * numberOfPossibilities) + minimumValue;
```





## Learning to write classes
### blocks, scope, instances, atributes, fields, constructors

#### code blocks and variable scope
- the code that is enclosed in a set of `{ }` curly braces is called a block of code
- the body of a class, as well as the body of a method, form blocks of code.
```java
public class Blah {
    // a block
}

public static void main(String[] args){
    // also a block
}
```

- a variable may only be used within the block of code in which it is declared. This is called the variable's __scope__
    - the scope of a parameter variable is the method it is a parameter for
- when the code block ends, the variable is __out of scope__ and cannot be accessed, and its name can be reused for a different variable

#### writing classes
- review: we can write a class in order to use it as the data type of a variable. We do this when we instantiate an object of the class(also called an instance of the class) and store a reference to the object in the variable
```java
Circle sun = new Circle();
```
- we write classes to represent concepts
- an object can remember more information than a primitive
    - Circle class from IntroPicture project remembers its size, color, transparency, position

#### parts of a class
- the body of a class that is meant to be instantiated has 3 main parts
    - __instance variables__
    - __constructors__
    - __methods__
- all three must have access modifiers attached to them

#### instance variables
- also called __fields__ or __attributes__
- instance variables represent the data that an object stores in its memory. They are declared(not initialized) at the start of a class body
- the usual access modifier for instance variables is `private`
```java
public class NumberLinePoint {
    private int position;
    private String lable;
}
```

#### constructors
- constructors look very similar to methods but they __do not have a return type__ (not even void) and their identifier is the same as the class name. They are nearly always `public`
- their job is to initialize the instance variables. Often, they use parameter variables to do this.
```java
public NumberLinePoint(int p, String l) {
    position = p;
    label = l;
}
```
- parameter variables of a constructor can have the same name of the instance variables
- in these cases, the `this` keyword is used to disambiguate. `this` always to the object, so `this.variableName` refers to the instance variable

#### methods
- the default access modifier is public, but exceptions are more common than with instance variables
- think from the perspective of someone using your object. Methods are how they can actually do stuff with your object
- a __local variable__ declared inside a method cannot be used in another method, but instance variables may be used in any method in the class
- it is very common to write a getter method and a setter method for each instance variable in your class
- a __getter method__ returns the instance variable. This is how the person using your object can access the variable
    - formally known as accessor methods
```java
public String getLabel() {
    return label;
}
```
- a __setter method__ assigns a new value to the instance variable. This is how the person using your object can modify the variable.
    - formally known as mutator methods
```java
public void setLabel(String l) {
    label = l;
}
```



## a note about `static`

#### what does `static` actually mean?
- `static` means that a property(field or method) of a class belongs to the class, not the objects of that class
    - non-static example: `length()` method returns length of a String object, this method belongs to objects of the String class
    - static example: `sqrt()` method computes a square root, doesn't need an object, this method belongs to the Math class itself

#### `static` methods
- when deciding whether to make a method `static` or not, askk if you need to use any instance variables in the method. Instance variables belong to the object, so they cannot be used inside `static` methods
    - also simply ask if it makes more sense to ask an instance of the class to performt he method, or if it makes more sense to ask the class itself