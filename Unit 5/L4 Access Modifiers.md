## Access Modifiers
### 10/28/21

#### access modifiers
- access modifiers(eg `public` and `private`) determine whether a class' methods and isntance/class variables can be seen by other classes
- in the VendingMachine repl, you also have a Main class where you are testing out your VendingMachine
- the Main class is allowed to see and call the `getMoneyInserted()` and `sellSoda()` methods on the VendingMachine object because those methods are `public`

#### what if instance variables are `public`?
if a class' instance variables are `public`, they can be accessed using dot notation just like calling a method (except without parentheses)

#### encapsulation
- simple classes usually have a getter and setter method for each of their instance variables. However, sometimes how a class stores the data it returns with its methods is more complcated than expected
- we dont want the user of a class to worry about what its instance variables are, because they would have to thoroughly understand _how_ the class' methods work to understand the instance variables
- we want the user of a class to simply know _what_ its methods do, and be allowed to use them. It's much simpler for them that way.
- the principle of giving the parts of a class the strictest access modifiers possible is called __encapsulation__

#### encapsulation - ex 1
- similar to the idea of how people as young as 15 can drive car without a degree in Mechanical Engineering
- `public` methods of a Car class might be how to use the steering wheel, gas, break pedals, shift drives into reverse and forward, etc
- you dont need to know how a car works to _use_ a car, but you do need them to _design_ a car(these are like `private` instance variables)

#### helper methods
- instance/class variables should almost always be `private`. However, methods could be either
- sometimes a `public` method gets really long because it has to do so much
	- we often want to break methods up into smaller methods that are easier to read and debug
	- this is called __refactoring__ the code
- if the smaller methods don't need to be called by the user of a class, we should make them `private`. Informally, these are called __helper methods__

#### `this`
- `this` refers to the object you are working in
- when we use `this` to disambiguate instance variables from parameter ones, we're using the same dot notation as we would if an instance variable was `public`
```java
public Whatchamacallit(String label){
	this.label = label
}
```
- when calling methods withing a class, you don't need dot notation, but you can use dot notation with `this` if you want to, e.g. `this.getColor()`

#### methods that accept their own object type as a parameter
- sometimes, a class contains a method that accepts an object of its own type as a parameter. (such as `indexOf()` and `compareTo()` in the String class)
- First: We can access the argument object's instance variables even if they are private.
```java
public String methodA(Whatchamacallit input){
	return "A" + input.label;
}
```
- In this example: we can access input's instance variable, label, even though label is private.
- That's because we are actually in the Whatchamacallit class, so we have access to its instance variables.
- Second: If we want to allow objects to use _themselves_ as inputs to a method, we can do this with the `this` keyword
```java
public String methodB(){
	return "B" + methodA(this)
}
```
