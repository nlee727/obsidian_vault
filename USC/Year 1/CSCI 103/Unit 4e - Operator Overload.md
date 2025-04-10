## Operator Overloading
Write a custom function to overload an operator
1. Make a global level function
2. As a member function of the class on which it will operate

### Global Functions
Define global functions with name "operator{+,-,...}" with two arguments.
Left is the first argument, right is the second
When the compiler encounters an operator with objects of specific types it will look for an operator function to match and call it.
```c++
string operator+(int time, string suf){
	string res = to_string(time);
	res += suf;
	return res
}

string time = hour + suffix; // will compile
```

### Class Members
Take what is on the lefthand size, and turns it into the calling function, the right being the argument
```c++
Complex c3 = c1 + c2;
// Same as c3 = c1.operator+(c2);
```

### Summary
If the left hand side of the operator is an instance of the class make the operator a member function

if the left hand side is an instance of a different class, make the operator a friend function of the class.