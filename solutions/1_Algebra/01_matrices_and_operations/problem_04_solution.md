# Problem 4: Matrix Multiplication and Noncommutativity

## Question

Given the $2 \times 2$ matrices

$$
A =
\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix}, \qquad
B =
\begin{pmatrix}
2 & 0 \\
3 & 1
\end{pmatrix},
$$

compute $AB$ and $BA$. Is $AB = BA$? Use this example to explain what **noncommutativity** of matrix multiplication means.

---

## Key Rule — How to Multiply Two $2 \times 2$ Matrices

For two $2 \times 2$ matrices

$$
X =
\begin{pmatrix}
x_{11} & x_{12} \\
x_{21} & x_{22}
\end{pmatrix}, \qquad
Y =
\begin{pmatrix}
y_{11} & y_{12} \\
y_{21} & y_{22}
\end{pmatrix},
$$

the product $XY$ is computed by taking **dot products of rows of $X$ with columns of $Y$**:

$$
XY =
\begin{pmatrix}
x_{11}\,y_{11} + x_{12}\,y_{21} & x_{11}\,y_{12} + x_{12}\,y_{22} \\
x_{21}\,y_{11} + x_{22}\,y_{21} & x_{21}\,y_{12} + x_{22}\,y_{22}
\end{pmatrix}.
$$

In words: to find the entry in **row $i$, column $j$** of the product, take the $i$-th row of the left matrix and the $j$-th column of the right matrix, multiply their corresponding entries together, and add up the results.

---

## Step 1 — Compute $AB$

We compute each of the four entries of the $2 \times 2$ result.

### Entry (1, 1): row 1 of $A$ · column 1 of $B$

$$
\begin{pmatrix} 1 & 2 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 3 \end{pmatrix}
= 1 \cdot 2 + 2 \cdot 3 = 2 + 6 = 8.
$$

### Entry (1, 2): row 1 of $A$ · column 2 of $B$

$$
\begin{pmatrix} 1 & 2 \end{pmatrix}
\cdot
\begin{pmatrix} 0 \\ 1 \end{pmatrix}
= 1 \cdot 0 + 2 \cdot 1 = 0 + 2 = 2.
$$

### Entry (2, 1): row 2 of $A$ · column 1 of $B$

$$
\begin{pmatrix} 0 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 3 \end{pmatrix}
= 0 \cdot 2 + 1 \cdot 3 = 0 + 3 = 3.
$$

### Entry (2, 2): row 2 of $A$ · column 2 of $B$

$$
\begin{pmatrix} 0 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 0 \\ 1 \end{pmatrix}
= 0 \cdot 0 + 1 \cdot 1 = 0 + 1 = 1.
$$

### Result for $AB$

$$
AB =
\begin{pmatrix}
8 & 2 \\
3 & 1
\end{pmatrix}.
$$

---

## Step 2 — Compute $BA$

Now $B$ is on the left and $A$ is on the right. We repeat the same dot product process, taking rows of $B$ and columns of $A$.

### Entry (1, 1): row 1 of $B$ · column 1 of $A$

$$
\begin{pmatrix} 2 & 0 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 0 \end{pmatrix}
= 2 \cdot 1 + 0 \cdot 0 = 2 + 0 = 2.
$$

### Entry (1, 2): row 1 of $B$ · column 2 of $A$

$$
\begin{pmatrix} 2 & 0 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 1 \end{pmatrix}
= 2 \cdot 2 + 0 \cdot 1 = 4 + 0 = 4.
$$

### Entry (2, 1): row 2 of $B$ · column 1 of $A$

$$
\begin{pmatrix} 3 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 0 \end{pmatrix}
= 3 \cdot 1 + 1 \cdot 0 = 3 + 0 = 3.
$$

### Entry (2, 2): row 2 of $B$ · column 2 of $A$

$$
\begin{pmatrix} 3 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 1 \end{pmatrix}
= 3 \cdot 2 + 1 \cdot 1 = 6 + 1 = 7.
$$

### Result for $BA$

$$
BA =
\begin{pmatrix}
2 & 4 \\
3 & 7
\end{pmatrix}.
$$

---

## Step 3 — Compare $AB$ and $BA$

Placing the two results side by side:

