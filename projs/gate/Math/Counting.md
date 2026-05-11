# 6.1 The Basics of Counting

## 6.1.1 Introduction

Suppose that a password on a computer system consists of six, seven, or eight characters. Each of these characters must be a digit or a letter of the alphabet. Each password must contain at least one digit. How many such passwords are there?

## 6.1.2 Basic Counting Principles

>[!definition] The Product Rule
>Suppose that a procedure can be broken down into a sequence of n tasks and there are $n_i$ ways to do the $i_{th}$  task, then there are $\prod_{i}^{n} n_i$ ways to do the procedure.

There is another way to state the product rule in terms of Cartesian Products of Sets. 

>[!definition]
>For $A_i$ then the number of elements in the Cartesian product of these sets is the product of the number of elements in each set. The task of choosing an element in the Cartesian product is done by choosing an element in $A_1$ and an element in $A_2$ and so on.

>[!definition]
>THE SUM RULE:
>In a task can be done in either in one of $n_1$ ways or in one of $n_2$ ways where none of the $n_1$ ways are the same as any in the set of $n_2$ ways, 

>[!note]
>Product rule corresponds to loops within loops while sum rule corresponds to loops one after the other, perhaps writing a pseudo-code program can help me in counting. 

## 6.1.3 More Complex Counting Problems

Many complicated counting problems can be solved by using both the rules together. 

## 6.1.4 The Subtraction Rule (Inclusion-Exclusion for two sets)

>[!definition The Subtraction Rule]
>If a task can be done in $n_1$ or $n_2$ ways, then the total number of ways to do the task is $n_1+n_2$ minus the common number of ways.

Also called the **Principle of Inclusion-Exclusion** esp when it is used to count the number of elements in the union of two sets.

in the following form:

$$
| A_1 \cup A_2 | = |A_1| + |A_2| - |A_1\cap A_2|
$$

## 6.1.5 The Division Rule

There are $n∕d$ ways to do a task if it can be done using a procedure that can be carried out in $n$ ways, and for every way $w$, exactly $d$ of the $n$ ways correspond to way $w$.


# 6.2 The Pigeonhole Principle

>[!theorem 1] 
>If $k$ is a positive integer and $k+1$ or more objects are placed into $k$ boxes, then there is at least one box containing two or more objects.

### Aside - Heuristics for counting problems

You've hit on one of the most challenging aspects of combinatorics! Recognizing which principle applies takes practice, but you can develop heuristics (mental shortcuts or rules of thumb) to guide you. It's less about memorizing formulas and more about understanding the _structure_ of the counting process.

Here’s a breakdown to help you identify when to use which principle, moving beyond just "practice":

1. **Understand the Core Question:**
    
    - **What constitutes ONE outcome?** Are you forming a sequence, a group, making a single choice, or multiple choices? Be precise.
    - **Does order matter?** If you rearrange the selected items, does it count as a _different_ outcome? This is often the biggest hurdle.
    - **Are there stages or steps?** Do you build the outcome piece by piece?
    - **Are there distinct cases?** Can the outcomes be broken down into non-overlapping groups?
    - **Are items replaced or used only once?** (Usually specified or implied).
2. **Linking Questions to Principles:**
    
    - **Multiplication Principle (Rule of Product): Use when...**
        
        - An outcome is formed by a **sequence of independent choices or steps.**
        - You can phrase the process as "Do Task 1 **AND** Task 2 **AND** Task 3..."
        - You are filling distinct "slots".
        - _Keywords:_ **AND**, sequence, steps, stages, filling positions, constructing.
        - _Example:_ Picking 1 Math major (18 ways) **AND** 1 CS major (325 ways) -> 18×325. Forming a 5-char string (choose char 1 **AND** char 2 **AND**...) -> 128×128×...
    - **Addition Principle (Rule of Sum): Use when...**
        
        - You can break the set of possible outcomes into **disjoint (non-overlapping) cases.**
        - You can phrase the choice as "Choose Option A **OR** Option B **OR** Option C..." where A, B, C cannot happen simultaneously.
        - _Keywords:_ **OR**, **EITHER/OR**, cases, mutually exclusive, disjoint sets.
        - _Example:_ Picking 1 representative who is Math **OR** CS -> 18+325.
    - **Complement Principle: Use when...**
        
        - The condition involves words like **"AT LEAST ONE"** or **"NOT ALL"**.
        - Counting the desired outcomes directly involves many complex cases (like your PIE example).
        - Counting what you _don't_ want (the complement) is much simpler.
        - The **Total** number of outcomes is easy to calculate (often using the Multiplication Principle).
        - _Formula Idea:_ (Desired Outcomes) = (Total Possible Outcomes) - (Undesired Outcomes / Complement)
        - _Example:_ Strings with **AT LEAST ONE** '@' = (Total 5-char strings) - (Strings with **NO** '@').
    - **Permutations (Order Matters): Use when...**
        
        - You are selecting items from a set **AND** the order/arrangement of the selected items matters.
        - Think about assigning specific roles, positions, or creating a sequence where A, B is different from B, A.
        - _Keywords:_ **ARRANGEMENT**, sequence, order, ranking, schedule, assigning distinct roles.
        - _Example:_ How many ways to award Gold, Silver, Bronze (order matters) from 10 competitors? P(10,3). How many ways to arrange 5 books on a shelf? 5!=P(5,5).
    - **Combinations (Order Doesn't Matter): Use when...**
        
        - You are selecting items from a set **AND** the order of selection does _not_ create a different outcome.
        - Think about forming a group, committee, or subset where {A, B} is the same as {B, A}.
        - _Keywords:_ **SELECTION**, choose, group, committee, subset, sample (often implies order doesn't matter).
        - _Example:_ How many ways to choose a committee of 3 (order doesn't matter) from 10 people? C(10,3). Dealing a 5-card poker hand (the order you receive the cards doesn't change the hand). C(52,5).
    - **Principle of Inclusion-Exclusion (PIE): Use when...**
        
        - You are counting outcomes based on an **"OR"** condition, but the sets/cases **overlap**.
        - You tried an additive approach (like your 5×1284) and realized you were **overcounting**.
        - You need to find the size of the **union** of multiple sets that are not disjoint.
        - Often related to "at least one" conditions when the complement is not easier.
        - _Example:_ Counting numbers divisible by 2 **OR** 3 (overlap: numbers divisible by 6). Your attempt to count strings with '@' in position 1 **OR** position 2, etc.
3. **Strategy Steps When Facing a Problem:**
    
    1. **Identify the basic outcome:** What does one "thing" you are counting look like?
    2. **Order?** Does the order of components within the outcome matter? (-> Permutations vs. Combinations/Multiplication).
    3. **Stages?** Can you build the outcome in steps? (-> Multiplication).
    4. **Cases?** Can you break the problem into distinct, non-overlapping groups? (-> Addition).
    5. **Keywords?** Look for "at least one," "or," "and," "arrange," "select."
    6. **"At Least One"?** Try the Complement Principle first. Calculate Total. Calculate None. Subtract.
    7. **Overlapping OR?** If using "OR" and the cases overlap, think PIE (but double-check if Complement is simpler).
    8. **Simplify:** Can you rephrase the problem? Can you solve a smaller version first to see the pattern?

It _is_ practice, but hopefully, this structured thinking and keyword association helps you choose the right tool more often. Don't be discouraged; these problems require careful thought!
