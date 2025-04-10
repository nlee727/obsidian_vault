### Coupling
Refers to how much components depend on each other

### Composite Objects
Before the constructor executes, all of its data members come alive, reverse order for when the destructor executes

## Header Guards
```c++
#indef string
#define string

//code

#endif
```
Avoids multiple inclusions of header files

- Don't put 'using namespace' statements in header (.h) files
- use std:: when taking from any library