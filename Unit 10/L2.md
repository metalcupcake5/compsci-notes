## Tracing Recursive Methods
### 12/6/21
#### recursion
- the concept of a method calling itself is called __recursion__
	- methods that implement recursion are called __recursive__
	- the part of a recursive method where it calls itself is called the __recursive call__
- tracing recursive methods can be challenging! you must be able to visualize the call stack
	- every stack call must finish before it is popped off the call stack

#### recursion vs iteration
- all problems that can be solved with iteration (loops) can also be solved with recursion, and vice versa. They are fundamentally equivalent
- however, some problems are much easier to solve with iteration, and other problems are much easier to solve with recursion, so a skilled programmer should be comfortable with both
- analogous to an infinite loop, a poorly written recursive method may call itself forever, leading to __infinite recursion__
- to avoid this, a recursive method needs to have a branch with no recursive call, called the __base case__

#### side note
- unlike an infinite loop, infinite recursion usually doesn't actually go on forever; you can't push stack calls onto the call stack forever. Eventually, the call stack runs out of memory and crashes. This is called a __stack overflow__ error.