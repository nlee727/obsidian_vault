Pass-by-reference without pointers

Declaring a reference type (T&) creates an alias for another already-existing variable
```c++
int y;
int &x = y;
```
once you make an alias, you can never change what its alias does.

### When to Use References
1) You want to modify an input parameter of the calling function
2) To avoid making a copy when passing big struct or class objects