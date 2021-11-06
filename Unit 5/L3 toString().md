## `toString()`
### method overriding
### 10/26/21

#### printing objects
- print statements are really versatile! Strings and all 8 primitive data types print without problems

#### `.toString()`
- when you try to print an object, the compiler actually implicitly calls the `toString()` method on the object and prints its return value
- it is a special method that is automatically defind for every class in Java, __even if you write the class yourself__
```java
public String toString()
```
- by default, it returns a short String of the format `className@memoryLocation`
- to cause something more helpeful, you have to define the `toString()` method in your class, which overwrites the default version
	- this is called __method overriding__

#### `toString()` example
- what you might define `.toString()` for a Puppy class
```java
public String toString(){
	return name + " is a " + breed + " who is " + age + " years old.";
}
```
- you're __returning__ what you want to be __printed__ if your object is printed
- it is up to decide what is pertient information to print, usually we want to see some of the important instance variables