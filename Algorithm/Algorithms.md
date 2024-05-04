# Introduction
This Note Contains A Lot About All Sorts of Algorithms and the content is divided into different smaller parts.

Copyright: @QiuYiXiang

> Enjoy The Power of Algorithms ! :>

-Acknowledgement-
Reference TextBook : 

Introduction To Algorithm
![](../../_IMG/AL/Snipaste_2024-05-04_18-22-27.png)

Algorithm 4th
![](../../_IMG/AL/Snipaste_2024-05-04_18-23-41.png)

Reference University Course :
- Stanford CS 106B : Programming Abstraction
- Stanford CS 161 : Algorithm Analysis
- MIT 6.001 : Introduction to Algorithm


Overview of the Content:

- Algorithm Analysis
- Recursion

# Algorithm Analysis

# Recursion

## Basics of Recursion

There are two critical components to recursive functions:
1. **Base Case.** Include some sort of terminating condition that returns the result for some canonical case where we know the answer immediately.
2. **Recursive Call.** Decompose the current input into subproblems, one of which involves making a recursive call to the function

Example of easiest recursive function Factorial $n!$ !
if $n=5$ which means $1 \times2 \times3\times4\times5$ ,In the recursive call of $n!$ which mean we need to calculate $(n-1)!$

Base case : $n = 1$
recursive call : $n \times factorial(n-1)$
```c++
int factorial(int n){  
    if (n == 0)  
        return 1;  
    return n * factorial(n - 1);  
}
```
