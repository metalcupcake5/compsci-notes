## `for`
### 11/10/21

#### structure of a loop
- avoiding an infinite loop is important, so we want ot always make sure our loop condition becomes `false` eventually
- oftentimes, we know exactly how many times we want a loop to execute, and so we simply create an `int` variable to keep track of the iterations. This variable is called a __loop control variable__
- this is such a common practice that Java has another version of the `while` loop that makes it easier to build in a loop control variable, called a __for loop__

#### `for` loops
```java
for (int i = 0; i < 10; i++)
{
	// these lines of code only execute if the condition is true
}
```

#### initialization statement
- the initialization statement is executed only one time and is the very first thing the `for` loop does. Usually initializes the loop control variable
- it does not _have_ to declare the variable (it can use one that was previously declared), but if it does, __the variable goes out of scope when the loop ends__

#### loop condition
- aka continuing condition, this is the exact same thing as the boolean condition for a `while` loop
- it is checked __after the initialization statement__ before the loop executes for the first time and __after the update__ during every execution after

#### update
- also called the __increment__, but this is a bad name because the update doesn't always increment the loop control variable
- executes after each iteration of the loop, before checking the loop condition
- doesn't have a semicolon!
- the update should move the `for` loop closer to its termination. In most cases, `i++` is the statement used, but `i--`, `i+=2`, and `i/=10` are all examples of other valid update statments
- the example below will execute ten times(as long as the loop body does not modify the value of `i`)

```java
for(int i = 0; i < 10; i++)
{
	//body
}
```

#### `for` loop example
```java
for (int smile = 0; smile < 5; smile++)
{
	System.out.println("/\\(ᐛ)/\\");
}
```
- looks much cleaner than the while loop because the loop header deals with the loop control variable, so the body is focused only on what the loop is actually there for

#### when to use a `for` loop
- any `while `loop can be rewritten as a `for` loop and vice versa. The only difference is which is easier to use in a given situation
- generally, if your loop does not need an intialization statement, a `while` loop is cleaner
- if your loop uses an `int` loop control variable, which is 90% of the time, a `for` loop is typically more efficient