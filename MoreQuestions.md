## Lists

### Q1: is a list sorted (easy)

Write a function called is_sorted that takes a list as a parameter and returns True if the list is sorted in ascending order and False otherwise. For example:
> is_sorted([1, 2, 2])
True
> is_sorted(['b', 'a'])
False

### Q2: Anagrams (little above easy)

Two words are anagrams if you can rearrange the letters from one to spell the other. Write a function called is_anagram that takes two strings and returns True if they are anagrams.

## Dicts

### Sparse Matrix

Asparse vector is a vector whose entries are almost all zero, like [1, 0, 0, 0, 0, 0, 3, 0, 0, 0]. Storing all those zeroes in a list wastes memory, so programmersoften use dictionaries instead to keep track of just the nonzero entries. For example, the vector shown earlier would be represented as {0:1, 6:3}, since the vector it is meant to represent has the value 1 at index 0 and the value 3 at index 6.

a) Write a function called sparse_add that takes two sparse vectors stored as dictionaries and returns a new dictionary representing their sum.1

b) Write another function called sparse_dot that calculates the dot product of two sparse vectors.

c) Your boss has asked you to write a function called sparse_len that will return the length of a sparse vector (just as Python’s len returns the length of a list). What do you need to ask her before you can start writing it?
