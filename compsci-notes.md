Unit 1
======





## 8/26/21 - Overflow, underflow, and floating-point imprecision
### the real reason there aren't any level 1 Pokemon and Red and Blue
#### an int in memory
- the designers of Java allocated 32 bits of memory to each `int`: an `int` can represent 2^32 different numbers
- half of them were used to represent negative numbers, half of them for positive


#### overflow and underflow
- if an int holding the maximum value of 2147483647 is increased by one, its value "wraps around" to the minimum value of -2147483647. this is called **overflow**


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
- we dont need to only create the variable, by declaring it - we also have to create the data, by instantiating it
- data is called an object. a class-type variable holds a reference to an object
```java
Square wall = new Square();
```
#### instantiating objects
- use the `new` keyword to instantiate an object, followed by the class name and a pair of parentheses
```java
Square wall = new Square();
```
- **Strings are an exception.** Can be created like primitives - this is a shortcut to make them easier to use. You may also instantiate them formally like other objects
 - following lines are equivalent
```java
String greeting = "Hello";
String greeting = new String("Hello");
```

#### what's a method?
- an important feature of objects that is *not* true about primitives is: we can call methods objects
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
- some methods have __parameters__, which are types it asks for inside its parentheses
- when you call a method, the value you place inside the parentheses to satisfy the paremter is an __argument__
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

command.indexOf("A"); // returns 0
command.indexOf("k"); // returns 5
command.indexOf("tack"); // returns 2
```
- the method will return the first occurrence if there are multiple
- the method will return `-1` if the argument is not found
```java
String command = "Attack!";
				//0123456

command.indexOf("t"); // returns 1, not 2
command.indexOf("g"); // returns -1; not found
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

command.substring(2); // returns "tack!"
command.substring(6); // returns "!"
command.substring(0); // returns the whole String ("Attack!")
```
- if the argument is equal to its length, the method returns the empty string
- if the argument is greater than its length or less than 0, the method crashes with a `StringIndexOutOfBoundsException`
 - runtime error
```java
String command = "Attack!";
				//0123456

command.substring(7); // returns ""
command.substring(10); // ERROR
command.substring(-1); // ERROR
```
#### String methods: `substring()`(version 2)
##### `substring(int, int)`
- parameters: `int`, `int`
- return type: `String`
- the two parameter `substring()` method returns a copy of the String starting from the index specified by the first arugment (inclusive) and ending at the index specified by the second argument (exclusive)
```java
"Attack!".substring(2,6); // returns "tack"
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
String aggressiveCatThoughts = catThoughts.toUpperCase();
/* aggressiveCatThoughts now contains the all caps version, but catThoughts has not changed */
```
- the String class does not contain any methods that alter the original String(other classes do).  Because of this, we say that Strings are __immutable__
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
Math.abs(1); // returns 1
Math.abs(0); // returns 0
Math.abs(-1); // returns 1
```

#### Math methods: `abs()` (version 2)
##### `abs(double)`
- parameter: `double`
- return type: `double`
- returns the absolute value of the argument
```java
Math.abs(1.0); // returns 1.0
Math.abs(0.0); // returns 0.0
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
Math.sqrt(9); // returns 3.0
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
Math.min(-75, -45); // returns -75
```

