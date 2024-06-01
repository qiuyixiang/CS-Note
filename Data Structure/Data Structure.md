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


# Tree

Some Basic Terminology In Tree : 
- nodes : nodes is the basic part of a tree which normally has its value
- edges : edges are normally the connection between nodes
- root node : only one per tree, usually in the top of the tree
- leaf node : nodes with no children

## Binary Tree

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

### Heap Sort
Using Heap Data Structure We can implement an efficient Sort Algorithm.

1. Insert n elements into miniHeap - $O(n\ log\ n)$
2. Remove all elements from miniHeap place them in a vector as they come out - $O(n\ log\ n)$


### Heapify
Heapify is an Algorithm for turning an arbitrary array/complete binary tree into a miniHeap in place (without creating a new array)

Let BRMNLN be the index of the bottom-right most non-leaf node in the complete binary tree represented by the given array call `percolateDown()` starting at index BRMNLN and down through index 0 (the root)
```c++
for (int i = BRMNLN; i >= 0; i--){
	percolateDown(i);
}
```
This Percolates Larger Values down while squishing smaller elements up in the heap !

# Graph


# Hash table