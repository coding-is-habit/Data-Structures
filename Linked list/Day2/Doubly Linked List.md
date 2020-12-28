
# Doubly Linked List

Doubly linked list is a type of linked list in which each node apart from storing its data has two links. The first link points to the previous node in the list and the second link points to the next node in the list. The first node of the list has its previous link pointing to NULL similarly the last node of the list has its next node pointing to NULL.

![Double Linked List](https://www.studytonight.com/data-structures/images/doubly-linked-list-1.png)

  

The two links help us to traverse the list in both backward and forward direction. But storing an extra link requires some extra space.

----------

## Implementation of Doubly Linked List

First we define the node.

```c++
struct node
{
	int data;     	// Data
	node *prev;  	// A reference to the previous node
	node *next; 	// A reference to the next node
};
```
