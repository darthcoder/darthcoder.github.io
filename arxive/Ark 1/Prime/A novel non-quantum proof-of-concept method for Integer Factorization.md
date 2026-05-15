>[!abstract]
> Integer factorization especially, the factorization of large primes is a very important problem in number theory and cryptography. Most of our internet security protocols and cryptography rest on the purported difficulty of their factorization and the relative ease of their generation. 
> In this paper, we demonstrate a novel, non-quantum method that can speed up integer factorization. 
> In the first section of the paper, we talk about the background of how this proposed method will work. 
> In the second section of the paper, we provide an implementation in Haskell. We strategically limit ourselves to smaller primes than those used in cryptography as we intend to show just the proof of concept and are not interested in "breaking crypto".
> In the third section of the paper, we compare the performance with typical libraries used for this purpose.
> Finally we note some limitations and way forward in the conclusion section.


## Introduction

One of the central problems of Computer Science and indeed all of mathematics is the $\mathcal{P=NP}$ problem, which is as of yet, unresolved. While we don't comment directly on this problem, we will mention that Prime factorization has canonically been understood to be a member of the $\mathcal{NP}$ set. 

This assumption of the purported difficulty for factorizing large primes by traditional methods has been the catalyst in the adoption of prime factorization and related methods as the mainstay of cryptography and internet security. It could be considered that without having a rigorous proof of the complexity class of Prime factorization, it was not ideal to adopt it as the mainstay of internet security, but that ship has sailed a while ago.

Quantum methods for factorization are already a thing. And there is obviously some research into securing systems from quantum attacks and developing new "quantum-secure" methods. Of course, this research and its adoption are not progressing as fast as they should be perhaps simply because there are no quantum computers yet, that can factor the RSA and similar primes. 

While mathematical papers shy away from such comments, owing to the nature of this work, we wish to point out that this seems like a very bad strategy and it would lead to a Y2K like crisis if and when a Quantum computer of sufficient power emerges unexpectedly. 

We have known since at least 2004 by the landmark AKS paper that Primes are indeed in $\mathcal{P}$. It could have been conjectured even at that time, that perhaps it is possible to have Factorization also in $\mathcal{P}$. However, owing to many reasons, which could be clubbed together into what may be termed as "collective wisdom" and "sheer inertia", somehow the status-quo has prevailed. 

In this paper we present a radically different proof-of-concept method for factorization. While as of now, it is fundamentally an open question whether it is an improvement or not, we believe that actual mathematicians will probably be able to improve it further.

>[!to-do]
> Implementation of the algorithm and speed comparisons with usual methods for primes of different sizes.


We confess that the big idea is to just guess the factors. While that sounds bad, hopefully, the implementation and the logic behind the method should convince the reader that there is something of worth in the method. 


### Setting up the problem. 

Suppose, knowing nothing about the background of number theory we are asked to factorize a large number. One of the ways we might proceed is to simply try numbers at random until we find if there are any factors other than one and the number itself. If we denote the number by $N$, in the worst case, it would take us $O(N)$ steps. One optimization of course is to proceed in increasing order upto $\sqrt{N}$. That much is of course obvious. 

But consider a rather different approach. A number $N$ can be thought of as a sequence of digits, lets say of length $L$. The problem of finding two factors of $N$, is equivalent to finding two digit sequences of length $L$, such that their product is $N$, where we just pad the most significant digits with zeroes if required. 

For the following analysis, we stick to base10 for reasons of naturalness but that is not necessary and could be reconsidered in future work.

In the brute force approach, we have 10 choices for every digit which leads to an exponential $\mathcal{O}(10^L)$ solution. The question we investigate here, by various means is simply, can we do better? 

### A probable candidate

We try to reverse engineer the common multiplication algorithm to see what can we improve upon. Lets assume for the moment that the digit in the units place is $5$. This $5$ **can only** arise from the multiplication of the units digits of the two sequences, hereinafter referred to as $a_i$ and $b_i$. The units digits can only be $1\times 5$, $3\times 5$, $5\times 5$, $7\times 5$ or $9\times 5$. Already we are off to a good start. Instead of $10$ guesses each for the last digits, we only have to consider $5$ combinations.

Clearly, the method is elementary, we keep doing trial and error, lets say we choose $a_{\mathit{units-digit}} = 7$ and $b_{units-digit}=5$. Then there product is $35$. So we now move to the digits in the next significant position and try guessing it. Yet still the formula seems to explode. For $2L$ digits we have to try $m$ combinations where hopefully  $m\lt 10$. Whats worse is that for each of these $2L$ digits, we have to keep trying these combinations and there seems to be a combinatorial explosion. Are we doing any better? At the best case, we can assert that we have some $\mathcal{O}(m^L)$ solution, which might be better, but that is not guaranteed. In fact due to the combinatorial explosion, it seems that we might actually be worse off than simply multiplying numbers up to $\sqrt(N)$.

