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

### Basic Symbols

There are some Set Operations. And They all follow some rules !
![](../_IMG/MATH/Snipaste_2024-06-04_20-07-34.png)
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

#### Exercises

There are some power set exercises.
1. Give a set equal to $\emptyset \cup \{\emptyset\}$
$$ \emptyset \cup \{\emptyset\} = \{\emptyset\}$$
2. Give a set equal to $\emptyset \cap \{\emptyset\}$
$$ \emptyset \cap \{\emptyset\} = \emptyset$$
3. Give a set equal to $\{\emptyset\} \cup \{\{\emptyset\}\}$  
$$\{\emptyset\} \cup \{\{\emptyset\}\} = \{\emptyset, \ \{\emptyset\}\}$$
4. Give a set equal to $\{\emptyset\} \cap \{\{ \emptyset\}\}$
$$\{\emptyset\} \cap \{\{ \emptyset\}\} = \emptyset$$
5. Give a set equal to $\wp(\wp(\emptyset))$
$$ 
\begin{align}
\wp(\wp(\emptyset)) &= \wp(\{\emptyset\}) \\
&= \{\emptyset,\ \{\emptyset\}\}
\end{align}
$$
6. Give a set equal to $\wp(\wp(\wp(\emptyset)))$
$$
\begin{align}
\wp(\wp(\wp(\emptyset))) 
&= \wp(\wp(\{\emptyset\})) \\
&= \wp(\{\emptyset,\ \{\emptyset\}\}) \\
&= \{\emptyset,\ \{\emptyset\},\ \{\{\emptyset\}\},\ \{\emptyset, \{\emptyset\}\}\}
\end{align}
$$

### Set Laws

# Mathematical Proof

Proof is used to prove some mathematical theorems are true. And mathematical theorems are made of statements.
## Statement

There are some statements in Mathematical theorems 
Overview :
- Universally-Quantified Statement : User can make any arbitrary choices
- Existentially-Quantified Statement : Only Some Particular choices can be used

### Universally-Quantified Statement

A universally-quantified statement usually in this format !
	For all x, _some-property_ holds for x

Example :

Theorem: For any integers $m$ and $n$, if $m$ and $n$ are odd, then $m + n$ is even.

Proof: Consider any arbitrary integers $m$ and $n$ where $m$ and $n$ are odd. We need to show that $m + n$ is even. 
Since m is odd, we know that there is an integer k where 
$$ m = 2k + 1. \ (1) $$
Similarly, because n is odd there must be some integer r such that 
$$n = 2r + 1.\ (2) $$
By adding equations (1) and (2) we learn that 
$$ \begin{align} 
m + n &= 2k + 1 + 2r + 1 \\ &= 2k + 2r + 2 \\ &= 2(k + r + 1). \ \ (3)
\end{align}
$$ 
Equation (3) tells us that there is an integer $s$ (namely, $k + r + 1$) such that $m + n = 2s$. Therefore, we see that $m + n$ is even, as required.■

### Existentially-Quantified Statement

An existentially-quantified statement is a statement of the form
	There is some $x$ where _some-property_ holds for x.

Example:

Theorem: For any odd integer $n$, there exist integers $r$ and $s$ where $r^2 - s^2=n$
Proof: Let n be an arbitrary odd integer. We will show that there exist integers $r$ and $s$ where  $r^2 - s^2=n$ 
Since $n$ is odd, we know there is an integer $k$ where $n = 2k + 1$. Now, let $r = k+1$ and $s = k$. Then we see that 
$$
\begin{align}
r ^2 \ – \ s ^2 &= (k+1)^2 –\ k ^2 \\ 
&= k ^2 + 2k + 1 \ – \ k ^2 \\&= 2k + 1 \\&= n.
\end{align}
$$
This means that $r^ 2\ – \ s^ 2 = n$, which is what we needed to show. ■

Direction using normal statement to state that the propositional logical is true. A Direct Proof usually using an implication to confirm this statement.
An implication is a statement of the form :
	If P is true, then Q is true.
In mathematics, implication is directional.

Direct Proof always keep with the formal propositional logic and sometimes has a statement.

### Negation of Statement

The Negation of a Propositional Logical Statement is either true or false.
- The Negation of a Universal Statement is the Existential Statement
- The Negation of a Existential Statement is the Universal Statement

The Negation of Universal-Statement:
	Every $P$ is a $Q$
	Negation : There exist $P$ which is not a $Q$.

The Negation of Existential-Statement:
	There exists an $x$ where $P(x)$ is true.
	Negation : For all $x$, $P(x)$ is false.

The Negation of an implication is not an implication:
	For every $x$, if $P(x)$ is true, then $Q(x)$ is true.
	Negation: There is an $x$ where $P(x)$ is true and $Q(x)$ is false

## Direct Proof

### Implication

Implications are one of the most common types of statements.an **_implication_** is a statement of the form:
	if $P$ is true, then $Q$ is true

As a reminder, the **_antecedent_** of this implication is the statement $𝑃$ is true, and the **_consequent_** of this implication is the statement $𝑄$ is true.

Prove Implications:

Suppose we want to prove this implication:
	if P is true, then Q is true

We Have Three Options available to us:
- **_Direct Proof_**:
	Assume $P$ is true, then prove $Q$ is true
- **_Proof By Contrapositive_**:
	Assume $Q$ is false, then prove $P$ is false
