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
        final int DEFAULT_CAPACITY = 50;
        final int MAX_CAP = 10000;

        public CircularArrayQueue() {
            this(DEFAULT_CAP);
        }

        public CircularArrayQueue(int capacity) {
            if (capacity > MAX_CAP) {
                throw new RuntimeException("Size exceeds max.");
            } else {
                integrityOK = false;
                @SuppressWarning("unchecked")
                T[] tempQueue = (T[]) new Object[capacity + 1];
                queue = tempQueue;
                frontIndex = 0;
                backIndex = 0;
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
            if (queue[frontIndex] == null) {
                queue[frontIndex] = entry;
            } else {
                if (frontIndex == (backIndex + 2) % queue.length) {
                    throw new IllegalStateException("Queue is full.");
                }
                queue[backIndex] = entry;
            }
            backIndex = (backIndex + 1) % queue.length;
        }
        public T dequeue() {
            checkIntegrity();
            if (isEmpty()) {
                throw new IllegalStateException("Queue is empty.");
            }
            T result = queue[frontIndex];
            queue[frontIndex] = null;
            (frontIndex + 1) % queue.length;
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

### Dictionary

### Tree

#### Binary Search Tree

#### Heap

---

## Other Concepts

### Recursion

### Iterators

### Hashing 