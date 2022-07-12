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


