# Doubly linked list

A bit similar to a [singly-linked list](singlyLinkedList.md), a doubly-linked list is a linked list made of nodes, except that the
nodes contain a third field with a link to the previous node as well as the next node.

The advantage of a doubly linked list is that we can traverse back to the previous node for deletion for example. The operations are **bi-directional**.

Node:

* `data` stores the value
* `previous` points to the previous node in the list
* `next` points to the next node in the list

Operations:

* `_length`
* `head`
* `tail`
* `add(value)`
* `searchNodeAt(position)`
* `remove(position)`


