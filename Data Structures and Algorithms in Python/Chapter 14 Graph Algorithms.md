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
## DFS
```
def DFS(G,u):
   u.visited()
   for v in u.edge :
      if not v.visited:
         DFS(G,v)
```
* Running Time
 * called at most once on each vertex 
 * every edge is examined at most twice for an undirected graph, once from each of its end vertices, and at most once in a directed graph,
 
 ## BFS
 > traversaling level by level
```
def BFS(s,G,discoversed):
   Q=[s]
   s.visited(True)
   while Q:
       for v in s and not v.visited():
          Q.append(v)
          v.visited(True)
       Q.pop(0)
            
```
# topological ordering
> an ordering such that any directed path in Gì traverses vertices in increasing order.

> a topological ordering if and only if it is acyclic.
 * topological sorting:computing a topo- logical ordering of a directed graph
 ```
 def topological sort(g):
”””Return a list of verticies of directed acyclic graph g in topological order.
    If graph g has a cycle, the result will be incomplete. ”””
     topo = [ ]
     ready = [ ]
     incount = { }
    for u in g.vertices():
        incount[u] = g.degree(u, False) 
        if incount[u] == 0:
           ready.append(u) 
    while len(ready) > 0:
    u = ready.pop( ) 
    topo.append(u)
    for e in g.incident edges(u):
        v = e.opposite(u) 
       incount[v] −= 1
       if incount[v] == 0:
          ready.append(v)
     return topo
 ```
 * Performance :runs in O(n + m) time using O(n) auxiliary space
 
 # Shortest Paths
 ## Weight Graphs
 > a graph that has a numeric label associated with each edge e
 ## Dijkstra's Algorithm
 * Greed method
 * BFS
 * Heap based
 * No negative weight edge
 * Edge relaxation
 ```
 if D[u]+w(u,v)<D[v]:
    D[v]=D[u]+w(u,v)
 ```
 
 ## Implementation
 ```
 def Dijkstra(g,start):
    d={}
    cloud={}
    Q=Heap()
    for v in g.vertives():
        if v==start:
            d[v]=0
        else:
            d[v]=float('inf')
        Q.push(d[v],v)
    while Q:
        key,u=Q.pop()
        cloud[u]=key
        for v in u.connections():
            if v not in cloud:
                weight=e(u,v)
                if d[u]+weight<d[v]:
                    d[v]=d[u]+weight
                    Q.update(d[v],v)
 ```
# Minimum Spanning Trees
 > a tree T that contains all the vertices of G and has the minimum total weight over all such trees.
## Prim-Jarn ́ık Algorithm
> Start an arbitrary vertex,in each iteration, we choose a minimum-weight edge e
* Running time: O(mlogn) 
```
def prim(g):
    start=g.random(vertices)
    unvisited=[v of v in g.vertices() if v is not start]
    Q=heap.push(start.connection of edge)
    tree=[start]
    while unvisited:
       edge=Q.pop()
       cur=edge.opposite()
       tree.append(cur)
       for v in cur.connections:
          if v in unvisited:
             Q.push(edge)
       unvisited.remove(cur)
     return tree
```
 ## Kruskal’s Algorithm
 * Edge based 
 * order edge by increasing weight
 * merge clouds
 * Running time：O(m log n)
  1. Ordering of edges by weight can be implemented in O(m log n).
  2. the management of clusters can be implemented in  O(m + n log n) t）
### Disjoint partitions
* A tree based partition: the root of each node are same (path compression)
```
def find(p):
   if p.parent!=p:
      p.parent=self.find(p.parent)
   return p.parent
   
def union(p,q):
   a=find(p)
   b=find(q)
   if a is not b:
      if a.size>b.size:
        b.parent=a
        a.size+=b.size
      else:
        b.parent=a
        b.size+=a.size
 
 
 
