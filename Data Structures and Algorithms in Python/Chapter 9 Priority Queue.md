# Priority Queue ADT
## Operations
* `P.add(k, v)`: Insert an item with key k and value v into priority queue P.
* `P.min()`:Return a tuple, (k,v), representing the key and value of an item in priority queue P with minimum key (but do not re- move the item); an error occurs if the priority queue is empty.
* `P.remove min()`:Remove an item with minimum key from priority queue P, and return a tuple, (k,v), representing the key and value of the removed item; an error occurs if the priority queue is empty.
* `P.is_empty( )`: Return True if priority queue P does not contain any items. Return the number of items in priority queue P.
* `len(P)`:Return the number of items in priority queue P.

# Heaps
>  a more efficient realization of a priority queue
* two properties:
  1. Heap-Order Property(parenties are greater than children)
  2. Complete Binary Tree Property: A heap T storing n entries has height h = [log n]
  
* Up-Heap bubbling after an Inserting
* Down-Heap bubbling after an removing：Put last node to root, consider the smaller key of the two children if root is greater than their children

* Python `heapq` Module

Method|Description
------|------------
heappush(L, e)|Push element e onto list L and restore the heap-order property. The function executes in O(log n) time.
heappop(L)| Pop and return the element with smallest value from list L, and reestablish the heap-order property. The operation executes in O(log n) time.
heappushpop(L, e)|Push elemente on list L and then pop and return the smallest item. The time is O(log n), but it is slightly more efficient than separate calls to push and pop because the size of the list never changes. If the newly pushed el- ement becomes the smallest, it is immediately returned. Otherwise, the new element takes the place of the popped element at the root and a down-heap is performed.
heapreplace(L, e)|Similar to heappushpop, but equivalent to the pop be- ing performed before the push (in other words, the new element cannot be returned as the smallest). Again, the time is O(log n), but it is more efficient that two separate operations.
heapify(L)|Transform unordered list to satisfy the heap-order property. This executes in O(n) time by using the bottom-up construction algorithm.
nlargest(k, iterable)|Produce a list of the k largest values from a given iterable. This can be implemented to run in O(n+klogn) time, where we use n to denote the length of the iterable
nsmallest(k, iterable)|Produce a list of the k smallest values from a given it- erable. This can be implemented to run in O(n + k log n)

# Sorting with a Priority Queue
