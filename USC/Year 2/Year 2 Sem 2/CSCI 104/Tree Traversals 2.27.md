#### Recursive Tree Travels
Iterates over all nodes of the tree
- Usually depth-first, recursive approach

- 3 general traversal orderings
    - Pre-Order (process root then visit subtrees)
    - In-Order(Visit left subtree, process root, visit right subtree)
        - 10,20,25,30,50,60,80
        - Will always output in sorted order
    - Post-Order (Visit left, visit right, process root)
        - 10,25,50,30,20,80,60

##### Example: Count Nodes
Write a recursive function to count how many nodes are in a binary tree
- Want post-order traversal
- Count to the left, count to the right, then add one and return

##### Example: Prefix Sums
Write recursive function to have each node store the sum of hte values on the path from the root to each node.
- Want pre-order traversal
- Recurse down the tree 

##### Depth First Search
Explores all children before completing a parent
BFS completes a parent before any children

- Lets us assign a start and finish time when a node is completed

