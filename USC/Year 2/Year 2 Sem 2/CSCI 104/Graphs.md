- Collection of vertices and edges that connect vertices
#### Graph ADT
- addvertex()
- addEdge(v1,v2)
- getAdjacencies(v1) : List\<Vertices>
    - Returns any vertex with an edge from v1 to itself
- removeVertex(v)
- removeEdge(v1,v2)
- edgeExists(v1,v2) : bool

- N = # of vertices
- E = # of edges

- Adjacency List Representation
    - O(n+m) memory storage
    - Existence of an edge requires O(m+log(n)) time
- Adjacency Matrix Representation
    - O($n^2$) storage
    - Existence of an edge requires O(1) lookup

#### Directed vs. Undirected Graphs
- For adjacency list form, you may need 2 lists per vertex for both predecessors and successors
![[Pasted image 20240215112643.png]]
### Graph Algorithms
#### BFS
- Starts at u and fans out along edges
- FIFO implies use of a Queue
- Put newly found vertices in the back and pull out a vertex from the front to explore next
- Mark a vertex the first time we encounter it and mark a vertex by adding them to a set or by simply setting some data member that indicates we've seen this vertex before.

#### Page Rank Algorithm
- If we let a bunch of people randomly walk the graph, what is the probability that they end up at a certain location
- Write a system of linear equations from adjacency matrix for probabilities

#### Dijkstra's Algorithm
Each edge has a weight associated with it, Dijkstra's finds the shortest path from a source node to all other nodes

- Similar to BFS but always chooses the closest vertex to the source to explore next as opposed to FIFO
![[Pasted image 20240220111402.png]]

##### Analysis
Guaranteed that there is no shorter path to that vertex

Total Runtime
$$
(V+E)*\log(V)
$$
With an indexed priority queue
Uses two arrays, one that keeps track of pointers to nodes and heap

#### A* Search Algorithm
Guided BFS - Heuristic Search as opposed to BFS Brute Force Search
Good for path planning and constrained optimization 
##### Heuristic
Scores of how close an interim solution is to the final goal.
- Must be easy to compute
- Usually developed by simplifying the constraints on a problem

Must define a heuristic score h and number of moves form start it took to get to current state g, 
f = g + h
- Always explore the state with the lowest f-score
- Heuristics should always underestimate the distance to the goal
    - If they do, A* guarantees optimal solutions

Maintain 2 lists
- Open list = Nodes to be explored (chosen from)
- Closed list = Nodes already explored
![[Pasted image 20240220121149.png]]
