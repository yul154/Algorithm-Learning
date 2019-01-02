# Recursion
> A method of solving problems that involves breaking a problem down into smaller and smaller subproblems until you get to a small enough problem that it can be solved trivially

* hint: tuple assignment:(a,b)=(b,a),(a,b,c,d)=(1,2,3,4)

* Usually involves a function calling itself

## Three laws of recursion

1. Must have a base case
2. Must change its state and move toward the base case
3. Must call itself, recursively

```
def listsum(numList):
    if len(numList)==1:# basic case
        return numList[0]
    else:
        return numList[0]+listsum(numList[1:])#changing list toword len(numList)==1
```
* Stack & Recursion
  * base case is peek in Stack frame of the recursion function
  * each enviroment which contain function and local variable as a element on the **stack frame
```
from pythonds.basic.stack import Stack
def toStr(n,base):
    res=''
    s=Stack()
    convertString = "0123456789ABCDEF"
    while n>0:
        if n<base:
            s.push(convertString[n])
        else:
            s.push(convertString[n%base])
        n=n//base
    
    while not s.isEmpty():
        res+=str(s.pop())
    return res
 ```
 ```
 def toStr(n,base):
     convertString = "0123456789ABCDEF"
     if n<base:
        return convertString[n]
     else:
        return toStr(n//base,base)+convertString[n%base]
 ```


* Tower of Hanoi
> Three poles, transfer all dices from one to another one, only move one disk at a time, and they could never place a larger disk on top of a smaller one
1.  Move all but the bottom disk on the initial tower to an intermediate pole
2.  Moves the bottom disk to its final resting place
3.  Move the tower from the intermediate pole to the top of the largest disk
```
def moveTower(height,fromPole, toPole, withPole):
    if heigh>=1:
      moveTower(height-1, fromPole, withPole, toPole)
      moveDisk(fromPole,toPole)
      moveTower(height-1,withPole,toPole,fromPole)
def moveDisk(fp,tp):
    print('moving from',fp,'to',tp)
```
#  Dynamic Programming
> Optimize value
* Greedy Method:try to solve as big a piece of the problem as possible right away
* cons in Recursion: 
  1. only make one change for same targe
  2. re-doing too many calculations: improved by memoization(caching)
```
def rec(lst,targetm,map):
    mincons=target
    if target in lst:
        return 1
        map[target]=1
        return 1
    elif map[target]>0:
        return map[target]
    else:
        for i in [j in lst if j<=target]:
            numcon=1+rec(lst,target-i,map)
        if numcon<mincons:
            mincons=numcon
            map[targe]=mincons
    return mincons
 ```
 * Dynamic: at each step of the algorithm we already know the optimized solution
  1. `optimize_current= optimize(current,optimize_current-1+current)`
  2. `global=optimize(global,optimize_current)`
  
 
