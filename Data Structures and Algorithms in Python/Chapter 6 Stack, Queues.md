# Stacks
* Web browsers store the addresses of visited
* `undo` Mechanism
* it is more efficient in practice to construct a list with initial length n than it is to start with an empty list and append n items

# Queue
* Using an Arrat Circularly: `Queue.dequeue()`-->O(1)
  * front entry= (Front index+1)/len(array) 
```
def dequeue(self):
”””Remove and return the first element of the queue (i.e., FIFO).
                     Raise Empty exception if the queue is empty. ”””
   if self.is empty():
     raise Empty( Queue is empty )
   answer = self.data[self.front]
   self.data[self.front] = None
   self.front = (self.front + 1) % len(self. data) self. size −= 1
   return answer
```

```
def enqueue(self, e):
”””Add an element to the back of queue.””” if self. size == len(self. data):
self.resize(2*len(self.data)) # double the array size avail = (self. front + self. size) % len(self. data)
self.data[avail] = e
self.size += 1
```

```
def resize(self, cap): # we assume cap >= len(self) ”””Resize to a new list of capacity >= len(self).”””
    old = self.data
    self.data = [None]*cap 
    walk = self.front
    for k in range(self. size):
        self. data[k] = old[walk]
        walk = (1 + walk) % len(old) 
        self.front = 0

```

# Double-Ended Queue
> supports insertion and deletion at both the front and the back of the queue
* Implement with Circular Array: All(Opertations) having O(1)
  1. `Deque.last(): `(self.front + self.size − 1) % len(self. data)`
  2. `Deque.front():(self.front − 1) % len(self.data)`

* Deques in Python.collections

Our Deque ADT | collections.deque | Description
--------------|-------------------|---------------
len(D)        | len(D)            | number of elements
D.add first()|D.appendleft( )|add to beginning
D.add last()|D.append( )|add to end
D.delete first()|D.popleft( )|remove from beginning
D.delete last()|D.pop()|remove from end
D.first( )|D[0]|access first element
D.last( )|D[−1]|access last element
 |D[j]|access arbitrary entry by index
 |D[j] = val| modify arbitrary entry by index
 |D.clear( )|clear all contents
 |D.rotate(k)| circularly shift rightward k steps
 |D.remove(e)| remove first matching element
 |D.count(e)| count number of matches for e
