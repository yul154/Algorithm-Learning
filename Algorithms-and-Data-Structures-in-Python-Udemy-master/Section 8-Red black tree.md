# Red-black properties:
1. Structure
* Each node is either red or black
* The root node is always black
* Children(NIL or NULL) of all leaves are black
* Every red node must have two black child nodes and no other chidren--> it must have a black parent
* Every path from a given node to any of its descendant NIL/NULL nodes contains the same number of black nodes

2. Operations
* Rotation as same as AVL trees
* Every new node is red b default
* On every insertion, check the tree properties
* If violated, make rotations or just recolor the new node


# Logic
* No path is more tha twice as long as any othe path in the tree

# Case 1: parent and uncle are red(node and uncle in same direction)
1. Swap parent and uncle color from red to black
2. Swap grandparent color from black to red
3. check recursively on the whole tree


# Case 2 : Parent is red and Uncle is black(Uncle and node is in same direction(right or left))
> the node is a right child:
  *  Make a left rotation on the node parent
> the node is a left child 
  * Make a right rotation on the node parent
  
# Case 3: Parent is red and Uncle is black(Uncle and node is in different direction(right or left))
> Node is a left child
* make a right rotation on node grandparent
* Color of parent and grandparent should be swappped
> Node is a right child
* make a left rotation on node grandparent
* color of parent and grandparent should be swapped

# Case 4: Parent and Uncle are red(uncle and node in different direction)
1. recolor parent and uncle
2. check recursively on the whole tree

# 
|Red black tree|AVL trees|
---------------|----------
approximately balanced tree|Rigidly balanced tree
Insert faster(sometime just recolor)| insert and deletion slow ,almost rotate each insertion
Insert intensive tasks|Look-ups faster
