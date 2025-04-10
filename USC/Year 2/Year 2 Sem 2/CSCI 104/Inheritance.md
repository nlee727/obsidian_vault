### Public
User can call the base list functions and break the queue order
### Private
Hide the base class, users can only call derived class interface

For a protected or private inheritance, "as a" or "is implemented in terms of" relationships

### Scoping Base Functions
```c++
else return Car:getmpg();
```
using "::" to call functions from inherited classes

### Composition
Public Inheritance -> "is a" relationship
Composition -> "has a" relationship

- Public inheritance mainly when we want to add or specialize behavior
  #### Assignment of Base/Derived
  Can do person = student, but student = person will not compile because there are attributes in student that will not have full values
- You can also create person *  that points to a student
```c++
Person* pptr = &s;
```
#### Review Question 1
If you have a person* and dereference it, is there a way to get it to use the derived class function
- Use dynamic binding (things that are known at run time not compile time)
```c++
virtual void print_info();
```
If not virtual, it will always use the base class function;

- Abstract class contains pure virtual functions and allows many possible derived implementations
- Any derived implementation will have to conform to these public member functions