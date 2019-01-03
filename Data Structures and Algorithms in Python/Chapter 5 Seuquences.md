# Low level Arrays
## Each cell of an array must use the same number of byte
* Referential arrays: a list or tuple instance using an internal storage mechanism of references
(At the lowest level, stored is a consecutive sequence of memory addresses at which the elements of the sequence reside. )
* Compare array: storing the bits that represent the primary data
  * Pros:  
  1. the overall memory usage will be much lower: explicit storage of the sequence of memory references
  2. primary data are stored consecutively in memory

# Dynamic Arrays
* A list instance maintains an underlying array that often has greater capacity than the current length of the list.


  
