# Stack
* Basic Operations: `pop(),push(),peek()`,all can be done in O(1) 
* LIFO `stack[-1]`
* Implement in DFS ,strong connnection and Euler-cycle in graph

|Stack memory |Heap memory
--------------|-----------
memory size limited| no-limited
fast access  |lower access 
Local variables| Global variables and objects
Space is managed by cpu| Space is managed by programmer
variables can't be resized| variables can be resized
* Stack and Recursion
  1. if we use recursion, The OS will use stacks anyways
  2. The recursive function calls ar pushed onto the stack unitl bumped into the base case
* Applying(Stack) in real world:
  1. back button on browser
  2. undo operation in softwares
  
# Queue
* Basic Operations: `enqueue(),dequeue() and peek()`
* FIFO `queue[0]`
* Implement in BFS

