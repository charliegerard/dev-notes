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

## Code sample

![bfs graph](https://he-s3.s3.amazonaws.com/media/uploads/2ffb073.jpg)

Considering the graph above, here's a code sample in JavaScript to get the distance from the root node to each other node

```javascript
function bfs(graph, root){
  let distances = {}

  for(var i = 0; i < graph.length; i++){
    distances[i] = Infinity; // Starting by setting all nodes to infinity, meaning they are not reachable by the root node.
  }

  distances[root] = 0;

  var queue = [root];
  var current;

  while(queue.length != 0){
    current = queue.shift(); //popping off a node from the queue to traverse.

    var connectedToCurrent = graph[current];
    var neighborIds = [];
    var ids = connectedToCurrent.indexOf(1);

    while(ids != -1){
      neighborIds.push(ids);
      ids = connectedToCurrent.indexOf(1, ids + 1);
    }

    for(var j=0; j < neighborIds.length; j++){
      if(distances[neighborIds[j]] == Infinity){
        distances[neighborIds[j]] = distances[current] + 1;
        queue.push(neighborIds[j]);
      }
    }
  }
  return distances

}

var graph = [
  [0,1,2,0,0], // Source node's connections
  [1,0,0,0,0], // Node 1 connections
  [1,0,0,0,0], // Node 2 connections
  [0,0,0,0,0], // ....
  [0,0,0,0,0]
]

console.log(bfs(graph, 1)) // returns { '0': 1, '1': 0, '2': Infinity, '3': Infinity, '4': Infinity }
```



More info: https://medium.com/basecs/going-broad-in-a-graph-bfs-traversal-959bd1a09255
