# Disjoint sets
> Check cycle
* Union-find data structures: keep track of a set of elements partitioned into a number o disjoint(no everlapping)subsets
* represented by linked list and tree(in general)
* Three main operations: `union` and `find` and `makeSet`
  * Makeset: set the parent of the given node to its self(make distinct set)
  * find:represent an set with one of its item, find function going to return the representative(root node)
  * union:merge two disjoint sets together by connecting them according to th representatives(easily unbalance)
    1. union rank--> attached small trees to the root of the larger one
    2. Path compression-->flattening the structure of the tree (set every visited node to be connected to the root)
```
def find(x):# path compression
    if x.parent!=x:
       x.parent=find(x.parent)
    return x.parent
    
def makeset(x):
   x.paren=x
   
def union(x,y):
    rootx=find(x)
    rooty=find(y)
    rootx.parent=rooty

```
# Kruskal Algorithm
* Spanning tree: subgraph that includes all the vertices of graph(may not all edges)
* A tree has several spanning trees
* MST(minimum spanning tree): a spanning tree with minimum edges
* Kruskal-Algorithm
  * sort all edges by their weights(O(E* logE))
  * check cycle--> disjoint sets(O(logV))
  * all vertices in an union, algorithm will done 
 
 # Prim Algorithm(BFS)
 * build the spanning tree from a given vertex(adding the smallest edge to MST)
 * Kruskal is edge basd, Prims is vertex based
 * Two implementations
 1. Lazy: add neighbour edges to the heap without deleting its content
 2. Eager: keep updating the heap if the distance from a vertex to the MST has changed
 * Running time: O(E*logE)(ave),O(E*logV)(worse)
 * additionay memory: O(E）# HEAP
 * Process
 1. consider all edges related to a given vertex
 2. put edge informtaion into heap
 3. pick the one with lowest cost
 4. check disjoint sets
 * Compare Prim and Kruskal
 1. prim is faster in dense graph
 2. Kruskal performs better in sparse graph
 3. Kruskal can perform better if edge sort in O(v)
 4. Prim perfom better if the numbeR of edges is high
 5. Kruskal don't need additional memory(heap)
 
 # Applications of spanning trees
 * Post traveler
 * K-means clustering: stop on connecting witt large weight
