ABSTRACT DATA TYPES|DATA STRUCTURE
-------------------|----------------
Specification interface| concrete implementation
behaviors defined by human|interior data structure
have an underlying data structure|None
# Priority queue(ADT)
* Queue with an addtional property: a priority value
* Retrieved first element with highest priority value

##  PQ Operations
* `Insert(data,priority()`
* `getHighestPriorityElement()`: pop element
* `peek()`: return the element with highest priority

# Heap
## why or why not
* why:
 1. accessing element with highest priority take O(1)
 2. Stable running time
 3. In-place algorithm(don't need addition memory)
* why not:
 1. Not stable(not going to maintain the order of items)
## Basic
* A binary tree

* Heap type: min and max heap
 1. Max heap: the root has highest value, the keys of parent are greater than chidlren
 2. Min heap: opposite
 
*  Applications: Dijkstra's, Prims algorithm

* Properoties
 1. Complete:Construct the heap from left to right each level(last level may not be completely full)
 2. The parents have higher priority(access root node  O(1))
 3. There is no priority betwee left child and right child

## Array representation
1. Assign index to every node from root `array[0]` to leaves(from left to right)
2. The priority will be the index in a on dimensional array
3. The index of parent node is i, The index of left child is 2*i+1, The index of right child is 2*i+2

##  Build a heap(insertion)
1. Insert the data to heap by complete principle
2. Check whether the heap properties are met
3. If violated, reconstruct the heap(heapify)
  * Time complexity: O(N)+O(logN)=O(N)
  * just like adding a element to arrat with incremented index

## Remove operation
1. Get rid of the item
2. Put the last item on the hole
3. Heapify
  * Time complexity: delete root node: O(1)+O(logN), delete arbitrary node: O(N)+O(logN)

## Heapsort
* Comparsion-based sorting algorithm
* Taking advantage of heap to find the maximum
* Unstable sort(heapify), but don't need additional memory(in-place algorithm)
* Process:
  1. swapping root and last element, root is no longer part of the tree
  2. put root into array(optional)
  3. heapify the new tree
* Running Time: O(N*logN),need consider each element

## Operation complexities
1. Memorycomplexity:O(N)
2. Find the Maximum: O(1)!!!!
3. Insert new item:O(logN),append it at the end of list, and heapify
4. Remove item(maximum):O(logN),remove root and heapify
  
## Heaps in Python
 ```
from heapq import heappop,heappush,heapify
heap=[]
nums=[12,3,-2,6,4,8,9]
for num in nums:
    heappush(heap,num)
while heap:
    print(heappop(heap))
    
heapify(nums)
print(nums)# in heap order
 ```
  





