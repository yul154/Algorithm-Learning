# Tuple
* Immutable: can't change element values
* Represented with parenthesis`()`
* Indexing and slicing: `tuple[0]`,`tuple[1:2]`
* Concatenated: `tuple1+tuple2`
* Only one element tuple: `(1,)`,comma indicate that is a tuple not just a value
* Swap vairable values: 
```
temp=x
x=y
y=temp
# tuple 
(x,y)=(y,x)
```
* Iterate: `newTup+=(aTup[i],)` NOTICE: comma

# List
* Denoted by square brackets,[]
* Mutable
* Index can be a vairable or expression(int): `list[i-1]`
* Operations: 
  1. dot:object call method
  2. Methods are functions that belong to a class(an object is an instance of a class)
  3. Add:
    * Concatenate: `list1+list2`(didn'change original list)
    * Extend:`list.extend(iterable)`,add element from iterable to list
    * `insert(index,pbject)`: 
    * `append(element)`:add elemtn into end of list
  4. Remove: 
    * `del(list[:])`: slicing remove, avoid IndexError
    * `list.remove(elemnt)`: remove first element by value,raise ValueError()
    *`list.pop(index)`: return value by removed element,raise IndexError()
  5. with String
    * Convert string to list: `list(string)` will create a list within every character
    * Convert words to list:`string.split(default=space)`
    * Convert list ot string:`".join(iterable)`
  6. Change order:
    * sort():mutate original list order
    * sorted(): doesn't mutate and create new one
    * reversed() and reverse()
    * sort() inPython is stable: if keies are same, order in unsort order, reverse is not stabel
  7.`range()`:
    * range(5): (0,1,2,3,4)
    * range(2,6):(2,3,4,5)
    * range(6,1,-2):(6,4,2)
  8. `count(element)`: count the occurance of element
# Mutation,Aliasing,Cloning
* Alisas: same obect have different names
`a=[1,2],b=a,b#alisa# is a(True)`
`a=[1,2],b=[1,2], b#different object# is a(False), a==b(True)`
* because lists are mutable, all alisas pointing to same list object would be affect if object changed
* Cloning:create a new list which every element from old list
  1. a=b[:] not a=b!!
  2. avoid mutatig a list as list are iterating
  ```
  for i in L1:
    if i in L2:
      L1.remove(i)# can't evaluate second element
  # right version
   l1c=l1[:]
   for i in l1c:
      if i in l2:
        l1.remove(i)
  ```
# Functions as objects
* Functions:
  1. have types
  2. can be elements of data structure: `list.append(f(x))`
  3. can appear in expressions `function1(data,functions2)`
    * as part of an assignment statement
    * as an argument(parameter) to a function(higher order functions)
  4. `map`:a general purpose HOP `map(abs,[1,3,-4])`,`map(min,list1,list2)`

# Dictionaries
* store pairs of data(key, value)
* no particular order
* `diciontay[key]--->value`
* Operations
1. add an entry: `dictionary[new_key]=new_value`
2. test a key in dictionary use`in` or use `dict,has_key(key)`
3. `del dictionary[key]`
4. `dictionary.keys()`--> sequence of keys
5. `dictionary.values()`--> sequence of values
* value and key
1. value can duplicates, key must be unique
2. value can be any type(immutable and mutable),key must be immutable
```
def dic_fib(n,d):
  if n in d:
    return d[n]
  else:
    ans=dic_fib(n-1,d)+dic_fib(n-2,d)
    d[n]=ans
    return ans
d={1:1,2:2}
```
* Global variables
1. `global` outside a function has no effect
2. `global` to read and write a global variable inside a function to change value of it 
3. When we create a variable inside a function, it’s local by default
4. `global` is convenient for comparsion among functions and keep track information inside a function


