# Trees

### Quiz #8 Code Answer

	public int getHashIndex(String s) {
		int hashIndex =  s.hashChode() % hashTable.length;
		return hashIndex < 0 ? hashIndex + hashTable.length : hashIndex; 
		}
> The code portion 
>`hashIndex < 0 ? ` basically puts it into an if statement. If it's true, the left hand side of the colon runs `hashIndex + hashTable.length` and returns it; if it's false, the right hand side code runs and returns the value of `hashIndex`.

# 26-March-2024
## Traversals

Traversals of a Binary Tree
- Preorder Traversal
	- **N**ode -> **L**eft -> **R**ight
	- Visit the **Node**, then go to its left sub tree;
		- repeat until each subtree node is visited
- Inorder Traversal
	- **L**eft -> **N**ode -> **R**ight
	- 
- Postorder Traversal
	- **L**eft -> **R**ight -> **N**ode
- Level-order Traversal
	- Begin at root and visit nodes one level at a time

Traversals of a General Tree
- Types of traversals
	- level order
	- preorder
	- postorder
- Not suited for general tree traversal
	- inorder

Code To Do These Traversals
- Level-Order Traversal
	1. Enqueue all nodes on the top level
	2. Dequeue node and enqueue all children
		- continue until all nodes from level are dequeued, then move onto next level (children of the dequeued nodes)
- 

## Interfaces for All Trees

	public interface TreeInterface<T> {
		public T getRootData();
		public int getHeight();
		public int getNumberOfNodes();
		public boolean isEmpty();
		public void clear();
	}

### Traversals
	import java.util.Iterator;
	/**An interface of iterators for the ADT tree. */
	public interface TreeIteratorInterface<T> {
		public Iterator<T> getPreorderIterator();
		public Iterator<T> getPostorderIterator();
		public Iterator<T> getInorderIterator();
		public Iterator<T> getLevelOrderIterator();
	}

## Building a Binary Tree
- Start with leaf nodes:

### Code
	BinaryTreeInterface<String> dTRee = new BinaryTree<>();
	/**"D" is the node of dTree, null (2) is its left child, and null (3) is its right child. */
	dTree.setTree("D", null, null);
	
	BinaryTreeInterface<String> aTRee = new BinaryTree<>();
	dTree.setTree("A", bTree, cTree);