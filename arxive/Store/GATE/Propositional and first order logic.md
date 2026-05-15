> [!definition]
> **Proofs**:
> A verification of a proposition by a chain of logical deductions from a set of axioms.

> [!definition]
> A **proposition** is a statement that is true or false.

> [!definition]
> A **predicate** is a proposition whose value is dependent on the value of a variable.

 
```ad-info
Propositional and first order logic - Rosen Chapter 1 - 1.1 to 1.6
```


>[!Definition]
> XOR is true when only one of the two propositions is true and is false otherwise.

>[! Definition]
>A conditional statement $p \to q$ is false if $p$ is true and $q$ is false and is true otherwise.

From an implication, three kinds of propositions can be derived. 

1. Contrapositive i.e $\neg p \to \neg q$ 
2. Converse i.e $q \to p$
3. Inverse i.e $\neg p \to \neg q$

The statement $p \leftrightarrow q$ is called a biconditional also known is iff or if and only if.

## Constructing truth tables of Compound Propositions

You make it step by step.

e.g. to get the truth table of $\left( p \lor \neg q\right) \to \left( p \land q\right)$

```ad-important
Given any propositional function $f(p,q)$ of $p$ and $q$ then there are 4 values that $p$ and $q$ can have and hence, 4 values that $f(p,q)$ can have. Thus, any function $f$ can be reduced to an elementary function of $p,q$. Can this logic be extended to larger circuits?

Regarding SAT - if we can show that a given circuit is not a contradiction then it is by definition satisfiable. This can be done in two ways, either we show that there is a satisfaction i.e a unique value of the variables that gives $\mathbf{T}$ as the output, or we show that there are no values that lead to a satisfaction. 

What I mean to say is that no matter how complex a function of two logical variables, it would either be equivalent to the variables being AND, OR, XOR together in some combination. i.e a complex expression can be simplified to yield the desired truth table. There is no reason why such logic cannot be extended to larger number of variables.
```

>[!question] 
>Can analogues to Kirchoff's Laws be discovered for Boolean Circuits? 

| $p$ | $q$ | $\neg q$ | $p \lor \neg q$ | $p \land q$ | $\left( p \lor \neg q\right) \to \left( p \land q\right)$ |
| --- | --- | -------- | --------------- | ----------- | --------------------------------------------------------- |
| T   | T   | F        | T               | T           | T                                                         |
| T   | F   | T        | T               | F           | F                                                         |
| F   | T   | F        | F               | F           | T                                                         |
| F   | F   | T        | T               | F           | F                                                         |

## Rules of precedence of Logical Operators in Compound statements

1. Negation operator is applied before all other operators
2. Conjunction takes precedence over disjunction i.e. $\land$ over $\lor$ 
3. Conditionals and biconditionals have lower precedence than conjunction and disjunction operators


## 1.2 Applications of Propositional Logic

1. Translating english sentences
2. Expressing system specifications
3. Boolean searches
4. Logic puzzles
5. Logic Circuits

## 1.3 Propositional Equivalences

> [!Definition]
> A compound proposition that is always true, no matter what the truth values of the propositional variables that occur in it, is called a tautology. A compound proposition that is always false is called a contradiction. A compound proposition that is neither a tautology nor a contradiction is called a contingency.

> [!Definition]
> Propositions that have the same truth values in all possible cases are called logically equivalent.

>[!note] De Morgan Laws
>$\neg\left(p \land q)\right) \equiv \neg p \lor \neg q$
>$\neg\left(p \lor q)\right) \equiv \neg p \land \neg q$

```ad-note
$p \to q \equiv \neg p \lor q$
```

### Logical Equivalences

