## 8/18/21 - Variables and Data Types
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
- Represents a single lexicographical character (letter/number/symbol)
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
| variables/methods | camelCase   | count        |
| classes      | UpperCamelCase | String       |
| ???        | ALL_CAPS    | PI         |

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
