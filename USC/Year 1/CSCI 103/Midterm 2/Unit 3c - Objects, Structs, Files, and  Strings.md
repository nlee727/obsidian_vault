### Objects
Usually higher level concepts (beyond an integer, char, etc.)

Contain data members and methods/functions
- Data needed to model the object & code that operates on the object

### C++ Objects: Structs vs. Classes
- Struct originated in the C language, predecessors of classes

### Type and Instances
- A type indicates how much memory, what the bits mean, what operations can be performed
- They are like the blueprints

- A variable or object is an actual instance (allocation of memory) for one of these types

### Membership Operator (.)
We use the dot/membership operator to access that member in an instance of the object.

#### Object Assignment
assigning one object to another will perform a member-by-member copy of the entire source object to the destination object.

- the "=" is the only assignment you get for free on an object

## Pointers to Objects
Address of a struct is just its starting address 
```c++
student s1;
student *stu_ptr;
stu_ptr = &s1
```
#### Accessing members from a pointer
```c++
stu_ptr.id = 4; //incorrect
(*stu_ptr).id = 4; //correct
```
### Arrow (->) Operator
Always of the form: ptr_to_struct -> member
Every arrow is one derefrence
```c++
(*stu_ptr).id = 4; 
stu_ptr -> id = 4; //equivalent statement
```


#### When are Pointers to objects used?
Pointers to objects occur commonly when objects are a passed by reference or dynamically allocated

### Text File I/O - 
##### ifstream
behaves exactly like cin
```c++
ifstream ifile("input.txt");

if(ifile.fail()) {
	cout << "Couldn't open file" << endl;
	return 1;
}
```
##### ofstream
behaves exactly like cout
```c++
ofstream ofile("output.txt");
```


## C++ Strings
```c++
#include <string>

string str2 = "CS 103";
string str3("Hello");

str2[5] = '4'; // now str2 = "CS 104";
cout << str2 << endl; // "CS 104"

cin >> str2; // Will adjust to hold whatever the user types
```

#### Behind the Scenes
Dynamically allocates the char array (deep copy)
Can concatenate to a string with the + operator
o(n) runtime

#### String Comparison
C++ strings will perform alphabetical comparison with (<,>, == ) are applied
- Comparison operators do not work with plain old character arrays

Call the .size() or .length() function on a string to get the number of characters stored in the string.

### String <-> Number Conversion
```c++
to_string(int);
to_string(double);

int stoi(string);
unsigned int stoul(string);
double stod(string);
```

