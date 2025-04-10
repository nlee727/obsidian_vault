## Compilation
#### Compilation and Execution Process:
-g = Enable Debugging
-Wall = Show all warnings
-o "name" = Specify output executable program name.

#### Splitting over Multiple .cpp files:
- Compiler only compiles one file at a time
- **All** source code files must be supplied in the complier command for it to link and create an executable
```
g++ -g split-main.cpp split-sum.cpp -o split
./split
```

## Basic Debugging
