# Sorting and Searching Algorithms :sparkler:

This project assignment is prepared for the 'Kodluyoruz' course. It includes 'insertion sort, selection sort, merge sort, binary search tree' sorting, and searching algorithms.



## Selection / Insertion Sort :star:
---
### Insertion sort :sparkles:
Linear

The worst case and average case are O(n^2). The best case (already sorted) is O(n). Shifting is performed. It starts from index 1. The number is checked against its left. If the left one is larger, it is shifted to the right. Otherwise, it moves to index 2. If the left number is larger, it is shifted to the right.


```cs
[22,27,16,2,18,6]
```
1) ***:question:Write down the steps of the given array according to the sorting type.***

<br/>

   ```cs
// It starts from index 1. Checks left. Since the number on the left is smaller, there's no change.
[22,27,16,2,18,6]
// The number at index 2 (16) is compared with those on its left (27, 22). Since the ones on the left are larger, they're shifted to the right.
[16,22,27,2,18,6]
// The number at index 3 (2) is compared with those on its left. The larger numbers on the left are shifted to the right.
[2,16,22,27,18,6]
// The number at index 4 (18) is compared with those on its left. The larger numbers on the left are shifted to the right.
[2,16,18,22,27,6]
// The number at index 5 (6) is compared with those on its left. The larger numbers on the left are shifted to the right. Thus, the list is sorted.
[2,6,16,18,22,27]
   
   ```

<br/>    

2) ***:question:Write the Big-O notation***
:white_check_mark: *The total number of comparisons (worst and average): n + (n-1) + (n -2) ... 1 => n&#42;(n+1/2) => O(n^2)*

<br/>

3) ***:question:Time Complexity: After the array is sorted, which of the following cases does the number 18 fall into? Write down.***

    
    ***a&#41;*** Average case: The number we are looking for is in the middle.
    ***b&#41;*** Worst case: The number we are looking for is at the end.
    ***c&#41;*** Best case: The number we are looking for is at the beginning of the array.


    :white_check_mark: ***a&#41; Avarage case `[2,6,16,18,22,27]`***

<br/>

### Selection Sort :sparkles:
Linear

First, the smallest (or largest) element in the list is found and swapped with the one at the beginning. Numbers continue to be sorted by swapping places.

The entire list is traversed each time (except for the sorted part). Hence, initially, there are n operations. For the comparison of the 2nd number, (n-1) operations remain. It proceeds like this. At each step, n-1 comparisons are made.

n + (n-1) + (n-2) + .... + 1
The sum of operations from 1 to n = n*(n+1)/2. Therefore, the big O notation is O(n^2).

```cs
[7,3,5,8,2,9,4,15,6]
```

***:question:Write down the steps of the array according to Selection Sort.***



```cs
// The smallest element (2) is found and swapped with the one at the beginning (7).
[2,3,5,8,7,9,4,15,6]
// The smallest 2nd element (3) is found. No changes occur.
[2,3,5,8,7,9,4,15,6]
// The smallest 3rd element (4) is found. Swap is performed with (5).
[2,3,4,8,7,9,5,15,6]
// The smallest 4th element (5) is found. Swap is performed with (8).
[2,3,4,5,7,9,8,15,6]
// The smallest 5th element (6) is found. Swap is performed with (7).
[2,3,4,5,6,9,8,15,7]
// The smallest 6th element (7) is found. Swap is performed with (9).
[2,3,4,5,6,7,8,15,9]
// The smallest 7th element (8) is found. No changes occur.
[2,3,4,5,6,7,8,15,9]
// The smallest 8th element (9) is found. Swap is performed with (15).
[2,3,4,5,6,7,8,9,15]
// Thus, our list is sorted according to the selection sort algorithm.

```
    

## Merge Sort :star:
---
Logarithmic
O(nlogn)
Divides into smallest parts (until only one element remains) - divide
Sorts while merging - conquer

<br/>

```cs
[16,21,11,8,12,22]
```

1) ***:question:Write down the steps of the given array according to the sorting type.***

```cs
                                             [16,21,11,8,12,22]
 Division stages                              /             \
 1. Divide into halves:                  [16,21,11]     [8,12,22]
                                          /    \          /   \
 2. Divide again:                      [16]  [21,11]  [8,12] [22]
                                               /  \     / \
 3. Divide again:                           [21] [11] [8] [12]


Merging stages                         [16] [21] [11] [8] [12] [22]
                                           \/        \/       \/
1. Merge by sorting:                     [16,21]   [8,11]   [12,22]
                                                 \/ 
2. Merge again:                           [8,11,16,21]   [12,22]
                                                       \/
3. Merge again:                                [8,11,12,16,21,22]

// Thus, after division and merging stages, the array is sorted as follows:
[8,11,12,16,21,22]

```

<br/>

2) ***:question:Write the Big-O notation***
:white_check_mark: *O(nlogn)*

## Binary Search Tree :star:
---
First, the root node is selected.
Only left and right children can be added.
Left children must always be smaller than the parent.
Right children must always be larger than the parent.
Every added node is in leaf state.


```cs
[7,5,1,8,3,6,0,9,4,2]
```
 1) ***:question:Write the Binary Search Tree stages of the given array.***
 ```cs
 7 is selected as the root node.                              7
                                                             /
5 is added to the left because it's smaller.                5
                                                           /
                                                          1
                                                               7
                                                                \
8 is added to the right of 7.                                    8  

                                                          1
                                                           \
3 is added to the right of 1.                               3

                                                           5
                                                            \
6 is added to the right of 5.                                6

                                                          1
                                                         /
0 is added to the left of 1.                            0

                                                                 8
                                                                  \
9 is added to the right of 8.                                      9

                                                           3
                                                            \
4 is added to the right of 3.                                4

                                                           3
                                                          /
2 is added to the left of 3.                             2


Here is the completed form:


                                                            7
                                                           / \
                                                          5   8
                                                         / \   \
                                                        1   6   9
                                                       / \
                                                      0   3  
                                                         / \
                                                        2   4   
  
 ```