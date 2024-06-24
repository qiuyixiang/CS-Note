This Note is about Data Structure and its related algorithms in Computer Science !

This Note Also Include Some Advanced Topics in Data Structure and Advanced Data Structure !

Glimpse of the Content : 
- Array
- Linked List
- Tree
- Heap
- Graph
- Hash Table

Referenced Text Book: 

Introduction to Algorithm
![](../../_IMG/AL/Snipaste_2024-05-04_18-22-27.png)

# Linked List

Linked List is a Basic Linked Node Structure. With Node Structure linked list can be implemented quite easy.

```c++
template<typename _Tp>
struct node{
	_Tp data;
	node<_Tp> * next;
}
```
this is a single list node structure

## Single linked list

## Double linked list


# Tree
![](../../_IMG/AL/Snipaste_2024-06-24_15-38-04.png)
A Tree is either an empty data structure or a single node with zero or more non-empty subtrees.

Some Basic Terminology In Tree : 
- nodes : nodes is the basic part of a tree which normally has its value
- edges : edges are normally the connection between nodes
- root node : only one per tree, usually in the top of the tree
- leaf node : nodes with no children
- depth : the depth of a node is the length of its path to the root
- height : the height of a tree is defined to be the number of levels that a tree has

## Binary Tree

A Binary tree is a tree where every node has either 0,1 or 2 children. No node in a binary tree can have more than 2 children.

```c++
template<typename _Tp>  
struct tree_node{  
    _Tp M_data;  
    tree_node<_Tp>* M_left;  
    tree_node<_Tp>* M_right;  
    explicit tree_node(const _Tp& data) : M_data(data), M_right(nullptr), M_left(nullptr){ };  
};
```
Binary Tree Traverse

First Order:
```c++
template<typename _Tp>  
void first_order_print(tree_node<_Tp>* root){  
    if (root){  
        std::cout << root->M_data << " ";  
        first_order_print(root->M_left);  
        first_order_print(root->M_right);  
    }  
}
```
In Order:
```c++
template<typename _Tp>  
void in_order_print(tree_node<_Tp>* root){  
    if (root){  
        first_order_print(root->M_left);  
        std::cout << root->M_data << " ";  
        first_order_print(root->M_right);  
    }  
}
```
Post Order:
```c++
template<typename _Tp>  
void post_order_print(tree_node<_Tp>* root){  
    if (root){  
        first_order_print(root->M_left);  
        first_order_print(root->M_right);  
        std::cout << root->M_data << " ";  
    }  
}
```

## Binary Search Tree

## AVL Tree

## Red-Black Tree

## B Tree

## B+ Tree


# Heap
Heap is a special Data Structure. Which Inner Implementation is a binary tree Diagram.
## Mini Heap

Definition : A Min Heap is a binary tree with the following structural and ordering properties.
- It is a complete binary tree : every level fills up from left to right with no gaps before moving on to the next level.
- Ordering Property : Every Node's value (priority) must be less than or equal to the values of any/all of its children

### Operation
Mini Heap Operation Runtime

| Operation       | Best-Case Runtime | Worst-Case Runtime |
| --------------- | ----------------- | ------------------ |
| insertion(push) | $O(1)$            | $O(logn)$          |
| deletion(pop)   | $O(1)$            | $O(logn)$          |
| findMin(peek)   | $O(1)$            | $O(1)$             |

> MiniHeap Only Support deletion of the minimum value in the heap, not of arbitrary values. Same for the find/search/get operation

Insertion Process In MiniHeap
1. Insert at the next open position
2. percolate up
Deletion Process In MiniHeap
1. Preserve the structural property, the last value (bottom-right) moves up to the root position
2. Restore ordering property by percolating down.

### Structure
Mini Heap is representation using an array/vector depends on the situation, so that we can have $O(1)$ time to access elements in the mini heap !

Formula for the structure.
- $leftchild(i)=2i+1$
- $rightchild(i)=2i+2$
- $parent(i)=(i-1)/2$

The `Buffer[0]` is the minimal elements in the heap and the Buffer `[Buffer.size()-1]` is the insertion position of the element.

## Maxi Heap

A MaxiHeap has the same structure property as a miniHeap, but the ordering property is inverted every node's value (priority) must be greater than or equal to the values of any/all of its children.

We can implement this traits using functor in the template parameter.
### Operation
Maxi Heap Operation Runtime

| Operation       | Best-Case Runtime | Worst-Case Runtime |
| --------------- | ----------------- | ------------------ |
| insertion(push) | $O(1)$            | $O(logn)$          |
| deletion(pop)   | $O(1)$            | $O(logn)$          |
| findMin(peek)   | $O(1)$            | $O(1)$             |

> Maxi Heap Only Support deletion of the maximum value in the heap, not of arbitrary values. Same for the find/search/get operation

