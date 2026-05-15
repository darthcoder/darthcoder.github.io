---
id: dlse9rqzv8rud9w836e9kcv
title: Paper
desc: Paper on efficient factorisation
updated: 1731055451672
created: 1731049446924
---

## A novel method for Prime Factorisation

### Abstract

A novel method is presented for prime factorisation, based on using the number itself to try to guess the digits that might have been multiplied to obtain the final number itself. Considering the last digit to be $a_n$ and knowing that only a few combinations exist that, when multiplied will lead to the last digit, we can extend the argument and considerably constrain the problem in such a manner that we are not guessing $2\times 10^n$ digits as the naive case would expect. The problem is simplified by assuming that only two numbers are being multiplied to yield the product $a$ and further factors can be achieved by applying the same method to the resulting numbers.

The algorithm is presented in Haskell and the code could be found on Github. Some rudimentary performance analysis is also performed.

We also consider the implications for the $P=NP$ problem that this algorithm implies.

### Introduction

Efficient Factorisation of Primes is a problem that has long occupied number theorists and Computer Scientists. It is telling that despite the amount of resources and research poured into this problem, we still are not significantly better off than the traditional sieve methods that have been known for thousands of years. As a result, Prime Factorisation has been considered to be a member of class $NP$. However, we have known since the [AKS2004] paper that "Primes are in $P$", conventional wisdom has always maintained that Factorisation is in the class $NP$. This has often been asserted without a rigorous proof.

Part of the problem lies in the fact that we conceive of numbers as magnitudes of size $n$. If we instead look at a number as a sequence $a_i$ we are at once stuck with the insight that all the digits of the number under investigation arise from the multiplication of two digits. Now in base 10 since there are only 10 digits, it stands to reason that there are only a few possibilities that could generate the last digit. However, further progress might seem complicated owing to the seemingly combinatorial explosion that might exist whereby its not clear which digits to multiply to get the $a_i$th number. The problem is further confounded by the fact that when we multiply two digits, we often end up with a carry digit, which is carried over to the next digit of the product. Thus, not knowing what the digits are and not knowing what the carry terms are, can make the problem seem hopeless and it could seem like we can do no better than the naive approach of guessing $2\times 10^n$ numbers, at which point multipling numbers $k,l$ such that $k,l \le \sqrt{n}$ might seem like a much better approach.

However, as we will demonstrate with arguments and a detailed worked out example in the next section, there is yet ample reason to be hopeful.

The crucial insight is that for any two numbers $b,c$ that are being multiplied to yield the product $a$, if we start from the units digit of $a$ we have a few possible canditates for the units digits of $b,c$ and then when we carry out the multiplication procedure, we notice that when we are trying to compute the digit $a_i$, the only unknowns in that step of multiplication are the $b_i$ and $c_i$, as all $b_j$ and $c_j$, where $i \le j \le n$ are known for the current iteration. Since the carry term is fully determined by the same digits, it is also known. Thus the problem of finding $a_i$ reduces to an integer programming problem, subject to the constraints:

$$
\begin{equation}
p\times b_i + q\times c_i + c = f[a_i]
\end{equation}
$$

where $p$ and $q$ are known and $f[a_i]$ represents a number ending in the digit $a_i$ and c represents the total sum of all the carry terms and is known from the digits $b_j$ and $c_j$

thus we can determine the minimum and maximum values for $f[a_i]$

Once the range of values is known, we can obtain the specific numbers which end in the digit $a_i$ to determine the possible values of $f[a_i]$

We are stating this now without any rigorous proof but since $b_i$ and $c_i$ are the only unknowns, but would be illustrated with an example in the next section, that not all combinations will work as these are equations that have to be satisfied by integer values.

The basic claim is simple but perhaps somewhat radical, the space of solutions is much smaller than the total space of all possible combinations of digits.

We will now illustrate in the next section.

### A Worked Out Example, for illustrating the basic method, without regards to any optimisation

Let the number under investigation be $a = 5321$, which for the moment we assume that we don't know the prime factors of. Let the two factors be $b$ and $c$ such that $b = b_1b_2b_3b_4$ and $c = c_1c_2c_3c_4$ where the index $4$ represents the units digit.

