## `while`
### 11/8/21

#### `while` loops
- a `while` statement, usually called a __while loop__, is a control structure that looks a lot like an `if` statement

```java
while( ) // boolean condition
{
	//these lines of code only execute
	//if the condition is true
}
```
- `while` loops actually have a lot in common with `if` statements. Like with an `if` statement, if the boolean condition evaluates to `false`, the body gets skipped. The `while` loops executes teh code in the body only if its conidtion evaluates to `true`
- where a `while` loop is different is that, at the end of the body, it checks the condition again, and if it is still `true`, the body is executed again and again, until the condition is `false`
- thats why it's called a loop. The code repeats itself until its condition becomes `false`. The condition is sometimes called a __continuing condition__. Code with loops is called __iteration__

#### `while` loop example
```java
int smile = 0;
while (smile < 5)
{
	System.out.println("/\\(ᐛ)/\\");
	smile++;
}
```
- the first time the loop executes, smile is 0 and gets increased to 1. The fifth time it executes, smile is 4 and updates to 5. After the fifth time, the `while` loop checks the condition; `5 < 5` is `false`, so it terminates

#### infinite loops
- it is important to make sure your loop condition eventually becomes `false`. If it doesn't the loop will go on forever, called an __infinite loop__
- notes that in the example, smile gets updated within the loop body

```java
int smile = 0;
while (smile < 5)
{
	System.out.println("/\\(ᐛ)/\\");
	//smile++;
}
```
- if we remove this line of code, smiley faces will forever print into the console.

#### dealing with infinite loops
- Infinite loops are a particularly annoying type of runtime error because the code really will go on forever. Some IDEs, including repl.it, have a Stop button for this reason
- for IDEs that are not web-based, sometimes you'll have to just close the IDE program

#### a reminder about `return` statements
- when a method returns a value, it terminates. There is no reason it would keep going
- make sure you don't `return` until you have accomplished the task your method is supposed to do