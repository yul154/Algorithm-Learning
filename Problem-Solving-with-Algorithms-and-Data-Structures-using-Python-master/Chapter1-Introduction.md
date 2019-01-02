# What is Computer Sicence
* View problem in two different way
  * logical view: drive a car
  * physical  view: repair a car

# Porgramming
* Representation of our solutions
* Data types: prive an interpretation for thr binary data

# Data Structure
* Abstract data type(ADT): a logical description of how we view the data and the operations that are allowed without regard to how they will be implemented
* DS: The implementation of abstract data types

# Algorithms
* tradeoff

# Review of Basic Python
## Data types
* Atomic data types
  * Two numeric class: `int`,`float`
  * Bool class(boolean data type):`True`,`False`，
  * Boolean operator: `and`,`or`,`not`
* Collection data types: 
  * Objects of built-in types like (int, float, bool, str, tuple, unicode) are immutable. 
  * Objects of built-in types like (list, set, dict) are mutable.
  1. List(sequences):an ordered collection of zero or more references to Python data objects
     * Comma-delimited values enclosed in square brackets
     * When Python evaluates a list, the list itself is returned
     * `list(range(5,10,2)) ---> [5,7,9]`
     * Repetition operator is that the result is a repetition of references to the data objects in the sequence
```
myList = [1,2,3,4]
A = [myList]*3
print(A)
myList[2]=45
print(A)
```  
Operation Name|	Operator|	Explanation
--------------|---------|-----------------------------
indexing|[ ]|	Access an element of a sequence
concatenation|+|	Combine sequences together
repetition|	*	|Concatenate a repeated number of times
membership|in|Ask whether an item is in a sequence
length	|len|	Ask the number of items in the sequence
slicing|[ : ]|	Extract a part of a sequence
 
> Notice the familiar “dot” notation for asking an object to invoke a method.

Method Name|Use|	Explanation
-----------|---|------------
append|	alist.append(item)|	Adds a new item to the end of a list
insert|	alist.insert(i,item)|	Inserts an item at the ith position in a list
pop|	alist.pop()|	Removes and returns the last item in a list
pop|	alist.pop(i)|	Removes and returns the ith item in a list
sort|	alist.sort()|	Modifies a list to be sorted
reverse|	alist.reverse()|	Modifies a list to be in reverse order
del|	del alist[i]|	Deletes the item in the ith position
index|	alist.index(item)|	Returns the index of the first occurrence of item
count|	alist.count(item)|	Returns the number of occurrences of item
remove	alist.remove(item)	Removes the first occurrence of item

  2. String(sequences):sequential collections of zero or more letters, numbers and other symbols
      * String values are differentiated from identifiers by using quotation marks (either single or double)
      * A major difference between lists and strings is that lists can be modified while strings cannot

Method Name|Use|	Explanation
-----------|---|------------
center|astring.center(w)|	Returns a string centered in a field of size w
count|astring.count(item)|	Returns the number of occurrences of item in the string
ljust|astring.ljust(w)|	Returns a string left-justified in a field of size w
lower|astring.lower()|	Returns a string in all lowercase
rjust|astring.rjust(w)|	Returns a string right-justified in a field of size w
find|astring.find(item)|	Returns the index of the first occurrence of item
split|astring.split(schar)|	Splits a string into substrings at schar

  3. Tuples(sequences): A tuple is a kind of cannot be changed list
     * Written as comma-delimited values enclosed in parentheses
     * Heterogeneous
  4. Set:an unordered collection of zero or more immutable Python data objects
     * Do not allow duplicates
     * written as comma-delimited values enclosed in curly braces
     * Heterogeneous

Operation Name|Operator|	Explanation
--------------|--------|-------------
membership|in|	Set membership
length|len|	Returns the cardinality of the set
/|aset/ otherset|Returns a new set with all elements from both sets
&|aset& otherset|Returns a new set with only those elements common to both sets
-|aset- otherset|Returns a new set with all items from the first set not in second
<=|aset <= otherset|Asks whether all elements of the first set are in the second

