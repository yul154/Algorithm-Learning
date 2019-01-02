# Tree
> A tree starts from root and add data to branches

* Tree is an extension of a linked list
* Terminology
  1. Levels:root level is 1
  2. leaves: no child
  3. Path: a group of connections taken together
  4. Height: height of left is 0
  5. Depth:: inverse with Height
* Tree Traversal
  1. DFS: exploring children nodes is priority
    * Pre-order:Check off a node as u see it before you traverse any further in the tree
    * In-order: Firstly check off left child node,and then check off its parent
    * Post-order: No check off a node until seen all of its children
  2. BFS: visiting every node on the same level is priority
    

* Binary Search Trees(bst): Parents at most have two children
  1. No order
  * Search: O(n)
  * Delete: one Child or child of children move up
  * Insert: Finding a open sopt: O(log(n)) 
  2. In order: every value one the left is smaller than right
  * Search:ave->O(log(n)),worse-> O(n)
  * insert: same
  * Delete: same
* Heap
  1: elements arranged in increasing or decreasing order
  2. don't need binary tree
  3. complete: all level without last one are completely full
  4. Searchl:O(n)
  5. Heapify:reorder the tree by heap property
    * compare it with parents and swapping them
    * Extract:remove root and stick the rightmost left in the root spot
    * O(logn)
* Self-balanced Tree: Tris to minimize the number of levels
  * red-black-tree: 
  1.Node are assigned color property
  2.Every node in tree that doesn't two leaves,must have null leaf nodes(black),
  3.If node red,both its children are black
  4. The root node must be black
  5. path of a node to its children null nodes must contain the same number of black nodes
  6. insertion:insert one new node as a red node
