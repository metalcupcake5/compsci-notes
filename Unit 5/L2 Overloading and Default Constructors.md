## Overloading and Default Constructors
### 10/22/21

#### method overloading
- a method is considered __overloaded__ if a class has two different methods with the same identifier
- you already know two overloaded methods: `substring()` from the String class, and `abs()` from the Math class
	- the `substring` method allows you to call it with either one parameter or two, and the `abs` method matches its return type to the parameter data type
- overloaded methods must have different parameter lists. Otherwise, the compielr will complain it can't tell them apart

#### errors with methorloading
```java
public void fun(int a, int b, String sign)
public void fun(int b, int a, String sign)
```
- this is __not valid__ because both versions have a list of(`int`, `int`, `String`). Swapping the names of the parameter variables doesn't help

```java
public int abracadabra(String input)
public double abracadabra(String input)
```
- this is also __not valid__ because both versions have a list of (`String`). The return types are different, but the compiler still has no idea which version to use when you call the method

```java
public void alakazam(String input1, int input2)
public void alakazam(int input1, String input2)
```
- this one __is valid__ because the first version's list is (`String, int`) and the second one's is (`int, String`)-- although this is not very good coding practice

#### constructor overloading
- a class can have multiple constructors. IN this case, the constructor is considered __overloaded__
- it is very common to have at least two versions of a constructor for any given class: one that takes in parameters to initialize its instance variables, and one with no parameters that initializes the instance variables with default values that make sense for the class. (It is usually better for hte user to use the first one, but having the no-parameter one available helps protect against bugs)
- overloading the constructor follows the same rules as overloading methods

#### default constructors
- if the writer of a class does not write any constructors, Java implicitly supplies a __default constructor__ that has no parameters. If this constructor is used, all the isntance variables are initialized to their __default values__
	- number types(`int`, `double`) initialized to 0
	- `boolean`s initialized to `false`
	- all reference types initialized to `null`
- memorize these - will show up in unit 6

- it is bad coding practice to actually use the default constructor. However, it is convenient that it exists, because it means that if you don't instend for a class to be instantiated, you don't have to write a constructor, and your code will still compile