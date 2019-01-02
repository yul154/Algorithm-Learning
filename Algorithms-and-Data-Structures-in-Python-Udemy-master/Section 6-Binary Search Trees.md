# Advantages
Data structure|Insert|Search|Remove
--------------|------|------|--------
Sorted arrays|O(N)|O(logn)(binary search)|O(N)
Linked list|O(1)insert in head|O(N)|O(1) remove in head|
BST|O(logN)|O(logN)|O(logN)|

# BST
* Every node at most have two children
* Left child is smaller than parent
* Right child is greater than parent
* 2^height-1 =number of node
* keep the height of tree at a minimum:h=logn(balanced),in order to keep running time on log(N)

# Operaions
* Delete:
1. The node is leaf: Search and del, O(logN)
2. The node has two children: 
   1. Looking for the largest item on the left subtree(predecessor)
   2. Finding the smallest item on the right subtree(successor),O(logN)
3. The node has single child: set the pointer from parent to child,O(logN) 
* Traversal
 1. In-order traversal(sorted): visit left subtree->root node-> right subtree recursively
 2. Pre-order traversal:visit root node->left subtree-> right subtree recursively
 3. Post-order traversal: visit left subtree-> right subtree-> node recursively

 

