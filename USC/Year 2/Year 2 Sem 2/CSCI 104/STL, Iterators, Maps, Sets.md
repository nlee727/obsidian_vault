#### Iteration
Instead of using get(), use an iterator
- Object containing an internal state variable (pointer/index) that moves one step in the list at a time as you iterate, saving your position
- Entire job is to be able to step to the next item in $O(1)$
Iterator provide the semantics of a pointer to the values in the list

- Never compare iterators from different instances of the data structure.
- You should not modify a container as you iterate through it
- Though not efficient, one could iterate through a copy while erasing form the original

### C++ Pair Struct/Class
```c++
template <class T1, class T2>
struct pair {
    T1 first;
    T2 second;
}
```
- Map is built with the pair
```C++
#include <iostream>
#include <utility>
#include <string>
using namespace std;

void func_with_pair_arg(pair p) { 
    cout << p.first << " " << p.second << endl;
}
```
- Option 1 - Anonymous pair constructed and passed
```c++
func_with_pair_arg( pair<char,double>("c",2.3));
```
- Option 2 - Less typing, library function
```c++
func_with_pair_arg( make_pair("c",2.3));
```

### Associative Containers
```c++
#include <map>
```
- Ordered map class
- Map is made up of pairs, and the keys are how you find any particular item
- Enable log finding behavior $O(\log_{2}(n))$


- Option 1: inserting the pair
```c++
stumap["Tommy"] = s1;
// will insert into map unless key already exists, then just updates
```
- Option 2: using insert()
```c++
stumap.insert(pair("Tina", s2));)
stumap.insert( make_pair("Tina", s2));
```

#### Maps & Iterators
```c++
map<string,student>::iterator it;
for(it = stumap.begin(); it != stumap.end(); ++it){
    cout << "Name/key is " << it->first;
    cout << it->second.get_grade(0); 
}
```
- Dereference is required since the iterator is a pointer to a pair
##### Another Use of Maps: Sparse Arrays
- Large range of possible indices but only a small fraction will be used
- Example: zip codes
    - You could declare an array with 10 digit elements
    - You could use a map
    - Key = zip code, value = occurrences

### Binary Tree
- Depth of binary tree storing N elements is $\log(n)+1$
#### Binary Search Tree
- Tree where all nodes meet the property that
    - All descendants on the left are less than the parent's value
    - All descendants on the right are greater than the parent
- Can find value in $\log_{2}(n)$ time.
- Maps and sets use binary trees internally to store the keys
- This is why < operator needs to be defined