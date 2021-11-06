## 8/20/21 - Arithmetic
#### copying variable values
- The contents of a variable can also be assign to a variable
```java
int x = 5;
int y = x; // x is now 5
```
- When it is done with primitive data types, the value of x is copied into y
- You can assign the result of an expression to a variable


#### meth
- `+` for addition
- `-` for subtraction
- `*` for multiplication
- `/` for division
- `%` for modulus
- addition/subtraction/multiplication work in the way you’d expect
- With doubles, division works the way you would expect
- PEMDAS is in full effect


#### dividing ints
- When dividing ints, decimals in the quotient are discarded
- The modulus operation (%) find the remainder of the division expression 
```java
int y = 20 % 3; // y is 2; 20/3 has a remainder of 2
double x = 3 / 2; // x is 1; 3 and 2 are integers so it is still int division
double z = 3.0 / 2; // zy is 1.5; you must have at least one floating point value to do proper division
```

#### widening
- If arithmetic involves a combination of ints/doubles, or result of int operation is assigned to a double, the final result is a double
- Named widening


#### casting
- The opposite of widening is not true
- If you need to assign a double to an int, you must cast it
```java
int z = (int) (3.0 / 2.0);
```
- When a double is cast to an int the decimal is truncated
- Only the part before the decimal point is kept
