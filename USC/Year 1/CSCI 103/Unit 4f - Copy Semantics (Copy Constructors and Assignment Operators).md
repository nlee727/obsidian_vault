##### this pointer
How member functions know which objects data to operate on

The compiler adds an argument to the member function containing the "Object\* this" pointer


## Copy Constructors
A constructor that carries the same data type
Should pass by reference (ideally const reference)

C++ automatically generates a default copy constructor and performs an element by element copy

If an object comes alive, the compiler will call the copy constructor. 

Default assignment and copy constructors perform member-by-member copies (shallow)

If you need more than the default of any of the following: a copy constructor, an assignment operator, and a destructor, then you need all 3.
