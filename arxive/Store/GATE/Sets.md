>[!definition]
>Two sets are equal iff they have the same elements. Thus we can write 
>$A\equiv B \iff \forall x (x \in A \iff x\in B)$


>[!definition]
>**EMPTY SET - $\emptyset$ **
>The special set that has no elements

>[!definition]
>**Subset $\subset$**
>$A$ is a subset of $B$ denoted $A \subset B \iff \forall x( x\in A \rightarrow x \in B)$
> further if $A \subset B \land A \ne B$ then $A$ is called a **proper subset** of $B$

### 2.1.4 Size of a set
>[!definition]
>Let $S$ be a set. then its size($n$) is the number of elements in it. If $n$ is a non-negative integer then $S$ is said to be finite. The size is also called **Cardinality** of the set. Denoted $|S|$

### 2.1.5 Power Sets

>[!definition]
>The set of all subsets of $S$ is called the power set of $S$, denoted $\mathcal{P}(S)$

### 2.1.6 Cartesian Products

The order of elements in a collection  is often important. This is provided by **ordered n-tuples**

>[!definition]
>The _ordered n-tuple_ $(a_i)$ is the ordered collection that has $a_1$ as its first element, $a_2$ and so on...

Two ordered n-tuples are equal if the corresponding pairs of their elements are equal. Ordered 2-tuples are called **ordered pairs**.

>[!definition]
>Let A and B be sets, the _Cartesian product of A and B_ denoted $A \times B$, is the set of all ordered pairs $(a,b)$ where $a\in A$ and $b \in B$, Hence,
>$A \times B = [(a,b) | a\in A \land b\in B]$

### 2.1.7 Using Set Notation with quantifiers

We can use set notation in combination with quantifiers. 

### 2.1.8 Truth Sets and Quantifiers

Given a predicate $\mathcal{P}$ and a domain $D$, we define the **truth set** of $\mathcal{P}$ to be the set of elements $x$ in $D$ for which $\mathcal{P}(x)$ is true denoted as $[x\in D | \mathcal{P}(x)]$


## 2.2 Set Operations

Union $\rightarrow \cup$ those elements that are either in $A$ or in $B$ or in both.

Intersection $\rightarrow \cap$ those elements that are in both $A$ and $B$.

A _disjoint_ set has no members in its intersection i.e has no elements in common or the intersection is an $\emptyset$ 

**Principle of Inclusion-Exclusion** 

$|A\cup B| =|A|+|B|-|A\cap B|$

>[!definition]
>Let $A$ and $B$ be sets. The _difference_ of $A$ and $B$ denoted $A - B$ is the set containing elements that are in $A$ but not in $B$. It is also called _complement of B w.r.t A_ it is sometimes denoted $A\setminus B$
>

$A^{\complement} = \overline{A} = U - A$


**Union of $n$ sets**
$\bigcup_{i=1}^{n} A_i$

**Intersection of $n$ sets**
$\bigcap_{i=1}^{n} A_i$

### 2.2.2 Set Identities

| **Identity**                                                                                                | **Name**             |
| :---------------------------------------------------------------------------------------------------------- | :------------------- |
| $A\cap U = A$<br>$A\cup \emptyset = A$                                                                      | Identity Law         |
| $A\cup U = U$<br>$A\cap \emptyset = \emptyset$                                                              | Domination Laws      |
| $A\cup A = A$<br>$A\cap A = A$                                                                              | Idempotent Laws      |
| $\overline{(\overline{A})}$                                                                                 | Complementation Laws |
| $A\cup B = B\cup A$<br>$A\cap B = B\cap A$                                                                  | Commutative Laws     |
| $A\cup(B\cup C) = (A\cup B)\cup C$<br>$A\cap (B \cap C)= (A\cap B)\cap C$                                   | Associative Laws     |
| $A\cup(B\cap C) = (A\cup B)\cap (A\cup C)$<br>$A\cap(B\cup C) = (A\cap B)\cup (A\cap C)$                    | Distributive Laws    |
| $\overline{A\cap B} = \overline{A}\cup \overline{B}$<br>$\overline{A\cup B} = \overline{A}\cap\overline{B}$ | De Morgan's Laws     |
| $A\cup(A\cap B) = A$<br>$A\cap(A\cup B)= A$                                                                 | Absorption Laws      |
| $A\cup \overline{A} = U$<br>$A\cap \overline{A} = \emptyset$                                                | Complement Laws      |
There are 3 basic methods to prove set identities.

1. Subset Method - Show that both sides of the identity are subsets of each other.
2. Membership table - For each possible combination of the atomic sets, then show that an element in exactly one of these atomic sets must either belong to both sides or neither sides. 
3. Apply existing identities - start with one side and transform it into the other side using a sequence of steps by applying existing identities.

### Computer Representation of Sets

One method is to store the elements of the set in an unordered fashion. But then set operations will consume a lot of time as a lot of searching will be required.

We need to assume that the universal set $U$ is finite. First we specify an arbitrary ordering of the elements of $U$, for instance $a_1,a_2,..., a_n$. Represent a subset $A$ of $U$ with the bit string of length $n$, where the $ith$ bit will be $1$ if $a_i$ belongs to $A$ and $0$ otherwise.

This way it is much easier to find unions, intersections and complements of sets. 


### 2.2.5 Multisets

If the number of times an element occurs in an unordered collection matters then it is called a **multiset**. 

The notation is similar to a normal set but we list a member as many times as it occurs. To avoid this ambiguity, we can use the notation $m_i \cdot a_i$. The $m_i$ are called the multiplicities of the elements. 

**Union**, **intersection**, **difference** and **sum** etc need to be redefined to integrate multiplicities. 

**Union** - The multiplicity will be the maximum of the multiplicities.
**Intersection** - It will be the minimum in this case.
**Difference** - Multiplicity will be the difference of the multiplicities of the element in the sets.
**Sum** - Here the multiplicities will be the sum of the multiplicities of the element in the sets.

