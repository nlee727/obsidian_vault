## Conditional Statements
Use comparison operators
ex. if (x == y)

To indicate what code is part of the condition, use {}
else if (condition)

##### Logical Operators
&& means AND 
	If( (x== 0) && (y== 0) )
|| means OR

##### DeMorgan's Theorem:
!a || !b $\leftrightarrow$ !(a && b)
!a && !b $\leftrightarrow$ !(a || b)

## Iterative Structures/Loops
#### 4 necessary parts of a loop
1) Initialization
2) Condition
3) Body
4) Update

##### While loop:
Essentially a repeating 'if' statement
```c++
int i = 1;
while (i<= 1000)
{
cout << i << endl;
i++;
}
```
For when you **DON'T** know how many times to iterate before the loop starts. 
- Whenever you see or use the word **'until'** 
- "until x" = "while not x"

##### For loop:
```c++
for(int i=1; i<= 1000; i+=1)
{
cout << i << endl;
}
return 0;
```
```c++
for (initialization; condition; update)
{
	body;
}
```
For when you **DO** know the number of time to iterate before starting the loop

#### Nested Loops
• Key Idea: Execute all iterations of inner loop for each iteration of the outer loop

###### Tips:
- 2 loops allows us to process data that corresponds to 2 dimensions
- 3 loops allow us to process data that corresponds
to 3 dimensions

#### I/O Manipulators:
```c++
   // Experiment with the setw(n) and setfill(char) manipulator
   cout << "Tabular values: " << endl;
   // cout << 11 << " " << 10 << " " << 12 << endl;
   cout << setw(4) <<  11 <<  setw(4) << 10 <<  setw(4) << 12 << endl;
   // cout << 8 << " " << 7 << " " << 5 << endl;
   cout << setfill('.') << setw(4) <<  8 << setw(4) << 7 << setw(4) << 5 << endl;
```

```c++
   // Experiment with the fixed and setprecision(n) manipulator
	double pi = M_PI;  
   cout << setprecision(2) << fixed << pi << endl;
   cout << 1000*pi << endl;
```
fixed - only look at decimal places

Times table
```c++
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
   // get the input
   int n;
   cin >> n;

   // to print out fixed-width columns, print out each item with
   // cout << setw(4) << "item"; // see page 49
   for(int r=1; r <= n; r++ ) {
      // one iteration = 1 row
      for(int c=1; c<=n; c++ ) {
         // one iteration = 1 column
         cout << setw(4) << r*c;
      }
      // one iteration per row
      cout << endl;
   }

   return 0;
}
```

##### Break Statement:
- break
	- Ends the current loop immediately and continues execution
##### Continue Statement:
- continue
	- Starts the next iteration of the loop

### Scope
- Lifetime and visibility of a variable
- A variable's scope is the curly braces it is declared within
	- If initiated in a loop, dies after it ends
