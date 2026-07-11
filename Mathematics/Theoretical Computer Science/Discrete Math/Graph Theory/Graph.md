---
date: 2024-12-01
---
An [[Mathematical Object|Object]] consisting of a [[Set]] of 
[[#Vertex|vertices]] (nodes) connected by *edges* where the edges may be directed or undirected.
* If the same vertices are connected in the same way by edges, the graphs are the same; it doesn't matter how you draw the graph so long as it satifies the aforementioned condition
# Examples

| Example        | Vertices | Edges     |
| -------------- | -------- | --------- |
| Maps           | Cities   | Roads     |
| Neural Network | Neurons  | Synapses  |
| Social Media   | Users    | Relations |


# Definitions
## Vertex
An object that makes up the graph, that is connected by edges
## Node
The same as a vertex
## Edge
The thing connected the vertices
## Order
\# vertices
## Size
\# edges
## Adjacent
A property of vertices, when they are connected (by an edge)
## Connected
* Two vertices are *Connected* if there is a Path that connects them
* A Graph is *Connected* if for every pair of Vertex there exists a path connecting them
* A graph is *Disconnected* if there exists a pair of vertices with no path between them
## Weight
The cost of traversing a given edge on a graph.
## Dense
A graph is dense if random vertex pairs are likely to be connected
## Sparse
A graph is dense if random vertex pairs are not likely to be connected
## Simple
* There are no self loops
* There are no parallel edges
## Cycle
A path that repeats vertices
## Directed
Edges have required direction(s)
## Path
A [[Set]] of edges that connect a pair of vertices
## Trail
A set of edges where repeated vertices are allowed
## Walk
A trail where edges can also repeat
## Circuit
A trail where the first and last vertices connect
