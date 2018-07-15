# Breadth-First Search algorithm

The BFS algorithm traverses a graph by visiting each neighbor node before visiting children nodes.

It uses a **queue data structure**.

As with DFS, our starting node can be any of the nodes in the graph as there is no concept of "root".

Steps:

* Add a node/vertex to the queue of nodes to be "visited".
* Visit the top node in the queue and mark it as visited.
* If that node has any neighbor, check to see if they have been visited or not.
* Add any neighbor nodes that have not yet been visited to the queue.
* Remove the nodes that have been visited from the queue.

These steps are repeated for every node in the graph, until we have no more node in the queue.

BFS is often used to find the **shortest path** between a node in the graph and the "parent" node.

Most BFS implementations will keep track of every single node's parent nodes that come before it.
The parents pointers can be rearranged to form a tree, which makes it easier to see how many steps to take to get from a node back to the parent node, hence finding the shortest path.

## Runtime complexity

Directed graph: O(V + E)

Undirected graph: O(V + 2E)

**Linear complexity**

---

More info: https://medium.com/basecs/going-broad-in-a-graph-bfs-traversal-959bd1a09255
