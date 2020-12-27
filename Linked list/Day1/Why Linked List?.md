# Why Linked Lists?
There are many data structures tha do the same thing as linked lists. Let's understand the difference between linked list and arrays. Both linked list and arrays are used to store collections of data, but we need to differentiate their usage.


### Disadvantages of Arrays:
* Preallocates all needed memory up front and waste memory for indices in the array that are empty.
* The size of array is static ( fixed and specify the array size before using it).
* One block allocation: Sometimes it may not be possible to get the memory for the complete array if array size is big.
* Insertion and Deletion operation requires shifting which is expensive process.
## Advantages of Linked List:
Can be **expanded in constant time**. To create an array, we must allocate memory for certain number of elements. To add more elements to the array when full, we must create a new array and copy the old array into the new array and **this can take a lot of time**.

**Solution** :We can solve this problem with linked list. With a Linked list, we can start with space for just one allocated element and add on new elements without the need to do any copying and reallocating.