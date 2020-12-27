# Linked List
A linked list is a data structure used for storing collections of data. A linked list is **linear dynamic data structure**. 
### Linked list has the following properties
* Each node of linked list is made up of two items- the data and reference to the next node. 
* Successive elements are connected by pointers.
* The entry point into linked list is called head of the list.(head os not a seperate node, but the reference to the first node)
* If the list is empty then the head is NULL.
* The last elements points to NULL.
* Can grow and shrink in size during execution of a program.
* Can be made just as long as required (until system memory exahusts).
* Does not waste memory space (but takes some extra memory for pointers). It allocates memory as list grows.

# Why Linked Lists?
There are many data structures tha do the same thing as linked lists. Let's understand the difference between linked list and arrays. Both linked list and arrays are used to store collections of data, but we need to differentiate their usage.

### Advantages of Arrays:
* Simple and easy to use.
* Faster access to the elements.

### Disadvantages of Arrays:
* Preallocates all needed memory up front and waste memory for indices in the array that are empty.
* The size of array is static ( fixed and specify the array size before using it).
* One block allocation: Sometimes it may not be possible to get the memory for the complete array if array size is big.
* Insertion and Deletion operation requires shifting which is expensive process.

# Dynamic Arrays
* Dynamic Arrays ( also called ar growable arrays, resizable array, dynamic table or array list) is a random access, variable-size list data structure that allows elements to be added or removed.
* One simple way of implementing dynamic arrays is to intially start with fixed size arrays.  As soon as that array become full, creates the new array double the size of the orignal array.

## Advantages of Linked List:
Can be **expanded in constant time**. To create an array, we must allocate memory for certain number of elements. To add more elements to the array when full, we must create a new array and copy the old array into the new array and **this can take a lot of time**.
**Solution** :We can solve this problem with linked list. With a Linked list, we can start with space for just one allocated element and add on new elements without the need to do any copying and reallocating.
### Disadvantages of Linked List ( Why Arrays over Linked list ) :
* Arrays take O(1) time to access the any element in the array, whereas linked list take O(n) for access to an element in the list in the worst case.
* Linked list waste memory in terms of extra reference points.

### Comparison of Linked list with Arrays and Dynamic Arrays
|            parameter            |         Linked List        |                Array               |                  Dynamic array                  |
|:-------------------------------:|:--------------------------:|:----------------------------------:|:-----------------------------------------------:|
|             Indexing            |            O(n)            |                O(1)                |                       O(1)                      |
| Insertion/Deletion at beginning |            O(1)            |                O(n)                |                       O(n)                      |
|       Insertion at ending       | O(1), if array is not full |                O(1)                | O(1) if array is not full O(n) if array is full |
|        Deletion at ending       |            O(n)            |                O(1)                |                       O(n)                      |
|       Insertion in middle       |            O(n)            | O(n), because of shifting elements |                       O(n)                      |
|        Deletion in middle       |            O(n)            | O(n), because of shifting elements |                       O(n)                      |
|           Wasted space          |     O(n), for pointers     |                  0                 |                       O(n)                      |

### Singly Linked List
* The linked list consist series of structures called **nodes** .
* The first part of node is field that stores data and second part is field that store pointer to node.
* Each node contains two fields: a data field and next field which is pointer used to link one node to the next node.

```c++
struct ListNode {            // defines a ListNode in a Linked List
    int data;                // the data
    struct ListNode* next;   // pointer to next ListNode
};
```
### Basic Operations on Linked list:
* Traversing the list
* Inserting an item in the list
* Deleting an item from the list

### Traversing the linked list:
Let us assume that the head points to the first node of the list. To traverse the list we do the following:
* Follow the pointers.
* Display the content of the nodes (or count) as they traversed.
* Stop when the next pointer points to NULL.

```c++
void print(struct ListNode* head) {
    struct ListNode *curr = head;
    while(curr != NULL) {
        cout<<curr->data<<" ";    // print the node's data
        curr = curr -> next;     // advancing the pointers
    }
    return;
}
```
* **Time Complexity: O(n), for scanning the list of size n**
* **Space Complexity: O(1), for creating a temporary variable**

Practice this problem [Print the element of Linked List](https://www.hackerrank.com/challenges/print-the-elements-of-a-linked-list)
### Singly Linked List Insertion
Insertion into a single linked list has three cases:
* Inserting a new node before the head (at the beginning).
* Inserting a new node after the tail (at the end of the list).
* Inserting a new node at the middle of the list (ranodom location).

### Inserting a Node in Singly Linked List at the Beginning
In this case, a new node is inserted before the current head node. Only one **next pointer** need to be modified and it can be done in two steps:
* Update the next pointer of new node, to point to the current head.
* Update head pointer to point to new node.
```c++
struct ListNode * insertAtBeginning(struct ListNode * head, int data) { // insert at beginnning of list
  ListNode * temp = new ListNode(); // create a node
  // create a new temp node
  temp -> data = data; // set temp data value
  temp -> next = NULL; // set as end of list

  if (head == NULL) { // then list empty, so set as head node
    head = temp;
    head -> next = NULL;
  } else { // else add tp left of list
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
* New node next points to NULL.
* Last nodes next pointer points to the new node.
```c++
struct ListNode * insertAtEnd(struct ListNode * head, int data) { // insert at end of list
  ListNode * temp = new ListNode(); // create a node
  ListNode * curr = head; // iterator for list
  // create a new temp node
  temp -> data = data; // set temp data value
  temp -> next = NULL; // set as end of list

  if (curr == NULL) { // then list empty, so set temp as head
    head = temp;
  } else {
    // find end of current list
    while (curr != NULL) {
      curr = curr -> next;
    }
    // curr is now the last node in list (next==NULL)
    // set temp as new next node
    curr -> next = temp;
  }
  return head;
}
```
* **Time Complexity: O(n), for scanning the list of size n**
* **Space Complexity: O(1)**

Practice this problem [Insert Node at the end of the list](https://www.hackerrank.com/challenges/insert-a-node-at-the-tail-of-a-linked-list)
### Inserting a Node in Singly Linked List at the Given Position
Let us assume that we are given a position where we want to insert the new node. In this case also, we need to modify two next pointers.

```c++
// Insert a new node (new) at positon n and returns head.
// head - reference of list
// newNode - node to be inserted
// n - position for insertion
struct ListNode * insertAtEnd(struct ListNode * head, struct ListNode * newNode, int n) {
  // pred will point to predecessor of new
  ListNode * pred = head;
  //Special case: adding at head
  if (n <= 1) {
    newNode -> next = head;
    return newNode;
  }
  // find the n-1 node (predecessor): decrement and move down the list
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