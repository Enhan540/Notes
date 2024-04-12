# Midterm 2 Review

## ADTs

Abstract Data Type
- Specification of data set and the operations on that data
- Does not indicate how to store the data or how to implement the operations

---
### Bag
Can be implemented using array or linked nodes.

Interface methods:
```
boolean add(T entry);
T remove();
T remove(T entry);
boolean contains(T entry);
boolean isEmpty();
boolean isArrayFull();
T[] toString();
int getFrequncyOf(T entry);
void clear();
int getCurrentSize();
```
---
### Stack

---
### Queue

- Waiting line; **FIFO (First In, First Out)**
- Can only view the first item
- Additions go to the back

Interface methods:
```
void enqueue(T entry);
T dequeue();
T getFront();
boolean isEmpty();
void clear();
```
##### Implementations
Can either have linked implementations (nodes) or circular array.
- Linked Implementation
    - Keeps a pointer at the end of the linked list, where new additions are added.
        ```
        public final class LinkedQueue<T> implements QueueInterface<T> {
            ...
            public void enqueue(T entry) {
                Node newNode = new Node(newEntry, null);
                if (firstNode == null) {
                    firstNode = newNode;
                } else {
                    lastNode.next = newNode;
                }
                lastNode = newNode;
            }
        }
        ```
    - Dequeue takes the front node's data and moves to the next node as the front.
        ```
        public T dequeue() {
            //Will throw an exception if there is no item.
            T result = getFront();
            firstNode.data = null;
            firstNode = firstNode.next;
            //If there was only one item, lastNode needs to be updated too.
            if(firstNode == null) {
                lastNode = null;
            }
        }
        ```
- Circular Array Implementation
    - Uses an array with two pointers for the front and back; when the back pointer reaches moves to an index past the last index, circles back to the front.
        - Uses array of size + 1 to solve isEmpty complications.
    - Can use linked list for circular as well.
    ```
    public final class CircularArrayQueue<T> implements QueueInterface<T> {
        T[] queue;
        int frontIndex;
        int backIndex;
        boolean integrityOK;
        final static int DEFAULT_CAPACITY = 50;
        final static int MAX_CAP = 10000;

        public CircularArrayQueue() {
            this(DEFAULT_CAPACITY);
        }

        public CircularArrayQueue(int capacity) {
            if (capacity > MAX_CAP) {
               throw new RuntimeException("Size exceeds max.");
           } else {
               integrityOK = false;
               @SuppressWarnings("unchecked")
               T[] tempQueue = (T[]) new Object[capacity + 1];
               queue = tempQueue;
               frontIndex = 0;
               backIndex = capacity;
               integrityOK = true;
            }
        }

        private void checkIntegrity() {
            if (integrityOK == false) {
                throw new IllegalStateException("Queue is corrupt.");
           }
       }

        public void enqueue(T entry) {
            checkIntegrity();
            backIndex = (backIndex + 1) % queue.length;
            queue[backIndex] = entry;
        }
        public T dequeue() {
            checkIntegrity ();
            if (isEmpty()) {
                throw new IllegalStateException("Queue is empty.");
            }
            T result = queue[frontIndex];
            queue[frontIndex] = null;
            frontIndex = (frontIndex + 1) % queue.length;
            return result;
        }
    
        public T getFront() {
            return queue[frontIndex];
        }
    
        public boolean isEmpty() {
            checkIntegrity();
            return frontIndex == ((backIndex + 1) % queue.length);
        }

        public void clear() {
            while (!isEmpty()) {
                dequeue();
            }
        }
    }
    ```

#### Deque
- Double ended queue
- has queue-like operations and stack-like operations

Interface Methods:
```
void addToFront(T entry);
T removeFront();
T getFront();
void addToBack(T entry);
T removeBack();
T getBack();
boolean isEmpty();
void clear();
```

#### Priority Queue
- organizes objects acording to their priorities
- "priority" depends on context/nature of items

Interface Methods:
```
void add(T entry)
T remove();
T peek();
boolean isEmpty();
int getSize();
void clear();
```


### List
- Similar to bag, but order can be implemented
- Items have position; typically ignore index 0 if using array
- Should have no gaps between entries; should shift to make room or fill gaps when adding/removing

Interface Methods:
```
void add(T entry);
void add(int position, T entry);
T remove(int position);
void clear();
T replace(int position, T entry);
T getEntry(int position);
T[] toArray();
boolean contains(T entry);
int getLength();
boolean isEmpty();
```

##### Implementations
- Array
- Linked List


### Dictionary

### Tree

- Binary Tree
    - Traversals
        1) Inorder      -> LNR
        2) Preorder     -> NLR
        3) Postorder    -> LRN

#### Binary Search Tree
- Given a root, the left child should have a lower value than the root and the right child should have a greater/equal value compared to the root value.
- When adding a node, go through the tree depending on its value:
    - if newNode < rootNode, go to left subtree;
    - else, go to right subtree;
    - repeat until reach a null rootnode, where the newNode takes that spot
#### Heap
- Max Heap
    - Root node of a max heap should be greater than all descendants
    - when adding, add in a manner that it keeps the max heap as a complete binary tree
    <blockquote>
    Using array to represent a heap:

        - Root = n;
        - LeftChild = 2n;
        - RightChild = 2n + 1;
    </blockquote>
    


---

## Other Concepts

### Recursion
- Needs base case
- function calls itself until it reaches its base case
    - it then will begin returning values to the instance of the function that it was called from

### Iterators

### Hashing
- technique that determines an index into a table using only an entry's search key
- Hash code = integer given by a function
- Hash index = hashCode() % table.length;
    - include check for when the hashIndex is < 0, where you would add hashTable.length to the hashIndex
#### Collisions
When multiple search keys map to the same hashIndex, a collision occurs, which we must handle.

##### Open addressing w/ Linear Probing
- method of handling collisions by probing for available indexes after the given hashIndex for the new search key to be put into
- Pseudocode:
```
probe(int index, K searchKey) {
    while (key not found && currentIndex is not empty) {
        if (currentIndex is not AVAILABLE) {
            if (searchKey is the same as key in currentIndex) {
                key is found;
            } else {
                index = next index;
            }
        } else {
            if (availableIndex not recorded yet) {
                save this index as the earliest available index;
                index = next index;
            }
        }
    }
    if (key was found or no index was AVAILABLE) {
        return recorded index;
    } else {
        return lastAvailableIndex;
    }
}
```
##### Quadratic probing
- Uses indices k, k + 1, k + 4, k + 9;
    - k + j<sup>2</sup> for as many j's needed
##### Double Hashing
- Uses two hashing functions to probe
- Dependent on search key
- Have nonzero number
- Takes first hashIndex and increments by the value of the second hash function
