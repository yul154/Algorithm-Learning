# why and why not
## why(TST)
* search is faster than hash map
* save more memory than tires
* Compare dictionary, TST support sort operation very very efficiency
## why not
* Works only for strings


# Ternary search trees（TST）
* Stores single characters or strings on nodes as keys
* Each node has 3 children: less(left child), next character (middle child),greater(right child)

# Tries
* Root node contain NUll
* Have as many edges fro every node as the number of characters in the alphabet

# TST Operation
* `put`: insert a new element into the TST with a given key,compare each characters with same index
* `get`: get an item from TST with a given key, 
   1. faster--> may return after second character(use each character of key)
   2. Hashmap need to consider each charater in hash function

# Application
* **Combine Tries with TST**: a Tries at root, TST at lower level
* Compare Hashing with Tst:

Hashing|TST
-------|----
Need to examine the entire key| Only examine just enough key characters
Search hit and misses cost the same| Search miss may only involve a few characters
The running time and operformane heavily relies on hashfunction| Faster than hashing, more flexible than BST
None| support more opertaions(sorting)
None| Works only for strings

* Applications
1. auto-complete feature 
2. spell-checkers
3. package routing
4. prefix matching
