# Graphs
 - A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.


- terminology used when working with Graphs:

1. Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
2. Edge - An edge is a connection between two nodes.
3. Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
4. Degree - The degree of a vertex is the number of edges connected to that vertex.

# Directed vs Undirected

1. Undirected Graphs :  is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.


2. Directed Graphs:  also called a Digraph is a graph where every edge is directed.
- Digraph has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.

## Complete vs Connected vs Disconnected

- Complete Graphs : A complete graph is when all nodes are connected to all other nodes.

- Connected : A connected graph is graph that has all of vertices/nodes have at least one edge.

- Disconnected : A disconnected graph is a graph where some vertices may not have edges.

## Acyclic vs Cyclic

- Acyclic Graph : is a directed graph without cycles.

 - (A cycle is when a node can be traversed through and potentially end up back at itself). 

- Cyclic Graphs : is a graph that has cycles.

- (A cycle is defined as a path of a positive length that starts and ends at the same vertex).

## Graph Representation
1. Adjacency Matrix
2. Adjacency List

1. Adjacency Matrix
An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix

- Each Row and column represents each vertex of the data structure. The elements of both the column and the row must add up to 1 if there is an edge that connects the two, or zero if there isn’t a connection.

>  a sparse graph is when there are very few connections. a dense graph is when there are many connections


2. Adjacency List
An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.


- Weighted Graphs : is a graph with numbers assigned to its edges. These numbers are called weights.

> When representing a weighted graph in a matrix, you set the element in the 2D array to represent the actual weight between the two paths. If there is not a connection between the two vertices, you can put a 0

## Traversals
1. Breadth First:  is when you visit all the nodes that are closest to the root as possible. From there you traverse outwards, level by level, until you have visited all the vertices/nodes.

- starting at a specific vertex/node. This node must be specified when calling the BreadthFirst() method
- graphs can have cycles. Traversing a graph that has cycles will result in an infinite loop
- add the previously-unvisited vertex to a visited set, so we know not to visit it again as traversal continues

- Here is what the algorithm breadth first traversal looks like:

1. Enqueue the declared start node into the Queue.
2. Create a loop that will run while the node still has nodes present.
3. Dequeue the first node from the queue
4. if the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.


2. Depth First: 

The algorithm for a depth first traversal is as follows:

1. Push the root node into the stack
2. Start a while loop while the stack is not empty
3. Peek at the top node in the stack
4. If the top node has unvisited children, mark the top node as visited, and then Push any unvisited children back into the stack.
5. If the top node does not have any unvisited children, Pop that node off the stack
6. repeat until the stack is empty.


