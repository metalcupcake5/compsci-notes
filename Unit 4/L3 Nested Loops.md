## Nested Loops
### 11/15/21

#### it's inception time
- what happens if there's a loop __inside of a loop__? This situation is called a __nested loop__
- The convention for the indentifier for the loop control variable of the innner loop of a nested loop is `j`

#### tracing nested loops
- the key to understanding nested loops is to realize that the inner loop goes through all of its iterations _for every iteration of the outer loop_. In other words, the inner loop restarts every time the outer loop goes through an iteration.
- this means that if the outer loop goes through _n_ iterations, and the innner loop goes through _m_ iterations per interation of the outer loop, the total number of times the inner loop executes is _n_ x _m_.
- CollegeBoard will ask you many multiple choice questieons about how many times a loop iterates because in advanced code analysis, the number of times a loop iterates is used to measure how long a program takes to run, and therefore how efficient an algorithm is