One more observation helps us here, multiplication of two numbers is functionally equivalent to a convolution of the sequences of individual digits. Also, for every guess when we are at the $i^{th}$ digit, we know(i.e have already guessed) the values of all the digits to the right of it, assuming we are using standard Hindu-Arabic notation to denote the numbers in base-10. 

Thus, we have for the $i^{th}$ digit, a linear Diophantine equation of the following form:
$$
\begin{align}
ax+by = c
\end{align}
$$

where $a$ and $b$ are known coefficients in terms of the digits to the right and $c$ is sort of known (this notion will be made clear when we illustrate and implement the algorithm in the next section). 

Now, we know from elementary number theory that a linear Diophantine equation **only** has a solution when:

$$
\begin{align}
c \mod{gcd(a,b)}  = 0
\end{align}
$$

This additional constraint imposes a rather strict condition on what choices of $c$ are admissible. 

The question then becomes, is it enough? How much do these optimizations improve on the brute search method?

The author is not a mathematician by any stretch of imagination. Thus, we will employ a shortcut. We know for a fact, that primes aren't going to change, so we can just compare this improved algorithm with the usual sieve methods from established libraries that are used for this computation. Let's find out shall we?


## Implementation

### A look at the multiplication algorithm

Consider the problem of multiplying two numbers as the problem of multiplying two sequences $a_i$ and $b_i$. 

Let the product be denoted by $c$ then, we have,

$$
\begin{align}
c_i = \Sigma^{i}_{k=1} a_k b_{i-k+1}
\end{align}
$$
for the $i^{th}$ term of $c$. 

The multiplication algorithm is made complicated by the fact that we only retain the least significant digit of $c_i$ and the rest is "carried over" to the next most significant digit. 

We first explain the algorithm in words, then in pseudo-code and then provide an implementation in Haskell. 

#### In words

We begin with the units digit and note down all possible combinations that lead to the digit in the units place. We can, without loss of generality assign one of these digits to $a_1$ and the other to be $b_1$. Now it is possible that the product of $a_1$ and $b_1$ is greater than 10, in which case we have to account for the carry digit too. Lets save the carry digit in a temporary variable $t$. Now, we know the first digits have to be one of these combinations. We store the possible values for $a_1$ and $b_1$ in a map with the key as 1 and the possible values as an array of numbers. For each of these numbers we store a boolean set as true to indicate whether we have tried out that combination or not.  

Thus our data structures look something like:

```python
c_1 = 5 //lets assume
a_1 = {1:[(1,false),(3, false),(5, false),(7, false),(9, false)]}
b_1 = {1:[(5,false),(5,false),(5,false),(5,false),(5,false)]}
```

Now we have for the second digits:

$$
\begin{align}
a_2\times b_1 + b_1\times a_2 + t_1 = [t_2, c_2]
\end{align}
$$
where the notation $[t_i,c_i]$ is a sequence where $t_i$ refers to the carry digits and $c_2$ is the second digit of the number being factored.

This can be rewritten in the form of a linear Diophantine equation as follows:

$$
\begin{align}
a_1\times b_2 + b_1\times a_2 = [t_2, c_2] - t_1 
\end{align}
$$
Looking at our equation we know the values subscripted with $1$ and $c_2$. Thus, we have one equation in three unknowns viz. $a_2$, $b_2$ and $t_2$, subject to the conditions:

$$
a_2, b_2 \in [0,9]
$$ 
thus we can obtain the $max(a_1\times b_2 + b_1\times a_2)$. Further, since $a_1$ and $b_1$ also have to satisfy the above constraint, we can rewrite the right side of the equation as:


$$
\begin{align}
a_1\times b_2 + b_1\times a_2 = [t_2, c_2 - t_1]
\end{align}
$$
Thus the right side is a number, ending in a digit ($|c_2 - t_1|$) Lets denote this number as $k_2$ . 

Then we have, 

$$
\begin{align}
a_1\times b_2 + b_1 \times a_2 = k_2
\end{align}
$$

Now, the problem is that, as of now, $t_2$ is also unknown. But since we are only multiplying digits and we know (from our guesses) $c_2$ thus we have lower and upper bounds on the values of $t_2$ and hence on $k_2$. 

Further since the equation to determine $k_2$ is a linear Diophantine equation, we have:

$$
\begin{align}
k_2 \mod{gcd(a_1,b_1)} = 0
\end{align}
$$
#### A recap of the algorithm

1. Store possible digit pairs that lead to the last digit of $N$ in a **((data structure))** for $a_1$, $b_1$ and $c_1$
2. now with $c_1$ known, determine the minimum and maximum possible values of $k_2$.
3. Using the relation 
