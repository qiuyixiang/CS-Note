# Introduction
This Note Contains A Lot About All Sorts of Algorithms and the content is divided into different smaller parts.

Copyright: @QiuYiXiang

> Enjoy The Power of Algorithms ! :>

-Acknowledgement-
Reference TextBook : 

Introduction To Algorithm
![](../_IMG/AL/Snipaste_2024-05-04_18-22-27.png)

Algorithm 4th
![](../_IMG/AL/Snipaste_2024-05-04_18-23-41.png)

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
![](../_IMG/AL/Snipaste_2024-05-05_12-23-49.png)
The Picture Above is Just a Approximation of Big-O Algorithm Chart,
Here is a Very Concise Chart.
![](../_IMG/AL/Snipaste_2024-05-05_12-42-38.png)

We can see that $O(log\ n)$ is very close to $O(n)$ and $O(2^n)$ is very close to $O(n^2)$ 

# Recursion

## Basic Recursion

There are two critical components to recursive functions:
1. **Base Case.** Include some sort of terminating condition that returns the result for some canonical case where we know the answer immediately.
2. **Recursive Call.** Decompose the current input into subproblems, one of which involves making a recursive call to the function

Basic Recursion is quite easy, In most cases, you can translate the mathematical definition directly into a recursive implementation by plugging the appropriate expressions into the standard recursive paradigm.

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

### Fibonacci


### Pascal’s Triangle

The Pascal's Triangle Formula is defined Here : 
$$ c(n, k) = \frac{n!}{k!\ \times
 (n - k )!}$$
And Using this Formula, we can form this Triangle :
![](../_IMG/AL/Snipaste_2024-05-10_12-19-28.png)
Pascal’s Triangle has the interesting property that every entry is the sum of the two entries above it, except along the left and right edges, where the values are always 1.
![](../_IMG/AL/Snipaste_2024-05-10_12-18-52.png)
This entry, which corresponds to c(6, 2), is the sum of the two entries—5 and 10—that appear above it to either side.

Simple Implementation (Without Generating the Triangle And Without Optimization): 
```c++
int __factorial(int n){  
    if (n == 1)  
        return n;  
    return n * __factorial(n - 1);  
}  
int c(int n, int k){  
    if (k == 0 || n == k)  
        return 1;  
    return (__factorial(n)) / (__factorial(k)  * __factorial(n - k));  
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


## Advanced Recursion

### Towers of Hanoi
Towers of Hanoi is a very classical example of Advanced Recursion

![](../_IMG/AL/Snipaste_2024-05-10_13-30-20.png)
At the beginning, all eight disks are on spire A. Your goal is to move the eight disks from spire A to spire B, while adhering to the following rules:

- You can only move one disk at a time.
- You are not allowed to move a larger disk on top of a smaller one.

In order to apply recursion to the Towers of Hanoi problem, you must first frame the problem in more general terms. Although the ultimate goal is to move eight disks from A to B, the recursive decomposition of the problem will involve moving smaller subtowers from spire to spire in various configurations. In the more general case, the problem you need to solve is moving a tower of a given height from one spire to another, using the third spire as a temporary repository. To ensure that all subproblems fit the original form, your recursive procedure must therefore take the following arguments:

1. The number of disks to move
2. The name of the spire where the disks start out
3. The name of the spire where the disks should finish
4. The name of the spire used for temporary storage

Problem Solving :

------------ 
The goal here is to move eight disks from spire A to spire B. You need to ask yourself how it would help if you could solve the same problem for a smaller number of disks. In particular, you should think about how being able to move a stack of seven disks would help you to solve the eight-disk case.

you can solve the problem by dividing it into these three steps:

1. Move the entire stack consisting of the top seven disks from spire A to spire C. 
![](../_IMG/AL/Snipaste_2024-05-10_17-00-11.png)
2. Move the bottom disk from spire A to spire B.  
 ![](../_IMG/AL/Snipaste_2024-05-12_12-59-06.png)
3. Move the stack of seven disks from spire C to spire B.
![](../_IMG/AL/Snipaste_2024-05-12_12-59-32.png)
Code Solution : 
```c++
void __move_single(char __start, char __finish){  
    std::cout<<__start<< " -> " << __finish <<"\n";  
}  
void hanoi(int n, char start, char finish, char temp){  
    if (n == 1)  
        __move_single(start, finish);  
    else{  
        hanoi(n - 1, start, temp, finish);  
        __move_single(start, finish);  
        hanoi(n - 1, temp, finish, start);  
    }  
}  
int main(int argc, char *argv[]) {  
    hanoi(3, 'A', 'B', 'C');  
    return 0;  
}
```

Output Result:
```shell
A -> B
A -> C
B -> C
A -> B
C -> A
C -> B
A -> B
```
### SubSet

Given a Set $\{1,2,3\}$ write a function that generate the given result 
$$ \{1,2,3\} \rightarrow \{\{2\}, \{1,2\}, \{1\}, \{\}, \{2,3\}, \{1,2,3\}, \{1,3\}, \{3\}\}$$
which has similar effect with the power set of a set in Discrete Mathematics
The size of the set is 2 so it will generate a 8-size-set $2^3 = 8$ ($2^N$)

Deal With this Problem Using Recursion :
```c++
using subset = std::vector<std::vector<int>>;  
  
