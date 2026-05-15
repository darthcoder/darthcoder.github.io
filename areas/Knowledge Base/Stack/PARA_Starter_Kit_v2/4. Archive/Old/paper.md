---
id: dlse9rqzv8rud9w836e9kcv
title: Paper
desc: ''
updated: 1731055451672
created: 1731049446924
---

## The Era of Secrets is over, presenting a trivial factorization algorithm with a phenomenological proof

### Abstract

Traditional belief has long held that factorization of primes belongs to the class $NP$ and the field of cryptography has blossomed with that aforesaid assumption.

Herein, we demonstrate a trivial algorithm that doesn't use any complex mathematical constructs.

The basic insight is that instead of considering a natural number $n$ as a magnitude we consider it as a sequnce $p_i$ of digits. Assuming that $p_i$s arise as a product of two sequences $a_i$s and $b_i$s, the naive algorithm will have 10 possibilities for each of them and the complexity would be exponential in the number of digits. However, as we show below, there are certain considerations that make the algorithm polynomial.

### Sketch of the proof

We will illustrate with an example. Let's consider the number 1234567. For the moment, lets assume that we don't know whether this number is a prime or a composite number. Now lets look at the number not as a magnitude but as a sequence of 7 digits. The last digit is 7. If we look at the multiplication tables then the only ways to get a 7 in the units digit is either to muliply 9 by 3 resulting in 27 or 7 by 1 resulting 7. There are simply no other digits which when multiplied yield 7 in the units place. For the moment we are assuming that 1234567 is the product of two numbers. These two numbers can be written as a sequence $a_1a_2a_3a_4a_5a_6a_7$ and $b_1b_2b_3b_4b_5b_6b_7$. It should be obvious that there cannot be more digits than these in the product. Now, if the number has multiple prime factors, we can recursively apply the procedure to these two numbers (once determined) and get the next prime factors until all the prime factors are known.

Now we proceed in a graph like manner, either $a_7$ and $b_7$ are 9 and 3 or they are 7 and 1. We proceed with both possibilities in parallel and work out the case of 9 and 3 first. Since we have chosen $a_i$ and $b_i$ at random, it doesn't matter which is which and we assign $a_7$ to be 9 and $b_7$ to be 3.

Now on multiplying 9 and 3 we get 27. 7 becomes the units digit and 2 gets carried over. Now we consider the case of $a_6$ and $b_6$. When we work out the normal multiplication procedure,
$$
\begin{equation}
a_6b_7 + b_6a_7 + 2 = 6
\end{equation}
$$

where, we already have $a_7 = 9$ and $b_7 = 3$ so the above equation becomes:
$$
\begin{equation}
3\times a_6 + 9 \times b_6 = c4
\end{equation}
$$

where $c$ is a carry digit. By brute force search, there are ten possibilities for $a_6$ and ten possibilities for $b_6$. N.B. it is very easy to implement a constant time lookup table or a myriad of other data structures where we can look up in constant time the possible solutions to the above equation, but the essence of the argument remains the same. By a partial search we find the following cases: $3\times5 + 9 \times1 = 24$, $3\times 9 + 9\times 3 = 54$. Two patterns we can notice are as follows: since both $3$ and $9$ are divisible by three therefore the sum i.e. $c4$ should also be divisible by $3$, also we can see the max value possible is $108$ which is attained when both $a_6$ and $b_6$ attain their maximum values i.e. $9$. Of course if we are using any halfway decent data structure we don't need to rely on such shortcuts, but I am just illustrating a point. We can see the only other $c4$ pattern number lesser than $108$ is $84$. This has three possibilites $3\times 7+9\times 7 = 84$, $3\times 4 + 9\times 8 = 84$ and $3\times1 + 9\times 9 = 84$. Thus the pattern $c4$ has 5 possibilities. We need to proceed with all of them. To wit, we had two possibilities for the first digit and five possibilities for the second digit. The naive version of the algorithm, where we tried all possible combinations of digits would have had $10\times 10 = 100$ possibilities and would have led to an exponential explosion. At two digits we have succesfully contrained the problem to one order of magnitude less possibilities. We will continue for one more digit to illustrate the solution further.

Now we have:

$$
\begin{equation}
b_7a_5+b_6a_6+b_5a_7 = c5
\end{equation}
$$

plugging known values from the first case i.e. $a_6 = 5$ and $b_6 = 1$  , we have:
$$
\begin{equation}
3\times a_5 + 9\times b_5 + 5 = c5
\end{equation}
$$
now max value of this is attained when a_5 and b_5 are both 9. Which is $27 + 81 + 5 = 113$ and minimum value is $5$. So possibilites are 5, 15, 25, 35, 45, 55, 65, 75, 85, 95 and 105. Now since 5 is a constant we can decrease it from c5 to get c0. Thus the modified equation becomes:
$$
\begin{equation}
3\times a_5 + 9\times b_5 = c0
\end{equation}
$$

again the max value is $108$. Then, the possibilities become, 0, 10, 20, 30, 40, 50, 60, 70, 80, 90 and 100. A little exploration convinces us that this equation has no solution. Thus, this possibility can be discarded, we now continue with the next possibility. Note that in a real world scenario, we would be doing these calculations in parallel. The question arises as to how many digits should we backtrack by and this question of optimality is left by the author to actual mathematicians. It however seems plaausible to move back a digit only when we have exhausted all the possibilities in the forward pass. 

Thus, we now try the next possibility: $a_6 = 9$ and $b_6 = 3$. Now, we have: 