#### Math methods: `max()`
##### `max(int, int/double, double)`
- parameters: `int`, `int` or `double`, `double`
- return type: `int` or `double`
- returns the larger argument
```java
Math.max(4.0, 16.0); // returns 16.0
Math.max(-75, -45); // returns -45
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
- when we design a class or method, we have to keep in mind how they will be used
- we write classes thinking about how they will function as objects
- when we write methods, we need to think about what arguments we need to ask for from the user, and how to compute the return value correctly


#### structure of writing a method
- this is a very simple method that takes an int as an argument and returns twice its value
- methods have two parts: a __header__ and a __body__. The header and body together form the __definition__ of the method
```java
public static int doubleValue(int input)//header
{ // 
 return 2 * input; //  body
} // 
```

#### the body
- the body of a mehod is where the "code" goes (where the Java statements that end in semicolons go)
- when a method is called, the computer stops whatever it was doing and executes the lines of code in the body of that method one by one
```java
public static int doubleValue(int input)
{ // 
 return 2 * input; //  body
} // 
```

#### return statements
- if a method is supposed to return a value, it must end with a __return statement__ (or else you'll get a compile-time error).
- a return statement consists of the reserved word `return` and then the  you're returning
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
	3. 1. return type
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
- it seems significantly more helpful to return an `int` within a range than to return a `double` in the range\[0.0, 1.0)
- how can we use the output of Math.random() to select a whole number within a range?


#### randomly generating an integer
```java
(int) (Math.random() * 7);
```
- multiplying the range \[0.0, 1.0) by 7 results in the range \[0.0, 7.0). When this is cast to an int, because of how truncation works, the result will be between 0 and 6(inclusive)
 - *notice how 7 is the number we multiplied by, and there are seven possible results*
- find a random number between 4 and 10
```java
(int) (Math.random() * 7) + 4;
```
- add 4 to the result of the previous example, so the outcomes are 4 and 10 (inclusive)
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
- a variable may only be used within the block of code in which it declared. This is called the variable's __scope__
 - the scope of a parameter variable is the method it is a parameter for
- when the code block ends, the variable is __out of scope__ and cannot be, and its name can be reused for a different variable
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
- a __local variable__ declared inside a method cannot be used in another method, but variables may be used in any method in the class
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
- when deciding whether to make a method `static` or not, ask if you need to use any instance variables in the method. Instance variables belong to the object, so they cannot be used inside `static` methods
 - also simply ask if it makes more sense to ask an instance of the class to perform the method, or if it makes more sense to ask the class itself


## Memory management
#### managing data
- objects contain substantially more data than primitives. As a result, the computer manages them in its memory more conservatively
```java
int x = 3;
Puppy myDog = new Puppy("Floof", 4, false, true, 78);
```
- variables for primitives "hold" a value, but variables for objects hold a __reference__ to their object
#### memory for primitives
- for primitives, the computer just has to remember the data type, variable name, and value


#### memory for objects
- when an object is instantiated with the `new` keyword, the object is constructed in memory
- its variable, however, remembers only one thing: where to find the object in the memoryspace. This location is called a __reference__
- we sometimes say the variable "points to" or "refers to" the object
- if a reference-type(class-type) variable is used as the right hand side of an assignment, the object is NOT duplicated(would take too long to copy so much data!). Instead, the reference is copied, so we have two variables that refer to the same object
- if you see the `new` keyword, you make a new object, so the reference changes
- __important. the ap exam will try to trick you on this__
- analogy: the object is like a TV and the references are like TV remotes
 - we interact with the object via its references - we interact with a TV using its remote
 - we can have several references to the same object - we can sync multiple remotes to the same TV


#### automatic garbage collection
- one facet of Java that makes it an easier language to learn for beginners than certain other languages is that Java has __automatic garbabe collection_
- if all of the variables that refer to an object go out of scope(or are reassigned to a different reference), then Java automatically deletes the object for its memory


Unit 3
=====
## Conditional Statements
#### what's a conditional statement?
- conditional statements allow us a much greater level of control of our programs: certain lines of code are executed only if particular conditions are met


#### `if` statements
```java
if (    ) // condition of the if statement
{
	 // these lines of code only execute if the condition is true
	 // body of the if statement
}
```

- note that
- there is no semicolon after the condition
- the body of an if statement is a code block inside the method. Variables declared inside it go out of scope when the `if` statement's body ends


#### the condition
- the condition that goes inside the parentheses should be a boolean expression
```java
boolean isHungry = true;
if(isHungry){
	 // om nom nom
}
```

#### the condition
- like with number expressions, a boolean expression could be
- a raw value
```java
if(true) // will always exexcute
```
- a `boolean` variable

```java
if(hasWings)
```
- an expression that evaluates to a `boolean`
```java
if (x < 3)
```
- a method that returns a `boolean`
```java
if (str1.equals(str2))
```

#### boolean expressions
- just like `-` and `%` indicate math expression operations, there are operators like `<` and `!=`(does not equal) for boolean expressions that evaluate to `boolean`s

| operator | meaning                  |
| -------- | ------------------------ |
| <        | less than                |
| <=       | less than or equal to    |
| >        | greater than             |
| >=       | greater than or equal to |
| ==       | equals                   |
| !=       | does not equal           |

#### example
```java
if (x < 3){
	 // this code will be executed
	 // if x is less than 3, otherwise
	 // the comipiler just skips this block
}
```

#### CAUTION DANGER WARNING
- in computer science, `=` is the assignment operator, `==` is our comparison operator to check for equality
- `x = y;` takes the value of `y` and copies it into `x`
- `x == y` evaluates to `true` if `x` and `y` are equal and to `false` if not
- the compiler might not give you a compile-time error if you mix them up


#### `else`
- what if, when the condition evalues to `false`, we don't want it to simply skip the `if` block, we want it to do something else?
- we can use an `else` block!
```java
if (x >= 5){
	 // execute if x is greater than or equal to 5
} else {
	 //executes if x is less than 5
}
```

#### `else if`
- use an `else if` if you need more than 2 cases to check for
```java
if (x > 0) {
	 System.out.print("I'm positive");
} else if (x < 0) {
	 System.out.print("I'm negative");
} else {
	 System.out.print("I'm zero");
}
```

#### common error
- for non-void methods, the compiler checks to make sure you always return something
- for the example below, the compiler thinks "What if all three conditions are `false`?
```java
if (x > 0) {
	 return "positive";
} else if (x < 0) {
	 return "negative";
} else if (x == 0) {
	 return "zero";
}
```

## Compound equations and boolean algebra
#### boolean algebra
- the study of formal logic outcomes with TRUE and FALSE
#### binary and unary operators
- operators are classified as __binary__ if they operate on two values and __unary__ if they operate on one
- binary operators: +, *, %, <, ==
- casting is a unary operator; it only affects the value directly after it


#### the NOT operator: `!`
- the `!` operator is a unary operator that means NOT. It flips the truth value of the boolean after it
```java
if(!true) // same as false; will never execute
if(!(x < 4)) // if x is not less than 4
if(!canFly) // if canFly is false
if(!str1.equals(str2)) // if str1 doesn't equal str2
```
- usually programmers write if statements like this
```java
if(canFly) // rather than if(canFly == true)
if(!canFly) // rather than if(canFly == false)
```

#### compound conditions
- what if we wanted to check two conditions and execute an `if` block only if both of them are true? Or if at least one of them is?


#### OR operator: `||`
- the OR operator is a double pipe(Shift + \\)
- a binary oeprator that makes two boolean expressions evalue to `true` as long as one of them is `true`
```java
if (0 < 5 || 4 > 9)
{
	 // this code will run
}
```

#### AND operator: `&&`
- the AND operator is a double ampersand(Shift + 7)
- a binary operator that makes two boolean expressions evaluate to `true` only if both of them are `true`
```java
if (0 < 5 && 4 > 9)
{
	 // this code will not run
}
```

#### short-circuiting
- in some situations with compound conditionals, the computer doesn't even need to check the second condition to decide what the outcome will be
- with an `&&` statement, if the first condition is `false`, the conditional will be `false` regardless of the second condition
- with an `||` statement, if the first condition is `true`, the conditional will be `true` regardless of hte second condition
- in these cases the computer genuinely doesn't check the second condition. This is called __short-circuiting__
- we can use short-circuiting to do a safety check to make sure our program doesn't crash
```java
if(x / y > 4) // what if y is 0?
if(y != 0 && x / y > 4)
```
- in the second version, if y is 0, the conditional short-circuits to `false` and division is not performed


## `null` and object equality
### `.equals()` and the weirdness of the magic String constructor
#### `null`
- normally, reference-type variables hold references; that is, they hold a memory location for an object
- but what if we declare a variable without initializing it?

- the practical answer is "it doesn't really matter" because if you try to access the value in a variable that hasn't been initalized, you wil get a compile-time error

- technically, the answer is it is `null`(sometimes called a null reference)

- `null` means a variable does not refer to an object/does not hold a memory location.

- you can assign the value `null` to a variable on purpose if you want to

```java

