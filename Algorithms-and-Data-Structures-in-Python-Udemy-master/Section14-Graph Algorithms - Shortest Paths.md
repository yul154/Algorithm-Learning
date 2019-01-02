# Dijksftra
* Greedy ALgorithm: On every iteration we want to find the minimum distance to the next vertex 
* Only concerned about positive edge weights
* Construct a shortest sparse tree-> from a source to all other nodes min_distane
    * Con:if start point changed, the shrotest path tree would be unuseful
* Time conplexity: O(V* logV +E)
* Appropriate data structure: Heap,priority queue


```
class Node:
     name
     min_distance
     node_predecessor

Dijkstra(Graph,source# start point):
     distance[source]=0
     Q=heap_queue[]
     for v in Graph:
          if v != source:
             distance[v]=inf  #1.initialize min_distances fo all node without start node are infinity
             predecessor[v]=undefined
             add v to Q
          
     while Q:               #2.yield heap for start point
          u=Q.pop()
          for (each neighbor) v of u:     # Check any shorter path 
               tempdist=distance[u]+distance(u,v)
               if tempdist<distance[v]:
                    distance[v]=tempdist# update min_distance
                    predecessor[v]=u
                    Q.push(v)
    return distane[]
               
```

# Bellman-Ford 
* Dynamic Programming
* Slower than Dijkstra, but more robust(handle negative edge weights)
* Dijkstra relaxe on edge at the same time, bellman-ford relax all edges at the same time for V-1 iterations
* If total weifht decreases in the V-th iteration, there is a negative cycle,
* Running time:O(V* E)
* Yen optimization: terminate the algorithm if there is no change in the distance between two iteraions(bublble sort)
```
Bell-man(vertices,edges,start):
     distance[start]=0
     q=[]
     for v in Graph:# 1. initialize
          distance[v]=inf
          predecessor[v]=None
          
     for  i in range(vertice_num -1):# 2.Update min_distance of every node each iteration
          for each edge(u,v) with weight(w):
               temp=distance[u]+w
               if temp<distance[v]:
                    distane[v]=temp
                    predecessor[v]=u
                    
     for each edge(u,v) with weight(w):# 3. check negative cycle
          if distane[u]+w<distance[v]:
               Negatie cycle detected
```

