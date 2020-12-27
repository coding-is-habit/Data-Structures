### Traversing the linked list:
Let us assume that the head points to the first node of the list. To traverse the list we do the following:
### Approach:
* Follow the pointers.
* Display the content of the nodes (or count) as they traversed.
* Stop when the next pointer points to NULL.

**Below is the implementation of the above algorithm.**
```c++
// prints all the nodes of Linked List
// head- pointer to head of Linked List
void print(struct ListNode* head) {
    struct ListNode *current = head;
    while(current != NULL) {
        cout<<current->data<<" ";    // print the node's data
        current = current -> next;     // advancing the pointers
    }
    return;
}
```
* **Time Complexity: O(n), for scanning the list of size n**
* **Space Complexity: O(1), for creating a temporary variable**

Practice this problem [Print the element of Linked List](https://www.hackerrank.com/challenges/print-the-elements-of-a-linked-list)
