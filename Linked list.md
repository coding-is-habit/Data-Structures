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
