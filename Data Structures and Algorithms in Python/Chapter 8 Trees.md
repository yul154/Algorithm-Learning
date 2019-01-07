# General Tree
> Productivity experts say that breakthroughs come by thinking “nonlinearly.”
## The Tree ADT
* Duck Typing: you shouldn't care what type of object you have,just whether or not you can do the required action with your object
## Computing Depth an Height
* Depth(level)
```
def depth(self,p):
    if self.is_root(p):
        return 0
    else:
        return 1+self.depth(self.parent(p))
```
* Height
```
def height(self,p):
    if self.is_left(p):
      return 0
    else:
      return 1+max(self.height(c) for c i self.children(p))
```
# Binary Tree
## Linked structure Binary Tree
* Node
```class   Node: # Lightweight, nonpublic class for storing a node. slots = _element , _parent , _left , _right
      def __init__(self, element, parent=None, left=None, right=None): 
          self. element = element
          self. parent = parent
          self. left = left
          self. right = right
```
* Binary Tree
```
class LinkedBinaryTree(BinaryTree):
    def __init__(self):
”””Create an initially empty binary tree.””” 
      self. root = None
      self.size = 0
```
## Array-Based a Binary Tree
* Assumption(level numbering):based on potential positions within the tree, not actual positions of a given tree
  1. If p is the root of T,then f(p)=0.
  2. If p is the left child of position q, then f(p) = 2f(q)+1. 
  3. If p is the right child of position q, then f(p) = 2f(q)+2.
* Advantage:  a position p can be represented by the single integer f(p),`root`,`parent`,`left`, and `right` can be implemented by arithmetic operations 
* Drawback: 
  1. Some update operations for trees cannot be efficiently supported
  2. The space usage of an array-based representation depends greatly on the shape of the tree

# Tree Traversal Algorithms
## DFS
* Preorder : root first,left subtree second
* Postorder: left subtree first, right subtree second
* Inorder
```
def inorder(self):
    if not self.is_empty():
        for p in self.subtree_inorder(self.root())
          yield p
def subtree_inorder(self,p):
    if self.left(p):
       for other i self.subtree_inorder(self.left(p)):
            yield other
    yield p
    if self.right(p):
         for other i self.subtree_inorder(self.lright(p)):
            yield other
    
```
## BST
* game tree(potential results in next step)
```
def BreastFirst(T):
    Q=queue()
    Q.enqueue(root)
    res=[]
    while Q:
        cur=Q.dequeue()
        res.append(cur)
        for children in cur:
            Q.enqueue()
```

