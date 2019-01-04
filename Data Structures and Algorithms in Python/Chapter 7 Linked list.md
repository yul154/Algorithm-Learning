# Linked list 
## Pros:
* The length of a Linked list as similar as  actual number of elements that it stores
* Insertions and deletions at interior positions of an array are efficient(No update index need)

## Cons:
* Elements of a linked list cannot be efficiently accessed by a numeric index k

# Single Linked List
> 
## Node
* a reference to an object that is an element of the sequence,
* a reference to the next node of the list 
```
class Node:
    def __init__(self,element,next=None):
        self.element=element
        self.next=next
```


## Linked List
* The linked list instance must keep a reference to the head of the list
* Insertiong an Element at the Head
  1. set its next link to refer to the current head 
  2. set the list’s head to point to the new node.
```
New=node(val)
New.next=Head
Head=New
size+=1
```
* Inserting an Element at the Tail
  1. set the next reference of the tail to point to this new node, 
  2. update the tail reference itself to this new node
```
New=Node(val)
New.next=None
Tail.next=New
Tail=New
size+=1
```
* Removing an Element
```
if not head:
  return
 Head=Head.next
 size-=1
```
## Implementing a Stack
*  assumptiong: orient the top of the stack at the head of our list.
```
class LinkedStack:
    def __init__(self):
        self.head=None
        self.size=0
    def __len__(self):
        retur self.size
    def is_empty(self):
        return self.size==0
    def push(self,e):
        New=node(e)
        New.next=self.head
        self.head=New
        #self.head=node(e,self.head)
        self.size+=1
     def top(self):
         if self.is_empty():
            return None
         return self.head
     def pop(self):
         if self.is_empty():
            retunr None
         temp=self.head.element
         self.head=self.head.next
         self.size-=1
         return temp
```
## Implementing a Queue
* use a singly linked list to implement the queue ADT while supporting worst-case O(1)-time for all operations.
* maintain both a head reference and a tail reference 
```
class LinikedQueue:
    def __init__(self):
        self.head=None
        self.tail=None
        self.size=0
    def front(self):
        if self.is_empty():
            return None
        return self.head.element
    def dequeue(self):
        if self.is_empty():
            return None
        temp=self.head.element
        self.head=self.head.next
        self.size-=1
        if self.is_empty():
           self.tail=None
        return temp
     def enqueue(self,e):
         New=node(e)
         if self.is_empty():
            self.head=New
         else:
            self.tail.next=New
         self.tail=New
         self.size+=1
```

# Circularly Linked Lists
> the tail of the list use its next reference to point back to the head of the list
* 
## Implementing a Queue
```
class Circular_Queue:
      def __init__(self)：
          self.tail=None
          self.size=0
      def dequeue(self):
          if self.is_empty():
              return None
          tem=self.tail.next
          if self.size==1:
             self.tail=None
          else:
              self.tail.next=temp.next
          self.size-=1
          return temp
      def enqueue(self,e):
          New=Node(e)
          if self.is_empty():
              New.next=new
          else:
              New.next=self.tail
              self.tail.next=New
          self.tail=New
          self.size+=1
       def rotate(self):
           if self.size>0:
              self.tail=self.tail.next
```
# Doubly Linked list
> each node keeps an explicit reference to the node before it and a reference to the node after it
* Head and Tail nodes do not store elements of the primary sequence.
* header and trailer nodes never change—only the nodes between them change
```
class node:
    def __init__(self,val=None,pre,next):
        self.val=val
        self.pre=pre
        self.next=next
```

```
class DoublyLinked:
    def __init__(self):
        self.head=node(None,None,None)
        self.tail=node(None,None,None)
        self.head.next=self.tail
        self.tail.pre=self.head
        self.size=0
    def insert(self,val,pre,suc):
        New=node(val,pre,suc)
        pre.next=New
        suc.pre=New
        self.size+=1
    def delete(self,node):
        pre= node.pre
        suc=node.next
        pre.next=node.next
        suc.pre=node.pre
        self.size-=1
        node.pre=node.next=node.val=None
```
# Positional List ADT
> Linked List support dices

# Link-Based vs. Array-Based Sequences

## Pros in Array-Based
1. O(1)-time access to an element based on an integer index
2. Array-based representations typically use proportionally less memory than linked structures(next reference).
3. Operations with equivalent asymptotic bounds typically run a constant factor more efficiently with an array-based structure versus a linked structure.
   * enqueue operation for a queue
      *  calculation of the new index  an increment of an integer  storing a reference to the element in the array
      *  the instantiation of a node  appropriate linking of nodes  and an increment of an integer

## Pros in Linked_Based
1. Link-based structures support O(1)-time insertions and deletions at arbitrary position(Positional List ADT)






