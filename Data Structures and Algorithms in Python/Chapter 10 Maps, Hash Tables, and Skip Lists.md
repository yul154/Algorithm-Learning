# Hash Tables
## Array-Based table
1. Can't provide exact length of array
2.  a map’s keys are integers.

## Hash function
* map general keys to corresponding indices in a table`A[h(k)]`
* bucket array: each bucket may manage a collection of items
* Collisions
1. Hash code:maps a key k to an integer
  * Hash code in Python:`hash(x)`
  * only immutable data types are deemed hashable in Python
2. compression function(table size):maps the hash code to an integer within length of a bucket array
* Evaluate hash function
  1. load factor: item num/len(buckets)
  2. rehash: it is a good requirement for the new array’s size to be at least double the previous size

## Sorted Maps
> assuming the keys have a naturally defined order
* Applications:
  1. flight databases

## Skip list

## Sets, Multisets, and Multimaps

### Set
> an unordered collection of elements, without duplicates


### Mutlisets(bag)
> a set-like container that allows duplicates.
1. implement a multiset is by using a map in which the map key is a (distinct) element of the multiset, 
2. the associated value is a count of the number of occurrences of that element within the multiset

### Multimaps
>  the same key can be mapped to multiple values
1.standard dict class as the map, 
2.a list of values as a composite value in the dictionary.()


  
