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

#### Implementations
- Circular Array
	- One unused index
	```
	frontIndex = 0;
	backIndex = queue.length - 1;

	add:
	backIndex + 1;
	queue[backIndex] = new entry;
	
	//Queue is full when:
		(frontIndex == (backIndex + 2) % queue.length)

	//Queue is empty when:
		(frontIndex == (backIndex + 1) % queue.length)
	```
- Circular Linked List

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
public T removeFront() {
	//Throws exception if empty.
	//Check whether frontNode is not null
		Gets data from frontNode;
		Clears data in front node
		Sets frontNode as frontNode's next node
	If frontNode is null,
		lastNode is also null;
	else frontNode sets previous node as null
	return frontNode data
}
//Rework removeFront for removeBack;
public T removeBack();

/**
 * Returns the entry at the front/back of the deque.
 * @return The entry being returned.
*/
public T getFront();
public T getBack();

/**
 * Checks whether the deque is empty.
 * @return True if empty, false if not.
*/
public boolean isEmpty();


//Inner class DoubleLinkedNode
private class DoublyLinkedNode {
	private T data;
	private Node previous;
	private Node next;

	//Getters and setters for fields.
}
```
### Priority Queue
#### Definition:
- A queuelike data collection taht organizes its objects according to their priorities instead of chronologically
#### Implementation
- Heap

## List
#### Definition
- A collection of objects in a specific order and having the same data type
#### Specifications
```
public class List {
	public void add(T entry);
	public void add(T entry, int position);
	public T remove(int position);
	public T replace(T entry, int position);
	public T getEntry(int position);
	public boolean contains(T entry);
	public int getLength();
	public boolean isEmpty();
	public T[] toArray();
	public void clear();
}
```
#### Implementations
Methods:
- Array
- Linked
	- Reference to first node and last node

Private Methods:
```
/*
 * Makes the index at the given position open while moving entries on/after the index down one.
*/
private void makeRoomArray(int position) {
	//Go to the end of the list and move the last index to the index + 1
	//Then move to the second to last index and move it to that index + 1
	//Continue until the given position gets shifted over.
}

/*
 * Shifts entries after the given position index back to fill the gap.
*/
private void removeGapArray(int position) {
	//Start at the index after the given position and shift it back; continue with the next index until the last entry is shifted back
}
```

## Recursion
#### Definition
- problem-solving process that breaks down a problem into identical but smaller problems
#### Time Efficienccy:
> O(n)
#### Requirements
- Calls itself (recursive call)
- Has a base case
- Must be given an input value

> Recursive methods part of an implementation are typically **private**
```
public void display() {
	displayArray(0, numOfEntries - 1);
}

private void displayArray(int start, int last) {
	System.out.println(bag[first]);
	if (first <= last) {
		displayArray(first + 1, last);
	}
}
```
#### Activation Record
Each recursive call generates a record of its activation
- keeps track of when the recursive method is called and where it should return to
- works almost like a stack:
	- each recursive call stacks on top of one another and tells where to return back to after finding its base case/finishing its recursive call
#### Tail Recursion
- tail recursion refers to the recursive call being the last action performed by the recursive method
	- should change to iteration/looping since it's more memory efficient
## Hashing and Searching

## Trees
#### Definitions
- set of nodes connected by edges that indicate the relationships among the nodes

#### Specifications for All Trees
```
public interface TreeInterface<T> {
	public T getRootData();
	public int getHeight();
	public int getNumberOfNodes();
	public boolean isEmpty();
	public void clear();
}
```
```
public interface TreeIteratorInterface<T>{
	public Iterator<T> getPreorderIterator();
	public Iterator<T> getPostorderIterator();
	public Iterator<T> getInorderIterator();
	public Iterator<T> getLevelOrderIterator();
}
```

### Binary Trees
- Each node can have a maximum of two children.

#### Traversals for Binary Tree
- Preorder traversal (NLR)
- Inorder traversal (LNR)
- Postorder traversal (LRN)
- Level-order traversal
	- Begin at root and visits nodes one level at a time
##### General Tree Traversals
- All the same, but inorder is not recommended
#### Specification/Implementation
```
public interface BinaryTreeInterface<T> extends TreeInterface<T>, TreeIteratorInterface<T> {
	/*
	 * Sets the root of this tree to contain the given object
	 * @param rootData The object to be put into the root.
	*/
	public void setRootData(T rootData);
	
