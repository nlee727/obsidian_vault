1/09/24,1/11/24,1/16/24

**Abstract Data Type**: Describes what data is stored and what operations are to be performed
- Example: List
    - You can think of a list as the appropriate way of solving the problem with certain operations
**Data Structure:** Specific way of storing the data implement  ing the operations
- Example: Linked List, array
    - All have different costs to the shared operations

# 103 Review
**Stack** is managed for us as we call functions, where local variables are kept
**Heap** is an area of memory that can be allocated and de-allocated during program execution

**Pointers**  are variables whose value is an address of another variable and can be updated
- Declared with int\*, char\*

**C++ Reference Variable** gives an alias to an already declared variable
- Declared with int&, string&
- Does not occupy any memory, just tells the compiler to allow another name to reference another variable
- Input and output of members in method functions
```c++
int y = 3, *ptr;
ptr = &y

int &x = y;
```
##### Null Pointer
- nullptr is better than "NULL" because it isn't always represented with all-bits-equal-zero.
- Assign when a pointer doesn't point to anything
```
g++ -std=c++11 -g -o test test.cpp
```


#### Correct Usage of Pointers
- Can use a pointer to have a function modify the variable of another
- Make sure you don't return a pointer or reference to a dead variable
- Need to return the pointer or save it somewhere in the heap

### Dynamic Allocation
- Need copy constructor, deconstructor, and assignment operator
- If you assign a returned referenced object to another variable, you are making a copy

```c++
Item& buildItem()
{
    Item* x = new Item(4,'hi');
    return *x; 
    //returning dereferenced pointer of something on the heap, return type of function is a reference
}

int main()
{
    Item& i = buildItem();
    Item i = buildItem(); //makes a copy, also has a memory leak as there is no way to access the allocated builditem
}
```

## Classes

##### Const
Const can be used with
- Input arguments to ensure they aren't modified
- After a member function to ensure data members aren't modified by the function
- Return values to ensure they aren't modified

- const references inside of function parameters can take in non const references

##### Constructors
- Initialization Lists are the most efficient means to initialize objects that are part of another class
- Construction Order

##### Friend
```c++
friend Complex operator+(const int&, const Complex&);
```
for having objects access private data members

- Friend classes for having classes grant access to data members of other classes

### Nested Types
Lets you scope the creation of a class inside of another one

In nonmembers,
```c++
ListInt::Item x;
```

Return type of a function is not inside the member function scope
```c++
// requires scoping the type
ListInt::Item* ListInt::find(int v) const
```

### Static Members
Creates a single copy of that data member that is shared amongst all data members of that type

### Singleton
When marking a method as static, it does not run as an instance
- Can access private members of the class

### Default Arguments
```c++
class IntVector{
public:
IntVector(size n = 10);
}

int main()
{
    IntVector vec1(50);
    IntVector vec2;
}
```

- Default aguments must terminate the argument list; a non default argument cannot come after a default argument
```c++
void good1(int a, int b = 10, string s = "hi");

// bad (non-default arg, s, after default arg, b)
void bad1(int a, int b = 10, string s);
```

### Multiple Inclusion
##### Conditional Compiler Directives
```c++
#ifndef STRING_H
#define STRING_H

class string{...};
#endif
```
##### Conditional Compilation
```c++
#ifdef DEBUG
code
#endif
```
-DEBUG in compiler will only run that code
## Operator Overloading
- Two ways to specify an operator overload
    - Global
    - Member function of a class

If left-hand side is a class, it looks for a member function that takes a single argument on the right, if not, it takes the global function.

##### Global Functions
```c++
string operator+(int time, string suf)
{
    stringstream ss;
    ss << time << suf;
    return ss.str;
}


int main()
{
    int hour = 9;
    string suffix = "hi";
    string time = hour + suffix;
    //will compile to
    // string time = operator+(hour, suffix);
}
```
##### Class Members
almost always call the right hand side as a const reference
```c++
Complex Complex::operator+(const Complex &rhs) const //left hand side const
{
    Complex temp;
    temp.real = real + rhs.real;
    temp.imag = imag + rhs.imag;
    return temp;
}
```

```c++
Complex c3 = c1 + c2;
// Same as c3 = c1.operator+(c2);
```

###### Notes
- You can overload any operator except member (.) and scope (::), and ternary (?:)
- You cannot change operator precedence
- Friend functions if left hand side is non member

##### Ostream Overloading
```c++
// in class
friend ostream& operator<<(ostream&, const Complex &c);


ostream& operator<<(ostream &os, const Complex &c)
{
    os << c.real << "," << c.imag << "j";
    //cout.operator<<(c.real).operator<<("",).operator...
}


int main()
{
cout << c1 << c2;
// operator<<( operator<<(cout, c1), c2);
}
```
##### Implicit Type Conversion
```c++
class Student{
    public:
        operator bool() {return gpa>= 2.0;}
        operator int() {return id;}
};

Student s1;
if(s1) //calls bool
    int x = s1; //calls int
```

## Copy Semantics
- Copy Constructor
```c++
Complex c1;
Complex c2 = c1;

Complex c1;
Complex c2(c1);

f(complex c1)
```
```c++
Complex(const Complex& rhs);
```

- Assignment Operator
```c++
Complex c1. c2;
c2 = c1
```
```c++
Complex& operator=(const Complex&);
```
- Needs to check for self assignment
```c++
MyArray& MyArray::operator=(const MyArray &rhs)
{
if(this == &rhs) return *this;
}
```
- existing data
```c++
MyArray& MyArray::operator=(const MyArray &rhs)
{
if(dat) delete dat;
}
```

- Default copy constructor performs shallow copy



