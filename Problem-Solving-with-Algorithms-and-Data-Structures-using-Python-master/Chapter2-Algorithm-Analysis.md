# Algorithm Analysis
* Focus on compare the amount of computing resources that each algorithm uses
   1. resource1: space or memory
   2. resource2: time: two ways to measure
      1. Benchmark analysis
          * Track the actual time 
          * Use `time()`function at begining and end.
          * Disadvasntage:dependent on a particular machine, program, time of day, compiler, and programming language. 
      2. Big-O Notation
          * Order pf magnitude 
          * Written as *O(f(n))*
          * Change each step as basic unit of computation to arithmeic expression
          
|f(n)|Name|
|----|----|
|1|Constant
|logn|Logarithmic
|n|Linear
|nlogn|Log Linear
|n2|Quadratic
|n3|Cubic
|2n|Exponential
   
 
 
 
* Performane of Python Data Structures
  * Measurement: `timeit()`:time how long it takes to execute the statement some number of times
      1. Create a `Timer` object whose two parameters are Python statement and statement that will run once to set up the test
      2. `number` allows you to specify how many times the test statement is executed
      
`t1 = Timer("test1()", "from __main__ import test1")
print("concat ",t1.timeit(number=1000), "milliseconds")# from __main__ import test1 imports the function test1 from the __main__ namespace into the namespace `

  * List: 4 ways to grwo a list
    1. `list=list+[i]`---> slowest
    2. `list.append(i)`---> slower
    3. `list=[i for i in range(1000)]`--->faster
    4. `list=list(range(1000))`---> fastest

Operation|Big-O Efficiency|
---------|----------------|
index []|O(1)
index assignment|O(1)
append|O(1)
pop()|O(1)
pop(i)|O(n)> When you remove the first element of a list, all the other elements of the list must be shifted forward.
insert(i,item)|O(n)
del operator|O(n)
iteration|O(n)
contains(in)|O(n)
get slice [x:y]|O(k)
del slice|O(n)
set slice|O(n+k)
reverse|O(n)
concatenate|O(k)
sort|O(n log n)
multiply|O(nk)

 * Dictioanray

operation|Big-O Efficiency
---------|-----------------
copy|O(n)
get item|O(1)
set item|O(1)
delete item|O(1)
contains (in)|O(1)
iteration	O(n)
