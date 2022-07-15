# DataStructures

## DS Foundations

A Data Structure is the collection of data values, the relationship among these values, and the functions and operations that we can apply on these

## Complexity Analysis

It is common for a problem to have multiple solution. There can be a better solution if this one has a better complexity. **Complexity** is the process of determining how efficient an algorithms is. Complexity analysis usually involves finding both the time complexity and the space complexity of an algorithm.

**Time Complexity:** A measure of how fast an algorithm runs, time complexity is a central concept in the field of algorithms and in coding interviews.

**Space Complexity:** A measure of how much auxiliary memory an algorithm takes up, space complexity is a central concept in the field of algorithms and in coding interviews.

## Memory

The bedrock of all DS, memory is the underlying concept that you absolutely need to know in order to understand why DS work they way the do

**Bit:** short for binary digit, a bit is a fundamental unit of information in CS that represents a state with one of two values, typically 0 and 1. Any data stored in a computer is, at the most basic level, represented in bits

**Byte:** A group of eight bits, for example 01101000 is a byte. A single byte can be represented up to 256 data values (2^8). A single binary number is a number expressed with only two symbols, like 0 and 1, a byte can effectively represent all of the numbers between 0 and 255, inclusive, in binary format. The following bytes represent the number 1, 2, 3, and 4 in binary format.

- 0000 0001
- 0000 0010
- 0000 0011
- 0000 0100

**Fixed-Width Integer:** An integer represented by fixed amount of bits. For example, a 32-bit integer is an integer represented by 32 bits (4 bytes), and a 64-bit integer is an integer represented by 64 bits (8 bytes).

The following is the 32-bit representation of the number 1, with clearly separated bytes:

00000000 00000000 00000000 00000001

Regardless of how large an integer is, its fixed-width-integer representation is, by definition, made up of a constant number of bits.

It follows that, regardless of how large an integer is, an operation performed on it fixed-with-integer representation consists of a constant number of bit manipulations, since the integer is made up of a fixed number of bits.

**Memory:** Broadly speaking, memory is the foundational layer of computing, where all data is stored.

In the context of coding interviews, it's important to note the following points:

- Data stored in memory is stored in bytes and, by extension, bits.
- Bytes in memory can "point" to other bytes in memory, so as to store references to other data.
- The amount of memory that a machine has is bounded, making it valuable to limit how much memory an algorithm takes up.
- Accessing a byte or a fixed number of bytes (like 4 bytes or 8 bytes in the case of 32-bit and 64-bit integers) is an elementary operation, which can be loosely treated as a single unit of operational work

## Big P Notation

The notation used to describe the time complexity and space complexity of algorithms. Variables used in Big O notation denote the sizes of inputs to algorithms. For example, O(n) might be the time complexity of an algorithm that traverses through an array of length n; similarly, O(n + m) might be the time complexity of an algorithm that traverses through an array of length n
and through a string of length m. The following are examples of common complexities and their Big O notations, ordered from fastest to slowest:

- Constant: O(1)
- Logarithmic: O(log(n))
- Linear: O(n)
- Log-linear: O(nlog(n))
- Quadratic: O(n2)
- Cubic: O(n3)
- Exponential: O(2n)
- Factorial: O(n!)

Note that in the context of coding interviews, Big O notation is usually understood to describe the worst-case complexity of an algorithm, even though the worst-case complexity might differ from the average-case complexity.
For example, some sorting algorithms have different time complexities depending on the layout of elements in their input array. In rare cases, their time complexity will be much worse than in more common cases. Similarly, an algorithm that takes in a string and performs special operations on uppercase characters might have a different time complexity when run on an input string of only uppercase characters vs. on an input string with just a few uppercase characters.
Thus, when describing the time complexity of an algorithm, it can sometimes be helpful to specify whether the time complexity refers to the average case or to the worst case (e.g., "this algorithm runs in O(nlog(n)) time on average and in O(n2) time in the worse case").

## Logarithm

A mathematical concept that's widely used in Computer Science and that's defined by the following equation:
logb(x) = y if and only if b^y = x
In the context of coding interviews, the logarithm is used to describe the complexity analysis of algorithms, and its usage always implies a logarithm of base 2. In other words, the logarithm used in the context of coding interviews is defined by the following equation:
log(n) = y if and only if 2^y = n
In plain English, if an algorithm has a logarithmic time complexity (O(log(n)), where n is the size of the input), then whenever the algorithm's input doubles in size (i.e., whenever n doubles), the number of operations needed to complete the algorithm only increases by one unit. Conversely, an algorithm with a linear time complexity would see its number of operations double if its input size doubled.
As an example, a linear-time-complexity algorithm with an input of size 1,000 might take roughly 1,000 operations to complete, whereas a logarithmic-time-complexity algorithm with the same input would take roughly 10 operations to complete, since 2 10 ~= 1,000.

## Arrays

Notes: there are 2 types, there is dynamic arrays, and static arrays.

For an static array, at initialization you specify the length of the array, and the system will allocate a specific amount of space in memory for the array.

When we are accessing an array, what is going on is that the OS is finding the starting index, then moving forward by the number of bytes necessary. For example, accessing arr[2] at an array that is long[10]. All the OS is doing is accessing the memory slot at 2 x 8 (long is 8 bytes). So in other words, an array points to the beginning, and moves forward by the index times the size of an element in memory!

