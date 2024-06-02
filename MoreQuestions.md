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

## Complexity

A) Analys the below code snippet's complexity in N, we assume N here is a power of 2:

```
count = 0;
i = N;
while i > 0: 
  for j in range(0, i) 
      count++;
  i = i//2;
```
B) Analys the below code snippet's complexity in N, note that they are all recursive functions!

**Take Away**: the <font color="red">first step</font> of analysing recursive functions' complexity is calculating the how many times will the function be called. The <font color="red">second</font> step is analysing the cost of calling once of the function. In the end, times them together.

B.1)
```
def recursiveFun1(n):
  if n <= 0:
    return 1
  else:
    return 1 + recursiveFun1(n-1)
```
B.2)
```
def recursiveFun2(n):
  if n <= 0:
    return 1
  else:
    return 1 + recursiveFun2(n-5)
```
B.3)
```
def recursiveFun3(n):
  if n <= 0:
    return 1
  else:
    return 1 + recursiveFun3(n//2)
```
B.4)
```
def recursiveFun4(n):
  for i in range(n):
    <O(1) operations>
  if n <= 0:
    return 1
  else:
    return 1 + recursiveFun4(n-1)
```

## Generally Tricky challenges

### Check Neighbours Again
 Given a string like below:

```
"
467..114..
...*......
..35..633.
......#...
617*......
.....+.58.
..592.....
......755.
...$.*....
.664.598..
"
```

We consider this string has two numbers that is now a "part number", 114 (top right) and 58 (middle right). It require a number to be **adjacent to a symbol** , even diagonally to be qualified as a part number.

Write a program that calculates the sum of the part numbers in such a string. You can assume that each line of the string contains the same amount of characters. 

### Poker Night

The word of snakes is a bit different to us, in the snake world, they play the game of cards like this, A hand of snake poker consists of five cards labled from "A, K, Q, J, T, 9, 8, 7, 6, 5, 4, 3, 2", where A is the strongest card, and 2 is the lowest.

Every hand is exactly one type, from strongest to weakest, they are:

>Five of a kind, where all five cards have the same label: AAAAA

>Four of a kind, where four cards have the same label and one card has a different label: AA8AA

>Full house, where three cards have the same label, and the remaining two cards share a different label: 23332

>Three of a kind, where three cards have the same label, and the remaining two cards are each different from any other card in the hand: TTT98

>Two pair, where two cards share one label, two other cards share a second label, and the remaining card has a third label: 23432

>One pair, where two cards share one label, and the other three cards have a different label from the pair and each other: A23A4

>High card, where all cards' labels are distinct: 23456

If two hands have the same type, a second ordering rule takes effect. Start by comparing the first card in each hand. If these cards are different, the hand with the stronger first card is considered stronger. If the first card in each hand have the same label, however, then move on to considering the second card in each hand. If they differ, the hand with the higher second card wins; otherwise, continue with the third card in each hand, then the fourth, then the fifth.

So, 33332 and 2AAAA are both four of a kind hands, but 33332 is stronger because its first card is stronger. Similarly, 77888 and 77788 are both a full house, but 77888 is stronger because its third card is stronger (and both hands have the same first and second card).

Write a ranking algorithm that ranks the hands of pokers by the above rule of strengths. For example, the input: 

```
"
32T3K
T55J5
KK677
KTJJT
QQQJA
"
```
is ranked into:
>32T3K is the only one pair and the other hands are all a stronger type, so it gets rank 1.

>KK677 and KTJJT are both two pair. Their first cards both have the same label, but the second card of KK677 is stronger (K vs T), so KTJJT gets rank 2 and KK677 gets rank 3.

>T55J5 and QQQJA are both three of a kind. QQQJA has a stronger first card, so it gets rank 5 and T55J5 gets rank 4.