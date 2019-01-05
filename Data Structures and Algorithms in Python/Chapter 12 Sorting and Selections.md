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
    
# Comparing sorting Algorithms
* Selection s
 