Method Name|Use|Explanation
-----------|---|-------------
union|aset.union(otherset)|	Returns a new set with all elements from both sets
intersection|aset.intersection(otherset)|	Returns a new set with only those elements common to both sets
difference|aset.difference(otherset)|	Returns a new set with all items from first set not in second
issubset|aset.issubset(otherset)|	Asks whether all elements of one set are in the other
add|aset.add(item)|	Adds item to the set
remove|aset.remove(item)|	Removes item from the set
pop|aset.pop()|	Removes an arbitrary element from the set
clear|aset.clear()|	Removes all elements from the set

  5. Dictionary: collections of associated pairs of items where each pair consists of a key and a value
     * Unorder
     * written as comma-delimited key:value pairs enclosed in curly brace

Operator|Use|Explanation
--------|---|---------------
[]|myDict[k]|	Returns the value associated with k, otherwise its an error
in|key in|adict	Returns True if key is in the dictionary, False otherwise
del|del adict[key]|	Removes the entry from the dictionary

Method Name|Use|Explanation
-----------|---|-------------
keys|adict.keys()|Returns the keys of the dictionary in a dict_keys object
values|adict.values()|Returns the values of the dictionary in a dict_values object
items|adict.items()|Returns the key-value pairs in a dict_items object
get|adict.get(k)	Returns the value associated with k, None otherwise
get|adict.get(k,alt)	Returns the value associated with k, alt otherwise

## Input and Output
* `input()`:ask a user to enter some data and returns a reference to the data in the form of a ***string***
  * `input()` function takes a single parameter that is a string which often called *prompt*
* Output: `print()` function
  * `print()` displays parameters with a single blank as separator, vhange the separator character by setting the `sep` argument
  * Each print ends with a newline character by default,default can be change with `end` argument
  * `print('%s is %d years ord.' %(name,age) )`
    * Formatted srting is a template
    * `%` format operator: insert value into formated string, value are taken in order(left to right)
    * the letter after format operator tell `%` what type of value can be inserted

|Character|	Output Format
|---------|----------------
|d,i|	Integer
|u|Unsigned integer
|f|Floating point as m.ddddd
|e|Floating point as m.ddddde+/-xx
|E|Floating point as m.dddddE+/-xx
|g|Use %e for exponents less than −4 or greater than +5, otherwise use %f
|c|Single character
|s|String, or any Python data object that can be converted to a string by using the str function.
|%|Insert a literal % character
   * Change filed width
 
|Modifier|Example|Description
|--------|-------|-----------
|number|%20d|Put the value in a field width of 20
|-|%-20d|Put the value in a field 20 characters wide, left-justified
|+|%+20d|Put the value in a field 20 characters wide, right-justified
|0|%020d|Put the value in a field 20 characters wide, fill in with leading zeros.
|.|%20.2f|Put the value in a field 20 characters wide with 2 characters to the right of the decimal point.
|(name)|%(name)d|Get the value from the supplied dictionary using name as the key.

## Control Structures
> iteration and selection
* Iteration
  1. `while`: focuse on conditional judgment 
  2. `for`: loops in iterable collections(sequence)
* Selection
  1. `if else`: binary selection uses
  2. `elif`: multiple choices
  
## Exception Handling
 * Two types of errors
   1. Syntax error
   2. Logic error: exceptions
 * two ways to handle exceptions
   1. `try, except`: program will not terminate but instead will continue on to the next statements
   2. `raise`: the program would still terminate but now the exception that caused the termination is something explicitly created by the programmer
 