Kitten ghostKitty = null;

```

- this can be a bit dangerous - if you call a method on a `null` variable, you will get a `NullPointerException` run-time error

  

#### checking for equality: primitives vs objects

- the == operator checks for equality. __However it only works as intended for primitives__

- when == is used on reference-type variables, it checks whether their reference are the same, not whether their objects are the same

- we need to use `.equals()` to check if the objects are the same


#### String methods: `equals()`

##### `equals(String)`

- parameter: `String`

- return type: `boolean`

- the `equals()` method determines if `this` String is identical to the argument(contains the same character sequence) and returns `true` if so, `false` if not (it is case sensitive)

#### checking for equality
- almost all classes pre-built in Java have a `.equals()` method(but the only one in the AP Java Subset is the String one)
- the exception is when checking if a String variable contains `null` - using `.equals()` will crash the program(because you cannot call a method on a null reference)
- in this case you _do_ in fact want to use `==` or `!=` (because you are actually checking if the __reference__ is `null` )

#### another annoying thing about Strings
- we usually instantiated Strings using a shortcut constructor instead of the normal, formal one that uses the `new` keyword
```java
String str1 = "Hello";
String str1 = new String("Hello");
```
- the shortcut constructor that lacks the new keyword actually does not always create a new object. If there is an existing object that is identical, it assigns a reference to the existing object instead of creating a new one.
- Remember, if you see the new keyword, a new object is being created with its own unique reference. Always.


## Order of Operations and DeMorgan's Laws

#### what happens
- if you use boolean expressions like these?
```java
!x < 4
7 == 4 + x
```

#### complete order of operations
| operation                            | operators            |
|--------------------------------------|----------------------|
| parentheses                          | ()                   |
| all unary oeprators                  | !, casting           |
| multiplication, division, modulus    | \*, /, %             |
| addition, subtraction, concatenation | +, -                 |
| all relational operators             | >, <, >=,<=, \==, != |
| AND                                  | &&                   |
| OR                                   | \|\|                   |
| Assignment                           | =                    |

#### what happens
- assume `x` is an `int` variable whose value is `3`. What will this expression evalue to?
```java
!x < 4
```
- __compile time error__ (bad operand type). `!` is evaluated before the `<`, but `!` cannot operate on `int` variables. `!` only works on `boolean`s

```java
7 == 4 + x
```

- `true`. the `+` operator is evaluated before the `==` operator, computer compares the sum of the right to `7`

- lets say we have a compound boolean expression with more than two conditions
```java
if(breathesFire && isAngry || isHungry && isCarnivorous)
```
is the same as
```java
if((breathesFire && isAngry) || (isHungry && isCarnivorous))
```
however
```java
if(breathesFire || isAngry && isHungry || isCarnivorous)
```
is the same as
```java
if(breathesFire || (isAngry && isHungry) || isCarnivorous)
```
- AND has a higher priority

#### De Morgan's Laws
- what happens if I negate a compound expression?
```java
!(a && b)
```
- according to De Morgan's Laws, when distributing NOT across parentheses, you must flip AND to OR, and vice versa
```java
!(a && b) is the same as !a || !b

