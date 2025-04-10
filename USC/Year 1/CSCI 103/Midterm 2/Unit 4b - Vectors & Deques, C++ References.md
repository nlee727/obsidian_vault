## Templates
- Allows the type of variable to be a parameter specified by the programmer

### Vector Class
Container class
Call a constructor using () not []
- Array based list that can be used like an array but can resize automatically

###### Vectors
Vectors abstract arrays
Vectors dynamically allocate arrays of size n, making a vector a pointer. 
When adding more, it will allocate a bigger array, copy down everything to the bigger array, and delete the original.
- Potentially dangerous operation, as it has runtime O(N).
#### Performance
- Pros
	- Fast access for random access O(1)
	- Allows for fast addition or removal of items O(1)
- Cons
	- Inserting / Removing item at front or in the middle (will have to shift all items up or down) O(n)
	- Adding an item when the array is full will trigger O(n) resize (pushback)



