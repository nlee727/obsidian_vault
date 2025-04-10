### Object-Oriented Approach
- Objects fuse data and functions that operate on data into one item.
- Encapsulation - I want to control how other people use my code
- Abstraction - Creating usable and intuitive objects


Classes are the construct used to define objects, their data members, and methods/functions

- Class - Definition/Blueprint of an object
- Object - Instance of the class, actual allocation of memory, variable

### Access Specifiers
- Private, can call or access only by methods that are part of that class
- Public, can call or access by any other code
- Protected, 

- Structs default to public access, classes default to private access

### Constructors/Destructors
Ensures that data is initialized and cleaned up after an object dies

Constructor is a function of the same name as the class itself
```c++
#include<iostream>
#include "deck.h"

Deck::Deck() {
	top_index = 0;
	for(int i=0; i < 52; i++){
		cards[i] = i;
	}
}
```
Destructor is a function of the same name as class itself with a "~" in front.
- Use to free/delete any memory allocated by the object or close bay open file streams.
```c++
Deck::~Deck()
{ /* not needed for this class */ }
```
- Both are called automatically when the object is created or goes out of scope

### Multiple Constructors
- Provides options to client software for how they'd like to initialize the object
```c++
class Student {
	public:
		Student(); // Default ctor
		Student(string name, int id, double gpa);
		// "Initializing" ctor
		
		~Student(); // Destructor
		string get_name();
		int get_id();
	
		double get_gpa();
		void set_name(string name);
		void set_id(int id);
		void set_gpa(double gpa);
	private:
		std::string name_;
		int id_;
		double gpa_;
};

Student::Student()
{
	name_ = "", id_ = 0; gpa_ = 2.0;
}
Student::Student(string name, int id, double gpa)
{
	name_ = name; id_ = id; gpa = gpa_;
}
```

### Writing Member Functions
Compiler needs to know that a function is a member of a class because variables are initialized
Use '::' to check access to private/public variables

### Accessor/Mutator Methods
"get" (accessor)
"set" (mutator)
- Lets other code access desired private data members

### Calling Member Functions
- When outside the class scope, we need to specify with the specific object and dot operator
- When inside the class scope, we can call other member functions directly