!(a || b) is the same as !a && b
```

#### De Morgan's Laws Proof 1: Logic
- "Mr. Guiou is not a parent or a counselor."
```java
!(isParent || isCounselor)
```
- when this statement is made in English, the meaning we understand from it is that neither of these is true. Mr. Guiou is not a parent, and he also is not a counselor.
```java
!isParent && !isCounselor
```
- "Mr. Guiou does not have black hair and green eyes."
```java
!(blackHair && greenEyes)
```
- This statement is slightly more awkward, but what we understand form it is that the conditions are not __both__ true; __one__ of them could be.
```java
!blackHair || !greenEyes
```

#### De Morgan's Laws Proof 2: Truth Tables
| a | b | (a && b) | (a \|\| b) |
|---|---|----------|------------|
| T | T | T        | T 			|
| T | F | F 	   | T 			|
| F | T | F		   | T 			|
| F | F | F 	   | F 			|

| a | b | !(a && b) | !a | !b | !a \|\| !b |
|---|---|-----------|----|----|------------|
| T | T | F         | F  | F  | F		   |
| T | F | T 	    | F  | T  | T		   |
| F | T | T		    | T  | F  | T		   |
| F | F | T 	    | T  | T  | T		   |

| a | b | !(a \|\| b) | !a | !b | !a && !b |
|---|---|-------------|----|----|----------|
| T | T | F           | F  | F  | F		   |
| T | F | F 	      | F  | T  | F 	   |
| F | T | F		      | T  | F  | F		   |
| F | F | T 	      | T  | T  | T		   |

## `.compareTo()`
### 10/8/21

#### String methods: `compareTo(String)`
- parameter: String
- return type: int
- determines if `this` String comes before or after the argument String lexicographically (in the dictionary). It returns
	- a negative if `this` comes before the argument in the dictionary
	- a positive number if it comes after
	- 0 if the string literals are the same
- the exact number returned is the difference between the letter positions in the alphabet
```java
"a".compareTo("b"); //negative
"b".compareTo("a"); //positive
"A".compareTo("A"); //zero
"abs".compareTo("absolute");
//negative, due to how dictionaries work
```

- the one small way that `compareTo()` method is different from a dictionary is that it is based on Unicode, which means that
	- like a real dictionary, numerical digits come before letters
	- unlike a real dictionary, it is case-sensitive, with capital letters coming before lowercase ones
```java
"1".compareTo("B"); //negative because digits < letters
"Z".compareTo("a"); //negative because capitals < lowercases
```

# Unit 5
