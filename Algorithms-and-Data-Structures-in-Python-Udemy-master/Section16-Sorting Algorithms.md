# Sorting
* Features
  1. in place: make the sorting operations locally without any additional memory
  2. Recursive:merge sort (divide-conquer)
  3. stable: stable sorting algorithms maintain the relative order of reocrds with equal values
  4. Adaptive: performance rely on existing order(insert sorting)

## Bubble sorting
* bubble up the largest item on every iteration
* stable sorting algorithm
* In-place algorithm
* Time complexity: O(N^2)
```
bubble_sort(array):
   for i in range(len(array)-1):
      for j in range(i):
          if array[j]>array[j+1]:
              swap(j,j+1)
```

## Selection sorting
* Selection smallest value in unsort array, and swipe it with certain position
* No-stable sorting algorithm
* In-place algorithm
* Suitable for small array
* Time complexity:O(N^2)
* Always outperform bubble sort
```
selection_sort(array):
    for i in range(len(array)):
        index=i
        for j in range(i+1,len(array)):
          if array[j]<array[index]:
              index=j
        if index not i:
            swap(index,i)
```
## Insertion sorting
* Insert one element into sorted sublists each time
* Adaptive algorithm
* Stable sort
* In-place algorithm
* Suitable for small array
* Time complexity: O(N^2)
```
insertion_sort(array):
  for i in range(len(array)):
      j=i# expand sorted array
      while j>0 and array[j-i]>array[j]:# sorting sorted array
           swap(j,j-1)
           j=j-1
```
## Quick sorting
* Pick a pivot(if keep choice bad pivot, O(N^2)),partition all element into left section and right section
* No-Stable sort
* In-place  sort
* Time complexity: O(NlogN), O(N^2)(worse case)
* Divde-conquer algorithm(recursive)

```
quick_sort(array,low,high):
  if low>high:
  return
  pivot=partition(array,low,high)
  quick_sort(array,low,pivot-1)
  quick_sort(array,pivot+1,high)

parition(array,low,high):
  pivot=(low+high)//2
  swap(pivot,high)
  i=low
  for j in range(low,high):
      if array[j]<=array[high]:
        swap(j,i)
        i+=1
   swap(i,high)
   return i 
```
## Merge sorting
* Divide-conqure algorithm: divide into array, sort subarrays recursively
* Stable sorting
* Not in-place algorithm
* Time complexity: O(NlogN)
* In general, quicksort outperform mergesort
* Best choice for sorting a linked-list
```
merge(low,high):
  if (low>high)return
  middle=(low+high)/2
  merge(low,middle)
  merge(middle+1,high)
  return sort(lwo,middle,high)

sort(low,high):
  temp=[]
  l,r=0,0
  while l<len(left) && r<len(right):
    if left(l)<right(r):
      temp.append(left[l])
      l++
    else:
      temp.append(right[r])
    temp+=left[l:] and right[r:]
 return temp
```
# Hybrid Algorithms
* Combine algorithms to solve same problem
* Introspective sort: Quicksort(optimal performance)+Heapsort(steady fast average performance)
* Timsort: Insertion sort(small data) +merge sort(optimal in large data)
  * Performance: Best case_O(N),Worse case_O(NlogN),Worse space case_O(N)
 
# No-comparison sorting
* Performance beyond NlogN(low bound in comparsion sorting)

## Counting sort
* value should be interger
* the variant keys is not significantly greater than the number of item
* Running time: O(N+k)
1. iterate throught the orginal array, find K(maximum-minmum+1)
2. mark +1 on the index of counter, which correlated to value of old list
3. traverse the array of counters
```
counting sort(array,max,min):
  counter=[0]* (max-min+1)
  for i in array:
      counter[i-min]+=1
   z=0
  for i in length of counter:
      while counter[i]>0:
          array[z]=i+min
          z+=1
          counter[i]-=1       
``` 
## Radix sort
* Runnin time: O(k* N),k is the number of digits in the input number
* iterate k times, in each iterate,put the value in certain bucket according the value of same digit


