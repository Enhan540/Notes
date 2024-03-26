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
	- Visit the **Node**, then go to 
- Inorder Traversal
	- **L**eft -> **N**ode -> **R**ight
	- 
- Postorder Traversal
	- **L**eft -> **R**ight -> **N**ode