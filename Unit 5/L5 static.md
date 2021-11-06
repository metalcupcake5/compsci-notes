## `static`
### 11/2/21
#### `static` methods
- unlike non-static methods, methods that are `static` belogn to the class itself
	- they are called on the class name
- instance variables belong to instances (objects) of a class, not to the class. This makes them incompatible with `static` methods, and the compiler will complain if you try to use an instance variable in a `static` method

#### `static` methods and instance variables
```java
VendingMachine mach = new VendingMachine(50);
mach.sellSoda();
```
- code makes sense. The VendingMachine called mach can sell sodas. It has instance variables telling it the price and how many it has

```java
VendingMachine.sellSoda();
```
- does not make sense. If you try to call `sellSoda()` on the class itself... how many sodas are in stock? what is the price?

#### class variables
- like methods, variables in a class can be declared `static`. As with methods, this causes them to belong to the class itself, not to instances of the class
- these are called __class varialbes__. They are the fourth and final type of variable, after local, instance, parameter variables
- generally declared underneath instance variables

```java
public class Amoeba
{
	private String color;			// instance variable
	private static int count = 0;	// class variable
```

#### contrasting class variables and instance variables
- every object of a class gets its own copy of instance variables
- every time an object is created, the constructor initializes its copy of the instance variables
- since class variables belong to the class, there is only one copy of them. Therefore, the constructor doesn't initialize them. Instead, __they should be initialized in the same line in which they are declared__.
```java
private static int count = 0;
```

#### non-static methods and class variables
- are compatible. Every instance of a class is allowed to use its class variables
- however, there is only one copy of them. That means if one object changes the value of a class variable, every other object is affected by the change, too
- this is the main purpose of class variables: they are variables that are shared across every instance of a class

#### an example
- one of the more common uses for class variables is simply to keep track of how many objects have been created. Every time the contructor is called, increase the variable by one.

```java
public class Amoeba
{
	private String color;
	private static int count = 0;
	
	public Amoeba(String c)
	{
		color = c;
		count++;
	}
	
	public static int getPopulationTotla()
	{
		return count;
	}
}
```

#### `static` methods and class variables
- are also compatible. Although `static` methods cannot use instance variables, they CAN use class variables.

```java
public static int getPopulationTotal()
{
	return count;
}
```