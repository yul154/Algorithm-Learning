# Binary Search
* Process
  1. set middle,low and high
  2. compare middle and target
  3. if < target, low=middle
  4. if > target, high=middle
* Efficiency: O(logn+1)

# Recursion
> create function that call itself
* At some point call itself
* Have base case:Stop point
* Alter the input parameter at some point

# Sorting
* K*(logn+sorting)<=K*O(n)
* Theory
* Complexity
* In place or not
1. Bublle Sort
  * In each iteration, the biggest element will bubble on up to the top of array
  * Time complexity: O(n^2)
  * Space complexity: O(1)
2. Merge Sort(DC)
  * divde as much as possible subsets and merge subsets and sort by compare
  * Time Complexity:O(n*logn), run each halve in the same time
  * Space complexity:O(n)
  
3. Quick Sort
  * Random pick up a pivot, and put larger to right and smaller to left, recursively pick up one pivot in left and other one in right
  * Each iteration, ensure at least one element in a right place
  * Time complexity:
    1. worst case: O(n^2): near sorted
    2. average and best case: O(nlogn)
  * Space complexity: O(1)



