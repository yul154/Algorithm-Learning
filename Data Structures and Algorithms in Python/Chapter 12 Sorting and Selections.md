# Merge Sort
## Divide-Conquer
* Divide: Dividing input data to subsets which directly using a straighrforward method to solve
* Conquer: Recursively solve the subproblems associated with the subsets
* Combine: merge subsolutions into a solutions to the original problem
## Divied-Conquer sorting
1. Dividing input to zero or one element which is already sorted
2. Conquer: recursively sort sequences S1 and S2
3. Combine: Put elements back into S by merging the sorted S1 and S2 into a Sorted sequence
## Array-Based Implementation
```
def merge(S1,S2,S):
    i=j=0
    while i+j<len(S):
        if j==len(S2) or (i<len(S1) and S1[i]<S2[j]):
            S[i+j]=S1[i]
            i+=1
        else:
            S[i+j]=S2[j]
            j+=1
def merge_sort(S):
    if len(S)<2:
        return S
    mid=len(S)//2
    S1=S[:mid]
    S2=S[mid:]
    merge_sort(S1)
    merge_sort(S2)
    return merge(S1,S2,S)
```
## A Bottom-Up (Nonrecursive) Merge-Sort

## Running Time
1. Merge part: O(len(s1)+len(s2))
2. merge_sort part(number of recursion): O(log(len(S)))
3: Total: O(n*log(n))

# Quick Sort
* Divde: select pivot(Last one),put smaller element on the left, greater element on the right
* Recursively sort left and right
* Put left,right back into S
* The height would be linear if the list is already sorted

```
def quicksort(array):
    less=[]
    more=[]
    equal=[]
    if len(array)>1:
        pivot=array[0]
        for i in array:
            if i>pivot:
                more.append(i)
            elif i<pivot:
                less.append(i)
            else:
                equal.append(i)
        return quicksort(less)+equal+quicksort(more)
    else:
        return array
```
## Running Time
* in the worst case, the height of a quick-sort tree is Θ(n), Thus, quick-sort runs in O(n^2)
* The best case for quick-sort on a sequence of distinct elements occurs when subsequences L and G have roughly the same size

## Randomized Quick Sort
* Pick pivots at Random
* Addition optimizations
  1. In-place
```
def quick_Sort(S,a,b):
    if a>=b: return
    pivot=S[b]
    l=a
    r=b-1
    while l<=r:
        while l<=r and S[l]<pivot:
            l+=1
        while l<=r and pivot<S[r]:
            r-=1
        if l<r:
            S[l],S[r]=S[r],S[l]
            l,r=l+1,r-1
    S[l],S[b]=S[b],S[l]
    quick_Sort(S,a,l-1)
    quick_Sort(S,l+1,b)
```
  2. Hybrid Approach: Shell Sort
  
## Linear-Time Sorting: Bucket-Sort and Radix-Sort
* comparison-based sorting has an Ω(nlogn) worst-case lower bound on its running time
* the height of T is at least log(n!)
* Bucket-Sort(stable)
  * Assumption: The range of sequence is not too large
```
def bucket_sort(arr):
    largest=max(arr)
    size=largest/len(arr)
    bucket=[[] for num in range(len(arr))]
    for i in range(len(arr)):
        j=int(arr[i]/size)
        if j!=len(arr):
            bucket[j].append(arr[i])
        else:
            bucket[len(arr)-1].append(arr[i])
    for i in range(len(arr)):
        insert_sort(bucket[i])
    res=[]
    for i in range(len(arr)):
        res+=bucket[i]
    return res
```
    
# Comparing sorting Algorithms
* Selection Sorting: Best cast in O(n^2)
* Insertion Sorting: Insertion-sort is quite effective for sorting sequences that are already “almost” sorted, better in small size
* Heap Sorting: heap-sort tends to be outperformed by both quick-sort and merge-sort on larger sequences, but not stable
* Quick Sorting:  not in must make guarantees on the time needed to complete a sorting operation,default choice for a general-purpose, in-memory sorting algorithm.No stable
* Merge Sorting: Not in-place,guarantees on the time needed
* Bucket-Sort and Radix-Sort:sorting entries with small integer keys, character strings or d-tuples of keys from a discrete range,O(d(n+N))

# Python build-in sorting 
* Decorate-Sort-Undecorate Design Pattern
    1. Each element is temporarily replaced with a “decorated” version(keys)
    2. Sorting based upon the orde of keys
    3. The decorated elements are replaced by the original elements
  
 # Selection
## Prune search(Decease conquer)
* Pruning away a fraction of the n objects and recursively solving the smaller problem.
* Randomized Quick-Select
```
def quick select(S, k):
”””Return the kth smallest element of list S, for k from 1 to len(S).””” 
    if len(S) == 1:
        return S[0]
    pivot = random.choice(S)
    L = [x for x in S if x < pivot] 
    E = [x for x in S if x == pivot] 
    G = [x for x in S if pivot < x] 
    if k <= len(L):
        return quick select(L, k) 
    elif k <= len(L) + len(E):
        return pivot 
    else:
        j = k − len(L) − len(E) 
        return quick select(G, j)
```



