# Pattern-Matching Algorithms
## Basic `str` behaviors
* `find`: Returns the index of the first occurrence of the string searched for(-1 for None)
* `index`:Returns the index of the last occurrence of the string searched for(raises ValueError if not found)
* `count`: the number of substring
* `partition`:Returns a tuple containing the left part of the string split by the specified separator, the separator itself and the right part of the string.
## Brute force
```
def find_brute(T,P):
    n,m=len(T),len(P)
    for i in range(n-m+1):
        k=0
        while k<m and T[k]=P[k]:
            k+=1
        if k==m:
            return i
    return -1
```
* Performance:O(n*m)

## The Boyer-Moore Algorithm
```
def boyer_moore(T,P):
    n,m=len(T),len(P)
    if m==0:return 0
    last={}
    for k in range(m):
        last[p[k]]=k
    i=m-1
    k=m-1
    while i<n:
        if T[i]==P[k]:
            if k==0:
                return 1
            else:
                i-=1
                k-=1
        else:
            j=last.get(T[i],-1)
            i+=m-min(k,j+1)
            k=m-1
    return -1
```
## The Knuth-Morris-Pratt Algorithm
```
def kmp(t,p):
    n,m=len(t),lenz(p)
    if m==0: return 0
    fail=computer_kmp_fail(p)
    j,k=0
    while j<n:
        if t[j]==p[k]:
            if k==m-1:
                return j-m+1
            j+=1
            k+=1
        elif k>0:
            k=fail[k-1]
        else:
            j+=1
    return -1
def compute_kmp_fail(p):
    m=len(p)
    fail=[0]*m
    j,k=1,0
    while j<m:
        if p[j]==p[k]:
            fail[j]=k+1
            j+=1
            k+=1
        elif k>0:
            k=fail[k-1]
        else:
            j+=1
    return fail
```
# Dynamic Programming

