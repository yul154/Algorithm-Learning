# Program efficiency
* Separete time efficiency and space efficiency
* Tradeoff between time and space
* Measurement: best case, worse case, average case
  1. timer(`time`):computer performances, no access relationship between inputs and time
  2. count of operations:Which operation to count
  3. order of growth:express the growth of a program's runtime as the input size grows.
# Big O notation
  * describe worst case
  * limit thought：drop constants an multiplicative factors,focus on dominant terms: 2n^30+3^n-->3^n
  *  Analyzr statements inside functions
    1. law of addtion: used wit sequential statements
    2. law of multiplication: used with nested statements
# Complexity classes: grows with size of input(length or magnitude)
  * constant: can have a loops o recursive calls,the times is constant(not input)
  * logarithmic:divide the space of search in half each time
  * linear: iterative and recursive are the same order of growth
  * log-linear:Merge sort
  * polynomial: grows with polynomial of size of input
  * exponential:recursibe functions that each call with more than one recrusive call(call recursive and opertaions in one recursive)
# Recursive Complexity
  * linear:just one call each time
  * exponential: more than one call each time

# Search Alogrithms
* linear search: list doesn't have to be sorted
* bisection search(divide-conquer): list must be sorted
* Sort+k * O(log n)< k * O(n): search many times, Sort algorithms will be useful

# Sort Alogrithms
* Bubble Sort: 
  1. compare current point to rest of uncoverd points
  2. Time complexity: O(n^2)
* Selection sort: 
  1.compare current point with rest of points(finding the smallest one), and swap
  2. Time complexity:O(n^2)
* Merge Sort:
  1. divide list and then merge them an linear compare two sublist
  2. Time Complexity:O(n* log(n))
  


  
