### C Strings
You cannot use operations/operators other than typical array operations are provided because you are comparing starting addresses.

cstring library is provided to perform operations on strings

### Pointers
Example: Google doc link (pointer) vs Attachment

#### C++ Pointer Operators
&(address of op) evaluates to the address of the variable
\* evaluates to the data pointed to by the pointer

& (get link)
\* click on link

##### Generating a Pointer
```c++
int x = 30;
variable = &x;
```

 To declare a pointer, include an asterisk after the type (pointer to an int). That variable can then store pointers to addresses of the given type.
 ```c++
 int* ptr = &x
 double* ptr2 = &z
```

## Pass by Reference
Pass by Reference can swap variables.
Pass by values in a function does not change data in main

```c++
int main(){
int x = 5, y = 7;
swap2(&x, &y);
}

void swap2(int* x, int* y){
int temp = *x;
*x = *y;
*y = temp;
}
```

## Pointer Arithmetic and Arrays

**Array names and pointers are interchangeable**

### Misuse of Pointer
Never want pointer to outlive the variable

### Pointer Arithmetic
dat = &dat[0];
mean the same thing

Pointer arithmetic implicit scales the added value based on the type of pointer

```c++
(*ptr1)++; // increments the derefrenced value
*ptr2++; // increments the pointer
*ptr3++ = 4.0; // set derefrenced value to 4.0 then increment address
```

### const or non-const
A const pointer means we can dereference the pointer to get the data but not use the pointer to change it.

## Dynamic Memory Allocation
- There is ONE primary reason to use dynamic memory allocation and ONE secondary reason
- Primary Reason:
	- If we want to allocate memory in a function and have it stay alive even after the function ends
- Secondary Reason:
	- If we don't know how much memory we'll need until run-time (variable size array)


- A 'new' statement is used if you need extra space, and the system will allocate that memory from the heap and return the address of / pointer to the memory.
- When done, use a 'delete' statement

#### C++ new Operator
- **new** allocates memory from heap. 
```c++
double* dptr = new double; // allocates 1 double and gives the address
*dptr = 0; // to initialize

int *scores = new int[n]; // allocates n integer array
```

- new T or new T[n] returns a **pointer** of type T*

#### C++ delete Operator
- **delete** returns memory to heap
```c++
delete dptr;
delete [] scores; // use [] for arrays
```
- The pointer is not dead, rather the memory the pointer points to

##### Pointer Mistake
Never return a pointer to a local variable
- Pointer will now point to dead memory and the value it was pointing at will be overwritten/corrupted
