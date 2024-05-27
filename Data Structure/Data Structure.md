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

## Binary Tree

## AVL Tree

## Red-Black Tree

## B Tree

## B+ Tree

# Heap
Heap is a special Data Structure. Which Inner Implementation is a binary tree.
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

# Graph


# Hash table