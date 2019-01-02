# Basics
* Two dimensional array `list[][]`: first parameter is row ,second is column
* Index as key: O(1) of Operations with given index

# Operations
* `lst[:]`: print everything
* `lst[:-1]`: print everything without last one
* `lst[:-2]`: without last two

# Linked list
* Using Linked-list to implement Stack and Queue
* Operations:
  1. Insertion and Remove: 
    * At the begining: O(1)
    * At the end: O(n)
* Doubly linked list
  * Node structure: two references and data
* Linked-list VS Array
  * Search: array is faster than LL
  * Deletion: LL is better than array, array have to reconstruct the order
  * Memory: array better than LL(extra reference memory)
* Impelement
```
class Node:
    def __init__(self,data):
        self.data=data
        self.next=None
class Linkedlist:
    def __init__(self):
        self.head=None
        self.size=0
    def insert(self,data):
        self.size+=1
        new=Node(data)
        if not self.head:
            self.head=new
        else:
            new.next=self.head
            self.head=new
    def size(self):
        return self.size
    def count(self):
        current=self.head
        size=0
        while current:
            size+1
            current=current.next
        return size
    def insert_end(self,data):
        self.size+=1
        new=Node(data)
        current=self.head
        while current.next:
            current=current.next
        current.next=new
    def remove(self,data):
        if self.head is None:
            return
        self.size=self.size-1
        pre=None
        current=self.head
        while current.data!=data:
            pre=current
            current=current.next
        if not pre:
            self.head=current.next
        else:
            pre.next=current.next
    
```
