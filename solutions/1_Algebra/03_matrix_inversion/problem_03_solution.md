# Problem 3: When Does the Inverse Not Exist?

## Question

For

$$
A=
\begin{pmatrix}
2 & 4 \\
1 & 2
\end{pmatrix}
$$

explain in two ways why $A^{-1}$ does not exist: using the determinant and using dependence between the rows.

---

## Solution

### 1. Explanation 1: Using the Determinant

A square matrix $A$ is invertible if and only if its determinant is non-zero:

$$
\det A \neq 0
$$

Conversely, if $\det A = 0$, the matrix is singular and has no inverse.

For the given $2 \times 2$ matrix

$$
A=
\begin{pmatrix}
2 & 4 \\
1 & 2
\end{pmatrix}
$$

we evaluate the determinant using the formula $\det A = ad - bc$:

$$
\begin{aligned}
\det A &= (2)(2) - (4)(1) \\
       &= 4 - 4 \\
       &= 0
\end{aligned}
$$

#### Connection to the Explicit Inverse Formula

The algebraic formula for the inverse of a $2 \times 2$ matrix requires division by $\det A$:

$$
A^{-1} = \frac{1}{\det A}
\begin{pmatrix}
2 & -4 \\
-1 & 2
\end{pmatrix}
= \frac{1}{0}
\begin{pmatrix}
2 & -4 \\
-1 & 2
\end{pmatrix}
$$

Because division by zero is mathematically undefined, no matrix $A^{-1}$ can be constructed. Thus, $A^{-1}$ does not exist.

---

### 2. Explanation 2: Using Dependence Between the Rows

Let the rows of $A$ be denoted by row vectors $r_1$ and $r_2$:

$$
r_1 = (2, 4), \qquad r_2 = (1, 2)
$$

#### Identifying the Linear Dependence

Comparing the two rows entry-by-entry:

$$
r_1 = (2, 4) = 2 \cdot (1, 2) = 2 r_2
$$

Equivalently, row 2 is a scalar multiple of row 1:

$$
r_2 = \frac{1}{2} r_1
$$

This relationship can be expressed as a non-trivial linear combination equal to the zero vector:

$$
r_1 - 2 r_2 = (0, 0)
$$

Because there exist scalar coefficients $(c_1, c_2) = (1, -2) \neq (0, 0)$ such that $c_1 r_1 + c_2 r_2 = 0$, the set of rows $\{r_1, r_2\}$ is **linearly dependent**.

#### Why Row Dependence Precludes an Inverse

Linear dependence of the rows impacts the matrix in three equivalent ways:

- **Rank Deficiency:**
  The row rank of $A$ is the dimension of the subspace spanned by its rows. Since $r_1$ is a scalar multiple of $r_2$:

$$
\mathrm{row}(A) = \mathrm{span}\{r_1, r_2\} = \mathrm{span}\{(1, 2)\}
$$

  The row space is a 1-dimensional line in $\mathbb{R}^2$. Therefore:

$$
\mathrm{rank}(A) = 1 < 2
$$

  An $n \times n$ matrix is invertible if and only if it has full rank ($\mathrm{rank}(A) = n = 2$). Since $\mathrm{rank}(A) = 1$, the matrix is rank-deficient and singular.

- **Dimensional Collapse (Loss of Injectivity):**
  By the Rank-Nullity Theorem:

$$
\dim(\ker A) = 2 - \mathrm{rank}(A) = 2 - 1 = 1
$$

  The kernel (null space) contains non-zero vectors. The linear mapping $T(x) = Ax$ collapses an entire line onto the origin $(0, 0)$. A mapping that sends non-zero vectors to zero cannot be one-to-one (injective), which makes a two-sided inverse impossible.

- **Loss of Surjectivity:**
  The image (column space) of $A$ is also 1-dimensional (the line spanned by $(2, 1)^T$). The transformation cannot map onto all of $\mathbb{R}^2$, meaning it is not surjective. Hence, it has no inverse mapping.

---

## Verification and Consistency Checks

### Check 1: Explicit Non-Zero Vector in the Kernel

To verify that $A$ is not injective, we find a non-zero vector $v$ such that $Av = 0$:

$$
v =
\begin{pmatrix}
x \\
y
\end{pmatrix}
$$

$$
\begin{pmatrix}
2 & 4 \\
1 & 2
\end{pmatrix}
\begin{pmatrix}
x \\
y
\end{pmatrix}
= \begin{pmatrix}
2x + 4y \\
x + 2y
\end{pmatrix}
= \begin{pmatrix}
0 \\
0
\end{pmatrix}
$$

Both equations reduce to $x + 2y = 0$, or $x = -2y$. Choosing $y = 1$ gives the non-zero vector:

$$
v =
\begin{pmatrix}
-2 \\
1
\end{pmatrix}
\neq 0
$$

Testing $Av$:

$$
\begin{pmatrix}
2 & 4 \\
1 & 2
\end{pmatrix}
\begin{pmatrix}
-2 \\
1
\end{pmatrix}
= \begin{pmatrix}
2(-2) + 4(1) \\
1(-2) + 2(1)
\end{pmatrix}
= \begin{pmatrix}
0 \\
0
\end{pmatrix}
$$

If an inverse $A^{-1}$ existed, multiplying both sides by $A^{-1}$ would yield:

$$
v = A^{-1}(Av) = A^{-1}(0) = 0
$$

which contradicts $v \neq 0$. This contradiction confirms that $A^{-1}$ cannot exist.

### Check 2: Gauss-Jordan Elimination

Forming the augmented matrix $[A \mid I_2]$:

$$
\begin{pmatrix}
2 & 4 & \mid & 1 & 0 \\
1 & 2 & \mid & 0 & 1
\end{pmatrix}
$$

Subtracting $\frac{1}{2} R_1$ from $R_2$ ($R_2 \leftarrow R_2 - \frac{1}{2} R_1$):

$$
\begin{pmatrix}
2 & 4 & \mid & 1 & 0 \\
0 & 0 & \mid & -\frac{1}{2} & 1
\end{pmatrix}
$$

The second row on the left side consists entirely of zeros. It is impossible to produce the identity matrix on the left, proving that the Gauss–Jordan inversion algorithm terminates with no solution.

---

## Why This Exercise Matters

- **Unifying Algebraic and Geometric Perspectives:** Shows that a zero determinant ($\det A = 0$) and geometric row redundancy ($r_1 = 2r_2$) are two ways of observing the exact same underlying mathematical failure: loss of full rank.
- **Invertible Matrix Theorem:** Illustrates the equivalence between singularity, determinant vanishing, linear dependence of rows/columns, non-trivial kernel, and failure of Gauss–Jordan reduction.
- **System Solvability:** In a linear system $Ax = b$ with this matrix $A$, solutions either do not exist or are not unique, because the rows do not provide independent constraints.
