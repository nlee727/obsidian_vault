Recursive tracing
Efficiency with deque, vector, singly
Project 5 Streams and parsing, knowing when a stream will fail
1 coding with multiple parts

Putting const in front of an argument in a function will protect the argument
Putting const after a member function protects data members (does not work for global functions)
Putting const in front protects the return type e.g. once you return, it cannot be changed
If you have a const item, you can only call const functions on it or else compiler will not work.

Constructor Initialization Lists
Data members are always constructed before the outer class

Friend Function is a global scope function, but can access private data. not a member function

### Operator Overloading
How to decide whether to implement as a member or non-member function
- If the left side is your class, make it a member function, if not, global
```c++
y+5 //same as y.operator+(5)
5+y //use operator+(int, const BigInt& rhs)

w=x+y //+ operator and = operator will run
```


### Copy Constructor
Assignment operator runs when the object on the left is already alive
If a pointer is a data member, use a copy constructor
##### Rule of 3 
If you need any one of the
Destructor, copy ctor, or assignment op
you need all 3

### Inheritance
If you inherit privately, no one but the derived class can access public functions

Inheritance - is a
Composition - has a

### Polymorphism
Go to the classed based on the pointer, determine if it is virtual. if virtual, see what type of object the pointer points at.
Pointers/references to abstract class is legal, but not objects

### Recursion
Practice writing recursion with blocks

