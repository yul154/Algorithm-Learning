
# Algorithms 1: Exhaustive enumeration
* Exhaust all possbile options to use
    1. guess a value
    2. check if the solution is correct
    3. keep guessing until all value guesses

# Algorithms 2: Approximate sloutions
* tradeoff between speed and accuracy

# Algorithms 3: Binary Search 
* pick a middle as one guess
* move guess by middle
* Work on ordering property:the value of function increase as the input value increases
```
x=25
epsilon=0.1
numguesses=0
low=1.0
high=x
middle=(high+low)/2
while abs(middle**2-x)>=epsilon:
    numguesses+=1
    if middle**2<x:
        low=middle
    else:
        high=middle
    middle=(low+high)/2
print('number of guess',numguesses)
print(middle)
```

# Floats and Fractions
* Converting decimal integer to binary
```
def binary(x):
    string=''
    while x>0:
        string+=str(x%2)
        x=x//2
    return int(string[::-1])
```
```
def demical(x):
    string=str(x)[::-1]
    counter=0
    dem=0
    for i in string:
        dem+=2**counter*int(i)
        counter+=1
    return dem
```
* Coverting float to binary
1. Mutiply by a pwoer of two enought to convert into a whole number
2. convert it to binary
3. divde by same power of 2(directly shilt point to right)
  * Internal representation is always an approximations
  * testing equality of floats is not exact(use `abs()`) 
```
p=0
while ((2**p)*x)%1!=0:
        p+=1
num=int(2**p*floatt)
result=''
if num==0:
    result='0'
while num>0:
    result=(num%2)+result
    num=num//2
for i in range(p-len(result))
    result='0'+result
result=result[0:-p]+'.'+result[-p:]
```
* NEWON-RAPHON: update guess=(guess+integar/guess)/2

```
epslion=0.01
y=int(input('Enter an integar'))
guess=y/2.0
while abs(guess*guess-y)-y>epslion:
        guess=guess-（((guess**2)-y)/(2*guess)）
print ('Square root is :'+ guess)
```
```
guess=20
while abs(guess*guess-x)>0.05:
    guess=(guess + x/guess)/2
    print(guess,guess*guess)
```

# Functions
* Decompostion(modularity): Break problem into different-small pieces
* Abstraction: I don't need to know what's inside it as long as I know how it works.
* Function: 
1. are not run until they are 'called'
2. Characteritics:name,parameters(input),docstring(description),body
3. Calling function:
    * Formal parameter: gets bound to the value of Actual parameter when functions is called
    * Creating a new environment when function is called
    * variable which assignment in global environment will change in function scope interior, but will not change in global
    * No `return` in function:Python returns the value `None`
4. `print` VS `return`
    * `return`: only inside a function, `print`：can be used ouside functions
    * `return`: only one `return` executed once, `print`: can executed mutiple times in a function
    * `return`: code after return not executed,`print`: code can executed after `print`
    * `return`: has a value associated with,`print`:has a value associated with,it is simply output directly onto the console
5. Scope
    * Inside a function, can access a variable defined outside
    * Inside a function, can not modify a variable defined outside
6. Iteration VS Recursion
    * Resursion: divide-and-conquer
    1. divide problem into a simpler/smaller version of same problem
    2. keep reducing problem until reach a base case that can be sloved directly
    * Each recursive call to functions will creat new scope
    * Flow of control passes back to the previous scope
    3. Divide-and-conquer: divide a big question to easier sub-problems which solutions can combine to solve the original
```
def tower(n,fr,to,spare):
    if n==1:
        return (fr,to)
    else:
        tower(n-1,fr,spare,to)
        tower(1,fr,to,spare)
        tower(n-1,spare,to,fr)
```
```
# He's also going to assume that rabbits never die and that the female always produces one new pair, one every month from its second month on.
def rabbit(n):
    if n<2:
        return 1
    else:
        return rabbit(n-1)+rabbit(n-2)# last month+ new generate in this month

``` 
7. Files
    * `import filename`: import variables and functions from file
    * Call variable from file , use `filename.variable`
    * `from filename import *`, directlt use variable name
    * File handle: an operating-system independent means to access files
    


 