Now from the multiplication tables of digits we have the following possibilities (and only the following possibilities),
$$
\begin{equation}
\begin{aligned}
(b_4,c_4) = (1,1) = 1\\
(b_4,c_4) = (3,7) = 21\\
(b_4,c_4) = (7,3) = 21\\
(b_4,c_4) = (9,9) = 81\\
\end{aligned}
\end{equation}
$$

once we work out the next digits, we will find that one and only one of this equations is satisfied. For the sake of argument, lets assume $(b_4,c_4) = (9,9)$ to be the values.

Now we are to evaluate $b_3$ and $c_3$,

here we have,

$$
\begin{equation}
b_4 \times c_3 + b_3 \times c_4 + 8 = [x:2]
\end{equation}
$$

which becomes

$$
\begin{equation}
9\times c_3 + 9\times b_3 = [x':4]
\end{equation}
$$

now since, $0 \le b_3, c_3 \le 9$, we have $0 \le g[4] \le 162$ subject to the constraint that the last digit of $[x':4]$ is $4$.

This means that the possible values of $[x:4]$ are $4,14,24,34,54,64,74,84,94,104,114,124,134,144,154$.

Now solving the above equation, the only possible values are $54$ and $144$ because the number has to be divisible by 9.

for $54$,  $c_3+b_3 = 6$ and for $144$, $c_3+b_3 = 16$ thus we have the following two sets of pairs:

$$
\begin{equation}
\begin{aligned}
(b_3,c_3) = (0,6) = 6\\
(b_3,c_3) = (1,5) = 6\\
(b_3,c_3) = (2,4) = 6\\
(b_3,c_3) = (3,3) = 6\\
(b_3,c_3) = (4,2) = 6\\
(b_3,c_3) = (5,1) = 6\\
(b_3,c_3) = (6,0) = 6\\
\end{aligned}
\end{equation}
$$

$$
\begin{equation}
\begin{aligned}
(b_3,c_3) = (9,7) = 16\\
(b_3,c_3) = (8,8) = 16\\
(b_3,c_3) = (7,9) = 16\\
\end{aligned}
\end{equation}
$$

At the moment, we can do no better than checking all the 10 possibilities, but two factors are of note, one the naive implementation would have had a 100 possibilities and we have 10, thus we are an order of magnitude less possibilities to check. Secondly, most of these possibilities would get invalidated by the next digits. Also we can already see, that if we are lucky enough, the best case scenario is $O(n)$ in the _number of digits_ corresponding to guessing all the correct digits on the first try.

lets continue, again with the last possibility that $(b_3,c_3) = (7,9)$.

Then we have:

$$
\begin{equation}
b_2 \times 9 + b_3 \times c_3 + c_2 \times 9 + c = [y:3]
\end{equation}
$$
where $c$ is determined from the product as $c=[]$
putting in the known values, we have:

$$
\begin{equation}
9 \times b_2 + 9 \times c_2 = [y':0]
\end{equation}
$$

which should only have one solution i.e $[y':0] = 90$

then,
$$
\begin{equation}
\begin{aligned}
(b_2,c_2) = (5,5)
\end{aligned}
\end{equation}
$$
and it can be easily verified that this is the only possibility.

Then moving on, we have

$$
\begin{equation}
b_1\times c_4 + b_2 \times c_3 + b_3 \times c_2 + b_4 \times c_1 + c = [z:5]
\end{equation}
$$

again, substituting for known values, we have:

$$
\begin{equation}
9\times b_1 + 45 + 35 + 9\times c_1 + 2 = [z:5]
\end{equation}
$$

on simplification, we have,

$$
\begin{equation}
9\times b_1 + 9 \times c_1 = [z':3]
\end{equation}
$$

again, for which the solutions are (3,4) and (4,3), thus candidate numbers are (3579,4599) and (4579, 3599). We can easily multiply these numbers and find that they are not correct. Thus, we need to try again.

#### Trial #2

Now we try $b_4 = 3$ and $c_4 = 7$

then we have,

$$
\begin{equation}
b_3 \times 7 + c_3 \times 3 + c = [x:2]
\end{equation}
$$

since clearly, $c = 2$, we have:

$$
\begin{equation}
b_3 \times 7 + c_3 \times 3 = [x':0]
\end{equation}
$$

again, since $$ 0 \le b_3, c_3 \le 9$$we have $$ 0 \le f'[0] \le 90$$Thus, possible values of $[x':0]$ are $0,10,20,30,40,50,60,70,80,90$ and subject to the above constraints, we have:

$$
\begin{equation}
\begin{aligned}
(b_3, c_3) = (0,0) = 0\\
(b_3, c_3) = (1,1) = 10\\
(b_3, c_3) = (2,2) = 20\\
(b_3, c_3) = (3,3) = 30\\
(b_3, c_3) = (4,4) = 40\\
(b_3, c_3) = (5,5) = 50\\
(b_3, c_3) = (6,6) = 60\\
(b_3, c_3) = (7,7) = 70\\
(b_3, c_3) = (8,8) = 80\\
(b_3, c_3) = (9,9) = 90\\
\end{aligned}
\end{equation}
$$

now lets assume $(b_3, c_3) = (0,0)$ and move on.

now we have:

$$
7\times b_2 + 0 + 3\times c_2 + c = [y:3]
$$

simplifying and putting in the value of $c = 0$, we have:

$$
7\times b_2 + 3\times c_2 = g[3]
$$

subject to $0 \le [y:3] \le = 90$

thus, we have, possible values of $[y:3]$ equal to $3,13,23,33,43,53,63,73,83$
Which leads to the following cases:

$$
\begin{equation}
\begin{aligned}
(b_2, c_2) = (0,1) = 3\\
(b_2, c_2) = (1,2) = 13\\
(b_2, c_2) = (2,3) = 23\\
(b_2, c_2) = (3,4) = 33\\
(b_2, c_2) = (4,5) = 43\\
(b_2, c_2) = (5,6) = 53\\
(b_2, c_2) = (6,7) = 63\\
(b_2, c_2) = (9,0) = 63\\
(b_2, c_2) = (7,8) = 73\\
(b_2, c_2) = (8,9) = 83\\
\end{aligned}
\end{equation}
$$

then, we assume the first case as $(b_2, c_2) = (0,1)$

then, we have,

$$
c_4\times b_1 + b_2\times c_3 + b_3\times c_2 + b_4\times c1 + c = [z:5]
$$

on substituting known values, we have,

$$
7\times b_1 + 0 + 0 + 3\times c_1 + c = [z:5]
$$

which becomes:

$$
7\times b_1 + 3\times c_1 = [z:5]
$$

which has the bounds of $0 \le [z:5] \le 90$, which has the values, $5,15,25,35,45,55,65,75,85$

thus we have:

$$
\begin{equation}
\begin{aligned}

(b_1, c_1) = (0,5) = 15\\
(b_1, c_1) = (1,6) = 25\\
(b_1, c_1) = (2,7) = 35\\
(b_1, c_1) = (3,8) = 45\\
(b_1, c_1) = (4,9) = 55\\
(b_1, c_1) = (8,3) = 65\\
(b_1, c_1) = (9,4) = 75\\
\end{aligned}
\end{equation}
$$
Now, since we are looking for $a_1$ which is $5$, none of these combinations are valid as they all have an extra digit. Thus we need to try again. 

#### Trial #3

We try the next combination for $(b_3, c_3)$ which is $(1,1)$ 

Now we have:
$$
\begin{aligned}
(b_4,c_4) = (3,7)\\
(b_3,c_3) = (1,1)
\end{aligned}
$$

Continuing forward, we have:

$$
b_2c_4+b_3c_3+b_4c_2+c = [x:3]
$$
which on substituting known values, we have:

$$
7b_2+1+3c_2 = [x:3]
$$
simplifying: 

$$
7b_2+3c_2 = [x':2]
$$

then, we have: 
$0\le[x':2]\le 90$ 

thus, we have the following pairs for $(b_2,c_2)$