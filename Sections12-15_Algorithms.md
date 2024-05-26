# Recursion
- ### A function that calls itself
- ### Large function call stack (increase memory usage); not good if you're working with minimal memory
	- ### Can lead to stack overflow
- ### Use when a task has repeated sub tasks to execute, where the sub tasks are identical (E.g. tree traversal, graph traversal quick sort, merge sort...)
- ### Anything you can do with recursion, you can do iteratively (loops)

<br>

# Sorting
- ### As more and more data is handled, sorting andsearching become more important; less important with small amounts of data

<br>

- ## Elementary Sorting Algorithms
	- ### Bubble Sort
		- ### Not used in practice
		- ### Compare previous element with next element; if previous element is greater, swap
		- ### Repeat from beginning until no more swaps are needed
	- ### Insertion Sort
		- ### Only use when data is small or when a list is almost sorted; O(N) time in best case
		- ### Compare the next element to the elements before it, then insert into the correct ordered position
	- ### Selection Sort
		- ### Not used in practice
		- ### Search for the smallest element, then place first
		- ### Search for the next smallest element from the remaining elements, then place after the previous smallest item, etc...

<br>

- ## Divide and Conquer
	- ### Merge Sort
		- ### Can always guarantee O(N log N) time
		- ### Requires more memory than quick sort
		- ### Divide all elements into two halves, then keep dividing to the element
		- ### Compare elements and place in order
		- ### E.g.
			- ### 6 5 3 1 8 7 2 4
			- ### 6 5 3 1 ,  8 7 2 4
			- ### 6 5 , 3 1 , 8 7 , 2 4
			- ### 5 6 , 1 3 , 7 8 , 2 4
			- ### 1 3 5 6 , 2 4 7 8
			- ### 1 2 3 4 5 6 7 8
		- ### If comparing equivalent element, maintains the same order
	- ### Quick Sort
		- ### Faster than merge sort on average, but slower in worst case
			- ### Need to guarantee the pivot will not be worst case
		- ### Pick a pivot, all elements less than the pivot go to the left of it, all elements greater go to the right
		- ### Repeat for the left and right sides by picking pivot points
		- ### Worst case is O(N^2), if you pick a pivot that's the largest or smallest element
			- ### Since you're not dividing the list in half, so comparing every element with every other element

<br>

- ## Heap Sort
	- ### Heap = ordered binary tree
	- ### Max Heap = parent nodes are greater than child nodes
	- ### Create max heap, Remove largest item from tree (root), place to the left of the sorted portion of list, repeat until max heap no longer exists
	- ### E.g.
		- ### Tree:
			- ### 2 8 5 3 9 1
			- ### 9 8 5 3 2 1 (Max Heap)
		- ### Tree: 8 3 5 1 2
			- ### List:
				- ### [1, 8, 5, 3, 2, 9]
				- ### [8, 3, 5, 1, 2, 9]
		- ### Tree: 5 3 2 1
			- ### List:
				- ### [1, 5, 3, 2, 8, 9]
				- ### [5, 2, 3, 1, 8, 9]
		- ### Tree: 3 1 2
			- ### List:
				- ### [1, 2, 3, 5, 8, 9]
				- ### [3, 1, 2, 5, 8, 9]
		- ### Tree: 2 1
			- ### List:
				- ### [2, 1, 3, 5, 8, 9]
		- ### Tree: 1
			- ### List:
				- ### [1, 2, 3, 5, 8, 9]

<br>

- ## Non Comparison
	- ### Radix Sort, Counting Sort
		- ### Faster than O(N log N) time (quick sort, merge sort)
		- ### Only works with sorting numbers (integer) within a restricted range
		- ### Without making any comparisons between the elements. Instead, they use other operations such as counting, hashing, or distributing elements based on their digits or how they're stored in memory

<br>

# Traversal
- ## Graph + Tree traversals:  O(N) time
	- ### Perform operation or add some data property on every node
		- ### Used If the graph or tree has no order or not a binary search tree
	- ### Depth First Search and Breadth First Search
		- ### Since it' i's O(log N) to search, it's used instead of putting all the complex graph and tree data into an array, which is O(N) time to search

<br>

# Searching
- ## Linear (Sequential) Search
	- ### Sequentially search 1 by 1 through the list until element is found/not found
	- ### Best case O(1) if element is index 0
	- ### Worst case O(N) if element is last index

- ## Binary Search
	- ### Used on sorted lists
	- ### Get the middle element, if target is less, discard the right side elements, vice versa and repeat

- ## Depth First Search (DFS)
	- ### Start at root node, go down one branch until you reach the leaf node
	- ### Go up to parent of the leaf and go to the nearest ancestor node that hasn't been visited

- ### ***PRO***: Use if you know the location of the target node is somewhere in the lower levels of the tree
- ### ***PRO***: Determine if a path exists between 2 nodes
- ### ***PRO***: Requires less memory than BFS
- ### ***CON***: Can be slow if the tree/graph is many levels deep

<br>

- ## Breadth First Search (BFS)
	- ### Start at root node, then move to the next level from left to right nodes until you find the element

- ### ***PRO***: Use if you know the location of the target node is somewhere in the upper levels of the tree
- ### ***PRO***: Finding the ***Shortest Path*** between two nodes (assuming all edges have the same weight)
	- ### E.g. Closest connections on Linkedin, Most related items...
- ### ***CON***: Requires more memory than DFS
	- ### Wll require a lot of memory to track all the child nodes of the level that's being searched
- ### ***CON***: Can be slow if tree/graph is very wide
	- ### Wll require a lot of memory to track all the child nodes

<br>

- ## Shortest path algorithms when edges have different weights
- ### *Edge Weight = Cost of moving from one node to another*
	- ## Dijkstra's Algorithm
		- ### Shortest path from one node to all other nodes
		- ### Cannot accomodate negative edge weights 
		- ### Greedy
			- ### Always picks the next smallest edge weight (since it doesn't apply on negative edges, so cannot figure out actual shortest path via subtracting weights)
		- ### More Efficient than Bellman-Ford
	- ## Bellman-Ford Algorithm
		- ### Shortest path from one node to all other nodes
		- ### Can accomodate negative edge weights
		- ### Not Greedy
		- ### Worst case O(N^2) time

<br>

# Dynamic Programming
- ### An optimization technique using cache
- ### Breaking a problem down into subproblems, solving each subproblem once, and storing the solutions in a cache
	- ### Incase the same repetitive subproblem occurs again, you can just return the value in the cache

<br>

- ## Memoization
- ### Caching
	- ### Store values to be used in the future
	- ### Speed up programs, because we don't need to recalculate the same values repeatedly
- ### Memoization (Specific type of caching)
	- ### Caching the return value of a function based on it's parameters
	- ### E.g.
```
function memoizeAddTo80() {
	let cache = {};
	
	// Closure
	// prevent the need to declare `cache` outside the function
	const function(n) {
		if (n in cache) {
			return cache[n];
		} else {
			console.log('Execution taking a long time...');
			cache[n] = n + 80;
			return cache[n];
		}
	}
}

const memoized = memoizeAddTo80();

console.log('1', memoized(5));
console.log('2', memoized(5));

// OUTPUT:
// Execution taking a long time...
// 1 85
// 2 85
```

