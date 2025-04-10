## Deque
- Double ended queues allow for efficient insertion and removal from both sides of the list
- **A singly linked list cannot remove from the back in O(1)**
#### Performance
- Slower at random access than vector
- Fast at adding or removing items at front or back O(1)

## Doubly-Linked Lists
Can serve as a deque
Gives you 2 pointers and a value

#### Circular Linked List
Making the first and last item point at each other
```c++
head->prev;
```

There are more than 1 ways to implement a deque with an array which give O(1)

