### Pass by value & Pass by reference
#### Function Signatures/Prototypes:
- At most, 1 return value
	- We only specify type, 0 return values is indicated with "void"
- Passing parameters
	- Formal parameters (n1,n2) in a function
	- Actual parameters (x,y) when calling
	- When called, the parameter variable is copied. (Pass by value)
#### Memory Organization:
- All functions are stored in the "stack" which contain
	- Local variables
	- Arguments to the function
	- Return link (where to return) to the calling code
- Main will pause when a function is called and a new area in the stack is created, and when it ends, it dies (will be overwritten by any other function that is called)

##### Passing Arrays as arguments:
Put empty square brackets after the formal parameter name if it is an array.

#### Arrays and Pass-by Reference:
Single (scalar) variables are passed-by value
- Copy
Arrays are passed by reference
- Link/Starting address
- If you send a google doc link, it is edited and you don't need to return back a link
- To avoid copying a large array
###### Stack View of Passing Arrays:
If you have the start address, you can dig into other function's memories
```c++
// Function that takes an array
int sum(int data[], int size);
int sum(int data[], int size)
{
int total = 0;
for(int i=0; i < size; i++){
total += data[i];
}
return total;
}
int main()
{
int vals[100];
/* some code to initialize vals */
int mysum = sum(vals, 100);
cout << mysum << endl;
// prints sum of all numbers
return 0;
}
```

### More Function Details
#### Function Prototypes:
- The compiler needs to see a function's prototype or definition before it allows a call to that function. The prototype is like a promise to create the function later down the line
- "Compile Error" will occur when a call to a function is encountered before the definition
- Prototypes are necessary because you can have many functions and don't know which to put first **or** not even be able to use both functions at all sequentially.
```c++
int f1(int x)
{
return f2(x-1);
}
int f2(int y)
{
if(y <= 0) return 1;
else return f1(y);
}
int main()
{
cout
```

#### A Function's Signature
- What makes a function signature unique:
	- Name
	- Number and type of arguments
- No 2 functions can have the same signature
- Return type does not make a function unique