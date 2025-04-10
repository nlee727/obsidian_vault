## Data Types
A **type** indicates how many bits/bytes of storage are required and how to interpret the number being stored

**Integer**
- Signed by default (positive or negative), or unsigned (positive including 0)
- Express more things with an unsigned in (0 to 4 billion)
```c++
int a = -1;
unsigned int b = 2;
```
**Floating Point Types**
- A float (32 bits) or *double* (64 bits)
```c++
float d1 = 1.5;
double d2 = 3.14;
```
**String/Text Types**
- A single char (1 character)
- character arrays (C-String) / String (C++ string type)
```c++
char e[6] = "Hello";
string f = "Goodbye";
```
**Boolean Type**
- bool (true/false)

## Constants
- Integer
	- 496, -234
- Double
	- 12.0, -16., 4e-2
- Characters enclosed in single quotes (')
	- 'a', '5'
	- '\\n' ( newline), '\\t' (tab)
- Strings (C-String and C++ string type)
	- 0 or more characters between double quotes ("")
	- Array of characters
	- **Ends with a '\0'=0 aka NULL character added as the last byte to allow code to delimit the end of the string**
- Boolean (C++ only) : true, false
	- 0 = false, Everything else = true

## Variables
You must "declare" your variables before assigning to them
```c++ 
int x = 5
double y = 3.14
```
- C++ is a strongly-typed language
	- Requires variables to be declared before being used
## Scope & Initialization
- Scope - who can see and access
	- Global variables declared outside functions are visible to everything in the program
	- Local variables declared inside are only visible in the function and die when the function ends
- Variable Initialization
	- When declared they will have "garbage" values unless you initialize them

## Bits, Bytes, Words
- Bit is binary
- *Byte* is a group of 8-bits
	- Range is 0 to 255
- *Word* varies in size but usually 32-bits (4 bytes)
	- Range is 0 to 4,294,967,295
- A *type* indicates how many bits / bytes of storage are requires and how to interpret the number being stored

## Input and Output
inserts data into output stream
extracts data from input stream
"<<" is the insertion operator
```c++
cout << "Enter the number of bottles: ";
int bottles;
cin >> bottles;
```
You can read more than one value in a single input statement
```c++
cout << "Please enter the number of bottles and cans: ";
int bottles
int cans
cin >> bottles >> cans
```
*endl* = '\\n' + a flush of the output stream
- Use for debugging
#### Keyboard Input
cout for prompt
cin for assigning variables

##### Dealing with Whitespace
- cin SKIPS leading whitespace
- cin STOPS on the first trailing whitespace
##### Timing of Execution
- When reaching a cin statement, either *wait* for input if nothing is in the input stream, or *immediately extract* from the input stream is text is available and convert to desired data type

'>>' operator separates any number of variables you want to read in

## Expressions

#### Casting Motivation:

##### Definition:
Casting: Temporarily converting type of a data value

If you want a double as an output of division, at least one must be a double
- This is called implicit casting

Explicit casting
x+ (double) y / z;
x+ static_cast<double>(y) / z;

Dont try to cast ints to strings
Use #include <string> and string d = to string(c);
int f = stoi(e);


Difference between pre and post increment is in a larger expression
y= x++ + 5;
y= ++x +5;

Other functions
#include<iostream>
#include<math>


rand() returns an integer between 0 and RAND_MAX
using rand() r%m always gives range [0,m-1]

Dice roll - rand()%6 + 1 [1,6]
srand() - seeding
# include <ctime>
srand(time(0))