	/*
	 * Set's this binary tree to a new binary tree
	 * @param rootData The object in the tree's root
	 * @param leftTree The left subtree of this binary tree.
	 *@param rightTree The right subtree of this binary tree.
	*/
	public void setTree(T rootData, BinaryTreeInterface<T> leftTree,  BinaryTreeInterface<T> rightTree);
}
```
Uses binary node with data portion and references to left/right subtrees
```
public BinaryNode() {
	this(null);
}

public BinaryNode(T dataPortion) {
	this(dataPortion, null, null);
}

public BinaryNode(T dataPortion, BinaryNode<T> leftSubTree, BinaryNode<T> rightSubTree) {
	data = dataPortion;
	leftChild = leftSubTree;
	rightChild = rightSubTree;
}
```
#### Applications
##### Expression Trees
- With inorder form, the left operand is sthe left child, the operator is the parent node, and the right operand is the right child.
	- Operands could be their own expression tree as well
- Evaluating:
	- In postfix form, add each operand to a stack,
	- when an operator appears, pop once to get right-hand operand and pop again to get left-hand operand; perform operator with operands and push result back onto stack
##### Decision Tree
##### Binary Search Tree
- The node's data is greater than all the data in its left subtree
- The node's data is less than all the data in the right subtree
###### Efficiency for Binary Search Tree
- O(h), where h is the height of the tree

##### Heap
- complete binary tree whose nodes contain Comparable objects and are organized in a certain way
	- maxheap = largest is at the root node
	- minheap- smallest is at the root node

## Graphs
- collection of distinct vertices and distinct edges

## ADT Definitions
1. Bag
	- collection of objects of the same type with no order and allows duplicates
2. Stack
	- collection of objects in reverse chronological order
3. Queue
	- collection of objects in chronological order
4. Deque
	- double-sided queue
5. Priority Queue
	- collection of objects ordered by an unspecified priority
6. Lists
	- collection of objects of the same type in a specific order
7. Dictionary
	- a collection of entries which are are stored/retrieved according to their search-key values
8. Trees
	- a collection of nodes connected by edges that denote the relationship among the nodes
9. Graphs
	- collection of distinct vertices and edges

## Quiz/Midterm Questions

### Quiz 3
1. An implementation of an ADT with a programming language is called a/an:
	- data structure
	- abstract data type
	- collection
	- primitive
3. Show the code to create a groceryBag of the type BagInterface that can be used to store grocery items using their names, eg. "soup", "eggs", ...etc. and add a few items into it. You can assume there exists a ArrayBag implementation for thei BagInterface that you can use.
4. Write a class method removeAll that can remove all specific items from any type of bag. For example: removeAll(fruitBag, "apple"); //remove all "apple" from the fruitBag.

### Quiz 4
5. Show the implementation of the method that behaves like add named addEnd in LinkedBag. This method will add a new entry to the end of the chain instead to the beginning. Node is an inner class.

### Quiz 5
1. You should express the complexity of an algorithm in terms of its
- execution time
- space requirements
- problem size
- overall complexity
3. Order the following growth rates from smallest to largest: n^2, n!, n, log, n, 2^n, n, log n
5. What is postfix expression for the infix expression:	w + x * y / z
6. Show the pseudocode to evaluate a prefix expression using a stack. Hints: scan the expression from the last token;
- \+ a b
- \+ a * b c
- \+ w / * y z

### Quiz 6
4. Show the implementation of the constructor, enqueue and dequeue methods in the class ArrayQueue.
```
public final class ArrayQueue<T> implements QueueInterface<T> {
	private final static int DEFAULT_SIZE = 64;
	private int front, rear, entries;
	private T[] queue;

	public void enqueue(T newEntry);
	public T dequeue();
}
```
- a) No arg constructor
- b) enqueue; throw RuntimeException when full
- c) dequeue; throw RuntimeException when empty

### Quiz 7
4. The ADT dictionary is also known as
- map
- table
- associative array
### Quiz 9
4. Draw the binary tree
	Preorder:	R Q Y Z W X
	Inorder:	Q Y R W Z X