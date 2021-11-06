## Javadocs and Preconditions
### 10/18/21
#### javadocs
- both single-line comments with `//` and multi-line comments with `/* */` are ignored by the compiler and can be used to explain parts of your code
- when it comes to documenting constructors and methods, however, there is a formal way to do it called a __Javadoc__. Advanced IDEs reward you for using Javadocs by having pop-ups when a coder is using your method to explain what it does and what the parameters mean
- Javadocs should being with `/**`, include a `*` at the start of every line, and end on the line just above the constructor/method header with `*/`.
- Javadocs begin with a general description of what your method does, then includes tags with @ for specific information. The two most helpful tags are `@param` and `@return`.

#### `@param`
- describes parameters. You should have one `@param` tag for each parameter in your constructor or method
- format:
```java
* @param variableName Description
```
- example:
```java
/**
 * Overwrites the age of the puppy
 * @param a the new age of the puppy.
 */
public void setAge(int a)
{
	age = a;
}
```

#### `@return`
- describes what the method returns. This should go after any `@param` tags
- format:
```java
* @return Explanation
```
- example:
```java
/**
 * Returns the Puppy's name.
 * @return The name as a String
 */
public void getName()
{
	return name;
}
```

#### preconditions and postconditions
- in the real world, using documentation properly is vital for programmers to be able to remember what the code they wrote last month does, for their teammates to figure out what their code does, etc. Javadocs are a powerful way to facilitate this.
- In this course with very simple methods, however, using the `@param` and `@return` tags often feels unnecessary. For this reason, CollegeBoard recently dropped it from the AP Java subset
- Substantially more important for the AP exam are __preconditions__ and __postconditions__

#### preconditions
- a precondition is a warning to the user of the method, "only call this method if \_\_\_\_ is true". CAlling a method when the precondition is false may result in the program crashing or having unexpected behavior.
- potentially the designer of a method would need to use `if` statements to check for a lot of potential inputs that don't make very much sense. A precondition lets the designer of the method shrug their shoulders and say, "Just dont call my method with weird inputs."

#### preconditions: example
```java
/**
* Returns the substring beginning at index from until index to – 1.
* Precondition: from >= 0, from < this.length()
* Precondition: to >= from, to <= this.length()
*/

public String substring(int from, int to)
```

#### preconditions on the AP Exam
- the AP exampl will frequently ask you to write methods that have preconditions. If they supply a precondition for a method you need to write, __they are giving you permission not to error check it__
- for example, if you were asked to write the `substring()` method, you would NOT have to check that the inputs are nonnegative. The precondition lets you say, "Woe to the idiot who calls my method with negative numbers; it is not my problem."
- preconditions make your life _easier_

#### postconditions
- if a precondition is a contract saying "you need to promise this is true in order to use my method," then a postcondition is a contract saying "I promise the following will be true when my method has finished executing."
- for example, if your method takes a Puppy object as a parameter, a postcondition might be "I will not rename your dog inside of my method".
- postconditions make your life _harder_ (kind of; they're really just requirements for the method you're writing)