| Equivalence                                                                                                        | Name              |
| ------------------------------------------------------------------------------------------------------------------ | ----------------- |
| $p \land \mathbf{T} \equiv p$<br>$p \lor \mathbf{F} \equiv p$                                                      | Identity Laws     |
| $p \lor \mathbf{T} \equiv \mathbf{T}$<br>$p \land \mathbf{F} \equiv \mathbf{F}$                                    | Domination Laws   |
| $p \lor p \equiv p$<br>$p \land p \equiv p$                                                                        | Idempotent Laws   |
| $\neg(\neg p)\equiv p$                                                                                             | Double Negation   |
| $p \lor q \equiv q\lor p$<br>$p \land q \equiv q\land p$                                                           | Commutative Laws  |
| $(p \lor q) \lor r \equiv p\lor(q \lor r)$<br>$(p \land q) \land r \equiv p\land(q \land r)$                       | Associative Laws  |
| $p\lor(q \land r)\equiv (p\lor q)\land (p\lor r)$<br>$p\land(q \lor r)\equiv (p\land q)\lor (p\land r)$            | Distributive Laws |
| $\neg\left(p \land q)\right) \equiv \neg p \lor \neg q$<br>$\neg\left(p \lor q)\right) \equiv \neg p \land \neg q$ | De Morgan's Law   |
| $p \lor \neg p \equiv \mathbf{T}$<br>$p \land \neg p \equiv \mathbf{F}$                                            | Negation Laws     |

## 1.3.5 Satisfiability

A compound proposition is **satisfiable** if there exists some assignment of truth values to its variables that makes it true i.e if it is either a tautology or contingency.

## 1.3.6 Applications of Satisfiability

1. The n-Queens Problem
2. Sudoku

If a compound proposition is SAT, then its negation is a tautology


```ad-question
Show that the negation of an unsatisfiable compound proposition is a tautology and the negation of a compound proposition that is a tautology is unsatisfiable
```

```ad-success
### Part 1: Negation of an Unsatisfiable Proposition is a Tautology

**Given**: ϕϕ is unsatisfiable (always false).

**To Show**: ¬ϕ¬ϕ is a tautology (always true).

**Proof**:

- Since ϕϕ is unsatisfiable, in every possible interpretation (every row of the truth table), ϕϕ is false.
    
- The negation of a false statement is true. Therefore, ¬ϕ¬ϕ is true in every interpretation.
    
- Hence, ¬ϕ¬ϕ is always true, which means it's a tautology.
    

**Example**:

Let ϕ=p∧¬pϕ=p∧¬p.

- ϕϕ is unsatisfiable:
    
    - If pp is true, ¬p¬p is false, so p∧¬pp∧¬p is false.
        
    - If pp is false, ¬p¬p is true, so p∧¬pp∧¬p is false.
        
- ¬ϕ=¬(p∧¬p)¬ϕ=¬(p∧¬p).
    
    Let's construct the truth table for ¬ϕ¬ϕ:
    
    |pp|¬p¬p|p∧¬pp∧¬p|¬(p∧¬p)¬(p∧¬p)|
    |---|---|---|---|
    |T|F|F|T|
    |F|T|F|T|
    
    As we can see, ¬ϕ¬ϕ is always true, hence a tautology.
    

### Part 2: Negation of a Tautology is Unsatisfiable

**Given**: ϕϕ is a tautology (always true).

**To Show**: ¬ϕ¬ϕ is unsatisfiable (always false).

**Proof**:

- Since ϕϕ is a tautology, in every possible interpretation, ϕϕ is true.
    
- The negation of a true statement is false. Therefore, ¬ϕ¬ϕ is false in every interpretation.
    
- Hence, ¬ϕ¬ϕ is always false, which means it's unsatisfiable.
    

**Example**:

Let ϕ=p∨¬pϕ=p∨¬p.

- ϕϕ is a tautology:
    
    - If pp is true, p∨¬pp∨¬p is true.
        
    - If pp is false, ¬p¬p is true, so p∨¬pp∨¬p is true.
        
- ¬ϕ=¬(p∨¬p)¬ϕ=¬(p∨¬p).
    
    Let's construct the truth table for ¬ϕ¬ϕ:
    
    |pp|¬p¬p|p∨¬pp∨¬p|¬(p∨¬p)¬(p∨¬p)|
    |---|---|---|---|
    |T|F|T|F|
    |F|T|T|F|
    
    As we can see, ¬ϕ¬ϕ is always false, hence unsatisfiable

```


## 1.4 Predicates and Quantifiers

>[!example]
>x is greater than 3
>"is greater than 3" is the predicate
>$P$ is the propositional function $P(x)$
>Once a value is assigned to $x$, the statement $P(x)$ becomes a proposition that has a truth value.
>

