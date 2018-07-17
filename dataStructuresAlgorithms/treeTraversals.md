# Different types of tree traversals

There are 3 types of tree traversals: **Inorder, Preorder, Postorder**.

Example:

![Example of tree](https://www.geeksforgeeks.org/wp-content/uploads/2009/06/tree12.gif)

**Depth First traversal**:
* Inorder (Left, Root, Right): 4 2 5 1 3
* Preorder (Root, Left, Right): 1 2 4 5 3
* Postorder (Left, Right, Root): 4 5 2 3 1

**Breadth first traversal** or **Level Order traversal**: 1 2 3 4 5

## Implementation

```javascript
function Node(val){
  this.right = null;
  this.left = null;
  this.val = val;
}

function inorder(node){
  if(node){
    inorder(node.left);
    console.log(node.val);
    inorder(node.right);
  }
}

function preorder(node){
  if(node){
    console.log(node.val);
    preorder(node.left);
    preorder(node.right);
  }
}

function postorder(node){
  if(node){
    postorder(node.left);
    postorder(node.right);
    console.log(node.val);
  }
}

var root = new Node(1);
root.left = new Node(2);
root.right = new Node(3);
root.left.left = new Node(4);
root.left.right = new Node(5);
```
