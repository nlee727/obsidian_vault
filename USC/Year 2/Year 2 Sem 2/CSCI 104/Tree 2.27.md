### Definition:
Connected, acyclic graph with 
- Root node  that has 0 or more subtrees
- One path between any two nodes
In general
- Nodes have exactly one parent and 0 or more children
d-ary tree
- Tree where each node has at most d children
- Binary tree = d-ary Tree with d=2

Full d-ary tree, T, where
- Every vertex has 0 or d children and all leaf nodes are at the same level (adding 1 node requires increasing the height)

Complete d-ary tree, where
- Top h-1 levels are full and bottom level is filled left to right
- Each level is filled left-to-right and new level is not started until previous is complete

Balanced d-ary tree
- Where for every node, subtrees for each child differ in height by at most 1

#### Tree Height
A full or complete binary tree of n nodes has height
$$
h=\log_{2}(n+1)
$$
Maximum height of a tree with n nodes is n

## Tree Implementations
### Array-Based Complete Binary Tree
- If you can guarantee completeness, it can be stored nicely in an array 
Using 1 indexing, 
Parent(i)$$
\frac{i}{2}
$$Left_child(i)
$$
2i
$$
Right_child(i)
$$
2i+1
$$

Using 0 indexing,
Parent(i)
$$
\frac{i-1}{2}
$$
Left_child(i)
$$
2i+1
$$
Right_child(i)
$$
2i+2
$$
### Link-Based Approach
- Use NULL pointers to indicate no child

### Priority Queue
#### Traditional Queue
Traditional Queue
- Accesses/orders items based on Position
- Did not care about item's value

Priority Queue
- Orders items based on value
    - Either minimum or maximum
- Items arrive in some arbitrary order
- When removing an item, we always want the minimum or maximum depending on the implementation
- Leads to a sorted list
Pop in O(1)
Push in O(n)

#### Priority Queue
Member functions
- Push (add to appropriate location)
- top()
- pop() min or max
- size()

#### Priority Queue Efficiency
- If implemented as a sorted array list
    - Insert() = O(n)
    - Top() = O(1)
    - Pop() = O(1)
- If implemented as an unsorted array list
    - Insert() = O(1)
    - Top() = O(n)
        - Min()
    - Pop() = O(n)
        - Min(), then delete()

### Heap Data Structure
- Implementation for priority queue
- Complete binary tree that maintains the heap property
    - Every parent is better-than both children, but no ordering between children
- Minimum/Maximum value is always the top element

- Push: Add new item to head and modify as necessary
- Pop: Remove "best" item and modify heap as necessary
- Top: Returns best
- Can use array/vector as the container

#### Push Heap/Trickle Up
- Add item to first free location at bottom
- Recursively promote it up while it is less than its parent
- Doesn't need to look at siblings because if you need to swap it means you are by definition better than sibling

#### Pop Head/Trickle Down
- Takes last node puts and put it in the top location and then recursively swaps it for the smallest child until it is in its right place
- If you swap with best child, then its by definition better than the other 

#### Converting an array to a heap
- Consider all leaf nodes
- Call heapify() on each node in reverse order from bottom to top
- Optimization: skip leaf nodes
    - If you consider all leaf nodes as individual heaps of size 1, they are already small, valid heaps, so just start at first non-leaf

#### Make-Heap Run Time
- To build a heap from an arbitrary array require n calls to heapify
- n nodes swap once, n/2 nodes swap twice, n/3 nodes swap 3 times, etc.
- So as h approaches infinity, sum approaches $2n = \Theta(n)$

#### Heapsort
Sort by top and popping n times
- n calls to top() = O(1) and pop()=$\Theta(\log n)$ so nlog(n)