In general, a statement of the form $P(x_i)$ is the value of the propositional function $P$ at the n-tuple $(x_i)$ and $P$ is called an $n$-place predicate or an $n$-ary predicate.

## Quantifiers
```ad-important
**Quantification** expresses how to create a proposition from propositional functions. 
The area of logic that deals with predicates and quantifiers is called **predicate calculus**
```

```ad-important
The Universal Quantifier - $\forall$ 
The Existential Quantifier - $\exists$
The Uniqueness Quantifier - $\exists!$
```


These quantifiers have higher precedence than all logical operators from the propositional calculus. 

### 1.4.7 Binding variables

When a quantifier is used on the variable $x$, we say that the variable is **bound**. An unbound variable that is not attached to any quantifier is called **free**. It should be clear that all variables in a propositional function must be bound to turn it into a proposition. This can be done using a combination of universal quantifiers, existential quantifiers and value assignments. 

The part of the logical expression where the quantifier is applied is called the **scope** of the quantifier. Thus, it can be seen, if a variable is outside the scope of all the quantifiers in a propositional function, then that variable is free. 

### 1.4.8 Logical Equivalences Involving quantifiers
A universal quantifier can be distributed over a conjunction (i.e `and:` $\land$). 
>[!example] 
>$$
>\forall x(P(x) \land Q(x)) \equiv \forall xP(x) \land \forall xQ(x)
>$$

Similarly, we can distribute an existential quantifier over a disjunction $(\lor)$

## 1.4.9 Negating Quantified Expressions


$$
\begin{align}
\neg \forall xP(x) \equiv \exists x\neg P(x) \\
\neg \exists xQ(x) \equiv \forall x\neg q(x)
\end{align}
$$

### De Morgan's Laws for Quantifiers

| **Negation**          | **Equivalent Statement** | **When is negation true?**              | **When False?**                             |
| :-------------------- | :----------------------- | :-------------------------------------- | :------------------------------------------ |
| $\neg \exists xP(x)$  | $\forall x\neg P(x)$     | For all x, $P(x)$ is false              | There is some $x$ for which $P(x)$ is true. |
| $\neg \forall x P(x)$ | $\exists x\neg P(x)$     | There is an x for which $P(x)$ is false | $P(x)$ is true for every $x$                |
## 1.5 Nested Quantifiers

### 1.5.1. Introduction

>[!definition]
When one quantifier is in the scope of another its called a nested quantifier

e.g. 
$$
\forall x\exists y (x+y = 0)
$$
for all $x$ there exists some y s.t. $(x+y = 0)$ 

One shortcut could be to think of quantification as (nested) loops. 

```ad-example
Translate the statement: 
$$
\exists x\forall y\forall z((F(x,y)\land F(x,z)\land (y\neq z))\rightarrow \neg F(y,z))
$$
where $F(a,b)$ means $a$ and $b$ are friends and the domain $x$,$y$ and $z$ consists of all the students in your school
```
There exists some $x$ for all $y$ and $z$ such that if $x$ and $y$ are friends and $x$ and $z$ are friends and $y$ and $z$ are not the same person then it implies $y$ and $z$ are not friends.

In other words, there is a student none of whose friends are also friends with each other. 

### 1.5.2 Understanding statements involving nested Quantifiers
We need to unravel what the quantifiers and predicates in the expression mean.

THINKING OF QUANTIFICATION AS LOOPS 

### 1.5.3 The Order of Quantifiers
Order is important unless all quantifiers are of the same kind.
>[!example] 
> $$
> \begin{align}
> \exists y\forall x Q(x,y)  \enspace(1)\\
> \forall x \exists y Q(x,y) \enspace (2)
> \end{align}
> $$

are not the same statement. In the first case $y$ is a constant and independent of $x$ while in the second case, it depends on $x$. When $(1)$ is true, $(2)$ is also true. However the converse is not always the case.

