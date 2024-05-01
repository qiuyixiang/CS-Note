This Note Mainly List Some Class or template Class In C++ and Some Utilities Functions In C++ ! Later In this Note it also display how to implement a C++ Standard template Library !

Overview of the Content !

- String Library
- IO Library
- Container Library


# String Library

In C++ String Library Mainly include std::basic_string and some other forms of String Operation. The Library is implemented using Template and Class !

## basic_string

The class template _basic_string_ stores and manipulates sequences of character-like objects.
### basic_string Data Type


### basic_string member function

Overview of the basic_string member function

> All of these functions are member function, these notes is condensed and ignored the template and specialization traits !

| Member Function             | Descriptions                                                                                                                  |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| append(str)                 | add text to the end of a string                                                                                               |
| compare(str)                | return -1, 0, or 1 depending on relative ordering                                                                             |
| erase(index,length)         | delete text from a string starting at given index                                                                             |
| find(str)  <br>rfind(str)   | return first or last index where the start of str appears in this string (returns _string::npos_ if not found)                |
| insert(index, str)          | add text into string at a given index                                                                                         |
| length()                    | return number of characters in the string                                                                                     |
| replace(index,len,str)      | replace len chars at given index with new text                                                                                |
| substr(start, length)  <br> | return a new string with the next length chars beginning at start (inclusive); if length is omitted, grabs till end of string |
| size()                      | return number of characters in the string                                                                                     |


# IO Library

IO Library In C++ is divided into three different parts:
- Stream Based IO
- Print Based IO
- C-Style Based IO

The Most Important one is Stream Based IO Library

> the Print Based IO Start at ISO C++ 23

## Stream Based IO

### IO Hierarchy
The stream-based input/output library is organized around abstract input/output devices. These abstract devices allow the same code to handle input/output to files, memory streams, or custom adaptor devices that perform arbitrary operations on the fly.

IO Hierarchy :
![](../../_IMG/PL/Snipaste_2024-04-29_16-13-33.png)


## IO Manipulators

IO Manipulators are manipulators which control the output/input format of the Stream.


# Container Library

A Overview of containers in C++ STL (Standard Template Library)
- Sequence Container
	- [array](#array)
	- [vector](#vector)
	- [deque](#deque)
	- [forward_list](#forward_list)
	- [list](#list)
- Associative Container
	- [set](#set)
	- [map](#map)
	- [multiset](#multiset)
	- [multimap](#multimap)
- Unordered Associative Container
	- [unordered_set](#unordered_set)
	- [unordered_map](#unordered_map)
	- [unordered_multiset](#unordered_multiset)
	- [unordered_multimap](#unordered_multimap)
- Container Adaptor
	- [stack](#stack)
	- [queue](#queue)
	- [priority_queue](#priority_queue)

## Sequence Container

## Associative Container

## Unordered Associative Container

## Container Adaptor

### stack

Stack in C++ STL is a container adaptor. And it has LIFO (last in first out) traits.

```c++
template<typename T>
class stack;
```
By default, it has a actual data structure or container: _deque_

Member Function:

| Member Function | Description                                   |
| --------------- | --------------------------------------------- |
| top             | return the top element                        |
| empty           | return whether the size of the container is 0 |
| size            | return the size of the container              |
| push            | inserts element at the top                    |
| emplace         | construct element in-place at the top         |
| pop             | remove the top element                        |
| swap            | swaps the contents                            |

Examples For Stack:
```c++
std::stack<int>myStack;  

myStack.push(10);  
myStack.emplace(int(20));  
myStack.push(30);
```

### queue

A queue is a **FIFO** (first-in, first-out) data structure. Like the stack, it generally supports a limited set of operations.

Member Function:

| Member Function | Description                          |
| --------------- | ------------------------------------ |
| front           | access the first element             |
| back            | access the last element              |
| empty           | check whether the container is empty |
| size            | return the size of the queue         |
| push            | insert element at the end            |
| pop             | removes the first element            |
| swap            | swap the contents                    |
| emplace         | construct element at the end         |
