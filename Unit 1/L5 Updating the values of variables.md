## 8/26/21 - Updating the values of variables
#### updating a variable
- assuming that x and y have been initialized, the following lines of code are all valid
```java
x = 5 + 7;
x = 7*y;
x = x + 2;
```
- if the last one confuses you, realize that the computer evaluates the right side of the equation and stores the result in the variable on the left. the new value of x is the old value of x plus 2. We're just increasing x by 2


#### shortcut assignment operators
- when an arithmetic operator is combined with `=`, it's a shortcut to update x by the amount on the right hand side

| the shortcut | means the same thing as |
| ------------ | ----------------------- |
| `x += y;` 	| `x = x + y` 			   |
| `x -= y;` 	| `x = x - y` 			   |
| `x *= y;` 	| `x = x * y` 			   |
| `x /= y;` 	| `x = x / y` 			   |
| `x %= y;` 	| `x = x % y` 			   |

- these are helpful when you understand the logic behind them
```java
x -= 2; //decrease x by 2
x *= 3; //triple the value of x
x += y; //increase x by y
```

#### even shorter shortcuts
##### because programmers are lazy
- increasing or decreasing the value of a variable by 1 happens to be so helpful, it has its own shortcut.
```java
x++; //increment x by 1
x--; //decrement x by 1
```
- **IMPORTANT**: only use the shortcut as its own line of code, not inside a print statement