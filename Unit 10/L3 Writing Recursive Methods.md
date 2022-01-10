## Writing Recursive Methods
### 1/10/22
#### how to design a recursive method
1. break the problem into steps. What needs to happen during each step? *This is the backbone of the code.*
2. How can we tell when we've processed every step? *This is the base case in recursion and loop condition in iterative code.*
3. How do we keep track of the result? *In iterative code we usually have to commission a variable to keep track, but in recursive code this needs to be passed alont as the return value.*

```java
public static void repeat(String str, int count){
	System.out.println(str);
	if(count > 1){
		repeat(str, count - 1);
	}
} 
```

```java
public static void repeat(String str, int count){
	if(n >= 1){
		System.out.println(str);
		repeat(str, n-1);
	}
} 
```