# Low level Arrays
## Each cell of an array must use the same number of byte
* Referential arrays: a list or tuple instance using an internal storage mechanism of references
(At the lowest level, stored is a consecutive sequence of memory addresses at which the elements of the sequence reside. )
* Compact array: storing the bits that represent the primary data
  * Pros:  
  1. the overall memory usage will be much lower: explicit storage of the sequence of memory references
  2. primary data are stored consecutively in memory
```
from array import array# create compact array
primes = array('i', [2,3,5,7])
```

# Dynamic Arrays
* A list instance maintains an underlying array that often has greater capacity than the current length of the list.
* When reserved capacity will eventually be exhausted,the class requests a new, larger array from the system, and initializes the new array so that its prefix matches that of the existing smaller array. 

# Efficiency of Python’s Sequence Types
## List and Tuple
* tuples are typically more memory efficient than lists because there is no need for an underlying dynamic array with surplus capacity
* Constant-Time opertaions: `len()`,`lst[n]`,
* O(n) opertaions: `index()`,`count()`,`del()`,`in`
* Lexicographic Comparisons：`[1,100,3]<=[2,1,4]`
* Mutation behavior:
  * Insert:
  1. inserting at the beginning of a list is most expensive, requiring linear time per operation. 
  2. Inserting at the middle requires about half the time as inserting at the beginning, yet is still Ω(n) time. 
  3. Inserting at the end displays O(1) behavior
  * Remove: every call requires O(n) time.
  * Extend: If the second data set is quite large, there is some risk that the underlying dynamic array might be resized multiple times when using repeated calls to append. With a single call to extend, at most one resize operation will be performed.
  * Construct new list: 
  1.list comprehension syntax is significantly faster than building the list by repeatedly appending
  2. initialize a list of constant values using the multiplication operator is more efficient than building such a list incrementally

## String
* Composing Strings
 1. `string=string+c`(terribly inefficient)--->`string=''.join(c for c in document)`
 
 # Using Array-Based sequences
 
 
 # Multidimensional Data Sets
## Constructing a mutidimensional list
* data = [ [0]* c ]* r :references to the same instance of a list of c zeros

```
data=[[0]*3]*4
data
data[2][0]=100
data# [[100, 0, 0], [100, 0, 0], [100, 0, 0], [100, 0, 0]]
```
* data=[[0]* c for j in range(r)]:ensure that each cell of the primary list refers to an independent instance of a secondary list

  
  

  
