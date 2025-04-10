##### List Operations

##### Implementation Options
- Linked
    - Allocate each item separately
    - Random access 
    - Adding new items never requires other to move
    - Memory overhead due to pointers
- Array-based
    - Allocate a block of memory to hold many items
    - Random Access
    - Adding new items may require others to shift positions
    - Memory overhead to to potentially larger b lock of memory with unused locations

#### Linked Lists
- Changing value of a variable must be done by passing through reference or with a pointer to a pointer
- Append and pop front is O(1) with a tail pointer, pop back is still O(n)

- Worst case runtime of get(i) - $\Theta(i)$
- Worst cast runtime of insert(i, value) - $\Theta(i)$
- Worst case runtime of remove(i) - $\Theta(i)$