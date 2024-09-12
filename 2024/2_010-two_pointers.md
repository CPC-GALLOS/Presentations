---
marp: true
title: 
theme: am_nord
paginate: true
headingDivider: [2,3]
author: Ariel Parra
footer: CPC Γα=Ω5
---

<!-- _class: cover_e -->
<!-- _paginate: "" -->
<!-- _footer: ![](./img/GALLOS_black_rectangle_transparent.png) -->
<!-- _header: ![](./img/GALLO.png) -->

# <!-- fit -->


Two pointers method
In the two pointers method, two pointers are used to iterate through the array
values. Both pointers can move to one direction only, which ensures that the
algorithm works efficiently. Next we discuss two problems that can be solved
using the two pointers method.
Subarray sum
As the first example, consider a problem where we are given an array of n positive
integers and a target sum x, and we want to find a subarray whose sum is x or
report that there is no such subarray.
For example, the array
1 3 2 5 1 1 2 3
contains a subarray whose sum is 8:
1 3 2 5 1 1 2 3
This problem can be solved in O(n) time by using the two pointers method.
The idea is to maintain pointers that point to the first and last value of a subarray.
On each turn, the left pointer moves one step to the right, and the right pointer
moves to the right as long as the resulting subarray sum is at most x. If the sum
becomes exactly x, a solution has been found.
77
As an example, consider the following array and a target sum x = 8:

[1] 3 2 5 1 1 2 3

The initial subarray contains the values 1, 3 and 2 whose sum is 6:
1 3 2 5 1 1 2 3

Then, the left pointer moves one step to the right. The right pointer does not
move, because otherwise the subarray sum would exceed x.


1 3 2 5 1 1 2 3

Again, the left pointer moves one step to the right, and this time the right
pointer moves three steps to the right. The subarray sum is 2 + 5 + 1 = 8, so a
subarray whose sum is x has been found.

1 3 2 5 1 1 2 3
The running time of the algorithm depends on the number of steps the right
pointer moves. While there is no useful upper bound on how many steps the
pointer can move on a single turn. we know that the pointer moves a total of
O(n) steps during the algorithm, because it only moves to the right.
Since both the left and right pointer move O(n) steps during the algorithm,
the algorithm works in O(n) time

https://cses.fi/book/book.pdf
# Two pointer:
