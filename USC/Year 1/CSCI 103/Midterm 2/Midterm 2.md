Left side of an -> must be a pointer - true

Homework 3 - unit3b deep copy, strcompare

PR3 Maze - 
dynamically allocate the queue array

Create a new array that has the previous location 

Linked lists (Second coding problem) and Vectors will be on midterm 2

3 coding problem

Anything that can do all 4 list operations  in O(1) is a deque
Vector
Push front O(n)
Push back O(1)
Pop back O(1)

Singly Linked list w head
Push front O(1)
Push back O(n)
Pop back O(n)

single linked list w head and tail
Push front O(1)
Push back O(1)
Pop back O(n)

doubly linked list w head and tail
Push front O(1)
Push Back O(1)
Pop back O(1)

Tracing practice problem - Keep track of the stack, head, and screen
Stack
1. x becomes alive, int constructor is called
	1. C1i
	2. val=3
2. C1 object is not created, only pointer p becomes alive
3. Address of x is stuck into p
4. Do what's on the right of an equals sign. p2 now points at what p was pointing
	1. f1:start
	2. constructor must be called, no matter where it is allocated
		1. C1d
5. yp points to the object in the heap
6. f1:end
7. val=3
8. When an object in main dies, the destructor gets called again,
	1. val=3
9. 
Heap
4. val=-1
5. pointer to the object
6. val gets changed to 3 because of line 20

```c++
Complex::operator+(const Complex & rhs) const;
// first const protects the data member, second const protects the calling.
```

## Homework 4
Adding to front requires you to update 4 pointers
The order matters - fill in pointers that are blank first

Adding item* p to front (nonempty scenario)
```c++
else{
p->prev = NULL;
p->next = head;
head->prev = p;
head = p;
}
```

Adding item* p to middle
```c++
p->prev = curr;
p->next = curr->next;
curr->next = p;
p->next->prev = p; //doing (p->next)->prev
```

Removing Middle
```c++
curr->prev->next = curr->next;
curr->next->prev = curr->prev;
delete curr;
```


```c++

```

- Pointer to 1st thing a list, use just head. head is just a pointer
- Use a temp pointer to move down the list to avoid losing the head
```c++
Item* temp;
```

## Remove from Front
#### Empty
Both head and tail are null, so don't need to change anything and just return

#### One Item
Popping the last item, so both head and tail need to change and become null

#### Two Or More
Only head needs to change to point to second item

## Push Back
#### Empty
Head and Tail both point to the same item
#### One Item
Just tail needs to change
#### Two or More
Need to add a third, only tail needs to change so it collapses with the previous case