subset generate_subset(std::vector<int> buffer){  
    if (buffer.empty())  
        return {{}};  
    auto element = buffer.back();  
    buffer.pop_back();  
    subset result{};  
    for (auto & inner : generate_subset(buffer)){  
        auto inner_copy = inner;  
        // without the last element
        result.push_back(inner);  
		// with the last element
        inner_copy.push_back(element);  
        result.push_back(inner_copy);  
    }  
    return result;  
}  
  
void display(const subset& buffer){  
    std::cout<<"{";  
    for (auto outer = buffer.begin(); outer != buffer.end(); ++outer){  
        if (outer->empty())  
            std::cout<<"{}";  
        else{  
            std::cout<<"{";  
            for (auto Iter = outer->begin(); Iter != outer->end(); ++Iter){  
                std::cout<<*Iter;  
                if(Iter != outer->end() - 1)  
                    std::cout<<",";  
            }  
            std::cout<<"}";  
        }  
        if (outer != buffer.end() - 1)  
            std::cout<<", ";  
    }  
    std::cout<<"}\n";  
}
```

### Permutation String

Generate permutation For String
Given a string `ABC` list all possible permutation for this string
```shell
{ABC, ACB, BAC, BCA, CAB, CBA}
```

Implementation Using `str[0] str[1-N]`
```c++
std::set<std::string> generate_permutation(std::string str){  
    if (str.empty())  
        return {};  
    else{  
        const char first_element = str[0];  
        auto rest = str.substr(1);  
        auto result = generate_permutation(rest);  
        if (result.empty()){  
            result.insert(std::string{first_element});  
            return result;  
        }  
        std::set<std::string>__result;  
        for (auto & element : result){  
            for (size_t index = 0; index <= element.size(); ++index){  
                auto ele_copy = element;  
                ele_copy.insert(index, 1, first_element);  
                __result.insert(ele_copy);  
            }  
        }  
        return __result;  
    }  
}
```
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

## Selection Sort

Selection Sort go through the whole range of unsorted array, and search the smallest element in the array first, and mark it as smallest element and then after first loop it will swap the smallest element with the _left-most position_ element. And repeat the process for the remaining unsorted portion of the array.

![](../_IMG/AL/Snipaste_2024-06-19_09-37-49.png)
Example:
```c++
void selection_sort(std::vector<int>& buffer){  
    for (int index = 0; index != buffer.size() - 1; index++){  
        int smallest_element_index = index;  
        for (int loop_thr = index + 1; loop_thr != buffer.size(); ++loop_thr){  
            if (buffer[loop_thr] < buffer[smallest_element_index])  
                smallest_element_index = loop_thr;  
        }  
        std::swap(buffer[smallest_element_index], buffer[index]);  
    }  
}
```

Worst-Case Runtime : $O(n^2)$
Best-Case Runtime : $O(n^2)$

Operations: Heavy on comparisons, light on swaps.It spends a lot of time comparing elements in each pass before settling on which one to swap into the next target position.
## Insertion Sort

Insertion Sort insert one element into sorted range. Initially, consider the first element to constitute a separate, sorted vector. Then pull the first element out of the unsorted partition of the vector.
![](../_IMG/AL/Snipaste_2024-06-19_15-00-19.png)

```c++
void insert_sort(std::vector<int>& buffer){  
    for (int index = 1; index != buffer.size(); ++index){  
        int value = buffer[index];  
        int target_index = index;  
        for (int compare_index = index - 1; buffer[compare_index] > value  
        && compare_index >= 0; --compare_index){  
            buffer[target_index] = buffer[compare_index];  
            --target_index;  
        }  
        buffer[target_index] = value;  
    }  
}
```
Only Mark it without actually swap the elements.

Worst-Case Runtime : $O(n^2)$
Best-Case Runtime : $O(n)$
Operations: Heavy on swaps, potentially light on comparisons. A pass of insertion sort stops as soon as it encounters an element smaller than the one it's dragging down, though, meaning that it could potentially stop each pass early and end up doing fewer comparisons than selection sort.

## Merge Sort

Merge Sort will break down the vector, then merge the pieces back together.

Overview 
![](../_IMG/AL/Snipaste_2024-06-19_15-59-14.png)
Just Like a Decision Tree, When there is only one element in the buffer which have reached our base case.
![](../_IMG/AL/Snipaste_2024-06-19_16-03-20.png)

Example Using Recursive: 
```c++
void merge_sort(std::vector<int>& buffer, int low_index, int high_index){  
    if (low_index >= high_index)  
        return;  
    int mid_index = low_index + (high_index - low_index) / 2;
    merge_sort(buffer, low_index, mid_index);  
    merge_sort(buffer, mid_index + 1, high_index);  
    std::vector<int> auxiliary_buffer;  
    int _left = low_index;  
    int _right = mid_index + 1;  
    while (_left <= mid_index && _right <= high_index){  
        if (buffer[_left] <= buffer[_right]){  
            auxiliary_buffer.push_back(buffer[_left]);  
            ++_left;  
        } else{  
            auxiliary_buffer.push_back(buffer[_right]);  
            ++_right;  
        }  
    }  
    while (_left <= mid_index){  
        auxiliary_buffer.push_back(buffer[_left]);  
        ++_left;  
    }  
    while (_right <= high_index){  
        auxiliary_buffer.push_back(buffer[_right]);  
        ++_right;  
    }  
    std::copy(auxiliary_buffer.begin(), auxiliary_buffer.end(), &buffer[low_index]);  
}  
void merge_sort(std::vector<int>& buffer){  
    merge_sort(buffer, 0, buffer.size() - 1);  
}
```
## Heap Sort

## Quick Sort

Quick Sort Algorithm : 

1. Partition the elements into three categories based on a chosen _pivot_ element:
- Elements _smaller_ than the pivot
- Elements _greater_ than the pivot
- Elements _equal_ to the pivot

2. Recursively sort the two partitions that are not equal to the pivot (smaller and larger elements)

3. Concatenate the three now-sorted partitions together.

![](../_IMG/AL/Snipaste_2024-06-24_14-32-14.png)

Implementations for array:
```c++
void partition(std::vector<int>& buffer, std::vector<int>& less, std::vector<int>& equal,  
               std::vector<int>& greater, int pivot){  
    for (int index = 0; index != buffer.size(); ++index){  
        int value = buffer[index];  
        if (value < pivot)  
            less.push_back(value);  
        else if (value > pivot)  
            greater.push_back(value);  
        else  
            equal.push_back(value);  
    }  
    buffer.clear();  
}  
void concatenate(std::vector<int>& buffer, std::vector<int>& less, std::vector<int>& equal,  
                 std::vector<int>& greater){  
    auto inserter = buffer.insert(buffer.begin(), less.begin(), less.end());  
    inserter = buffer.insert(inserter, equal.begin(), equal.end());  
    buffer.insert(inserter, greater.begin(), greater.end());  
}  
void quick_sort(std::vector<int>& buffer){  
    if (buffer.size() <= 1)  
        return;  
    int pivot = buffer[0];  
    std::vector<int> less, greater, equal;  
    partition(buffer, less, equal, greater, pivot);  
  
    quick_sort(less);  
    quick_sort(greater);  
  
    concatenate(buffer, less, equal, greater);  
}
```

Quick Sort on Single Linked List
```c++
void partition(ListNode*& buffer, ListNode*& less, ListNode*& equal, ListNode*& greater, int pivot){
    ListNode* less_current, *equal_current, *greater_current;
    while (buffer != nullptr){
        if (buffer->data < pivot){
            if (!less){
                less = buffer;
                buffer = buffer->next;
                less->next = nullptr;
                less_current = less;
            }else{
                less_current->next = buffer;
                buffer = buffer->next;
                less_current = less_current->next;
                less_current->next = nullptr;
            }
        }else if (buffer->data > pivot){
            if (!greater){
                greater = buffer;
                buffer = buffer->next;
                greater->next = nullptr;
                greater_current = greater;
            }else{
               greater_current->next = buffer;
                buffer = buffer->next;
                greater_current = greater_current->next;
                greater_current->next = nullptr;
            }
        }else{
            if (!equal){
                equal = buffer;
                buffer = buffer->next;
                equal->next = nullptr;
                equal_current = equal;
            }else{
                equal_current->next = buffer;
                buffer = buffer->next;
                equal_current = equal_current->next;
                equal_current->next = nullptr;
            }
        }
    }
}
ListNode* joint(ListNode *& first, ListNode*& second){
    if (!first)
        return second;
    if (!second)
        return first;
    ListNode * result = first;
    ListNode * current = result;
    while (current->next)
        current = current->next;
    current->next = second;
    
    return result;
}
void concatenate(ListNode*& buffer, ListNode*& less, ListNode*& equal, ListNode*& greater){
    buffer = joint(less, equal);
    buffer = joint(buffer, greater);
    less = equal = greater = nullptr;
}
void quickSort(ListNode*& front) {
    if (!front || !front->next)
        return;

    int pivot = front->data;
    ListNode *less, *equal, *greater;
    less = equal = greater = nullptr;
    
    partition(front, less, equal, greater, pivot);

    quickSort(less);
    quickSort(greater);

    concatenate(front, less, equal, greater);

}
```