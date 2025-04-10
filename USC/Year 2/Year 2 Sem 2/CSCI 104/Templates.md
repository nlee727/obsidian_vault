- Allow alternate versions of the same code to be generated for various data types.
- Define a generic function for any type, T, then can call it for any type, T/ let compiler implicitly figure out T
```c++
template <typename T>
struct Item{
    T val;
    Item<T>* next;    
}
```
- Precede class with template\<typename T>
- Precede every definition of a function with typename and use T where you want a generic type
 
- Templated classes must have the implementation in the header file.

- Since we dont compile .h files, you cannot compile a templated class separately since the compilar does not know what type of data to generate code for and what code to generate

When working with templates, provide full scopes or precede member with this->


### Functor
Functors let us write code that is generic to an operation
