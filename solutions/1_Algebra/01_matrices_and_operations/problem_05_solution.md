# Problem 5: Matrix Times Vector

## Question

Given the $2 \times 2$ matrix and the $2 \times 1$ vector

$$
A = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix}, \qquad
\mathbf{x} = \begin{pmatrix} 4 \\ 2 \end{pmatrix},
$$

compute $A\mathbf{x}$. Then express $A\mathbf{x}$ as a **linear combination of the columns of $A$**, with coefficients coming from the vector $\mathbf{x}$.

---

## Key Rule — How to Multiply a Matrix by a Vector

There are two ways to see the product $A\mathbf{x}$. Both give the same answer, but each teaches us something different.

### View 1: Row-by-row (dot products)

Take each **row** of $A$ and dot it with $\mathbf{x}$:

$$
A\mathbf{x} = \begin{pmatrix}
\mathrm{row\,1} \cdot \mathbf{x} \\
\mathrm{row\,2} \cdot \mathbf{x}
\end{pmatrix}.
$$

This is the entry-by-entry recipe we already used in Problem 4 for matrix–matrix products.

### View 2: Column-by-column (linear combination)

Write $A$ in terms of its **columns** $\mathbf{a}_1$ and $\mathbf{a}_2$, and let $\mathbf{x} = \begin{pmatrix} x_1 \\ x_2 \end{pmatrix}$. Then:

$$
A\mathbf{x} = x_1 \, \mathbf{a}_1 + x_2 \, \mathbf{a}_2.
$$

In words: **scale each column of $A$ by the matching entry of $\mathbf{x}$, then add the scaled columns together**. This is called a *linear combination* of the columns of $A$.

Both views are mathematically identical. We will compute $A\mathbf{x}$ with View 1 first, and then verify the same result with View 2.

---

## Step 1 — Compute $A\mathbf{x}$ (row-dot-column)

### Entry 1: row 1 of $A$ · $\mathbf{x}$

$$
\begin{pmatrix} 2 & -1 \end{pmatrix}
\cdot
\begin{pmatrix} 4 \\ 2 \end{pmatrix}
= 2 \cdot 4 + (-1) \cdot 2 = 8 - 2 = 6.
$$

### Entry 2: row 2 of $A$ · $\mathbf{x}$

$$
\begin{pmatrix} 1 & 3 \end{pmatrix}
\cdot
\begin{pmatrix} 4 \\ 2 \end{pmatrix}
= 1 \cdot 4 + 3 \cdot 2 = 4 + 6 = 10.
$$

### Result

$$
A\mathbf{x} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}.
$$

---

## Step 2 — Express $A\mathbf{x}$ as a Linear Combination of Columns

### Identify the columns of $A$

$$
\mathbf{a}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix} \quad (\text{first column}), \qquad
\mathbf{a}_2 = \begin{pmatrix} -1 \\ 3 \end{pmatrix} \quad (\text{second column}).
$$

### Identify the coefficients from $\mathbf{x}$

$$
x_1 = 4, \qquad x_2 = 2.
$$

The first entry of $\mathbf{x}$ multiplies the first column of $A$; the second entry multiplies the second column.

### Build the linear combination

$$
A\mathbf{x}
= x_1 \, \mathbf{a}_1 + x_2 \, \mathbf{a}_2
= 4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix}.
$$

### Scale each column

$$
4 \begin{pmatrix} 2 \\ 1 \end{pmatrix}
= \begin{pmatrix} 8 \\ 4 \end{pmatrix}, \qquad
2 \begin{pmatrix} -1 \\ 3 \end{pmatrix}
= \begin{pmatrix} -2 \\ 6 \end{pmatrix}.
$$

### Add the scaled columns

$$
\begin{pmatrix} 8 \\ 4 \end{pmatrix}
+
\begin{pmatrix} -2 \\ 6 \end{pmatrix}
= \begin{pmatrix} 8 + (-2) \\ 4 + 6 \end{pmatrix}
= \begin{pmatrix} 6 \\ 10 \end{pmatrix}. \quad ✅
$$

Same answer as Step 1.

---

## Step 3 — Why Are the Two Views the Same?

It is worth seeing *why* row-dot-column and column-combination always give the same vector. Write everything out for general $2 \times 2$:

$$
\begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix}
\begin{pmatrix} x_1 \\ x_2 \end{pmatrix}.
$$

**Row view** computes each entry separately:

$$
\text{entry } 1 = a_{11}\,x_1 + a_{12}\,x_2, \qquad
\text{entry } 2 = a_{21}\,x_1 + a_{22}\,x_2.
$$


The expressions are identical — the arithmetic is just **grouped differently**. The row view groups by *output entry*; the column view groups by *input coefficient*. Rearranging one gives the other, because addition is commutative and associative.

---

## Verification

A quick size and magnitude check:

- $A$ is $2 \times 2$ and $\mathbf{x}$ is $2 \times 1$, so $A\mathbf{x}$ is $2 \times 1$. ✅
- The entries of $A$ and $\mathbf{x}$ are small single-digit numbers, so a result of $\begin{pmatrix} 6 \\ 10 \end{pmatrix}$ is in the right ballpark. ✅
- Both methods (row-dot-column and column combination) produced the same vector. ✅

---

## Why This Exercise Matters

- **Two ways to read the same product.** The row-dot-column method is the standard entry-by-entry recipe. The column-combination method gives a deeper geometric picture: $A\mathbf{x}$ is a *blend* of the columns of $A$, with the entries of $\mathbf{x}$ controlling the mix.
- **Linear combinations are everywhere.** Nearly every major idea in linear algebra — span, independence, basis, rank — is built on the concept of linear combinations. This exercise is where that concept first appears in matrix language.
- **Foundation for later topics.** When we study systems of equations $A\mathbf{x} = \mathbf{b}$, we will ask: "Can $\mathbf{b}$ be written as a linear combination of the columns of $A$?" That is exactly the question this column viewpoint prepares you for.
- **Geometric intuition.** If you picture each column of $A$ as an arrow in the plane, then $A\mathbf{x}$ is what you get by stretching those arrows by the factors $x_1$ and $x_2$ and laying them tip-to-tail. The result is a new arrow — the output vector.

