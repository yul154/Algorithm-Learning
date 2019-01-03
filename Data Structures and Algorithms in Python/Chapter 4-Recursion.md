# Linear Recursion
> If a recursive call starts at most one other
* Reverse a list

```
def rev(lst,l,r):
  if l<=r-1:
      lst[l],lst[r-1]=lst[r-1],lst[l]
      rev(lst,l+1,r-1)
      
def reverse_lst(lst):
    if len(lst)==1:
        return lst
    else:
        return lst[-1:]+reverse_lst(lst[1:-1])+lst[:1]

def reverse(S, start, stop):
”””Reverse elements in implicit slice S[start:stop].”””
    if start < stop − 1:
      S[start], S[stop−1] = S[stop−1],S[start] 
      reverse(S, start+1, stop−1)
  
```
* Power
```
def power(x,n):
    if n==0:
        return 1
    else:
        partial=power(x,n//2)
        result=partial*partial
        if n%2==1:
             return result*x
        return result
```



# Binary Recursion
> If a recursive call may start two others

* Summing the n elements of a sequence

```
def summ(s):
    if len(s)<=1:
        return s[0]
    mid=(0+len(s))//2
    return summ(s[:mid])+summ(s[mid:]) #making a copy of half the list would already take O(n) time,
```

```
def binary sum(S, start, stop):
”””Return the sum of the numbers in implicit slice S[start:stop].”””
   if start >= stop: return 0
   elif start == stop−1: return S[start]
   else:
      mid = (start + stop) // 2
  return binary sum(S, start, mid) + binary sum(S, mid, stop)
```
# Multiple Recursion
> If a recursive call may start three or more others


# Desifning Recursive Algorithms

* Base cases: every possible chain of recursive calls will eventually reach a base case
* Subproblems: have the same general structure as the original problem
* Requires that we redefine the original problem to facilitate similar-looking subproblems
  * Reparameterizing the function: using the additional parameters to demarcate sublists as the recursion proceeds
* Insist on clear signature: update parameters(making a copy of half the list would already take O(n) time)
  * having its body invoke a nonpublic utility function having the desired recursive parameters.

# Eliminating tail recursion
* Stack: convert a recursive algorithm into a nonrecursive algorithm by managing the nesting of the recursive structure ourselves, rather than relying on the interpreter to do so.
* Tail recursion:  recursion can be eliminated without any use of axillary memory.
  1. Must Linear recursion
  2. Recursive call that is made from one context is the very last operation in that context
```
return n*factor(n-1)# multiple after call
```
  3. Any tail recursion can be reimplemented nonrecursively by enclosing the body in a loop for repetition(new parameters by a reassignment of the existing parameters to those values)
