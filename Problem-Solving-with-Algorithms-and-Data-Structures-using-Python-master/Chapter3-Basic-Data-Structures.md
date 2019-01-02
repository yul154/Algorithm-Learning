# Catalog
1. linear structures
2. stack
3. stack.applications
4. queue
4. queue.applications
5. Linked list
6. Linked list.applications
# Linear Structures
* Two ends
* Distinguishes one linear structure from another: how items are added or removed

# Stack
> An ordered collection of items where the addition of new items and the removal of existing items always takes place at the same end(top)
* Items are closer to the base(bottom end) represent those that have been in the stack longer
* LIFO: last in, first out
* Application：
  1. The order that they are removed is exactly the reverse of the order that they were placed
  2. The order of insertion is the reverse of the order of removal
* Operations in Stack(abstract data type)

Name|Description
----|---------
Stack()| creates a new stack that is empty. It needs no parameters and returns an empty stack.
push(item)| adds a new item to the top of the stack. It needs the item and returns nothing.
pop()| removes the top item from the stack. It needs no parameters and returns the item. The stack is modified.
peek()| returns the top item from the stack but does not remove it. It needs no parameters. The stack is not modified.
isEmpty()| tests to see whether the stack is empty. It needs no parameters and returns a boolean value.
size()| returns the number of items on the stack. It needs no parameters and returns an integer.

* Stack class

```
class Stack:
    def __init__(self):
      self.items=[]
    def isEmpty(self):
        return self.items==[]
    def push(item):
        self.item.append(item)
    def pop(self):
        self.item.pop()
    def peek(self):
        return self.item[-1]
    def size(self):
        return len(self.items)
```
* Infix,Prefix and Postfix
  * Fully parenthesized:The parentheses dictate the order of operations
  * Infix: The operator is in between two operands
  * Prefix:The operators precede two operands that they work on
  * Postfix:The operators come after the corresponding operands
  * Conversion of Infix to other
    1. Conver Infix to fully parethesized
    2. Moving all operator to corresponding right parenthesis will convert to postfix
    2. Moving all operator to corresponding left parenthesis will convert to prefix
  
# Queue
> Add new items at rear, remove existing items at front

* FIFO: first in first out
* Abstract data type 

Operations|Description
---------|--------------
Queue()|creates a new queue that is empty. It needs no parameters and returns an empty queue.
enqueue(item)|adds a new item to the rear of the queue. It needs the item and returns nothing.
dequeue()|removes the front item from the queue. It needs no parameters and returns the item. The queue is modified.
isEmpty()|tests to see whether the queue is empty. It needs no parameters and returns a boolean value.
size()|returns the number of items in the queue. It needs no parameters and returns an integer.

* Queue class
```
class queue:
  def __init__(self):
      self.items=[]
  def enqueue(self):
      self.items.insert(0,item)
  def dequeue(self):
      return self.items.pop()
  def size(self):
      return len(self.items)
  def isEmpty(self):
       return self.items==[]
```
# Deque
> Double-ended queue

* Items operations can be done in either rear or front side
* Abstract data type

Methods|Description 
-------|--------------
Deque()| creates a new deque that is empty. It needs no parameters and returns an empty deque.
addFront(item)| adds a new item to the front of the deque. It needs the item and returns nothing.
addRear(item)| adds a new item to the rear of the deque. It needs the item and returns nothing.
removeFront()| removes the front item from the deque. It needs no parameters and returns the item. The deque is modified.
removeRear()| removes the rear item from the deque. It needs no parameters and returns the item. The deque is modified.
isEmpty()| tests to see whether the deque is empty. It needs no parameters and returns a boolean value.
size()| returns the number of items in the deque. It needs no parameters and returns an integer.
* Deque class

```
class Deque():
    def __init__(self):
        self.items=[]
    def isEmpty(self):
        return self.items==[]
    def addRear(self,item):
        self.items.insert(0,item)
    def addFront(self.item):
        self.items.append(item)
    def removeFront():
        return self.items.pop()
    def removeRear():
        return self.items.pop(0)
    def size(self):
        return len(self.items)
```

# Unordered Lists(linked list)
> A collection of items where each item holds a relative position with respect to the others

* Cannot contain duplicate items
* Abstract data type