## Object-Oriented Programming in Python: Defining Classes
* Classes and objects are the two main aspects of object oriented programming
* Abstract data types to provide the logical description of what a data object looks like (its state) and what it can do (its methods)
```
def gcd(m,n):# Euclid’s Algorithm
    while m%n != 0:
        oldm = m
        oldn = n

        m = oldn
        n = oldm%oldn
    return n

class Fraction:
     def __init__(self,top,bottom): #  constructor: data state
         self.num = top# self be used as a reference back to the object itself
         self.den = bottom# self will never be given an actual parameter value upon invocation

     def __str__(self):  #  all classes have str method that convert an object into a string
         return str(self.num)+"/"+str(self.den)# str method dosn't need other information except the special parameter self
     def show(self):
         print(self.num,"/",self.den)

     def __add__(self,otherfraction): # build in behavior have `__`, add method have two parameters
         newnum = self.num*otherfraction.den + \
                      self.den*otherfraction.num
         newden = self.den * otherfraction.den
         common = gcd(newnum,newden)
         return Fraction(newnum//common,newden//common)

     def __eq__(self, other): #  shallow equality are same reference, deep equality are same value
         firstnum = self.num * other.den
         secondnum = other.num * self.den

         return firstnum == secondnum
```
*  Inhertitance(`subclasses`,`superclasses`): one class to be related to another class

```
class LogicGate:

    def __init__(self,n):
        self.name = n
        self.output = None

    def getName(self):
        return self.name

    def getOutput(self):# When we invoke the getOutput method, the object must first call its performGateLogic method 
        self.output = self.performGateLogic()
        return self.output


class BinaryGate(LogicGate):

    def __init__(self,n):
        LogicGate.__init__(self,n)#  a subclass of LogicGate and will add two input lines

        self.pinA = None
        self.pinB = None

    def getPinA(self):
        if self.pinA == None:# choose pinA by default.
            return int(input("Enter Pin A input for gate "+self.getName()+"-->"))
        else:
            return self.pinA.getFrom().getOutput()

    def getPinB(self):
        if self.pinB == None:
            return int(input("Enter Pin B input for gate "+self.getName()+"-->"))
        else:
            return self.pinB.getFrom().getOutput()

    def setNextPin(self,source):## each togate can choose the proper input line for the connection.
        if self.pinA == None:
            self.pinA = source
        else:
            if self.pinB == None:
                self.pinB = source
            else:
                print("Cannot Connect: NO EMPTY PINS on this gate")


class AndGate(BinaryGate):

    def __init__(self,n):
        BinaryGate.__init__(self,n)

    def performGateLogic(self):

        a = self.getPinA()
        b = self.getPinB()
        if a==1 and b==1:
            return 1
        else:
            return 0

class OrGate(BinaryGate):

    def __init__(self,n):
        BinaryGate.__init__(self,n)

    def performGateLogic(self):

        a = self.getPinA()
        b = self.getPinB()
        if a ==1 or b==1:
            return 1
        else:
            return 0

class UnaryGate(LogicGate):

    def __init__(self,n):
        LogicGate.__init__(self,n)

        self.pin = None

    def getPin(self):
        if self.pin == None:
            return int(input("Enter Pin input for gate "+self.getName()+"-->"))
        else:
            return self.pin.getFrom().getOutput()

    def setNextPin(self,source):# each togate can choose the proper input line for the connection.
        if self.pin == None:
            self.pin = source
        else:
            print("Cannot Connect: NO EMPTY PINS on this gate")


class NotGate(UnaryGate):

    def __init__(self,n):
        UnaryGate.__init__(self,n)

    def performGateLogic(self):
        if self.getPin():
            return 0
        else:
            return 1


class Connector:#  HAS-A Relationship(not hierarchy)

    def __init__(self, fgate, tgate):
        self.fromgate = fgate
        self.togate = tgate

        tgate.setNextPin(self)

    def getFrom(self):
        return self.fromgate

    def getTo(self):
        return self.togate


def main():
   g1 = AndGate("G1")
   g2 = AndGate("G2")
   g3 = OrGate("G3")
   g4 = NotGate("G4")
   c1 = Connector(g1,g3)
   c2 = Connector(g2,g3)
   c3 = Connector(g3,g4)
   print(g4.getOutput())

main()
```