A linear collection of data values that are accessible at numbered indices, starting at index 0.

The following are an array's standard operations and their corresponding time complexities:

- Accessing a value at a given index: O(1)
- Updating a value at a given index: O(1)
- Inserting a value at the beginning: O(n)
- Inserting a value in the middle: O(n)
- Inserting a value at the end:

  - amortized O(1) when dealing with a dynamic array
  - O(n) when dealing with a static array

- Removing a value at the beginning: O(n)
- Removing a value in the middle: O(n)
- Removing a value at the end: O(1)
- Copying the array: O(n)

A static array is an implementation of an array that allocates a fixed amount of memory to be used for storing the array's values. Appending values to the array therefore involves copying the
entire array and allocating new memory for it, accounting for the extra space needed for the newly appended value. This is a linear-time operation.

A dynamic array is an implementation of an array that preemptively allocates double the amount of memory needed to store the array's values. Appending values to the array is a constant-time
operation until the allocated memory is filled up, at which point the array is copied and double the memory is once again allocated for it. This implementation leads to an amortized constant-time insertion-at-end operation. A lot of popular programming languages like JavaScript and Python implement arrays as dynamic arrays.

## Linked List

Notes: Linked list are going to store elements in the list anywhere in memory, and they are going to connect the elements using memory!

**Singly Linked List**

A data structure that consists of nodes, each with some value and a pointer to the next node in the linked list. A linked list node's value and next node are typically stored in value and next properties, respectively.

The first node in a linked list is referred to as the head of the linked list, while the last node in a linked list, whose next property points to the null value, is known as the tail of the linked list. Below is a visual representation of a singly linked list whose nodes hold integer values:

0 -> 1 -> 2 -> 3 -> 4 -> 5 -> null

A singly linked list typically exposes its head to its user for easy access. While finding a node in a singly linked list involves traversing through all of the nodes leading up to the node in question (as
opposed to instant access with an array), adding or removing nodes simply involves overwriting next pointers (assuming that you have access to the node right before the node that you're adding or removing).

The following are a singly linked list's standard operations and their corresponding time complexities:

- Accessing the head: O(1)
- Accessing the tail: O(n)
- Accessing a middle node: O(n)
- Inserting / Removing the head: O(1)
- Inserting / Removing the tail: O(n) to access + O(1)
- Inserting / Removing a middle node: O(n) to access + O(1)
- Searching for a value: O(n)

**Doubly Linked List**

Similar to a singly linked list, except that each node in a doubly linked list also has a pointer to the previous node in the linked list. The previous node is typically stored in a prev property. Just as the next property of a doubly linked list's tail points to the null value, so too does the prev property of a doubly linked list's head.

Below is a visual representation of a doubly linked list whose nodes hold integer values:

null <- 0 <-> 1 <-> 2 <-> 3 <-> 4 <-> 5 -> null

While a doubly linked list typically exposes both its head and tail to its user, as opposed to just its head in the case of a singly linked list, it otherwise behaves very similarly to a singly linked list.

The following are a doubly linked list's standard operations and their corresponding time complexities:

- Accessing the head: O(1)
- Accessing the tail: O(1)
- Accessing a middle node: O(n)
- Inserting / Removing the head: O(1)
- Inserting / Removing the tail: O(1)
- Inserting / Removing a middle node: O(n) to access + O(1)
- Searching for a value: O(n)

**Circular Linked List**

A linked list that has no clear head or tail, because its "tail" points to its "head," effectively forming a closed circle. A circular linked list can be either a singly circular linked list or a doubly circular linked list.

## Hash Tables

**Hash Table**

A data structure that provides fast insertion, deletion, and lookup of key/value pairs. Under the hood, a hash table uses a dynamic array of linked lists to efficiently store key/value pairs. When inserting a key/value pair, a hash function first maps the key, which is typically a
string (or any data that can be hashed, depending on the implementation of the hash table), to an integer value and, by extension, to an index in the underlying dynamic array. Then, the valueassociated with the key
is added to the linked list stored at that index in the dynamic array, and a reference to the key is also stored with the value.

Hash tables rely on highly optimized hash functions to minimize the number of collisions that occur when storing values: cases where two keys map to the same index.

Below is an example of what a hash table might look like under the hood:

```
[
0: (value1, key1) -> null
1: (value2, key2) -> (value3, key3) -> (value4, key4)
2: (value5, key5) -> null
3: (value6, key6) -> null=
4: null
5: (value7, key7) -> (value8, key8)
6: (value9, key9) -> null
]
```

In the hash table above, the keys key2, key3, and key4 collided by all being hashed to 1, and the keys key7 and key8 collided by both being hashed to 5.

The following are a hash table's standard operations and their corresponding time complexities:

```
Inserting a key/value pair: O(1) on average; O(n) in the worse case
Removing a key/value pair: O(1) on average; O(n) in the worse case
Looking up a key: O(1) on average; O(n) in the worse case
```

The worst-case linear-time operations occur when a hash table experiences a lot of collisions, leading to long linked lists internally, which take O(n) time to traverse. However, in practice and especially in coding interviews, we typically assume that the hash
functions employed by hash tables are so optimized that collisions are extremely rare and constant-time operations are all but guaranteed.
