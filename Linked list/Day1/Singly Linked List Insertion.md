### Singly Linked List Insertion
Insertion into a single linked list has three cases:
* Inserting a new node before the head (at the beginning).
* Inserting a new node after the tail (at the end of the list).
* Inserting a new node at the middle of the list (ranodom location).

### Inserting a Node in Singly Linked List at the Beginning
In this case, a new node is inserted before the current head node. Only one **next pointer** need to be modified and it can be done in two steps:
### Approach:
* Update the next pointer of new node, to point to the current head.
* Update head pointer to point to new node.

**Below is the implementation of the above algorithm.**
```c++
// inserts at beginnning of list
// head- refrence to Linked List
// data - newNode's data value 
struct ListNode * insertAtBeginning(struct ListNode * head, int data) { 
  ListNode * newNode = new ListNode(); // create a node
  newNode -> data = data; // set newNode's data value
  newNode -> next = NULL; // set as end of list

  if (head == NULL) { // then list empty, so set as head node
    head = temp;
  } else { // else add to left of list
    temp -> next = head;
    head = temp;
  }
  return head;
}
```
* **Time Complexity: O(1)**
* **Space Complexity: O(1)**

Practice this problem [Insert Node at the head of the list](https://www.hackerrank.com/challenges/insert-a-node-at-the-head-of-a-linked-list)

### Inserting a Node in sigle Linked List at the ending
In this case, we need to modify **two next pointers** (last nodes next pointer and new nodes next pointer).
### Approach:
* New node next points to NULL.
* Last nodes next pointer points to the new node.

**Below is the implementation of the above algorithm.**
```c++
// inserts at the end of Linked List
// head- refrence to Linked List
// data - newNode's data value 
struct ListNode * insertAtEnd(struct ListNode * head, int data) { 
  ListNode * newNode = new ListNode(); // create a node
  temp -> data = data; // set temp data value
  temp -> next = NULL; // set as end of list
  
  ListNode * current = head; // iterator for list
  if (current == NULL) { // then list empty, so set temp as head
    head = newNode;
  } else {
    // find end of current list
    while (current -> next != NULL) {
      current = current -> next;
    }
    // current is now the last node in list (next==NULL)
    // set temp as new next node
    current -> next = temp;
  }
  return head;
}
```
* **Time Complexity: O(n), for scanning the list of size n**
* **Space Complexity: O(1)**

Practice this problem [Insert Node at the end of the list](https://www.hackerrank.com/challenges/insert-a-node-at-the-tail-of-a-linked-list)
### Inserting a Node in Singly Linked List at the Given Position
Let us assume that we are given a position where we want to insert the new node. In this case also, we need to modify two next pointers.

**Below is the implementation of the above algorithm.**
```c++
// 1 base indexing
// Insert a new node (new) at positon n and returns head.
// head - reference of list
// data - data value of newNode
// n - position for insertion n>=1
struct ListNode * insertAtPosition(struct ListNode * head, int data , int n) {
  ListNode * newNode = new ListNode(); // create a node
  temp -> data = data; // set temp data value
  temp -> next = NULL; // set as end of list
  
  // pred will point to predecessor of newNode
  ListNode * pred = head;
  
  //Special case: adding at head
  if (n <= 1) {
    newNode -> next = head;
    return newNode;
  }
  // find the n-1 node (predecessor): decrement and move forward in the list
  // until either the list has ended or n becomes 0
  while (--n && pred != NULL) {
    pred = pred -> next; // repoint pred to next element
  }
  if (pred == NULL)
    return NULL;
  // if it is not NULL, insert new after its predecessor
  newNode -> next = pred -> next;
  pred -> next = newNode;
  return head;
}
```
* **Time Complexity: O(n)**
* **Space Complexity: O(1)**

Practice this problem [Insert Node at the specific position of the list](https://www.hackerrank.com/challenges/insert-a-node-at-a-specific-position-in-a-linked-list)
