# Tree properties
1. Tree are hierarchical: The more general things near the top and the more specific things near the bottom
2. All of the children of one node are independent of the children of another node
3. Each leaf node is unique

# Vocabulary of Tree
* Node:can have a name(key),may also have additional information(payload)
* Edge:connect two nodes, each node is connected by exactly one incoming edge from another node,but may have several outgoing edges
* Root:node in the tree that has no incoming edges
* Path: an ordered list of nodes that are connected by edges
* Children: The set of nodes c that have incoming edges from the same node to are said to be the children of that node.
* Parent:A node is the parent of all the nodes it connects to with outgoing edges
* Sibling: Nodes in the tree that are children of the same parent are said to be siblings
* Subtree:  a set of nodes and edges comprised of a parent and all the descendants of that parent.
* Leaf Node：No childe node
* Level: The level of a node n is the number of edges on the path from the root node to n
* Height: The height of a tree is equal to the maximum level of any node in the tree
* Binary tree: If each node in the tree has a maximum of two children

# Tree Traversals
>  Patterns to visit all the nodes in a tree.
* Preorder: visit the root node first, and the left subtree, followed by right subtree
* Inorder: Left subtree in first,then root, followed by right subtree
* Postorder: Left subtree, right subtree, root node

# Priority Queue
 > Queue in that you dequeue an item by its priority
 * The highest priority items are at the front of the queue and the lowest priority items are at the back
 * When you enqueue an item on a priority queue, the new item may move all the way to the front
 * Using a binary heap data structure to implement a priority queue
 
# Binary Heap
* Diagram looks like a tree, implement it use a single list as an internal representation
* Min heap: the smallest key is always at the front
* Max heap: the largest ket value is always at the front
* Binary Heap Operations: 

Name|Description
----|------------
BinaryHeap()| creates a new, empty, binary heap.
insert(k)| adds a new item to the heap.
findMin()| returns the item with the minimum key value, leaving item in the heap.
delMin()| returns the item with the minimum key value, removing the item from the heap.
isEmpty()| returns true if the heap is empty, false otherwise.
size()| returns the number of items in the heap.
buildHeap(list)| builds a new heap from a list of keys.

* Binary Heap Implementation
  *  Structure Property1:each level has all of its nodes, exception to this is the bottom level of the tree, which we fill in from left to right
  *  Structure Property2:represent it using a single list
  * Heap Order Property: the key of parent is smaller than or equal to the key of Children
  
 ```
 class Binheap:
    def __init__(self):
        self.heaplist=[0]
        self.currentsize=0
    def insert(self,k):
        self.heaplist.append(k)
        self.currentsize=self.currentsize+1
        self.swag(self.currentsize)
    def swag(self,i):
        while i//2>0:
            if self.heaplist[i]>self.heaplist[i//2]:
                self.heaplist[i],self.heaplist[i//2]=self.heaplist[i//2],self.heaplist[i]
    def delMin(self):
        rem=self.heaplist[1]
        self.heaplist[1]=self.heaplist[self.currentsize]
        self.heaplist.pop()
        self.swagdown(self.heap)
        return rem
    def swagdown(self,i):
        while{i*2}<=self.currentsize:
            child=self.minChild(i)
            if self.heaplist[i]>self.heap[child]:
                tmp=self.heaplist[i]
                self.heaplist[i]=self.heaplist[child]
                self.heaplist[child]=tmp
            i=child
    def minChild(self,i):
        if i*2>self.currentsize:
            return i*2
        else:
            if self.heaplist[i*2]<self.heaplist[i*2+1]:
                return i*2
            else:
                return i*2+1
    def buildHeap(self,alist):
        i=len(alist)//2
        self.currentsize=len(alist)
        self.heaplist=[0]+alist[:]
        while(i>0):
            self.swagdown(i)
            i-=1
 ```
# Binary Search Trees
* Search Tree Operations
1. `map()`: create a new,empty map
2. `put(key,val)`:  Add a new key-value pair to the map. If the key is already in the map then replace the old value with the new value.
3. `get(key)`:given a key, return the valur stored in the map or None otherwise
4. `del`: delelte the key-value pair from the map using a statement of the form `del map[key]`
5. `len()`: Return the nymer of key-value pairs stored in the map
6. `in` :Return True for a statement of the form key in map, if the given key is in the map.

