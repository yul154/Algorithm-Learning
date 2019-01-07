# Binary Search Trees
> an inorder traversal of that subtree will visit those keys in increasing order
## Searching
```
def Search(T,p,k):
    if k==p.key():
        return p
    if k<p.ley() and T.left(p):
       return Search(T,T.left(p),k)
    if k>p.key() and T.right(p):
       return Search(T,T.right(p),k)
    return p
```
## Insertions
```
def Insert(T,k,v):
    p=Search(T,T.root(),k)
    if k==p.key():
      p.val=v
    elif k<p.key():
      p.left(v)
    else:
      P.right(v)
```
## Deletion
* location has at most one child,replaces it with its child (if any)
* Two children,find position (predecessor) containing the item having the greatest key that is strictly less than that of position

# Balanced Search Trees
## AVL
> For every position p of T , the heights of the children of p differ by at most 1.
```
class Node(TreeMap. Node):
”””Node class for AVL maintains height value for balancing.”””
   _height # additional data member to store height
# will be recomputed during balancing
def __init__(self, element, parent=None, left=None, right=None): 
    super().__init__(element, parent, left, right)
    self. height = 0
def left height(self):
    return self. left. height if self. left is not None else 0
def right height(self):
    return self. right. height if self. right is not None else 0
def recomputer_height(self,p):
    p.height=1+max(p.left.height(),p.right.height())
def isbalanced(self, p):
    return abs(p. node.left height( ) − p. node.right height()) <=1
def rebalance(self, p): while p is not None:
      old height = p.node.height 
      if not self.isbalanced(p):
         p = self.restructure(self. tall grandchild(p)) 
         self.recompute_height(self.left(p))
         self.recompute_height(self.right(p))
         self.recompute_height(p)
      if p.node.height == old height:
         p = None 
      else:
          p = self.parent(p)
```
## Splay Trees
> A self-adjusting binary search tree with that recently accessed elements are quick to access again
* Splaying
  1. zig-zig:The node x and its parent y are both left children or both right children.convert x to root
  2. zig-zag:One of x and y is a left child and the other is a right child, convert child to root
  3. zig: no grandparent, convert child to parent
* When tp Splay
  1. When searching for a node, splay it to root
  2. when inserting a key
  3. when deleting a key, splay its parent
```
def splay(self,node):
    paren=self.parent(node)
    grand=self.parent(parent)
    if not grand:
       self.rotate(node)
    elif(parent==self.left(grand)==(node==self.left(parent))):
       self.rotate(parent)
       self.rotate(node)
    else:
        self.rotate(node)
        self.rotate(node)
```
* Analysis Time
  * the overall running time of a search, insertion, or deletion in a splay tree of height h is O(h),
