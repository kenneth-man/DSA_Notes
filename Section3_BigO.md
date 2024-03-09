## **Big O**
- ### Language we use to describe how long a function takes to run

<br>

## **Scalability**
- ### As the input size increases, how much does the function slowdown?

<br>

## **Big O Time Complexity**
- ### **O(1)**
	- ### ***Constant*** = No loops
- ### **O(log N)**
	- ### ***Logarithmic*** = Usually searching algorithms if they are already sorted e.g. Binary Search
- ### **O(n)**
	- ### ***Linear*** = Single loop through (N) items
- ### **O(n log(n))**
	- ### ***Log Linear*** = Usually sorting operations
- ### **O(n^2)**
	- ### ***Quadratic*** = Each element in a collection is compared with every other element
	- ### 2 nested loops
- ### **O(2^n)**
	- ### ***Exponential*** = Recursive algorithms that solve a problem of size (N)
- ### **O(n!)**
	- ### ***Factorial*** = Adding a loop for every element

<br>

![](./img/big_o.png)

### Iterating through half a collection is still O(n).

### Two separate collections: O(a * b).

<br>

## **What Causes Time in a Function?**
- ### Operations (+, -, *, /)
- ### Comparisons (<, >, ==)
- ### Looping (for, while)
- ### Outside Function call (function())

<br>

## **What Causes Space Complexity?**
- ### Variables
- ### Data Structures
- ### Function Calls
- ### Allocations