* Search Tree implementation
1. Bst property:keys that are less than the parent are found in the left subtree, keys that are greater than the parent are found in the right subtree
2. All of the keys in the left subtree are less than the key in the root. All of the keys in the right subtree are greater than the root.

```
class BinaryTree:
    def __init__(self,root):
        self.key=root
        self.left=None
        self.right=None
    def insertleft(self,node):
        if self.left==None:
            self.left=BinaryTree(node)
        else:
            self.left,Binarytree(node).left=Binarytree(node).left,self.left
    def put(self,key,val):
        if self.root:
            self._put(key,val,self.root)
        else:
            self.root=TreeNode(key,val)
        self.size=self.size+1
    def _put(self,key,val,currentNode):
        if key<currentNode.key:
            if currentNode.hasLeftChild():
                self._put(key,val,currentNode.leftChild)
            else:
                currentNode.leftChild=TreeNode(key,val,parent=currentNode)
        else:
            if currentNode.hasRightChild():
                self._put(key,val,currentNode.right(key,val,currentNode.rightChild()))
            else:
                currentNode.rightChild=TreeNode(key,val,parent-currentNode)
    def __setitem__(self,k,v):
        self.put(k,v)#self._res[key]=val
    def get(self,key):
        if self.root:
            res=self._get(key,self.root)
            if res:
                return res.payload
            else:
                return None
        else:
            return None
    def _get(self,key,currentNode):
        if not currentNode:
            return None
        elif currentNode.key==key:
            return currentNode
        elif currentNode.key>key:
            return self._get(key,currentNode.leftChild)
        else:
            return self._get(key,currentNode.rightChild)
    def __getitem__(self,key):
            return self.get(key)
    def __contains__(self,key):
        if self._get(key,self.root):
            return True
        else:
            return False
    def delete(self,key):
        if self.size>1:
            nodeToRemove=self._get(key,self.root)
            if nodeToRemove:
                self.remove(nodeToRemove)
                self.size=self.size-1
            else:
                raise KeyError('Not in tree')
        elif self.size==1 and self.root.key==key:
            self.root=None
            self.size=self.size-1
        else:
            raise KeyError('Not in tree')
    def __delitem__(self,key):
        self.delete(key)
    def remove(self,currentNode):
        if currentNode.isLeaf():#no children
            if currentNode==currentNode.parent.leftChild:
                currentNode.parent.leftChild=None
            else:
                currentNode.pafrent.rightChild=None
        elif currentNode.hasBothChildren(): #hastwoChildren
           succ = currentNode.findSuccessor()
           succ.spliceOut()
           currentNode.key = succ.key
           currentNode.payload = succ.payload
        else:# hasoneChildren
            if currentNode.hasLeftChild():
                if currrentNode.isLeftChild():
                    currentNode.leftChild.parent=currentNode.parent
                    currentNode.parent.leftChild=currentNode.leftChild
                elif currentNode.isRightChild():
                    currentNode.leftChild.parent=currentNode.parent
                    currentNode.parent.rightChild=currentNode.leftCHild
                else:
                    currentNode.replaceNode(currentNode.leftChild.key,
                             currentNode.leftChild.payload,
                             currentNode.leftChild.leftChild,
                             currentNode.leftChild.rightChild)
            else:
                if currentNode.isLeftChild():
                    currentNode.rightChild.parent= currentNode.parent
                    currentNode.parent.leftChild=currentNode.rightChild
                elif currentNode.isRightChild():
                    currentNode.rightChild.pafrent=currentNode.parent
                    currentNode.parent.rightChild=currentNode.rightChild
                else:
                    currentNode.replaceNode(currentNode.rightChild.key,
                             currentNode.rightChild.payload,
                             currentNode.rightChild.leftChild,
                             currentNode.rightChild.rightChild)
                    
    def findMin(self):
        current=self
        while current.hasLeftChild():
            current=current.leftChild
        return current
    def find Successor(self):
        succ=None
        if self.hasRightChild():
            succ=self.RightChild.findMin()
        else:
            if self.parent:
                if self.isLeftChild():
                    succ=self.parent
                else:
                    self.parent.rightChild=None
                    succ=self.parent.findSuccessor()
                    self.parent.rightChild=self
        return succ
    def spliceOut(self):
        if self.isLeaf():
            if self.isLeftChild():
                   self.parent.leftChild = None
            else:
                   self.parent.rightChild = None
        elif self.hasAnyChildren():
            if self.hasLeftChild():
                   if self.isLeftChild():
                        self.parent.leftChild = self.leftChild
                    else:
                        self.parent.rightChild = self.leftChild
                        self.leftChild.parent = self.parent
        else:
               if self.isLeftChild():
                    self.parent.leftChild = self.rightChild
                else:
                    self.parent.rightChild = self.rightChild
                    self.rightChild.parent = self.parent
    def __iter__(self):
        if self:
            if self.hasLeftChild():
                 for elem in self.leftChiLd:
                    yield elem # A normal function returns once; a generator function can yield multiple times
        yield self.key
        if self.hasRightChild():
             for elem in self.rightChild:
                yield elem

class TreeNode:
    def __init__(self,key,val,left=None,right=None,parent=None):
        self.key=key
        self.payload=val
        self.leftChild=left
        self.rightChild=right
        self.parent=parent
    def hasLeftChild(self):
        return self.leftChild
    def hasRightChild(self):
        return self.rightChild
    def isLeftChild(self):
        return self.parent and self.parent.leftChild == self
    def isRightChild(self):
        return self.parent and self.parent.rightChild == self
    def isRoot(self):
        return not self.parent
    def isLeaf(self):
        return not(self.rightChild and self.leftChild)
    def hasAnyChildren(self):
        return self.rightChild or self.leftChild
    def hasBothChindren(self):
        return self.rightChild and self.leftChild
    def replaceNode(self,key,value,lc,rc):
        self.key=key
        self.payload=value
        self.leftChild=lc
        self.rightChild=rc
        if self.hasLeftChild():
            self.leftChild.parent=self
        if self.hasRightChild():
            self.rightChild.parent=self
```
* Search Tree analysis
 * Height affect the performance of inner methods(worse is O(n), regular is 0(logn))

