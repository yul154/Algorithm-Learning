# Graph
* Direction: Edge have a direction
* Connective:
  1. Weak:
  2. Strong:have a path from every node and every other node.
* Graph Representation
  1. Vertex Object:
  2. Edge Object: represented by a list o two elements
  3. Adjacency list:vertex Id Corresponds to the index in array, each sublist contain adjacent nodes
  4. Adjacency Matrices:2D-array,indices of outer and inner array represent nodes Id(ONLY 0 AND 1)
* Graph Traversal
  1. DFS:
    * use stack to store th node we just saw
    * Pick an edge,follow it,mark that node as seen
    * add it to the stack
    * if run out of edges with new node, pop stack
    * Recursive:Picking an edge and mark a node as seen unitl run out of new nodes
    * Time complexity: O(V+E)
  2. BFS:
    * start on one node and marked as seen
    * visit a node adjacent to it, marked the node as seen, add it to a queue
    * 
  3. Eulerian Path:
    * start one node, traverse through all edges and might end up at another node
    * Eulerian circle: traverse every edge only once and end up at the same node
      * Alogrithm: 
      1. start on any vertex, follow edge unitl return back to it
      2. if didn't count every edge, start unseen edge which connect marked node
      3. Find node in common from all path
    * Hamiltonian Path:
      1. traverse all vertex once,start and end with same vertex
     
   
  
