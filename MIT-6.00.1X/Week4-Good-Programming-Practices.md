# Testing and Bedugging
> Bugs keep falling into soup
1. check soup for bugs: Testing
  * Compare input/output pairs to specifications
2. keep lid closed: Defensive programming(plans for avoid bugs)
  * specifications for functions:doc strings
  * Modularize:Break a single long function to obvious different pieces
  * Conditions:define input, deliver and ensure those  
3. clean kitchen: eliminate source of bugs(debugging)
  * Look up events leading up to an error
  
# Classes of tests
1. set up guildline
  * break program into modules: testing and debugging individually
  * document constrains: expected input and output
  * document assumptions: your logical thinking
2. Ready to test
  * ensure code runs
  * make a set of expected results
3. Classes of test
  * Unit testing: testing each function separately
  * Regression testing: catch reintroduced errors
  * Integration testing: correct to each other
4. Testing approaches
  * intuition: natural boundary to problem
  * random testing: if no natural boundary
  * black box testing: designed without looking at the code(path specifications(boundary cases))
  * glass box testing: testing directly with code(path-complete(still test boundary cases))
# Bugs
* Overt
1. Overt bug: an obvious manifestation
2. Cover: return a wrong value
* Persistent
1. Persistent: occurs every times code is run
2. Interminttent: only occurs some times even if the input are same

# Exceptions
* `try except`: exceptions raised by any statement in body of try, jump into except block
  * except can be separare clauses：`except errotype`
  * `try except`: handle a situation that some exceptions on data structure
  * `else`: only execute if there no errors, make code more clear
  *  `finally`: always executed after all, looks like close a file
* `raise <exceptionName>(<arguments>)`:just say something when a erro occurred 
 ```
 if something:
    raise Exception('My error!')
 ```
# Assertions
* `assert expression(condition), argument`: Raise an assert error if assumption are not met
* a nice way to doing defensive programming
* easily locate a source of a bug
* check: types,invariants,constraint


