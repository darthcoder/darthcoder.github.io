---
title: "Linear Algebra"
source: "https://www.deeplearningbook.org/contents/linear_algebra.html"
author:
  - "Ian Goodfellow et al."
published:
created: 2026-04-14
description: "Chapter 2 of DL book"
tags:
  - "clippings"
  - "dl"
  - "goodfellow"
---
Chapter 2

Linear Algebra

Linear algebra is a branch of mathematics that is widely used throughout science

and engineering. Yet because linear algebra is a form of continuous rather than

discrete mathematics, many computer scientists have little experience with it. A

good understanding of linear algebra is essential for understanding and working

with many machine learning algorithms, especially deep learning algorithms. We

therefore precede our introduction to deep learning with a focused presentation of

the key linear algebra prerequisites.

If you are already familiar with linear algebra, feel free to skip this chapter. If

you have previous experience with these concepts but need a detailed reference

sheet to review key formulas, we recommend The Matrix Cookbook (Petersen and

Pedersen, 2006). If you have had no exposure at all to linear algebra, this chapter

will teach you enough to read this book, but we highly recommend that you also

consult another resource focused exclusively on teaching linear algebra, such as

Shilov (1977). This chapter completely omits many important linear algebra topics

that are not essential for understanding deep learning.

2.1 Scalars, Vectors, Matrices, and Tensors

The study of linear algebra involves several types of mathematical objects:

• Scalars

: A scalar is just a single number, in contrast to most of the other

objects studied in linear algebra, which are usually arrays of multiple numbers.

We write scalars in italics. We usually give scalars lowercase variable names.

When we introduce them, we specify what kind of number they are. For

29

CHAPTER 2. LINEAR ALGEBRA

example, we might say “Let

s ∈ R

be the slope of the line,” while deﬁning a

real-valued scalar, or “Let

n ∈ N

be the number of units,” while deﬁning a

natural number scalar.

• Vectors

: A vector is an array of numbers. The numbers are arranged in

order. We can identify each individual number by its index in that ordering.

Typically we give vectors lowercase names in bold typeface, such as

x

. The

elements of the vector are identiﬁed by writing its name in italic typeface,

with a subscript. The ﬁrst element of

x

is

x

1

, the second element is

x

2

, and

so on. We also need to say what kind of numbers are stored in the vector. If

each element is in

R

, and the vector has

n

elements, then the vector lies in

the set formed by taking the Cartesian product of

R n

times, denoted as

R

n

.

When we need to explicitly identify the elements of a vector, we write them

as a column enclosed in square brackets:

x =











x

1

x

2

.

.

.

x

n











. (2.1)

We can think of vectors as identifying points in space, with each element

giving the coordinate along a diﬀerent axis.

Sometimes we need to index a set of elements of a vector. In this case, we

deﬁne a set containing the indices and write the set as a subscript. For

example, to access

x

1

,

x

3

and

x

6

, we deﬁne the set

S

\=

{

1

,

3

,

6

}

and write

x

S

. We use the

−

sign to index the complement of a set. For example

x

−1

is

the vector containing all elements of

x

except for

x

1

, and

x

−S

is the vector

containing all elements of x except for x

1

, x

3

and x

6

.

• Matrices

: A matrix is a 2-D array of numbers, so each element is identiﬁed

by two indices instead of just one. We usually give matrices uppercase

variable names with bold typeface, such as

A

. If a real-valued matrix

A

has

a height of

m

and a width of

n

, then we say that

A ∈ R

m×n

. We usually

identify the elements of a matrix using its name in italic but not bold font,

and the indices are listed with separating commas. For example,

A

1,1

is the

upper left entry of

A

and

A

m,n

is the bottom right entry. We can identify

all the numbers with vertical coordinate

i

by writing a “:” for the horizontal

coordinate. For example,

A

i,:

denotes the horizontal cross section of

A

with

vertical coordinate

i

. This is known as the

i

\-th

row

of

A

. Likewise,

A

:,i

is

30

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAwEAAAQbCAIAAABflzAxAAAACXBIWXMAABYlAAAWJQFJUiTwAAAaA0lEQVR42u3dX4hU5cPA8Sffkd/FeiHUbBMo7YZdVOwxEJJ0QYJRcA0sEGFGESK8qMy92AvJi113gyJiEW1zL8QuRGdvFBPaFdeNEnYNCS+aiYxa3AmDVofyZicKD/i7GN5FrHx903X+fT5Xs7OjM3POEb4+53nOCXNzcwEAoMk8cuvWLVsBAGg2i2wCAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBABoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAANZBMAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBABoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAGggmwAA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCADQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAQAPZBACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCADQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAGsgmAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCADQQDYBAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAIAGsgkAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIANBAAgAYCANBAAAAaCABAAwEAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgDQQAAAGggAQAMBAGggAAANBACggQAANBAAgAYCADSQTQAAaCAAAA0EAKCBAAA0EACABgIA0EAAABoIAEADAQBoIAAADQQAoIEAADQQAIAGAgC4LwmbgEYVx/HPP/8cQrhw4UII4bfffvvxxx9Xr149/4KlS5c+++yzy5YtSyT8QwDQQFDnisXiZ599dvr06YmJiXv8I6lU6qWXXlqzZs26deue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)

CHAPTER 2. LINEAR ALGEBRA

the i-th column of A. When we need to explicitly identify the elements of

a matrix, we write them as an array enclosed in square brackets:



A

1,1

A

1,2

A

2,1

A

2,2



. (2.2)

Sometimes we may need to index matrix-valued expressions that are not just

a single letter. In this case, we use subscripts after the expression but do not

convert anything to lowercase. For example,

f

(

A

)

i,j

gives element (

i, j

) of

the matrix computed by applying the function f to A.

• Tensors

: In some cases we will need an array with more than two axes.

In the general case, an array of numbers arranged on a regular grid with a

variable number of axes is known as a tensor. We denote a tensor named “A”

with this typeface:

A

. We identify the element of

A

at coordinates (

i, j, k

)

by writing A

i,j,k

.

One important operation on matrices is the

transpose

. The transpose of a

matrix is the mirror image of the matrix across a diagonal line, called the

main

diagonal

, running down and to the right, starting from its upper left corner. See

ﬁgure 2.1 for a graphical depiction of this operation. We denote the transpose of a

matrix A as A



, and it is deﬁned such that

(A



)

i,j

\= A

j,i

. (2.3)

Vectors can be thought of as matrices that contain only one column. The

transpose of a vector is therefore a matrix with only one row. Sometimes we

A =





A

1,1

A

1,2

A

2,1

A

2,2

A

3,1

A

3,2





⇒ A



\=



A

1,1

A

2,1

A

3,1

A

1,2

A

2,2

A

3,2



Figure 2.1: The transpose of the matrix can be thought of as a mirror image across the

main diagonal.

31