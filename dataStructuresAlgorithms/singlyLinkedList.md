# Singly-linked list

A singly linked list is a data structure that can store an indefinite amount of items. These items are connected using pointers in a sequential manner.

In a singly-linked list, every element contains some data and a link to the next element.

The elements of a linked list are called **nodes**.


A node has 2 fields: **data** and **next**.

* The data field contains the data being stored in that specific node.

* The next node contains the address of the next node.

The very first node in a linked list is called **head** and the last is called **tail**.


## Operations of a singly-linked list

* `_length` retrieves the number of nodes in the list.
* `head` assigns a node as the head of the list.
* `add(value)` adds a node to the list.
* `searchNodeAt(position)` searches for a node at n position in the list.
* `remove(position)` removes a node from the list.

For details on how to implement these operations, see [this article](https://code.tutsplus.com/articles/data-structures-with-javascript-singly-linked-list-and-doubly-linked-list--cms-23392)

The operations in a singly-linked list are only **uni-directional** as they always begin from the beginning of the list to the end of it.

If we want bi-directional operations, we need to look at [doubly-linked lists](doublyLinkedList.md)