To demonstrate, 
the statement: 
$$
\forall x \forall y \exists z Q(x,y,z)
$$ where $Q(x,y,z)$ is the statement $x+y=z$ then the above says for all $x$ and for all $y$, there exists a $z$ such that $x+y = z$ 
whereas, $\exists z \forall x \forall y Q(x,y,z)$ means there exists some $z$ for all $x$ and $y$ such that $x+y = z$. Which is obviously not true.

### 1.5.4 Translating Mathematical Statements into Statements involving nested Quantifiers

>[!example] 
>The sum of two positive integers is always positive
> For all integers $x$ and for all integers $y$, if $x > 0$ and $y> 0$, then $x+y >0$
> $\forall x \forall  y ((x>0)\land (y> 0)\rightarrow (x+y > 0))$





### 1.5.7 Negating Nested Quantifiers

Statements involving nested quantifiers can be negated by successively applying the rules for negating statements involving a single quantifier.

>[!example] 
>$\neg (\forall x \exists y (xy =1))$
>For all $x$ there exists $y$ such that $xy = 1$
>Wouldn't the negation be for some $x$ there exists no $y$ such that $xy = 1$
>Steps:
>$$
>\begin{align}
>\neg (\forall x \exists y (xy =1)) \\
>\equiv \exists x \neg\exists y (xy = 1) \\
>\equiv \exists x \forall y \neg (xy = 1) \\
>\equiv \exists x \forall y (xy \ne 1)
\end{align}
$$

thus, when you move in you toggle the quantifier type, from existential to universal and vice versa.

## 1.6 Rules of Inference

### 1.6.1 Introduction

 By an **argument**, we mean a sequence of statements that end with a conclusion. By **valid**, we mean that the conclusion, or final statement of the argument, must follow from the truth of the preceding statements, or **premises**, of the argument. That is, an argument is valid if and only if it is impossible for all the premises to be true and the conclusion to be false. To deduce new statements from statements we already have, we use rules of inference which are templates for constructing valid arguments. Rules of inference are our basic tools for establishing the truth of statements.

After we illustrate how rules of inference are used to produce valid arguments, we will describe some common forms of incorrect reasoning, called **fallacies**, which lead to invalid arguments.

### 1.6.2 Valid Arguments in Propositional Logic

Consider the following argument involving propositions (which, by definition, is a sequence of propositions): “If you have a current password, then you can log onto the network.” “You have a current password.” Therefore, “You can log onto the network.”


>[!tip] 
>Form of the above argument:
>Let $p$ = "You have a current password"
>Let $q$ = "You can log onto the network"
>$$
>\begin{align}
>p \rightarrow q \\
>p \\
>\hline
>\therefore q
\end{align}
>$$

>[!definition]
If all the premises are true, then the conclusion must necessarily be true. Such a form of argument is called a **valid** argument. 

This _form of argument_ is valid. By replacing concrete propositions by abstract propositional variables, we change an argument to an **argument form**.

>[!important] 
>It means that the actual propositions don't really matter, its the form of the argument that is important 🤯


>[!definition]
>An argument in propositional logic is a sequence of propositions. All but the final proposition in the argument are called premises and the final proposition is called the conclusion. An argument is valid if the truth of all its premises implies that the conclusion is true. An argument form in propositional logic is a sequence of compound propositions involving propositional variables. An argument form is valid if no matter which particular propositions are substituted for the propositional variables in its premises, the conclusion is true if the premises are all true

### 1.6.3 Rules of Inference for Propositional Logic


We can use a truth table, but as the number of input variables increase it could quickly become very unwieldy. Instead, we can first establish the validity of certain simpler argument forms called **rules of inference**. These can then be used to simplify more complex forms.

>[!attention] 
>how do forms relate to concrete beings? just like the form of an argument relates to an argument.
>

The tautology $(p \land (p \rightarrow q)) \rightarrow q$ is called _modus poens_ or the _law of detachment_. 

#### Rules of Inference:


