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