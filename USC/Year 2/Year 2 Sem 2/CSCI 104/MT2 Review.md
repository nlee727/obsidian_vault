## Chapter 9, PQ and Heaps
Full, Complete, Balanced

Full or complete binary tree of n nodes has height $h=\log(n+1)$ (also the minimum height of any tree with n nodes). Maximum height of a tree with n nodes is n.

###### Array Based Complete Binary Tree
1 Indexing:
Parent(i) = $\frac{i}{2}$
Left Child(i) = $2i$
Right Child(i) = $2i+1$
- Non-Complete binary trees are usually used with link-based approaches.
- Also works with d-ary trees

###### Link Based Approaches
```c++
template<typename T>
struct Item {
    T val;
    Item<T>* left, *right;
    Item<T>* parent;
};

template<typename T>
class BinTree{
    public:
    BinTree();
    ~BinTree();
    void add(const T& v);
    private:
    Item<T>* root_;
}
```

#### Priority Queues
Hospital ER, Air Traffic Control

- Push(item)
    - O(n) if implemented as a sorted array, O(n) otherwise
- Top()
    - O(1) if implemented as a sorted array, O(n) otherwise
- Pop()
    - Same as top
- Size()
- empty()
- Optional - changePriority(item, new_priority)
![[Pasted image 20240402222635.png]]
#### Heaps
- Complete binary tree that maintains the heap property
    - Every parent is better-than both children, but no ordering property between children.
- Min/Max value is always top element

Heap Operations
- Push, Pop, Top

```c++
template <typename T>
class MinHeap{
    public:
    MinHeap(int init_capacity);
    ~MinHeap();
    void push(const T& item);
    T& top();
    void pop;
    int size() const;
    bool empty() const;

    private:
    void heapify(int idx);
    vector<T> items_;
}
```

Push Heap/Trickle Up
- Add item to first free loc
- Recursively promote
```c++
void MinHeap<T>::push(const T& item){
    items.push_back(item);
    trickleUp(items_.size()-1);
}

void MinHeap<T>::trickleUp(int loc){
    int parent = loc/2;
    while(parent >=1 && items_[loc] < items_[parent]){
        swap(items_[parent], items_[loc]);
        loc = parent;
        parent = loc/2;
    }
}
```

Top
```c++
T const & MinHeap<T>::top(){
    if(empty()){
        throw(std::out_of_range());
    }
    return items_[1];
}
```

Pop Heap/Heapify(TrickleDown)
- Takes worst node and puts it in the top location and recursively swaps.
```c++
void MinHeap<T>::pop(){
    items_[1] = items_.back();
    items_.pop_back();
    heapify(1);
}

void MinHeap<T>::heapify(int idx){
    if(idx == leaf node){
        return;
    }
    int smallerChild = 2*idx;
    if(right child exists){
        int rChild = smallerChild+1;
        if(items_[rChild] < items_[smallerChild]){
            smallerChild = rChild;
        }
    }
    if(items_[idx] > items_[smallerChild]){
        swap(items_[idx], items_[smallerChild]);
        heapify(smallerChild);
    }
}
```

#### Make-Heap/Build-Heap
Build in O(n)
- First making heaps of both sub trees then combining the sub trees into one unified heap by calling heapify on their parent.
- Require n calls to heapify
```c++
void make_heap(vector<int>& dat){
    for(int i=dat.size()-1; i > 0; i--){
    heapify(i);
    }
}
```

#### HeapSort
- Call top and pop n times to get data in sorted order.
- n calls top top O(1),  and pop(log(n)), so O(nlogn)


## Graph Representation and Traversals
###### Graph Representations
- n refers to number of vertices, m number of edges
- Social Networks, Computer networks/Internet, Path planning, Interaction Diagrams, Bioinformatics

- Graphs are a list of lists (list of vertices each having their own list of adjacent vertices)
![[Pasted image 20240402225238.png]]
- Memory = (O(n+m))
- Degree be number of edges incident on a vertex
- Existence of edge requires O(deg(v)) runtime;
```c++
int sum = 0;
for(int i = 0; i<n; i++){
    sum+= adj[src][i]*adj[i][dst];
}
if(sum > 0) //two hop path exists
```


- Adjacency Matrix, 1 if there is an edge between vertex i and j.
![[Pasted image 20240402225302.png]]
- Memory = O(n^2)
- Existence of edge has O(1) lookup
- Take dot product

For a directed graph,  you may need 2 lists per vertex for both predecessors and successors
![[Pasted image 20240402230439.png]]

#### Graph Algorithms
###### Pagerank Algorithm
- If we let a bunch of people randomly walk the graph, what is the probability they end up at a certain location in the steady state
Weighted Adjacency Matrix
- aij/degree(j)
Use linear algebra to solve for probabilities

