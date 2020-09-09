# Graphs 
When netflix recommends another movie to you or if advertisers target you based off of something... Graphs are usually in play. 

## We're going to
- Explain what a graph is
- Compare and contrast different types of graphs and their use cases in the real world
- Implement a graph using an adjacency list
- Traverse through a graph using BFS and DFS
- Compare and contrast graph traversal algorithms

https://en.wikipedia.org/wiki/Graph_(abstract_data_type)

Basically it's a collection of nodes and connections between those nodes.

They are all treated equally.

This is a `Graph()` example of **wikipedia's** connectivity between pages..

![graph](https://media.git.generalassemb.ly/user/19642/files/6dfc3500-006a-11ea-95d4-c92d192ae2dd)


### Real world 
- Social Networks 
- Location / Mapping 
- Routing Algorithms 
- Visual Hierarchy
- File System Optimization 
- Everywherer!!

### Graph terms 
- **Vertex** - a node 
- **Edge** - connection between nodes 
- **Weighted/Unweighted** - values assigned to distance
- **Directed/ Undirected** 

Directed is when there is a one way relationship between nodes. 
Weighted is when there are values on the edges. You can think of this as a google map. 

#### Two ways to implement a graph 
Adjacency List
- Can take up less space (In space graphs)
- Faster to iterate over all edges

Adjacency Matrix
- Faster to look up specific edges
- Matrix is better for when our data is jam packed
 

## Adjacency list
You could use a nested array or we could also use a hash table. Better for real life situations - because data is typically spread out with few connections between nodes. 

### Adding a vertex 
- Write a method called addVertx

## Removing a Vertex (your turn)
- The function should accept a vertex to remove 
- The function should loop as long as there are any other vertices in the adjaceny list for that vertex
- Inside of the loop, call our **removeEdge** function with the vertex we are removing and any values in the adjacency list for that vertex
- Delete the key in the adjacency list for that vertex

## Traversing a Graph 
There are lots and lots off applicatons. Think about the friend recommendation on social media. A graph may need to traverse thousands of users to come up with a meaningful connection.

How does debth first and breadth first work with a graph?


## Depth ...
- Follow as far as possible down one branch before we circle back.
- Important to remember where we've been

We're going to do it recursively and iteratively

## DFS Pseudocode
Recursive

- The function should accept a starting node
- Create a list to store the end result, to be returned at the very end
- Create an object to store visited vertices
- Create a helper function which accept a vertex
	- The helper function should return earlier if the vertex is empty
	- The helper function should place the vertex it accepts into the visited object and push that vertex into the result array
	- Loop over all of the values in the adjacencyList for that vertex
	- If any of thos values have not been visited, recursively invoke the helper function with that vertex

	
	
## DFS - Iterative
We could just call it a day with the recursive solution, but we're going to go through again with an iterative example because it's important to see both the interative and recursive solution to a problem.

- The function should accept a starting node
- Create a stack to help us keep track of vertices (use a list/array)
- Create a list to store the end result, to be retrurned at the very end
- Create an object to store visited vetices
- Add the starting vertex to the stack, and mark it visited
- While the stack has something in it:
	- Pop the next vertex from the stack
	- If that vertex hasn't been visited yet:
		- Mark it as visited
		- Add it to the result list
		- Push all of its neighbors into the stack
	- Return the result array