$$
AB =
\begin{pmatrix}
8 & 2 \\
3 & 1
\end{pmatrix}, \qquad
BA =
\begin{pmatrix}
2 & 4 \\
3 & 7
\end{pmatrix}.
$$

| Position | $AB$ | $BA$ | Equal? |
|:--------:|:----:|:----:|:------:|
| (1, 1)   | 8    | 2    | ❌     |
| (1, 2)   | 2    | 4    | ❌     |
| (2, 1)   | 3    | 3    | ✅     |
| (2, 2)   | 1    | 7    | ❌     |

Three out of four entries are different. Therefore:

$$
AB \neq BA
$$

---

## What Does "Noncommutativity" Mean?

### The idea in one sentence

**Noncommutativity** means that the order in which matrices are multiplied matters: in general, $AB \neq BA$.

### The transformation perspective: order of operations on column vectors

When matrices act on a column vector $x$, matrix multiplication is associative and evaluated from right to left:

$$
(AB)x = A(Bx)
$$

- In the product $AB$, the matrix $B$ acts on $x$ **first**, and the matrix $A$ acts on the resulting vector $Bx$ **second**.
- In the product $BA$, the matrix $A$ acts on $x$ **first**, and the matrix $B$ acts on the resulting vector $Ax$ **second**:

$$
(BA)x = B(Ax)
$$

Because successive geometric transformations generally depend on their execution order, applying $B$ first and then $A$ yields a completely different vector from applying $A$ first and then $B$. Consequently, $AB \neq BA$.

### Contrast with ordinary numbers

With ordinary numbers, multiplication is **commutative** — the order does not matter:

$$
3 \times 5 = 5 \times 3 = 15.
$$

This is a property familiar from scalar arithmetic. But with matrices, this property **fails**. As shown above, $AB$ and $BA$ are both well-defined $2 \times 2$ matrices, yet they contain different entries.

### Why does it fail algebraically?

The entry in row $i$, column $j$ of $AB$ is the dot product of **row $i$ of $A$** with **column $j$ of $B$**. When we compute $BA$ instead, the same position uses **row $i$ of $B$** with **column $j$ of $A$** — completely different numbers go into the calculation.

Swapping the order swaps which matrix supplies the rows and which supplies the columns. Since rows and columns of $A$ and $B$ generally contain different numbers, the dot products come out differently.

### What to remember

1. **Never assume $AB = BA$** when working with matrices. Always respect the multiplication order.
2. In Problem 3 we saw an even stronger phenomenon: sometimes one order is defined but the reversed order is not even possible due to incompatible dimensions. Here both orders exist and have identical size ($2 \times 2$), yet they still differ — this is noncommutativity in its purest form.
3. There are special cases where $AB = BA$ does hold (for example, when one matrix is the identity matrix $I$, when one is a scalar multiple of $I$, or when two diagonalizable matrices share the same eigenvectors). But these are exceptions, not the general rule.

---

## Verification

A helpful check is that both products must have the same **trace** (the sum of main diagonal entries), because the trace identity $\mathrm{tr}(AB) = \mathrm{tr}(BA)$ holds for any two square matrices:

$$
\mathrm{tr}(AB) = 8 + 1 = 9, \qquad
\mathrm{tr}(BA) = 2 + 7 = 9.
$$

The traces match ($9 = 9$), confirming that our arithmetic is consistent even though the individual matrices $AB$ and $BA$ are unequal.

---

## Why This Exercise Matters

- **Core difference from number arithmetic:** Noncommutativity is the fundamental algebraic boundary separating matrix algebra from scalar algebra: **order matters**.
- **Practical consequence:** In applications (computer graphics, robotics, physics), when transformations act on column vectors, the product $AB$ corresponds to applying transformation $B$ first and transformation $A$ second. Applying $B$ then $A$ is **not** the same as applying $A$ then $B$ ($BA$). For instance, translating an object and then rotating it gives a different final position from rotating it first and then translating it.
- **Foundation for deeper topics:** Understanding noncommutativity prepares you for matrix Lie groups, quantum mechanics (where the commutator $[A, B] = AB - BA \neq 0$ implies the Heisenberg uncertainty principle), and modern linear algebra.
