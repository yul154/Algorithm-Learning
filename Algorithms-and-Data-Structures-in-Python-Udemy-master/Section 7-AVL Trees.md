# why and why not
* why: guaranteed log(n), and remain the in-order order, search fast
* why not: after each operation,check and rebalance(lead to a littl bit slower), cost of maintance and spare are large
# Basics
* The heights of the child subtrees of any node differ by at most one
* Checking balanced or not during inserting and deletion operations

# Height
* the height of children(NULL) of leave is -1
* Height=max(left.height(),right.height())+1

# Rotations: rotate the node which unbalanced, not its children 
* doubly-left heavy:
1. make a right rotation
2. the left child of the root node is gonna be the new root node
3. old root node become the right child of new root
4. if the left child have right node. it become old root left child

```
def rotatright(node):
    temp_left=node.left
    temp_node_right=temp_left.right
    temp_left.right=node
    node.left=temp_node_right
    
    node.update_height()
    temp_left.update.height()
    
```
* double-right heavy:
1.make a left rotation
2.root node is going to be child of left node
3. right node is going to be new root node
4. if the right node have left node, it become old root rigth child

* left-right situation:
1. make left child to be left child of sub right child
2. sub right child become left child of root
3. make a right rotation

```
def left_right rotation(node):
    temp_left=node.left
    t_right=temp_left.right
    node.left=t_right
    t_right.left=temp_left
    temp_left.right=None
    #node.right=self.rotateRight(node.right)
    #self.rotateLeft(node)
    
    rotateright(node)  
```

* right-left situation:
1.right child to sub right child
2.sub left child to be right child 
3. make a left rotation
```

```

# AVL sort:
1. insert N items
2. make an in-order-traversal
* Overall complexity: O(N* logN)
