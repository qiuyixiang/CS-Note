This Note Include A lot useful material and tips in Discrete Mathematics !

# Set Theory

## Concept
A set is an unordered collection of distinct objects, which may be anything, including other sets.

Set Traits:
- Sets can't contain duplicate elements any repeated elements are ignored
- Two Sets are equal when they have same contents regardless their order.

Some Special Set:
- $\mathbb{N}:$ Natural Set $\{0,1,2,3,4,5...\}$
- $\mathbb{Z}:$ Intergal Set $\{...-3,-2,-1,0,1,2,3,...\}$
- $\mathbb{R}:$ Real Number Set $\{e, 3.24342, -137, \pi,4\}$

SubSet
 A set S is called a subset of a set T (denoted S ⊆ T) if all elements of S are also elements of T.
- We say that S ∈ T if, among the elements of T, one of them is exactly the object S. 
- We say that S ⊆ T if S is a set and every element of S is also an element of T. (S has to be a set for the statement S ⊆ T to be true.) 

Empty Set

A Set which doesn't have one element is an empty set, the empty set is a subset of any set S.
Any elements doesn't belong to the empty set.
The Empty Set Write as $\emptyset$ in Set theory !

And This Statement is always true, $S$ is any Set
$$ \emptyset \subseteq S$$

## Set Operation

### Basic Operation

There are some Set Operations. And They all follow some rules !
![](../../_IMG/MATH/Snipaste_2024-06-04_20-07-34.png)
Given the Venn Diagrams:
$A = \{1,2,3\}$, $B=\{3,4,5\}$

| Operation            | Notation    | Value           |
| -------------------- | ----------- | --------------- |
| Union                | $A\cup B$   | $\{1,2,3,4,5\}$ |
| Intersection         | $A\cap B$   | $\{3\}$         |
| Difference           | $A-B$       | $\{1,2\}$       |
| Symmetric Difference | $A\Delta B$ | $\{1,2,4,5\}$   |

All Sets Operations Table

| Symbol          | Read As              | Meaning                                     |
| --------------- | -------------------- | ------------------------------------------- |
| $x \in S$       | Element of           | S contains x                                |
| $S \subseteq T$ | Subset of            | All the elements in S also in T             |
| $S\cup T$       | Union                | Set containing elements in either S or T    |
| $S\cap T$       | Intersection         | Set containing elements in both S and T     |
| $S - T$         | Difference           | Set containing elements in S, but not in T  |
| $S \Delta T$    | Symmetric Difference | Set containing elements in one but not both |
| $\wp(S)$        | Power Set            | Set of all subsets of S                     |
| $\emptyset$     | Empty Set            | Set with no elements                        |
| \|S\|           | Cardinality          | Number of elements in S                     |

### Power Set

Cardinality

The cardinality of a set is the number of elements it contains. Generally Speaking it is the size of the set. Denoted As $|S|$

> What is the cardinality of $\mathbb{N}$ $(|\mathbb{N}|)$ ?

There are many infinitely many natural numbers, so we need introduce a new term $\aleph_0$.
Let's Define $$|\mathbb{N}| = \aleph_0$$

Power Set

Define the power set of $S$, means the set of all subsets of $S$. We write the power set of S as $\wp(S)$ 
For Example Given The Set $S=\{1,2\}$, the power set of $S$ is 
$$ \wp(S) = \{\{\},\{1\},\{2\},\{1,2\}\}$$
If the cardinality of $S$ is $|S|$, then the cardinality of power set of $S$ will be $2^{|S|}$. So This Statement is also true if the $S$ is finite Set
$$|\wp(S)| = 2^{|S|}$$

Interesting Theorem:
![](../_IMG/MATH/Snipaste_2024-06-08_19-17-10.png)
Every Set is strictly smaller that its power set 

> Interesting Rules : Given elements of the set $\wp(\wp(\mathbb{N}))$. These are subsets of the set $\wp(\mathbb{N})$  