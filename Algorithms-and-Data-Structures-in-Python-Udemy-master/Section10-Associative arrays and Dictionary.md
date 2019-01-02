# Associative arrays
* Abstract data types
* Composed of a collection of key-value pairs which each key appears only once
* The aim is to reach O(1) running time of operations
* unsupport sorting

# Basic of Hashtables/Dictionary
* if u know the index of each value, The running tim of lookup is just O(1)
* Hash function(key)= index of value
* Modulo operator: H(x)=n(number o keys)%m(number of buckets)
* Collisions: When map two keys to the same bucket
  1. chaining: store in same bucket and use linked-list to connect them
    * no O(1) running time
    * has additional memory cost
  2. Open addressing: generate new index for the item
    * Linear probing:try next slot if collision
    * Quadratic probing:
    * Rehashing:hash the result again to get a empty slot
# Dynamic resizing
* Load factor: n/m, 
1. close to 1, almost full, Running time would be slower
2. close to 0, almost empty, a lot of memory wasted
* Threahold of load factor in python: 2/3
* Complex procedure: rehash all element again

