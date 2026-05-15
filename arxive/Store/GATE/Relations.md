## 9.1.1 Introduction
 
>[!definition]
>A _binary relation_ from $A$ to $B$ is a subset of $A\times B$

### 9.1.2 Functions as Relations

A function $f$ from $A$ to $B$ assigns one element of $B$ to each element of $A$. The graph of $f$ is a set of ordered pairs $(a,b)$ such that $b = f(a)$. Thus, the graph of $f$ is a subset of $A \times B$, hence it is a binary relation. 

A relation can be used to express a one-to-many relationship between elements of the sets $A$ and $B$. A function is a special kind of relation where exactly one element of $B$ has a relation with each element of $A$

### 9.1.3 Relations on a set

>[!definition]
>A _relation_ on a set $A$ is a relation from $A$ to $A$

>[!note]
>It is not hard to determine the number of relations on a finite set, because a relation on a set $A$ is simply a subset of $A\times A$


### 9.1.4 Properties of Relations

>[!definition]
>A relation $\mathcal{R}$ on a set is called _reflexive_ is $(a,a) \in \mathcal{R} \forall a \in A$

>[!example] 
>Is the "divides" relation on a set of positive integers reflexive?
>Yes because $a|a$ whenever $a$ is a positive integer. Not true for all integers because division by zero is not defined.

>[!definiton 4]
>A relation $\mathcal{R}$ on a set $A$ is called _symmetric_ if $(b,a) \in \mathcal{R}$ whenever $(a,b) \in \mathcal{R}$ further if for a relation $\mathcal{R}$ if $\forall a,b \in A$ if $(a,b)\in \mathcal{R}$ and $(b,a) \in \mathcal{R} \rightarrow a=b$ is called _antisymmetric_

By using quantifiers we can express this as: 

**Symmetric Relation** $\forall a\forall b((a,b)\in R\rightarrow (b,a)\in R)$
**Antisymmetric relation** $\forall a\forall b(((a,b)\in R\land (b,a)\in R))\rightarrow(a=b)$

So basically if a is related to be always implies that b is related to a. A relation is antisymmetric when a is related to b and be is related to a can only happen when a and b are the same.

>[definition 5]
>A relation $R$ is said to be _transitive_ if whenever $(a,b)\in R \land (b,c)\in R \rightarrow (a,c) \in R \space \forall a,b,c\in R$
>


> [!note]
> We can use [[arxive/Store/GATE/Counting]] techniques to determine how many relations with specific properties exist for finite sets.


### 9.1.5 Combining Relations

Since relations from $A$ to $B$ are subsets of $A\times B$, two relations from $A$ to $B$ can be combined in any way two sets can be combined.


> [!definition 6]
> Let $R$ be a relation from a set $A$ to a set $B$ and $S$ be a relation from $B$ to $C$. The _composite_ of $R$ and $S$ is the relation consisting of ordered pairs $(a,c)$ where, $a\in A, c\in C$  and for which $\exists b\in B \textit{s.t.} $(a,b)\in R$ and $(b,c)\in S$. The composite of $R$ and $S$ is denoted by $S\circ R$  

>[!definition 7]
>Let $R$ be a relation on the set $A$. The powers $R^n, n\in \mathcal{N}$ are defined recursively by $R^1 = R$ and $R^{n+1} = R^n \circ R$
>

>[!theorem 1]
>The relation $R$ on a set $A$ is transitive iff $R^n \subseteq R$ for $n\in \mathcal{N}$

## 9.2 n-ary Relations and their Applications

Relations can often arise between elements of more than two sets. When we study relations between elements of more than two sets, then it is called an *n-ary relation*.

### 9.2.2 n-ary Relations

>[!definition 1]
>Let $A_1, A_2, ..., A_n$ be sets. An _n-ary relation_ of these sets is a subset of $A_1 \times A_2\times ... A_n$. These sets are called the _domains_ of the relation and $n$ is called its _degree_.

## 9.3 Representing Relations

### 9.3.2 Representing Relations Using Matrices

Let $A = \{a_1, a_2, ... , a_n\}$ and $B =\{b_1, b_2, ... , b_n\}$. Then the relation $R$ can be represented by the matrix $M_R = \{m_{ij}\}$. Where $m_{ij} = 1\space \textit{if}\space (a_i, b_j) \in R$ and $0$ otherwise. 



