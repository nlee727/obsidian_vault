## Array Basics
```c++
int scores[150];
// allocates 150 integers with garbage values
```
- Array is a fixed size, named collection of ordered variables of the same type.
	- Cannot grow or shrink
Initialize the array
```c++
for(int i=0; i < 150; i++){
	cin >> scores[i];
// or scores[i] = 0;
}
```
if small enough, use
```c++
int data[5] = {9, 7, 8, 9, 5};
```

```c++
double dec[4] = {0.25, 0.3, 0.18, 0.2};
```

```c++
char str1[3] = {'C', 'S', '\0'};
```

```c++
char str2[3] = "CS";
```

## Lookup Tables
- Consider use of an array as a lookup table if there is little pattern or many cases
- Look-up Table Idea: Store pre-computed results in an array and then "look-up" the desired result using the input as the array index

use in project, use the value of one array and use it as an index

### Dealing with variable size arrays
- allocate a large array of the maximum size potentially needed 
- Use only a portion of it as the program runs
Better to use **Dynamic memory** allocation

- When you access x[2], int at address 7400 + 2 x 4 = 7408
- Because c++ does not perform bounds checking, it will access data beyond the end of the array
- Name of the array gives the starting address of the array

### C-Strings, Cout, and Cin
###### Character Array Cout:
Only character arrays will print out the entire array with cout
- cout will loop over the characters behind the scenes
- cout assumes that you want to print out all the characters in the array
- cout does NOT do this for any other array type
- stops at the null character.

###### Everything Else:
- To print out elements of an array you must use a loop
- No other array type has a null character that means stop

###### Character Array Cin:
You need a for loop to fill in every array but char arrays
- Cin will stop at the next space
- If the user inputs more characters than you have room for cin will not stop but start overwriting memory
- Char array of size n should have n-1 characters types because of the null character

