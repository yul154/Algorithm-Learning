# BFS
```
def BFS(vertex):
    queue=Queue()
    Vertex = visited
    queue.enqueue(Vertex)
    while Q not empty:
        actual= queue.dequeue
        for v in actual.neighbors:
          if v is not visited:
            v=visited
            queue.enqueue(v)
```
* Row by row

# DFS
```
def DFS(vertex):
 vertex=visited()
 print vertex
 for v in vertex neighbours:
    if v is no visited:
      DFS(v)
def DFS(vetex):
    vertex=visited()
    stack=Stack()
    stack.push(vertex)
    while stack:
      current=stack.pop()
      for v in current neighbours:
        if v is not visited:
            v=visited()
            stack.push(v)
```
* as deep as possible
* Detecting cycles
* Generating mazes or finding way out of a maze

# Memory complexity
* BFS: O(N) store N/2 leave nodes(one level nodes)
* DFS: O(logN): level of the tree