###### Breadth-First Search
Find shortest paths from the start vertex to every other vertex
- Must explore all nearer neighbors before exploring further away neighbors
- FIFO Queue
- We can mark vertexes by adding them to a ser or by having an explored array
![[Pasted image 20240402232929.png]]
- Shortest paths can be found by walking predecessor from any node backward
- $\Theta(n+m)$ runtime

#### Dijkstra's Algorithm
- Each edge has a weight (distance, cost of traversal)
- Find shortest path from a to other nodes
- Similar to BFS but always chooses the shortest distance vertex to explore next.
![[Pasted image 20240402233445.png]]
- Guaranteed that there is no shorter path to that vertex as you pull out from the PQ
- Runtime = $(V+E)\log(V)$

###### A* Search Algorithm
- Use Heuristics for quick computations to give an approximation 
- h = heuristic score
- g = # moves from start it took to get to current state
- f = g + h
- Assign each state an f-score and always explore state with lowest f score

- Open List = nodes to be explored
- Closed List = nodes already explored
![[Pasted image 20240402234913.png]]

## Recursive Graph & Tree Traversals Algorithms
- Recursive code should handle only 1 element, then use recursion to handle the remaining elements. Combine the solutions to the recursive calls with the one element being handled.

Pre-Order - process root then visit subtrees
In-Order - Visit left subtree, root, visit right subtree
- sorts tree lowest to highest
Post-Order - Left, right, root


Count Nodes
```c++
struct Tnode{
    int val;
    TNode *left, *right;
};

int count(TNode* root){
    if(root == NULL) return 0;
    else{
        return 1+count(root->left) + count(root->right);
    }
}

void prefix(TNode* root){
    prefixH(root, 0);
}

void prefixH(TNode* root, int psum){
    if(root == NULL) return;
    else{
        root->val += psum;
        prefixH(root->left, root->val);
        prefixH(root->right, root->val);
    }
}
```


#### General Graph Traversals
###### Breadth First Search
- BFS visits each node one and will induce a tree subgraph
- BFS doesnt allow for topological sorting, need DFS. All parent nodes need to be completed before any child node. 

###### DFS
Explores all children before completing a parent.
If we look at nodes in reverse order of finish time, we have a topological ordering.
![[Pasted image 20240403000746.png]]
## Chapter 12 - Recursion - Combinations & Backtracking

bin_combos_str
Zero_sum
Prime_products_print
Prime_products
basen_combos
all_letter_combos

###### Recursive Backtracking Search
Stop searching down a path at the first indication that constraints wont lead to aa solution

## Chapter 13 - Iterators
```c++
iterator it = mylist.begin();
for(it = mylist.begin(); it != myList.end(); ++it){
    cout << *it << endl;
}
```
Can be more efficient by keeping an internal state variable
Hides underlying implementation details from user

- Post Increment is less efficient because it causes a copy to be made

```c++
template<typename T>
class LList
{
public:
LList() {head_ = NULL;}

class iterator {
    private:
        Item<T>* curr_;
        iterator(Item(T)* init) : curr_(init) {}
    public:
        friend class LList<T>;
        iterator& operator++();
        iterator operator++(int);
        T& operator*();
        T* operator->();
        bool operator!=(const iterator & other);
        bool operator==(const iterator & other);
    };
iterator begin() {iterator it(head_); return it;}
iterator end() {iterator it(NULL); return it;}

private:
    Item<T>* head_;
    int size_;
}
}
```
- Outfitting LList to support iterators
- iterator class has friend LList so that it contains a private constructor that only iterator and LList can use.

Add another class for a const_iterator type;

Can have implicit conversions for iterator
operator bool()
{
return curr_ != NULL;
}

## Chapter 14 - Binary Search Trees and AVL Trees
#### Binary Search Trees
All nodes satisfy
- All values of nodes in left subtree and less than the parent
- All values of nodes in right subtree are greater than the parent.

Insert, Remove, Find

Remove,
0 children, simply remove node
1 child: Promote child into the node's location
2 children: Swap the value with its in order successor or predecessor then remove from its new location
![[Pasted image 20240403010300.png]]

Rotation's effect on height

#### AVL Trees
Height difference between left and right subtrees is at most 1
Right - Left subtree height = balance

Insert(n)

## Splay Trees
Find, insert, delete in O(n)
If you do m operations on a splay tree with n elements the total time is
$O(m*\log(n))$ amortized $O(\log(n))$
recently accessed elements will be near the top of the tree

Principle of Locality
- Spatial Locality - Future accesses will likely cluster near current accesses
    - Instructions and data arrays are sequential (they are all one after the next)
- Temporal Locality - Future access will likely be to recently accessed items
    - Same code and data are repeatedly accessed
    - 10% of written instructions account for 90% of executed instructions
- Splay trees help exploit temporal locality by guaranteeing recently accessed items near the top of the tree

- We attempt to access a node we must splay something
- Use rotations to attempt balance

## Hash Tables
Unordered Maps
