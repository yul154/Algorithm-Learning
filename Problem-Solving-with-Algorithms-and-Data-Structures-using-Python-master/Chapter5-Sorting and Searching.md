# Objective
1. sequential search and binary search
2. 6 types of sorting algorithms
3. hashing technique
4. map ADT

# Searching
> An algorithmic process of finding a particular item in a collection of items.
* Sequential search: searching an item in sequence.
  1. Time complexity: O(n)
  2. Sequential search is improved by ordering the list only in the case where we do not find the item.
* Binary search: examining the middle item. 
   1. If that item is the one we are searching for, we are done. 
   2. If it is not the correct item, we can use the ordered nature of the list to eliminate half of the remaining items. 
   * A good example of divide and conquer strategy.
   * The middle point is not exact middle
   * After each compare, the list need to change
   * Time complexity: O(log n))
   * Cost effective: sort once and search k times or a very large list need to sort
# Hashing
  1. Using a list with each element initialized to the special Python value None
  2. Computing hash value by hash function
  3. load factor into hash table
* Hash function:mapping between an item and the slot where that item belongs in the hash table
  * Perfect hash function: maps each item into a unique slot
  1. Remainder method: takes an item and divides it by the table size, returning the remainder
  2. Folding method: dividing the item into equal-size pieces and then add together to give the resulting hash value.
  3. Mid-square method: square the item, and then extract middle portion of the resulting digits and compute remainder
  4. String method: use `(ord)` function get integars and weight them by position,then remainder
  * Hash function should be efficient,because it not main part of storage and search process
* Collision: two or more items would need to be in the same slot,**rehash**
   1. Linear probing: start at the original position and then move in a sequential manner.
      * Disadvantage: if many collisions occur at the same hash value, a number of surrounding slots will be filled by the linear probing resolution. This will have an impact on other items that are being inserted
   2. “plus 3” probe: once a collision occurs, we will look at every third slot until we find one that is empty
   3. Quadratic probing: if the first hash value is h, the successive values are h+1, h+4, h+9, h+16, and then remainder
   4. Chaining: allows many items to exist at the same location in the hash table and then use searching technique.

# Sorting
>  Placing elements from a collection in some kind of order
*  analyze sorting process
  1. The total number of comparisons: measure a sort procedure
  2. Total number of exchanges : evaluating the overall efficiency of the algorithm
  
## Bubble sort
* Each pass through the list places the next largest value in its proper place
* Swap:
  1. In other language: 
  ```
  temp=n[0]
  n[0]=n[1]
  n[1]=temp
  ```
  2. In python: `n[0],n[1]=n[1],n[0]`
* Implementing in Python:
```
for i in reversed(range(len(n))):
    for j in range(i):
        if n[j]>n[j+1]:
            temp=n[j]
            n[j]=n[j+1]
            n[j+1]=temp
            # n[j],n[j+1]=n[j+1],n[j]
        else:
            continue
```
* Time complexity: O(n^2)
* Advantage: **too many exchange items**. but it will recognize the sorted list and stop

## Selection Sort
 * Finding biggest value by compare and exchange the position between biggest value and last one value in each pass
 * **Each pass have only one pass**
 * Implementing in Python:
```
for i in reversed(range(1,len(n))):# don't need to compare n[0]
    position=0
    max=0
    for j in range(1,i+1):
        if n[j]>max:
            max=n[j]
    position=n.index(max)
    n[position],n[i]=n[i],n[position]
```
* Time complexity:O(n^2):the reduction in the number of exchanges

## Insert Sort
* Insert one element into sorted sublists each time
* Implementing in Python:
```
for index in range(1,len(alist)):

     currentvalue = alist[index]
     position = index

     while position>0 and alist[position-1]>currentvalue:
         alist[position]=alist[position-1]# this is not a complete exchange as was performed in the previous algorithms
         position = position-1

     alist[position]=currentvalue
```
* Time complexity: O(n^2), ** a shift operation requires approximately a third of the processing work of an exchange ** since only one assignment is performed

## Shell Sort(diminishing increment sort)
* Bcs insert sort good at near sorted array, making a sort that more sorted after each pass will highly improve insert sort
* step:
  1. uses gap to create a sublist by choosing all items that are i items apart
  2. Each of sublist can be sorted by an insertion sort(reduce shift) **improvement**
  3. reduce gap
  4. repeat step 1,2
  5. Eventually, a single list is sorted with the basic insertion sort.
* Implementing in Python:
```
def shellsort(alist):
    gap=len(alist)//2
    while gap>0:
        for i in range(gap,len(alist),gap):
            index=i
            current=alist[i]
            while index>=gap and alist[index-gap]>current:
                alist[index]=alist[index-gap]
                index-=gap
            alist[index]=current
        gap//=2
    return alist
```
* Time complexity: betweem O(n) and O(n^2)

## Merge Sort
>  divide and conquer strategy, recursive algorithm 
* Step:
  1. Dividing list to two halvles until sublist is empty or has one item
  2. combining two smaller sorted lists into a single,sorted,new list
* Implementing in Python:
```
def merge_sort(alist):
    if len(alist)>1:
        middle=len(alist)//2
        left = alist[:middle]
        right = alist[middle:]

        merge_sort(left)
        merge_sort(right)
        #left=merge_sort(alist[:middle])
        #right=merge_sort(alist[middle:])
        l,r,n=0,0,0
        while l<len(left) and r<len(right):
            if left[l]<right[r]:
                alist[n]=left[l]
                l+=1
            else:
                alist[n]=right[r]
                r+=1
            n+=1
        while l<len(left):
            alist[n]=left[l]
            n+=1
            l+=1
        while r<len(right):
            alist[n]=right[r]
            r+=1
            n+=1
    return alist
```
* Time complexity : O(nlogn)
  1. split it into havles(logn)
  2. sort sub list(n)
* Space complexity:  requires extra space to hold the two halves
 
## Quick Sort
>  divide and conquer
* Step:
1. Pick up a pivot value
2. traveling from front and rear, if value is greater(less) than pivot in front(rear) side, stop and swith

* Implementing in Python:
```
def qsort(alist):
    if len(alist)<=1:
        return alist
    else:
        pivot=alist[0]
        return qsort([x for x in alist[1:] if x<pivot])+[pivot]+ qsort([x for x in alist[1:] if x>pivot])
```

```
qs = lambda xs : ( (len(xs) <= 1 and [xs]) or [ qs( [x for x in xs[1:] if x < xs[0]] ) + [xs[0]] + qs( [x for x in xs[1:] if x >= xs[0]] ) ] )[0]
```

* Time complexity:nlogn(unstable), worse case: O(n^2), decide by pivot choose
* *median of three*:consider median value of the first, the middle, and the last element in the list
