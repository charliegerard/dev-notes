# Depth-First Search - graph traversal algorithm

**The DFS algorithm will traverse down a single path, one child node at a time.**
DFS tells us if a path exists between node x and node y.

**DFS is like solving a maze, following a path until you can't follow it anymore and then backtracking and retracing a different path we haven't followed yet until we find one that leads to the end.**
DFS would allow us to figure out if there is a path that goes from the starting node to the end node.

DFS traversal can start **wherever we want** in the graph. There is no concept of "root" node unlike tree structures.
Once a node has been visited, we do not want to visit it again, so we will mark it as "visited".

The process of backtracking at a dead end and repeating the walk down the graph is actually **recursion**.
We are repeating the same action again and again, like a recursive function call.

To store the result of our traversal, we can use the stack data structure. The node that we choose to start from will be the first item in the stack.

After choosing our first parent node, we can decide to go through **any reachable node**. We then push them onto the stack one by one, mark them as "visited" and set their parent node to the previous node.

When we've gone as deep as possible in the graph on a particular path and there is no other option, we have to backtrack one step at a time and see if other paths can be taken. To do so, we pop off nodes one by one from the stack and check if any neighbor node can be visited and if there is a path down the graph from that node.

If any node only leads to a node that has already been visited, we need to backtrack again as we do not want to visit nodes that are already visited. If there are no new paths that can be taken, then we pop off all nodes from the stack one by one and come back to the parent node and try a different path.

**We don't actually finish visiting a parent node until we reach a dead end.** When we begin visiting a parent node, we are still in the process of visiting it when we visit one of its children.

## Runtime

The process of visiting every vertex (node) in the graph takes *constant time*. However, the expensive part of the dfs algorithm lies in the process of checking every edge outgoing from each vertex that we visit. Some nodes could have only 1 neighboring edge but some nodes could have thousands! The runtime of checking the edges depends solely on the size of a node's adjacent linked list, which is calculated in **linear time**.

For a directed graph (only goes in 1 direction), the runtime is O(V+E).

For an undirected graph, the runtime is calculated with O(V + 2E) as a node can be visited twice.

Both are linear time.

More details: https://medium.com/basecs/deep-dive-through-a-graph-dfs-traversal-8177df5d0f13