##  Balanced Binary Search Tree(AVL)
> The tree remains balanced at all times called an AVL tree
* Balance factor: balanceFactor=height(leftSubTree)−height(rightSubTree)
 1. If the balance factor is zero then the tree is perfectly in balance
 2. The balance factor is -1, 0, or 1
 3. Once the balance factor of a node in a tree is outside this range we will need to have a procedure to bring the tree back into balance.
 * At any time the height of our AVL tree is equal to a constant(1.44) times the log of the number of nodes in the tree
* AVL Tree Implementation 
```
def _put(self,key,val,node):
    if key<node.key:
        if node.hasLeftChild():
            self._put(key,val,node,leftChild)
        else:
            node.leftChild=TreeNode(key,val,parent=node)
            self.Balancing(node.leftChild)
    else:
        if node.hasRightvhilf():
            self._put(key,valu,node,rightChild)
        else:
            node.rightChild=TreeNode(key,val,parent=node)
            self.Balancing(node.rightChild)
def Balancing(self,node):
    if node.balancefactor>1 or node.balancefactor<-1:
        self.rebalance(node)
        return 
    if node.parent!=None:
        if node.isLeftChild():
            node.parent.balancefactor+=1
        elif node.isRightChild():
            node.parent.balancefacotr-=1
        if node.parent.balancefactor!=0:
            self.Balancing(node.parent)
def rotation()
def rebalance()
```

# Summary of Map ADT
operation|Sorted List|	Hash Table|Binary Search Tree|	AVL Tree
---------|-----------|-----------|------------------|----------
put	|O(n)|O(1)|O(n)|O(log2n)
get	|O(log2n)|O(1)|O(n)|O(log2n)
in	|O(log2n)|O(1)|O(n)|O(log2n)
del	|O(n)|O(1)|O(n)|O(log2n)

