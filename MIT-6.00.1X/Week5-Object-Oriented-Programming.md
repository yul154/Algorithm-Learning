# Object Oritented Programming（data abstraction）
## Object: every individual in computer world
  * define by a type,an internal data representation,a set of procedures for iteraction
  * Each instance is a particular type of object
  * `list` represented internally as linked list
  * distinction between creating a class and using an instance of the class
   1. creating the class: defining the class name,defining class attributes
   2. using the class: creaing new instances of objects, doing opertaions on the instances
  * Advantage of OOP
   1. bundle data into packages: share common attributes
   2. divide-conquer development: implement and test separately, increasd modularity reduces complexity
   3. class make it easy to reuse code 
   4. build layers of object abstractions that inherit behaviors from other classes
## Class
* Class attributes:
 1. data attributes: data structure
 2. procedural attributes(methods): as function
* Data Structure
  * Creat an instance model(data structure) of object in Class: `__init__` method
   * `self` as a parameter: refer to an instance of the class
   * Other parameter means, value passed into instance
   * Use dot notation to access an attribute of an instance
   * data attribute and global variables in totally different frames.If have reference, data attribute would not be changed
* Procedural attributes(methods): a way to manipulate data attributes
  * Method as funtions only work in the class
  * Python always passed the actual object(`self`) as tyhe first argument
  * `.` operator is use to access any attributes(data attribute or method)
  * `__str__`: define `print` function
  * Use `isinstance(object, class)` to check if an object is an object of class
  * Setter,Getter:
   1.don't manipulate the internal representation of an object. Want separate the use of the object from what's inside of it.
   2. Setter is a method to change the binding for internal data attributes
  * `__repr__`: returns a string that looks like a valid Python expression that could be used to recreate an object with the same value.
## Hierarchies
  * parent class(superclass)
  * child class(subclass)
    * inherits all data and behaviors from parent class
    * add more infor and behavior uniquel to themself
    * override behavior:define same method in child class, if want use parent behavior,`parentname.methodname(parameter)`
    * new data attributes from parent class: call `parent.__init__`(constructor) in `__init__` method
    * `__lt__`(`sort()`): sort instance of class by an given data attribute
    * `datatime` : supplies classes for manipulating dates and times in both simple and complex ways
    * comparsion decided by which class used firstly.
  * Generators:
   * `yield` means that is a generator, it pause the execution and return a value
   * `__next__()` starts/resumes execution of the procedure
   * `range()` is a generator
  * Interactions between classes
   * Interactions between same hieranchy
    1.if instance from both parent and child class,`pinstance.__lt__(cinstance)`
   ```
   class MITPerson(Person):
    nextIDNum = 0
    def __init__(self, name):
        Person. __init__ (self, name)# add person __init__ attributes on Mitperson class
        self.IDNum = MITPerson.nextIDNum
        MITPerson.nextIDNum += 1
        
    def getIDNum(self):
        return self.IDNum
        
    def __lt__(self, other):
        return self.IDNum < other.IDNum
        
    def speak(self, utterance):
        return (self.getLastName() + " says: " + utterance)
   ```
   * capture other class instance into a new class:
   ```
   class Grades(object):
    def __init__(self):
        self.students = []
        self.grades = {}
        self.isSorted = True
        
    def addStudent(self, student):
        if student in self.students:
            raise ValueError("Duplicate student")
        else:
            self.students.append(student)
            self.grades[student.getIDNum()] = []
            self.sorted = False    
            
    def addGrade(self, student, grade):# student is of type Student
        try:
            self.grades[student.IDNum()].append(grade)# access other class instance.method()
        except KeyError:
            raise ValueError("Student not in grade book")
            
    def getGrades(self, student):
        try:
            return self.grades[student.getIDNum()][:]
        except KeyError:
            raise ValueError("Student not in grade book")
   ```

 
 
   


