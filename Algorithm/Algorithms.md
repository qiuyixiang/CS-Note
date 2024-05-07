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
- Search
- Sort

# Algorithm Analysis

## Big-O Analysis

Here is some general outline for Big-O Analysis
- Assume the input is arbitrarily huge
- Find the statement (or statements) executed the most in that function, and count how many times they occur
- Drop any constant coefficients from your approximation and take the highest-order term as the Big-O runtime

| Big-O Runtime  | Alternative Phrasing | Description                                                                                             |
| -------------- | -------------------- | ------------------------------------------------------------------------------------------------------- |
| $O(n^3)$       | cublic               | this is a triple loop, with two nested loop                                                             |
| $O(n^2)$       | quadratic            | this is a double loop often occur with a nested loop                                                    |
| $O(n)$         | linear               | This is a n-based loop with only one loop                                                               |
| $O(n\ log\ n)$ | linearithmic         | if you repeatedly divide your input in half, and you  incur an $O(n)$ operation each time you do so     |
| $O(log\ n)$    | logarithmic          | if you repeatedly divide your input in half, and you only incur an $O(1)$ operation each time you do so |
| $O(2^n)$       | exponential          | if bumping your input up by 1 causes your runtime to double                                             |
| $O(1)$         | constant             | always do some fixed operations                                                                         |

> Important Note : $O(log\ n)$ most of the time means $O(log_2\ n)$
> This is because will always divide the input into two parts


Big-O Comparison
![](../../_IMG/AL/Snipaste_2024-05-05_12-23-49.png)
The Picture Above is Just a Approximation of Big-O Algorithm Chart,
Here is a Very Concise Chart.![](../../_IMG/AL/Snipaste_2024-05-05_12-42-38.png)

We can see that $O(log\ n)$ is very close to $O(n)$ and $O(2^n)$ is very close to $O(n^2)$ 


# Recursion

## Basics of Recursion

There are two critical components to recursive functions:
1. **Base Case.** Include some sort of terminating condition that returns the result for some canonical case where we know the answer immediately.
2. **Recursive Call.** Decompose the current input into subproblems, one of which involves making a recursive call to the function

## Examples

### Factorial
Easiest recursive function Factorial $n!$ 
if $n=5$ which means $1 \times2 \times3\times4\times5$ ,In the recursive call of $n!$ which mean we need to calculate $(n-1)!$

Base case : $n = 1$
recursive call : $n \times factorial(n-1)$
```c
int factorial(int n){  
    if (n == 0)  
        return 1;  
    return n * factorial(n - 1);  
}
```


### Maze Problem

Consider the flowing problem, there is a maze (a two dimensional array),
in the initial position _pos_ you need to get to the right-bottom of the maze, which can only go through _true_ block, how many routes you can go ?
```c++
int countWaysToEscape(Grid<bool>& maze, GridLocation location) {
    if (location.col == maze.numCols() - 1 && location.row == maze.numRows() - 1)
        return 1;
    int right_direction = 0;
    int down_direction = 0;

    // go right
    if (maze.inBounds(GridLocation(location.row, location.col + 1)) &&
        maze[GridLocation(location.row, location.col + 1)]){
        right_direction = countWaysToEscape
            (maze,GridLocation(location.row, location.col + 1));
    }
    // go down
    if (maze.inBounds(GridLocation(location.row + 1, location.col)) &&
        maze[GridLocation(location.row + 1, location.col)]){
        down_direction = countWaysToEscape
            (maze,GridLocation(location.row + 1, location.col));
    }
    return (right_direction + down_direction);
}
```

> this problem come from Stanford CS 106B Section2



# Search

## Linear Search

Linear Search look through the whole array to find some element.
Run-time Analysis : $O(n)$
- The best run-time : $O(1)$
- The Worst run-time : $O(n)$

Coding for a simple Linear Search
```c++
template<typename Tp>  
bool linear_search(const std::vector<Tp>& buffer, const Tp& target){  
    for (const auto & data : buffer)  
        if (data == target)  
            return true;  
    return false;  
}
```

## Binary Search

Binary Search is a more efficient way to find an element in the sorted group
Run-time Analysis : $O(log\ n)$

1. sorted the group
2. compare element with the middle element
3. narrow down the compare range to the right range or the left range
4. repeat the step 2

Iteration Implementation
```c++
template<typename _Tp>  
int binary_search_iteration(const std::vector<_Tp>& buffer, const _Tp& target){  
    int _left_index = 0;  
    int _right_index = buffer.size() - 1;  
    for (int _middle_index = (_left_index + _right_index) / 2 ;  
    _middle_index >= _left_index && _middle_index <= _right_index; ){  
        if (buffer[_middle_index] == target)  
            return _middle_index;  
        if (buffer[_middle_index] < target){  
            // search right range  
            _left_index = _middle_index + 1;  
            _middle_index = (_left_index + _right_index) / 2;  
        } else{  
            // search left range  
            _right_index = _middle_index - 1;  
            _middle_index = (_left_index + _right_index) / 2;  
        }  
    }  
    return int(-1);  
}
```

Recursive Implementation
```c++
template<typename _Tp>  
int __binary_search_recursive(const std::vector<_Tp>& _buffer, const _Tp& _target, int _low, int _high){  
    int _middle = (_low + _high) / 2;  
  
    if (_middle > _high || _middle < _low)  
        return  -1;  
  
    if (_buffer[_middle] == _target)  
        return _middle;  
  
    /// Search Left Range  
    if (_buffer[_middle] > _target)  
        return __binary_search_recursive(_buffer, _target, 0, _middle - 1);  
    /// Search Right Range  
    else  
        return __binary_search_recursive(_buffer, _target, _middle + 1, _high);  
}  

template<typename _Tp>  
int binary_search_recursive(const std::vector<_Tp>& buffer, const _Tp& target){  
    return __binary_search_recursive(buffer, target, 0, buffer.size() - 1);  
}
```


# Sort