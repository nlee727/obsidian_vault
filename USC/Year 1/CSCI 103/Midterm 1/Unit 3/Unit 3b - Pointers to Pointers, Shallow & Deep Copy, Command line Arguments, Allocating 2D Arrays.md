#### Invalid Pointers
Address 0 means invalid data, defined by the keyword NULL.
- NULL or nullptr
```c++
if(p != NULL)
```
If p is a valid pointer

#### Character Array
C-star you should think c string

## Pointers to Pointers
A chain of links - check slides

- Referencing a variable is the same as what the variable was holding

#### Checking yourself
Ensure that when you write code, the types match on either side of an operator

- Each * in an expression cancels a * from the variable type
- Each & in the expression adds a * to the variable type

## Arrays of Pointers
If a function has char* or int*, think of char[ ] and int[ ]
- T* $\leftrightarrow$ T[ ]

creating a 2D character array
```c++
char w[8] = "bill";
char x[8] = "Anika";
char y[9] = "Mei";

char* names[3] = {w,x,y};
for(int i=0; i < 4; i++){
	cout << names[i] << endl;
}
```

creating a 2D integer array
```c++
int* mat[4];
mat[1][2] = 5; // goes to index 1 of mat, then index 2 of the array it points to
```
mat is an int**

## Command Line Arguments
```c++
int main(int argc, char* argv[] // equivalent to char** argv ){
// will take the command line argument and convert into character arrays, separated by spaces

// providing enough arguments when they start the program
if(argc < x) {
	cout << "Not enough inputs";
	return 1;
}

int seed = atoi(argv[1]); // "42" => 42

}
```
argc indicates the length of the argv array


## Shallow vs Deep Copy

#### Jagged 2D arrays
Array of pointers



Shallow copy = copies of a pointer but not copies of the data
Deep copy = allocate a whole new array and make copy of the data, not just the pointer
A deep copy takes more work and usually requires allocating an array, Copying data from the old to the new
