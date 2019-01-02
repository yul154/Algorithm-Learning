# Shortest Path problem

## Dijkstra's Algorithm(greedy algorithm)
  1. The distance value initially infinity
  2. Using min priority queue to store distance
  3. Update the node distance adjacnt start node
  4. Always pick the node with the smallest distance value
  5. Updating their distance values if we can decrease it at all
  * O(v^2)
## Knapsack Problem()
  * brute force solution:Try every combination
  1.O(2^n)
  * Faster Algorothm: 
  1. set an arrary which indices mean weight, initial each with 0 value
  2. Update value at correspond index and every thing after it
  3. if met value collision, compare new value or combination with old one , update max value
  4. Iteration over each object
    * O(number of element*Weight),Pseudo-Polynomial time
  * Dynamic Progamming(DP)
    1. breaking one complicated problem to subproblem
    2. store solutions to subproblems in a lookup table(Memoziation)
    3. Create an euqation used at each step to update table
  * Traveling Salesman Problem(TSP): fiding fastest way to travel every city and reture home
    * Exact algorithms(Brute Force,DP):running slower, get correct solution
    * Approximate Algorithm:don't alway find out exact optimal solution but near
      1. Christofides Algorithm: turning graph to a tree,start on root.
  

  
  
