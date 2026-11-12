# Problem 1: Definition of the Inverse

## Question

For

$$
A=
\begin{pmatrix}
2 & 1 \\
1 & 1
\end{pmatrix},\qquad B=
\begin{pmatrix}
1 & -1 \\
-1 & 2
\end{pmatrix}
$$

check, without using a formula, whether $B=A^{-1}$. Compute $AB$ and $BA$ and relate the result to the definition of the inverse.

---

## Solution

### 1. Definition of the Inverse Matrix

Let $A$ be an $n \times n$ square matrix. An $n \times n$ matrix $B$ is called the **inverse** of $A$, denoted $A^{-1}$, if it satisfies:

$$
AB = I_n \qquad \mathrm{and} \qquad BA = I_n
$$

where $I_n$ is the $n \times n$ identity matrix. For $n = 2$:

$$
I_2 =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$

To determine whether $B = A^{-1}$ without appealing to any determinant or cofactor formula, we directly calculate both products $AB$ and $BA$.

---

### 2. Computation of $AB$

We multiply $A$ on the left and $B$ on the right:

$$
AB =
\begin{pmatrix}
2 & 1 \\
1 & 1
\end{pmatrix}
\begin{pmatrix}
1 & -1 \\
-1 & 2
\end{pmatrix}
$$

Computing each entry by taking the dot product of rows of $A$ with columns of $B$:
- Entry (1, 1): $(2)(1) + (1)(-1) = 2 - 1 = 1$
- Entry (1, 2): $(2)(-1) + (1)(2) = -2 + 2 = 0$
- Entry (2, 1): $(1)(1) + (1)(-1) = 1 - 1 = 0$
- Entry (2, 2): $(1)(-1) + (1)(2) = -1 + 2 = 1$

Combining the entries:

$$
AB =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
= I_2
$$

---

### 3. Computation of $BA$

Now we multiply $B$ on the left and $A$ on the right:

$$
BA =
\begin{pmatrix}
1 & -1 \\
-1 & 2
\end{pmatrix}
\begin{pmatrix}
2 & 1 \\
1 & 1
\end{pmatrix}
$$

Computing each entry by taking the dot product of rows of $B$ with columns of $A$:
- Entry (1, 1): $(1)(2) + (-1)(1) = 2 - 1 = 1$
- Entry (1, 2): $(1)(1) + (-1)(1) = 1 - 1 = 0$
- Entry (2, 1): $(-1)(2) + (2)(1) = -2 + 2 = 0$
- Entry (2, 2): $(-1)(1) + (2)(1) = -1 + 2 = 1$

Combining the entries:

$$
BA =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
= I_2
$$

---

### 4. Relating the Result to the Definition of the Inverse

Both matrix products yield the $2 \times 2$ identity matrix:

$$
AB = I_2 \qquad \mathrm{and} \qquad BA = I_2
$$

By the formal definition of the matrix inverse, these two equalities prove that:

$$
B = A^{-1} \qquad \mathrm{and} \qquad A = B^{-1}
$$

Matrix multiplication is generally non-commutative ($XY \neq YX$). However, for square matrices of the same dimension, if a matrix $B$ satisfies $AB = I$, then necessarily $BA = I$ as well. Evaluating both products confirms that $B$ is both a right inverse and a left inverse of $A$.

---

## Verification and Consistency Checks

### Check 1: Using the 2x2 Inverse Formula

For a general $2 \times 2$ matrix

$$
M =
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$

with $\det M = ad - bc \neq 0$:

$$
M^{-1} = \frac{1}{ad - bc}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}
$$

For matrix $A$:
- $a = 2$, $b = 1$, $c = 1$, $d = 1$
- $\det A = (2)(1) - (1)(1) = 2 - 1 = 1 \neq 0$

Applying the formula:

$$
A^{-1} = \frac{1}{1}
\begin{pmatrix}
1 & -1 \\
-1 & 2
\end{pmatrix}
= \begin{pmatrix}
1 & -1 \\
-1 & 2
\end{pmatrix}
= B
$$

This formula-based calculation confirms that $B = A^{-1}$.

### Check 2: Action on an Arbitrary Vector

Let vector $v$ be given by:

$$
v =
\begin{pmatrix}
x \\
y
\end{pmatrix}
$$

Applying transformation $A$:

$$
Av =
\begin{pmatrix}
2 & 1 \\
1 & 1
\end{pmatrix}
\begin{pmatrix}
x \\
y
\end{pmatrix}
= \begin{pmatrix}
2x + y \\
x + y
\end{pmatrix}
$$

Now apply $B$ to the resulting vector:

$$
B(Av) =
\begin{pmatrix}
1 & -1 \\
-1 & 2
\end{pmatrix}
\begin{pmatrix}
2x + y \\
x + y
\end{pmatrix}
$$

Performing the multiplication:

$$
B(Av) =
\begin{pmatrix}
1(2x + y) - 1(x + y) \\
-1(2x + y) + 2(x + y)
\end{pmatrix}
= \begin{pmatrix}
x \\
y
\end{pmatrix}
= v
$$

Transformation $B$ restores any vector $v$ transformed by $A$.

---

## Why This Exercise Matters

- **Definition Before Computation:** Grounding matrix inversion in the algebraic property $AB = BA = I$ prevents students from viewing the inverse as merely a formula to memorize.
- **Two-Sided Invertibility:** Demonstrates that the inverse must undo multiplication from both sides, an essential concept when solving matrix equations such as $AX = C$ versus $XA = C$.
- **Foundation for Linear Systems:** If $Ax = b$, multiplying both sides on the left by $A^{-1}$ immediately gives $x = A^{-1}b$, providing the algebraic cornerstone for solving square non-singular systems.
