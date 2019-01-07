# Graphs
* A graph is connected: for any two vertices, there is a path between them
* Strongly connected: for any two vertices u and v of G , u reaches v and v reaches u. 
* Subgraph: a graph H whose vertices and edges are subsets of the vertices and edges of G
* Spanning subgraph:a subgraph of G that contains all the vertices of the graph G.
* connected components of G: If a graph G is not connected, its maximal connected subgraphs 
* A forest: a graph without cycles
* A tree : a connected forest(there is not necessarily a designated root)
* A Spanning tree: a spanning subgraph that is a tree

# Data Structures for Graphs
1. Edge list:maintain an unordered list of all edges
2. adjacency list:maintain, for each vertex, a separate list containing those edges that are incident to the vertex.
3. adjacency map:the container of all edges incident to a vertex is organized as a map,outgoing vertex as value
4. adjacency matrix:Each entry is dedicated to storing a reference to the edge (u, v) for a particular pair of vertices u and v; if no such edge exists, the entry will be None.

## Edge List(edge-central)
* Performance:
  * Cons: O(the numbers of edge) get edge(u,v),degree(v), incident edges(v)(Return an iteration of all edges incident to vertex v)
  * Pors: Update the graph(add,remove edge or vertex) in O(1), remove_vertex in O(he numbers of edge)

## Ajacenct List(Vertex-central)
* Performance: 
  * easy to do implement edge methods(`get_edge()`,`degree(v)`)
  * `get_edge(u,v)`: O(min(deg(u)),deg(v))
## Adjacency Map 
* Performance
  * `get_edge(u,v)`:O(1)
  *  it essentially achieves optimal running times for all meth- ods, making it an excellent all-purpose choice as a graph representation.
## Adjacency Matrix
* Performance
  * any edge (u,v) can be accessed in worst-case O(1)
  * Adding or removing vertices from a graph, the matrix must be resized.
  * O(n2) space usage of an adjacency matrix is typically far worse than the O(n + m) space required of the other representations
  
  ##  Adjacency Map Implementation
  
  # Graph Treversals
  #
  # Graph Treversals#
  # Graph Treversals
