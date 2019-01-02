# List

1. Array:
  * Each element store: value and index
  * time complexity(`len()`): O(1)  
  * cons: add (`insert(index,object)`)and remove element(`list.remove(element)`) from array: O(n)
2. Linked list:
  * Each element store: value, a reference of nex element
  * Add element: assign next reference of new object to old next referene an change the next reference to new object
  * Remove element:change the previous element pointer to next element
  * `doubly linked list`: each element store value, a refernce of next element, a refernce of previous element
  * In high level programming:there is list that has the propoerties of linked-list and array
3. Stack:
  * push`append()`and pop`pop()`
4. Queue:
  * FIFO
  * The first(oldest) element is head, the last(newest) element is tail
  * Enqueue: add new element to tail
  * Dequeue: remove oldest element from head,`from collections import deque`
  * Peek: just look at the head
  * Double-ended queue:dequeue and enqueue from either end(stack+queue)
  * Priority queue:
    1. assign anumerical priority when element insert to queue
    2. remove highest priority when dequeue
    3. if the elements have the same priority, the oldest one firstly dequeue
  
  
 
  
