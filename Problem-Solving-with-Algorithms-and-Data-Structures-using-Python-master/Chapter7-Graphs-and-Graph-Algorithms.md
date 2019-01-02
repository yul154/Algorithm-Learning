# Catalog
* defination of graph
* matrix and adjacency list presentations
* dicitonary ADT implementation
* BFS
* DFS
* Dijkstra’s Algorithm
* Prim’s Spanning Tree Algorithm

# Vocabulary of Graph

* Vertex(node):it can have a name which is key, a vertex also have addition information which is payload
* Edge(arc):an edge connects two vertices to show the relationship, edges may be one-way or two-way, if one-way, the graph is driected graph(digraph)
* Weight:edges might be weighted to present a cost to go from one vertex to another
* Path: A sequence of vertices that are connected by edges
* Cycle: A path that starts and ends at the same vertex

## The Graph ADT
Method name| Function
-----------|----------
Graph()| creates a new, empty graph.
addVertex(vert)| adds an instance of Vertex to the graph.
addEdge(fromVert, toVert)| Adds a new, directed edge to the graph that connects two vertices.
addEdge(fromVert, toVert, weight)| Adds a new, weighted, directed edge to the graph that connects two vertices.
getVertex(vertKey)| finds the vertex in the graph named vertKey.
getVertices()| returns the list of all vertices in the graph.
`in`| returns True for a statement of the form vertex in graph, if the given vertex is in the graph, False otherwise.

## Implement in Python
1. An Adjacency Matrix
  * Use a two-dimensional matrix
  * The value that is stored in the cell at the intersection of row v and column w
  * cons: 
    1. A matrix is not a very efficient way to store sparse data
    2. access time:O(1)
  * pors: when the number of edges is large
2. An Ajacency List
  * A master list of all the vertices in the Graph object
  * Each vertex object in the graph maintains a dictionary of the other vertices that it is connected to
  * pros:
    1.Compactly represent a sparse graph
    2.Easily find all the links that are directly connected to a particular vertex.
  * Cons:
    1. slower check connect between two vertices
  * Implement
```
class Vertex:
    def __init__(self,key):
        self.id=key
        self.connectto={}
    def addNeighbor(self.nbr,weight=0):
        self.connectto[nbr]=weight
    def getConnections(self):
        return self.connectto.keys()
    def getId(self):
        return self.id
    def getWeight(self,nbr):
        return self.connectto[nbr]
    def __str__(self):
        return str(self.id)+'connect to'+str([x.id for x in self.connectto])
```
```
class Graph:
    def __init__(self):
        self.vertlist={}
        self.numVertices=0
    def addVertex(self,key):
        self.numVertice+=1
        newVertex=Vertex(key)
        self.verlist[key]=newVertex
        return newVertex
    def getVertex(self,n):
        if n in self.vertlist:
            return self.vertlist[n]
        else:
            return None
    def __contains__(self,n):#in operator
        return n in self.vertList
    def addEdge(self,f,t,cost=0):
        if f not in self.vertlist:
            nv=self.addVertex(f)
        if t not in self.vertlist:
            nv=self.addVertex(t)
        self.vertlist[f].addNeightbor(self.vertlist[t],cost)
    def getVertices(self):
        return self.vertlist.keys()
    def __iter__(self):
        return iter(self.vertlist.values())
```


## BFS
>  it finds all the vertices that are a distance k from s(start point) before it finds any vertices that are a distance k+1

* Implementation
```
from pythonds.graphs import Graph, Vertex
from pythonds.basic import Queue
def bfs(g,start):
    start.setDistance(0)
    start.setPred(None)
    vertQueue=Queue()
    vertQueue.enqueue(start)
    while (vertQueue.size()>0):
        currentVert=vertQueue.dequeue()
        for nbr in currentVert.getConnections():
            if (nbr.getColor()=='white'):
                nbr.setColor('gray')
                nbr.setDistance(currentVert.getDistance()+1)
                nbr.setPred(currentVert)
                vertQueue.enqueue(nbr)
        currentVert.setColor('black')
```
* Analysis BFS:O(vertices)

### Word Ladder
* At each step you must transform one word into another word, you are not allowed to transform a word into a non-word
```
from pythonds.graphs import Graph
def buildGraph(file):
    d={}
    g=Graph()
    file=open(file,'r')
    for line in file:
        word=line[:-1]
        for i in range(len(word)):
            key=word[:i]+'_'+word[i+1:]
            if key in d:
                d[key].append(word)
            else:
                d[key]=[word]
    for key in d.keys():
        for word1 in d[key]:
            for word2 in d[key]:
                if word1!=word2:
                    g.addEdge(word1,word2)
    return g
```