| S. No | **Rule of Inference**                                                          | **Tautology**                                                           | **Name**               |
| ----- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------- | ---------------------- |
| 1.    | $p$<br>$p\rightarrow q$<br>$-----$<br>$\therefore q$                           | $(p\lor(p\rightarrow q))\rightarrow q$                                  | Modus ponens           |
| 2.    | $\neg q$<br>$p \rightarrow q$<br>$-------$<br>$\therefore \neg p$<br>          | $(\neg q \land (p \rightarrow q)) \rightarrow \neg p                    | Modus Tollens          |
| 3.    | $p \rightarrow q$<br>$q \rightarrow r$<br>$---$<br>$\therefore p\rightarrow r$ | $((p\rightarrow q)\land (q \rightarrow r))\rightarrow (p\rightarrow r)$ | Hypothetical syllogism |
| 4.    | $p\lor q$<br>$\neg p$<br>$----$<br>$\therefore q$<br>                          | $((p \lor q)\land \neg p) \rightarrow q$                                | Disjunctive syllogism  |
| 5.    | $p$<br>$----$<br>$\therefore p \lor q$                                         | $p \rightarrow (p \lor q)$                                              | Addition               |
| 6.    | $p\land q$<br>$----$<br>$\therefore p$                                         | $(p \land q)\rightarrow p$                                              | Simplification         |
| 7.    | $p$<br>$q$<br>$------$<br>$\therefore p \land q$                               | $((p)\land (q)) \rightarrow (p \land q)$                                | Conjunction            |
| 8.    | $p\lor q$<br>$\neg p \lor r$<br>$-----$<br>$\therefore q \lor r$               | $((p \lor q)\land (\neg p \lor r))\rightarrow (q \lor r)$               | Resolution             |
These are straight forward derivations. 
#### Modus ponens is also called the law of the excluded middle. 
If $p$ is true and $p \rightarrow q$ then $q$ is also true
#### Modus tollens
If $q$ is false and $p \rightarrow q$ then necessarily $p$ is false

#### Hypothetical syllogism
If p implies q and q implies r then p implies r

#### DIsjunctive syllogism
If p or q is true and p is false then q has to be true

#### Addition
If p is true then p or q has to be true by definition of $\lor$

#### Simplification
If p and q are true, then p has to be true (also the same for q) again, by definition of $\land$

#### Conjunction
If p is true and q is true then p and q is also true. Again by definition. 

#### Resolution 
If p or q is true and not p or r is true then q or r has to be true by logical deduction.

### 1.6.4 Using Rules of Inference to build arguments

When there are many premises, several rules of inference are often needed to show that an argument is valid.

### 1.6.5 Resolution

Reasoning and proving theorems has been automated with the use of the rule of inference called *resolution*. It is based on the tautology:

$((p\lor q)\land (\neg p \lor r)) \rightarrow (q \lor r)$

The final disjunction is called the *resolvent*.

### 1.6.6 Fallacies

Incorrect reasoning is also called *fallacy of affirming the conclusion* or *fallacy of denying the hypothesis*.

### 1.6.7 Rules of Inference for Quantified Statements

*Universal instantiation* - to conclude $P(c)$ is true when $\forall xP(x)$ 
*Universal generalization* - to conclude $\forall xP(x)$ if itss true for arbitrary $c$ in the domain.

| *Rule of inference*                                                                 |           *Name*           |
| :---------------------------------------------------------------------------------- | :------------------------: |
| $\forall xP(x)$<br>$------$<br>$\therefore P(c)$                                    |  Universal instantiation   |
| $P(c) \textit{for an arbitrary} \space c$<br>$---------$<br>$\forall xP(x)$         |  Universal generalization  |
| $\exists xP(x)$<br>$------$<br>$\therefore P(c) \textit{for some element} \space c$ | Existential instantiation  |
| $P(c) \textit{for some element c}$ <br>$-----$<br>$\therefore \exists xP(x)$        | Existential generalization |

### 1.6.8 Combining Rules of Inference for Propositions and Quantified Statements

Universal instantiation and modus ponens are so often used together, their combination is often called *universal modus ponens*. In natural language, this rule tells us that if $\forall x(P(x) \rightarrow Q(x))$ is true, and if $P(a)$ is true for a particular element $a$ in the domain of the universal quantifier, then $Q(a)$ is true. 

Similarly, we have the *universal modus tollens*, which, perhaps unsurprisingly is a negation. If we again have the same inference for all $x$, and we have $Q(x)$ false for some $a$ in the domain of the universal quantifier, then $P(a)$ must also be false.


