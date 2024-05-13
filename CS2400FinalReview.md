# CS2400 Finals Reviews

## Topics

- Abstract data types (ADT) and their implementations
	- [Prelude]		Class and interfaces 
	- [Int. 1]		Generic 
- Linked and array-based data structures
	- [Ch. 1-3]		Bag
	- [Ch. 5-6]		Stack
	- [Ch. 7-8]		Queue, Deque, Priority Queue
	- [Ch. 10-11]	List
	- [Ch. 12]		Singly-linked, doubly-linked, circular array lists	
- [Ch. 9]		Recursion
- [Ch. 22-23]	Hashing and Searching
- [Ch. 4]		Analysis of Algorithms
- [Ch. 20-21]	Dictionaries
- [Ch. 24-25]	Trees
- [Ch. 26]		BST
- [Ch. 27]		Heap
- [Ch. 29-30]	Graphs

## ADTs and Bags

### Defintions
#### **Data Type**
- group of values and operations on those values that is defined within a specific programming language
#### **ADT**
- specification for a group of values and the operations on those values that is defined conceptually and independently of any programming language
#### **Data Structure**
- implementation of an ADT within a programming language
### **ADT Bag**
#### Definition:
- a collection of items in no particular order and allows for duplicates

#### Implementations
- Array
- Nodes
	```
	private class Node {
		private data;
		private next;

		//Traversal
		public void traversal() {
			Node currentNode = firstNode;
			//Include any other conditions...
			while(currentNode != null // any other conditions) {
				//Process data if necessary
				currentNode = currentNode.next;
			}
		}
	}
	```

## Stack
#### Definition:
- a collection of objects in reverse chronological order and having the same data type
- Follows the concept of LIFO: last in, first out

#### Implementations
- Array
- Nodes

#### Specifications
```
//Core methods

/**
 * Adds an entry to top of the stack.
 * @param entry The entry being added to the stack.
*/
public void push(T entry);

/**
 * Removes and returns the item at the top of the stack.
 * @return The entry at the top of the stack.
*/
public T pop();
```

## Queue, Deque, Priority Queue
### Queue
#### Definition:
- A collection of objects in chronological order and having the same data type

#### Queue Specifications
```
//Core methods

/**
 * Adds an entry to the queue.
 * @param entry The entry being added to the queue.
*/
public void enqueue(T entry);

/**
 * Removes and returns the entry at the front of the queue.
 * @return The entry being removed.
*/
public T dequeue();
```

### Deque
#### Definition:
- double-ended queue
#### Deque Specifications
```
//Core methods

/**
 * Adds an entry to the front/back of the deque
 * @param entry The entry being added.
*/
public void addToFront(T entry);
public void addToBack(T entry);

/**
 * Removes and returns the entry at the front/back of deque
 * @return The entry being removed.
*/
public T removeFront();
public T removeBack();

/**
 * Returns the entry at the front/back of the deque.
 * @return The entry being returned.
*/
public T getFront();
public T getBack();
```
### Priority Queue
#### Definition:
- A queuelike data collection taht organizes its objects according to their priorities instead of chronologically

## Trees

### Definitions
#### Tree
- collection of distinct vertices and distinct edges