## The Knight's Tour problem
> Find a sequence of moves that allow the knight to visit every square on the board exactly once.
```
from pythonds.graphs import Graph
def knightGraph(size):
    kng=Graph()
    for row in range(size):
        for col in range(size):
            node_id=Nodeid(row,col,size)
            newp=get_legel_moves(row,col,size)
            for e in newp:
                nid=Nodeid(e[0],e[i],size)
                ktg.addEdge(node_id,nid)
    return kng
def newp(row,column,size):
    return (row*board_size)+column
def get_legel_moves(x,y,size):
    newMoves = []
    moveOffsets = [(-1,-2),(-1,2),(-2,-1),(-2,1),
                   ( 1,-2),( 1,2),( 2,-1),( 2,1)]
    for i in moveOffsets:
        newx=x+i[0]
        newy=y+i[i]
        if legalcoord(newx,size) and legalcoord(newy,size):
            newMoves.append(newx,newy)
    return newMoves
def legalcoord(x,size):
    if s>=0 and x<size:
        return True
    else:
        return False
```
* Implement DFS in Knight Tour
```
from pythonds.graphs import Graph, Vertex
def knightTour(n,path,u,limit):
        u.setColor('gray')
        path.append(u)
        if n < limit:
            nbrList = list(u.getConnections())
            i = 0
            done = False
            while i < len(nbrList) and not done:
                if nbrList[i].getColor() == 'white':
                    done = knightTour(n+1, path, nbrList[i], limit)
                i = i + 1
            if not done:  # prepare to backtrack
                path.pop()
                u.setColor('white')
        else:
            done = True
        return done
```
* Analysis in DFS: O(k^n), n is the number of squares

## General Depth First Search
* `bfs` uses a queue, `dfs` uses a stack(recursive)

```
def def(graph):
   s= Stack()
   for i in graph.vertex:
       s.push(i)
       i.setVisit()
       
       while not s.isEmpty():
          s.pop()
          
          for j in i.connections():
              if not j.getVisit():
                 j.setVisit()
                 s.push(i)
      
```

* Topological sorting
> Applications to indicate the precedence of events
1. call dfs(g)
2. store vertices in a list in decreasing order of finish time
3. return the ordered list as the result of the topological sort

* Strongly connected components
> One graph algorithm that can help find clusters of highly interconnected vertices in a graph
  * Strongly connected: as the largest subset of vertices C⊂V,such that for every pair of vertices v,w∈C. we have a path from v to w and a path from w to v
  * G^t: G graph where all the edges in the graph have been reversed
  1. Call dfs for the graph G to compute the finish times for each vertex.
  2. Compute G^t
  3. Call dfs for the graph G^t, but in the main loop of DFS explore each vertex in decreasing order of finish time.
  4. Each tree in the forest computed in step 3 is a strongly connected component. Output the vertex ids for each vertex in each tree in the forest to identify the component.

## Shortest path problem
1. Dijkstra’s Algorithm(direction graph)
  * it present shortest distance from a given node to other nodes, if the start node change, all shortest distance would be change
  * Greedy ALgorithm: On every iteration we want to find the minimum distance to the next vertex
  * Dijkstra’s algorithm works only when the weights are all positive
  * Must have a complete representation of the graph in order for the algorithm to run
  * Time complexity:O((V+E)log(V))
```
from pythonds.graphs import PriorityQueue, Graph, Vertex
def dijkstra(graph,start):
    pq=PriorityQueue()
    start.setdistance(0)
    pq.buildHeap([(v.getDistance(),v) for v in graph])
    while not pq.isEmpty():
        current=pq.delMin()
        for next_ in current.connections():
            newDist=current.getDistance()+current.getWeight(next_)
            if newDist<next_.getDistance():
                next_.setDistance(newDist)
                next_.setPred(current)
                pq.decreaseKey(next_,newDist)
```

2. Prim’s Spanning Tree Algorithm(undirected graph)
> shortest path to reach every node
* Uncontrolled flooding: 
set a value which greater or equal  the number of edges between start and its most distant, pass on once ,value min 1
* A minimum weight spanning tree: a subset of tree which contain all vertices of G, have minimum sum of weights
* Prim’s algorithm belongs to a family of algorithms called the “greedy algorithms” 
```
from pythonds.graphs import PriorityQueue, Graph, Vertex
def prim(G,start):
    pq=PriorityQueue()
    for v in G:
        v.setDistance(sys.maxsize)
        v.setPred(None)
    start.setdistance(0)
    pq.buildHeap([(v.getDistance(),v) for v in G])
    while not pq.isEmpty():
        current=pq.pop()
        for nextV in current.connections():
            newcost=current.getCost(nextV)
            if nextV in pq, and newcost<nextV.getdistance():
                nextV.setPred(current)
                nextV.setDistance(newcost)
                pq.decreaseKey(nextVert,newCost)
```

# Summary
* Breadth first search for finding the unweighted shortest path.
* Dijkstra’s algorithm for weighted shortest path.
* Depth first search for graph exploration.
* Strongly connected components for simplifying a graph.
* Topological sort for ordering tasks.
* Minimum weight spanning trees for broadcasting messages.
