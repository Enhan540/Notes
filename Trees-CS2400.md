# Trees

### Quiz #8 Code Answer

	public int getHashIndex(String s) {
		int hashIndex =  s.hashChode() % hashTable.length;
		return hashIndex < 0 ? hashIndex + hashTable.length : hashIndex; 
		}

# 26-March-2024
### Traversals

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