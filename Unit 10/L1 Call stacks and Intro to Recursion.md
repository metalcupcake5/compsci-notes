## Call stacks and Intro to Recursion
### 12/2/21
#### stacks
- in computer science, a **stacc** is a data structure where the first block of data saved into the structure is the last block of data to be removed fromt he structure(sometimes called a LIFO structure, Last In First Out)
- that means if info is stored in a stack, the computer can only access the most recently stored info; accessing older info requires removing more recent info

#### call stacks
- in Java, when you call a method, the program stops what it was doing and starts executing the code from that method
- however, it needs to remember where it was before calling the method so that when the method is finished, it can resume where it left off
- Java uses a stack to keep track of method calls, called a **call stack**

#### call stack example
- lets trace a simple program that tests out some of the methods in our VendingMachine class
- for each level of the call stack (called a **stack call**), the computer must remember which class it was in, wat method it was executing, and what line of code it left off on