- **_Proof By Contradiction_**:
	Assume $P$ is true and $Q$ is false, then derive a contradiction


### Biconditional

A **_biconditional_** is a statement of the form:
	$P$ is true if and only if $Q$ is true
We use the phrase **_if and only if_** to indicate that two statements imply one another.

Prove Biconditional:

To Prove a theorem of this form:
	$P$ if and only if $Q$
you need to prove two separate statements:
1. first, that if $P$ is true, then $Q$ is true
2. second, that if $Q$ is true, then $P$ is true


## Indirect Proof

### Contradiction

Key Idea: Prove a statement P is true by showing that it isn’t false.

First, assume that P is false. The goal is to show that this assumption is silly. Next, show this leads to an impossible result. Finally, conclude that since P can’t be false, we know that P must be true.

For Example : 
Prove $P$ is true through assume $P$ is false and we need to prove it's impossible when $P$ is false, 
so $P$ is true

Theorem: For any integer $n$, if $n^2$ is even, then $n$ is even. 
Proof: Assume for the sake of contradiction that there is an integer $n$ where $n^2$ is even, but $n$ is odd.


### Contrapositive
The Contrapositive of the implication is the implication.

For Example. :
	If $P$ is true, then $Q$ is true
Contrapositive Proof 
	If $Q$ is false, then $P$ is false

It will swap the position of the two statements which means swap the _antecedent_ and _consequent_.
![](../_IMG/MATH/Snipaste_2024-06-19_18-32-13.png)
The contrapositive of an implication means exactly the same thing as the implication itself

>Proof by contrapositive is another technique for theorems with a sentence structure that has the form of an implication. In fact, proof by contrapositive will proceed exactly like a direct proof, with similar “assume” and “want-to-show” steps, but will do so only after taking the contrapositive of the theorem to get a new, equivalent statement to prove.


# Propositional Logic

## Logic Symbols
There are seven different Logic Symbols which called propositional connectives.

| Symbols               | Meaning             | Boolean Equivalence          |
| --------------------- | ------------------- | ---------------------------- |
| $\neg\ p$             | Logic Negation      | !p                           |
| $p\vee q$             | Logic disjunction   | \|\|                         |
| $p\land q$            | Logic conjunction   | &&                           |
| $p \rightarrow q$     | Logic Imply         | !(p && !q)                   |
| $p \leftrightarrow q$ | Logic biconditional | (!(p && !q)) && (!(q && !p)) |

**_Implication_**

Implication $p \rightarrow q$ truth table
- Only if $p$ is true and $q$ is false $p \rightarrow q$ is false

| $p$ | $q$ | $p \rightarrow q$ |
| --- | --- | ----------------- |
| $T$ | $F$ | $F$               |
| $T$ | $T$ | $T$               |
| $F$ | $F$ | $T$               |
| $F$ | $T$ | $T$               |

**_biconditional_**
biconditional statement $p \leftrightarrow q$ will be true only if the $p$ and $q$ have the same value
And We can known that $p \leftrightarrow q$ is equivalence to the expression $(p \rightarrow q) \land (q \rightarrow p)$.

| $p$ | $q$ | $p \leftrightarrow q$ |
| --- | --- | --------------------- |
| $F$ | $F$ | $T$                   |
| $F$ | $T$ | $F$                   |
| $T$ | $F$ | $F$                   |
| $T$ | $T$ | $T$                   |
There are two normal format when deal with the negation of biconditional $\neg(p \leftrightarrow q)$
- $\neg\ p \leftrightarrow q$
- $p \leftrightarrow \neg\ q$

Example : Simplify this expression As soon as possible $\neg((p \lor(q\land r)) \leftrightarrow (a \land b \land c \rightarrow d))$
$$ 
\begin{align}
\neg((p \lor(q\land r)) \leftrightarrow (a \land b \land c \rightarrow d)) 
&= (p \lor (q \land r)) \leftrightarrow \neg(a \land b \land c \rightarrow d) \\
&= (p \lor (q \land r)) \leftrightarrow (a \land b \land c \land \neg \ d) \\
&= p \lor q \land r \leftrightarrow a \land b \land c \land \neg \ d
\end{align}
$$
## Operation Laws

There are different many Arithmetic Laws In Propositional Logic.

| Laws                      | Operation                 | Equivalence                                 |
| ------------------------- | ------------------------- | ------------------------------------------- |
| De Morgan's Laws          | $\neg \ (p\lor q)$        | $\neg \ p \land \neg \ q$                   |
| De Morgan's Laws          | $\neg \ (p \land q)$      | $\neg \ p \lor  \neg \  q$                  |
| Implication Equivalence   | $p \rightarrow q$         | $\neg\ (p \land \neg\ q)$                   |
| Implication Equivalence   | $\neg\ (p \rightarrow q)$ | $p \land \neg\ q$                           |
| Biconditional Equivalence | $p \leftrightarrow q$     | $(p \rightarrow q) \land (q \rightarrow p)$ |

## Logic Translation

**_Simple Expression Translation_**
There are main ways to translate English Words To First-Order Logic
- Some $P$ is a $Q$ Translate to    : $\exists \  x\  (P(x) \land Q(x))$
- All $P$'s are $Q$'s Translate to  : $\forall\ x\ (P(x) \rightarrow Q(x))$

> Paring :
> The $\exists$ quantifier usually is paired with $\land$
> The $\forall$ quantifier usually is paired with $\rightarrow$