Method|Description
------|------------
List()| creates a new list that is empty. It needs no parameters and returns an empty list.
add(item)| adds a new item to the list. It needs the item and returns nothing. Assume the item is not already in the list.
remove(item)| removes the item from the list. It needs the item and modifies the list. Assume the item is present in the list.
search(item)| searches for the item in the list. It needs the item and returns a boolean value.
isEmpty()| tests to see whether the list is empty. It needs no parameters and returns a boolean value.
size()| returns the number of items in the list. It needs no parameters and returns an integer.
append(item)| adds a new item to the end of the list making it the last item in the collection. It needs the item and returns nothing. Assume the item is not already in the list.
index(item)| returns the position of item in the list. It needs the item and returns the index. Assume the item is in the list.
insert(pos,item)| adds a new item to the list at position pos. It needs the item and returns nothing. Assume the item is not already in the list and there are enough existing items to have position pos.
pop()|removes and returns the last item in the list. It needs nothing and returns an item. Assume the list has at least one item.
pop(pos)|removes and returns the item at position pos. It needs the position and returns the item. Assume the item is in the list.

* Linked list class

```
Class node:#data type
      def __init__(self,items):
          self.data=items
          self.next=None
      def getData(self):
          return self.data
      def getNext(self):
          return self.next
      def setData(self,newdata):
          self.data=newdata
      def setNext(self,newnext):
          self.next=newnext
Class Linkedlist:
      def __init__(self):
          self.head=None#the head of list doesn't refer to anything
      def isEmpty(self):
           return self.head==None
      def add(self,data):
          new=Node(data)
          new.setNext(self.head)
          self.head=new
      def size(self):
          current=self.head
          count=0
          while current!=None:
              count+=1
              current=current.getNext()
          return count
       def search(self,item):
            current=self.head
            found=False
            while current!=None and not found:# while loop will stop on 'False'
                  if current.getData==item:
                      found=True
                  else:
                      current=current.getNext()
             
             return found
             
        def remove(self,item):
            current=self.head
            previous=None
            found=False
            while not found:
                if current.getData()==item:
                    found=True
                 else:
                     previous=current
                     current=current.getNext()
             if previous==None:
                self.head=current.getNext()
             else:
                  previous.setNext(current.getNerxt())
                  
         def append(self,item):
            current=self.head
            found= False:
            while current.getNext()!=None:
                  current=current.getNext()
             if current==None:
                 self.head.setNext()=item
             else:
                 current.setNext()=item
                 
          def index(self,item):
              current=self.head
              count=0
              while current!=item:
                    count+=1
                    current=current.getNext()
              return count
          
          def insert(pos,item):
              current=self.head
              count=0
              while count!=pos:
                    current=current.getNext()
                    count+=1
              new=Node(item)
              new.setNext(current)
              current.setData()=new
           
           def pop(self):
               current=self.head
               previous=None
               while current.getNext()!=None:
                    previous=current
                    current=current.getNext()
                
               if previous==None:
                  self.head=None
               else:
                   previous.getNext=None
                   
            def pop(pos):
                current=self.head
                count=0
                previous=None
                while count!=pos:
                      previous=current
                      current=current.getNext()
                if previous==None:
                   self.head=current.getNext()
                else:
                   previous.setNext(current.getNerxt())           
```

# Ordered List
> A collection of items where each item holds a relative position that is based upon some underlying characteristic of the item.

* Abstract data type

Method|Description
------|------------
OrderedList()| creates a new ordered list that is empty. It needs no parameters and returns an empty list.
add(item)| adds a new item to the list making sure that the order is preserved. It needs the item and returns nothing. Assume the item is not already in the list.
remove(item)| removes the item from the list. It needs the item and modifies the list. Assume the item is present in the list.
search(item)| searches for the item in the list. It needs the item and returns a boolean value.
isEmpty()| tests to see whether the list is empty. It needs no parameters and returns a boolean value.
size()| returns the number of items in the list. It needs no parameters and returns an integer.
index(item)| returns the position of item in the list. It needs the item and returns the index. Assume the item is in the list.
pop()| removes and returns the last item in the list. It needs nothing and returns an item. Assume the list has at least one item.
pop(pos)| removes and returns the item at position pos. It needs the position and returns the item. Assume the item is in the list.

* Ordered List Class
  * only modification on `searc` and `add` method

```
def search(self,item):
  current=self.head
  found=False
  stop=False
  while current!=None and not found and not stop:
      if current.getData()=item:
          found=True
      elif current.getData()>item:
          stop=True
      else:
          current=current.getNext()
  return found

def add(self.item):
    previous=None
    current=self.head
    stop=False
    while current!=None and not stop:
        if current.getData()>item:
            stop= True
        else:
            previous=current
            current=current.getNext()
     new=Node(item)
     if previous==None:
        new.setNext(self.head)
        self.head=new
     eles：
        new.setNext(current)
        previous.setNext(new)
        
```

# Analysis of Linked lists
Method|Time complexity
------|---------------
`add(item)`,`isEmpty`|O(1)
`search()`,`remove`,`size()`|O(n)