Insertion Process In MiniHeap
1. Insert at the next open position
2. percolate up
Deletion Process In MaxiHeap
1. Preserve the structural property, the last value (bottom-right) moves up to the root position
2. Restore ordering property by percolating down.
   
### Structure
Maxi Heap is representation using an array/vector depends on the situation, so that we can have $O(1)$ time to access elements in the maxi heap !

Formula for the structure.
- $leftchild(i)=2i+1$
- $rightchild(i)=2i+2$
- $parent(i)=(i-1)/2$

The `Buffer[0]` is the maximum elements in the heap and the Buffer `[Buffer.size()-1]` is the insertion position of the element.


## Application

### Core Function

The Implementation For Core Function Percolate_Down And Percolate_Up
Notice That Percolate Up only need to consider the parent node, but the Percolate Down need more considerations so that it can treat the left child index and right child index properly !

Percolate Down :
```c++
template<typename _RandomAccessIterator, typename _Size, typename _Compare>  
void percolate_down(_RandomAccessIterator __first, _Size __index, _Size __len, _Compare __compare){  
    if (__len < 2)  
        return;  
    const _Size _search_max = (__len - 2) / 2;  
    while (__index <= _search_max){  
        _Size _left_index = __index * 2 + 1;  
        _Size _right_index = __index * 2 + 2;  
        _Size _swap_index;  
        /// Judge Whether the right node exist
        if (_right_index <= __len - 1){  
            if (__compare(__first[__index], __first[_left_index]) &&  
            __compare(__first[__index], __first[_right_index]))  
                return;  
            _swap_index = __compare(__first[_left_index],  
                                    __first[_right_index]) ? _left_index : _right_index;  
        } else{  
        /// Left Node must exist beacuse the boundary restrictions is to ensure that the search span only             ///cover valid range
            if (__compare(__first[__index], __first[_left_index]))  
                return;  
            _swap_index = _left_index;  
        }  
        std::swap(__first[__index], __first[_swap_index]);  
        __index = _swap_index;  
    }  
}
```

Percolate Up : 
```c++
template<typename _RandomAccessIterator, typename _Size, typename _Compare>  
void percolate_up(_RandomAccessIterator __first, _Size __index, _Compare __compare){  
    if (__index == 0)  
        return;  
    /// Just try to find parent node index until meet the boundary condition which index == 0
    for (_Size index_parent;  __index != 0; ){  
        index_parent = (__index - 1) / 2;  
        if (!__compare(__first[__index], __first[index_parent]))  
            break;  
        std::swap(__first[__index], __first[index_parent]);  
        __index = index_parent;  
    }  
}
```

### Heap Sort
Using Heap Data Structure We can implement an efficient Sort Algorithm.

1. Insert n elements into miniHeap - $O(n\ log\ n)$
2. Remove all elements from miniHeap place them in a vector as they come out - $O(n\ log\ n)$

Heap Sort Implementation in C++ Template
```c++
template<typename _RandomIterator>  
void heap_sort(_RandomIterator __first, _RandomIterator __last){  
    typedef typename std::iterator_traits<_RandomIterator>::value_type Value_Type;  
    container::priority_queue<Value_Type, std::less<Value_Type>, std::vector<Value_Type>> __buffer;  
    auto __current = __first;  
    for ( ; __current != __last; ++__current)  
        __buffer.push(*__current);  
    __current = __first;  
    while (!__buffer.empty()){  
        *__current = __buffer.top();  
        __buffer.pop();  
        ++__current;  
    }  
}
```

### Heapify
Heapify is an Algorithm for turning an arbitrary array/complete binary tree into a miniHeap in place (without creating a new array)

Let BRMNLN be the index of the bottom-right most non-leaf node in the complete binary tree represented by the given array call `percolateDown()` starting at index BRMNLN and down through index 0 (the root)

The BRMNLN Index is the last Botton-Right Most Non-Leaf Node In the Complete Binary Tree, And usual write as (length - 2) / 2 .
```c++
for (int i = BRMNLN; i >= 0; i--){
	percolateDown(i);
}
```
This Percolates Larger Values down while squishing smaller elements up in the heap !

Using Percolate_Down and Percolate_Up Function its quite easy to implementation functions such as heap_sort or heapify(In C++ Standard Template Library It is usually called std::make_heap), Just Using the implemented helper functions:
```c++
template<typename _RandomAccessIterator,  typename _Compare>  
void make_heap(_RandomAccessIterator __first ,_RandomAccessIterator __last, _Compare __compare){  
    typedef typename std::iterator_traits<_RandomAccessIterator>::difference_type Diff_Type;  
    Diff_Type  len = std::distance(__first, __last);  
    for (Diff_Type _index = (len - 2) / 2; _index >= 0; --_index){  
        percolate_down(__first, _index, len, __compare);  
    }  
}
```



# Graph



# Hash table