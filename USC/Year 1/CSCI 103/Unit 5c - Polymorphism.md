Only assign a derived into a base since the derived has everything the base does.

##### When a function gets called
Static Binding
- By default, the type of pointer used will apply the function from the corresponding class
- Only care about the pointer type
Dynamic Binding 
- Virtual functions allow derived classes to call functions based on the type of object pointed to rather than the type of pointer

### Polymorphism
Polymorphism via virtual functions allows one set of code to operate appropriately on all derived types of objects
- One data structure can now reference many types and the code can perform appropriate behavior on each as you iterate over the structure

### Abstract Classes & Pure Virtuals
A class with one or more pure virtuals is called an abstract base class (interface for future derived classes)
- indicated by setting their prototype=0

Functions that are not implemented by the base class must be implemented by the derived class to be able to create an instance of the derived object.

Objects of abstract class may not be declared/instantiated, but references and pointers are legal until each pure virtual function has a definition the class stays abstract.

#### When to use inheritance
Setup interface that allow for new, derived classes to be written in the future that provide additional functionality but still works seamlessly with original code.

## OO Design Principles
- Single Responsibility
	- A class should generally have only one responsibility
- Open/Closed Rule
	- A class should be open to extension but closed to modification. Its behavior can be changed through inheritance/polymorphism

### Virtual Destructors
Classes that have at least 1 virtual function should have a virtual destructor