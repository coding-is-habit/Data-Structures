## Delete last occurrence of an item from linked list

##### Given a liked list and a key to be deleted. Delete last occurrence of key from linked. The list may have duplicates.
Examples:
```
Input:   1->2->3->5->2->10, key = 2 
Output:  1->2->3->5->10
```
#### Intution:
* Traverse the linked list from beginning to end. 
* While traversing, keep track of last occurrence key. 
* After traversing the complete list, delete last occurrence by copying data of next node and deleting the next node.

```c++
// Function to delete the last occurrence 
void deleteLast(ListNode * head, int x) {
  ListNode * current = head, * previous = NULL;
  while (current) {

    // If found key, update 
    if (current -> data == x)
      previous = temp;
    current = current -> next;
  }

  // If the last occurrence is the last node 
  if (previous != NULL && previous -> next == NULL) {
    current = head;
    while (current -> next != previous)
      current = current -> next;
    current -> next = NULL;
  }

  // If it is not the last node 
  if (previous != NULL && previous -> next != NULL) {
    previous -> data = previous -> next -> data;
    current = previous -> next;
    previous -> next = previous -> next -> next;
    free(current);
  }
}
```
**Time Complexity:**  O(n), though we do have to make several passes of the list due to the reverses.

**Space Complexity:**  O(1) .

**Practice this Problem:**  [**Remove Linked List Elements**](https://leetcode.com/problems/remove-linked-list-elements/)
