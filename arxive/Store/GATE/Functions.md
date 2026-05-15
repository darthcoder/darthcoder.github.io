### 2.3.1 Introduction

>[!definition 1]
>Let $A$ and $B$ be non-empty sets. A _function_ $\mathit{f}$ is an assignment of exactly one element of $B$ to each element of $A$. We denote a function by $\mathit{f}: A\rightarrow B$

>[!Note]
>Functions are also called **mappings** or **transformations**


$A$ is called the **domain** and $B$ is called the **codomain** of the function.

>[!definition 5]
> A function $f$ is said to be one-to-one or an injection, if and only if $f(a) = f(b) \rightarrow a = b \forall a, b \in X$, the domain of $f$

>[!defnition 7]
>A function $f$ from $A$ to $B$ is called onto or a _surjection_ iff $\forall b\in B, \exists a\in A$ s.t. $f(a) = b$
>

In those diagrams that we used to make with the domain and its points on one side and the codomain and its point on the other side with arrows between them to indicate functions, what this means is that every element of the codomain has an arrow coming into it and no element in the codomain has arrows from more than one element in the domain. 

>[!note]
>Suppose $f:A\rightarrow B$ then, 
>_to show that $f$ is injective_ need to show that if $f(x) = f(y) \rightarrow x= y$
>_to show surjective_ for an arbitrary element in $y\in B$, find an element $x\in A$ s.t. $f(x) = y$

### 2.3.3 Inverse Functions and composition of Functions

If $f$ is a _bijection_ i.e. both one-one and onto, then every element of $B$ is the image of an element in $A$. Further, because of the one-to-one correspondence, the element is _unique_. Consequently, we can define a new function from $B$ to $A$ that reverses the correspondence given by $f$.

This function is called the inverse function of $f$ and its domain is the codomain of $f$ and its codomain is the domain of $f$. This basically reverses the direction of the arrows in the Venn diagram.


>[!definition 10]
>Let $g$ be a function from $A$ to $B$ and $f$ be a function from $B$ to $C$, then the composition of the functions denoted by $f\circ g$ is a function from $A$ to $C$ defined as: 
>$(f\circ g) (a) = f(g(a))$


### 2.3.4 The Graphs of Functions

>[!definition 11]
> Let $f$ be a function from the set of pairs in $A\times B$. The _graph_ of the function $f$ is the set of ordered pairs $[(a,b) | a\in A \& f(a) = b]$

### 2.3.6 Partial Functions

>[!definition 13]
>A _partial function_ $f$ from a set $A$ to a set $B$is an assignment to each element $a$ in a subset of $A$ called the _domain of definition_ of $f$, of a unique element $b$ in $B$. The sets $A$ and $B$ are called the _domain_ and _codomain_ of $f$ respectively. We say that $f$ is _undefined_ for elements in $A$ that are not in the domain of definition of $f$. When the domain of definition of $f$ equals $A$,  we say that $f$ is a _total function_.








