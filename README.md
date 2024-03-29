## p1

Given 2021/09/12 is Sunday, please provide an algorithm to calculate every date's weekday.

> Solution

To avoid paying to much attention on handling leap year's February case, we can use year's 1th Jan as pivot. To do this, extra days should be recorded, since we only know current day as pivot (or any other day given by the problem).

## p2

Given a number n, please print all available sequence in order.
e.g. n = 4
1
2
3
4
1 2
1 3
1 4
2 3
2 4
3 4
1 2 3
...
1 2 3 4

> Solution

Just recurse, the tranferring state is (currentSeq, leftSize)

## P3

Given ascending arrays A and B, length of m and n respectively. Please provide an algorithm to find the k-th number in these two arrays in O(lg(m+n)) time.

> Solution

The easiest way is to merge the two arrays until meets the kth item, which is O(k). To accelerate, we should notice that these 2 arrays are ascending, which means we can exclude a series of items at a time.

So, we can try to exclude k/2 items in one of the array:

- If `A[k/2] < B[k/2]`, then we can exclude k/2 item in A, vice versa.
- Let's say we have `A[k/2] < B[k/2]`, after previous step, we run `findKth(A[k/2:], B[:], k-k/2)`


## P4
Given N, which means you have numbers from 0~N-1. Given an mutex array indicates which two number should not be in the same group. Try to divide all the numbers into fewest groups.

eg. N=6, M=3, mutex=[[3, 5], [4, 3], [1, 2]]
Divided into fewest groups: [0, 1, 3] [2, 4, 5], so the output is 2 groups.

> Solution

Construct a graph from mutex array, then color it.

## P5
Implement an IEEE float triming machanim.

eg:
1.0100, reserve 1 decimal => 1.0
1.1100, reserve 1 decimal => 10.0


## P6
Given a senario that there are lots of events, each event has 2 properties: 
1. time, indicating when the event happened
2. type, indicating the type

Please provide a fucntion that finds out the top-K existing event types in a time window [a, b].

## P7
Implement the word counter example in MapReduce thesis.

## P8
Implement LRU.

PS: implement thread-safe LRU.

## P9
There is a batch of order records, and the data includes the order ID, entry time, and departure time.

Enter a time A, and you need to find all records that meet the time range of entering and leaving the store in this batch of records (A is greater than or equal to the time of entering the store, and A is less than or equal to the time of leaving the store).

The time complexity of a single query should be lgN.

Note that the order ID should be output in ascending order


## P10
Determine if a 9 x 9 Sudoku board is valid. Only the filled cells need to be validated according to the following rules:

- Each row must contain the digits 1-9 without repetition.
- Each column must contain the digits 1-9 without repetition.
- Each of the nine 3 x 3 sub-boxes of the grid must contain the digits 1-9 without repetition.

Note:
A Sudoku board (partially filled) could be valid but **is not necessarily solvable**.
Only the filled cells need to be validated according to the mentioned rules.

## P11
Given an array of meeting time intervals intervals where intervals[i] = [starti, endi], return the minimum number of conference rooms required.

## P12
There are n goods, each good has 3 properties a, b, c.

For good_i, if there is good_j that aj > ai, bj > bi, cj > ci, then good_i is marked as invalid.

Provide and algorithm to calculate how many goods are invalid.

## P13
Conver camelcase naming string to a underscore naming string.

## P14
Given several sets of 32-bit int numbers, the numbers in each set are not repeated. Please merge the sets that have intersections.

[1,2,3] [2,3,5] [8]
-> [1,2,3,5] [8]

## P15
Given two strings s and t , return the minimum substring of s such that every character in t (including duplicates) is included in the substring. If there is no such substring, return the empty string "".

A substring is a contiguous sequence of characters within the string.

## P16
Remove duplicate element in a sorted list.

## P17
Find the median from sorted int-stream.

If the current size of the stream is even, there is no middle value and the median is the mean of the two middle values.

Note that the stream can either be ascending or descending.

Follow up:
1. If all integer numbers from the stream are in the range [0, 100], how would you optimize your solution?
2. If 99% of all integer numbers from the stream are in the range [0, 100], how would you optimize your solution?

## P18 HARD!
Josephus Problem

There are N people sit in a table, numbered from 1 to N, and begin reporting number from the 1st person.

The number reported also starts from 1, the person who reports M should leave, then the next member continues to report the number from 1.

Reproduce this process (the departure order), or find the number of the last member present

## 19
Describe how you could use a single array to implement three stacks.

You should implement push(stackNum, value)、pop(stackNum)、isEmpty(stackNum)、peek(stackNum) methods. stackNum is the index of the stack. value is the value that pushed to the stack.

The constructor requires a stackSize parameter, which represents the size of each stack.

## 20
Implement a Trie url router.


## 21
Serialize and deserial a binary-tree.

## 22
Realize a structure to effectively store one-dimensional sparse matrix(or vector), and support matrix multipication.

Follow up:
What if to store dense matrix?