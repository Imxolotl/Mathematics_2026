# Problem 10: Detecting Dependence

## Question

Without carrying out a full determinant calculation, explain why

$$
\det
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 5
\end{pmatrix}=0.
$$

Identify a specific dependence between the rows and connect it with noninvertibility of the matrix.

---

## Solution

### 1. Identifying the Linear Dependence Between Rows

Let matrix $A$ be:

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 5
\end{pmatrix}
$$

Let the rows of $A$ be denoted by:

$$
r_1 = (1, 2, 3), \qquad r_2 = (2, 4, 6), \qquad r_3 = (0, 1, 5)
$$

Comparing row 1 and row 2 entry-by-entry:

$$
r_2 = (2, 4, 6) = 2 \cdot (1, 2, 3) = 2 r_1
$$

Row 2 is an exact scalar multiple of row 1. This relationship can be expressed as a linear combination equal to the zero vector:

$$
2 r_1 - r_2 + 0 r_3 = (0, 0, 0)
$$

Because there exist scalar coefficients $(c_1, c_2, c_3) = (2, -1, 0)$, not all of which are zero, satisfying:

$$
c_1 r_1 + c_2 r_2 + c_3 r_3 = 0
$$

the set of rows $\{r_1, r_2, r_3\}$ is **linearly dependent**.

---

### 2. Why Linear Dependence Implies $\det A = 0$ Without Full Expansion

Two fundamental properties of determinants immediately establish that $\det A = 0$ without expanding the determinant:

#### Method A: Row Operation Invariance

Applying the elementary row operation:

$$
R_2 \leftarrow R_2 - 2 R_1
$$

Subtracting a scalar multiple of one row from another does not alter the determinant:

$$
\det A = \det
\begin{pmatrix}
1 & 2 & 3 \\
2 - 2(1) & 4 - 2(2) & 6 - 2(3) \\
0 & 1 & 5
\end{pmatrix}
= \det
\begin{pmatrix}
1 & 2 & 3 \\
0 & 0 & 0 \\
0 & 1 & 5
\end{pmatrix}
$$

Expanding the determinant along the second row (which consists entirely of zeros):

$$
\det A = 0 \cdot C_{21} + 0 \cdot C_{22} + 0 \cdot C_{23} = 0
$$

Any square matrix containing a row of all zeros has determinant zero.

#### Method B: Multilinearity and Identical Rows

Factoring the scalar $2$ out of the second row using the linearity of the determinant with respect to row 2:

$$
\det A = 2 \cdot \det
\begin{pmatrix}
1 & 2 & 3 \\
1 & 2 & 3 \\
0 & 1 & 5
\end{pmatrix}
$$

A matrix with two identical rows has determinant zero: swapping the two identical rows reverses the sign of the determinant ($\det = -\det \implies 2\det = 0 \implies \det = 0$). Therefore:

$$
\det A = 2 \cdot 0 = 0
$$

---

### 3. Connection with Non-Invertibility of the Matrix

The condition $\det A = 0$ and the linear dependence of rows connect directly to non-invertibility through several equivalent properties of the Invertible Matrix Theorem:

1. **Rank Deficiency:**
   The row rank of a matrix is the dimension of the subspace spanned by its rows. Since row 2 is redundant ($r_2 = 2r_1$), the row space is spanned by only two vectors:

$$
\mathrm{row}(A) = \mathrm{span}\{r_1, r_3\}
$$

   Consequently:

$$
\mathrm{rank}(A) \le 2 < 3
$$

   An $n \times n$ matrix is invertible if and only if it has full rank ($\mathrm{rank}(A) = n = 3$). Because $\mathrm{rank}(A) < 3$, matrix $A$ is **singular** (not invertible).

2. **Non-Trivial Kernel (Failure of Injectivity):**
   By the Rank-Nullity Theorem:

$$
\dim(\ker A) = 3 - \mathrm{rank}(A) \ge 3 - 2 = 1
$$

   There exists at least one non-zero vector $v \neq 0$ such that $Av = 0$. This means the linear transformation $T(x) = Ax$ maps non-zero inputs to zero, so $T$ is not one-to-one (not injective). An injective mapping is required for an inverse to exist.

3. **Dimensional Collapse of the Image (Failure of Surjectivity):**
   The column space $\mathrm{col}(A)$ has dimension $\mathrm{rank}(A) \le 2$. The transformation $x \mapsto Ax$ compresses the three-dimensional space $\mathbb{R}^3$ into a two-dimensional plane. A mapping that collapses dimension cannot cover the entire codomain $\mathbb{R}^3$, so it is not onto (not surjective).

Because the linear map is neither injective nor surjective, no inverse mapping $A^{-1}$ can exist.

---

## Verification and Consistency Checks

1. **Full Determinant Calculation via Sarrus' Rule:**
   Directly evaluating the determinant of matrix $A$:

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 5
\end{pmatrix}
$$

   - Downward diagonal products:
     - $(1)(4)(5) = 20$
     - $(2)(6)(0) = 0$
     - $(3)(2)(1) = 6$
     - Sum: $S_1 = 20 + 0 + 6 = 26$

   - Upward diagonal products:
     - $(0)(4)(3) = 0$
     - $(1)(6)(1) = 6$
     - $(5)(2)(2) = 20$
     - Sum: $S_2 = 0 + 6 + 20 = 26$

   Subtracting the upward sum from the downward sum:

$$
\det A = S_1 - S_2 = 26 - 26 = 0
$$

   This confirms the theoretical conclusion that $\det A = 0$.

2. **Explicit Non-Zero Vector in the Kernel:**
   To verify that $\ker A \neq \{0\}$, find a non-zero solution to $Av = 0$:

$$
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 5
\end{pmatrix}
\begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}
= \begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$

   Row 3 requires:

$$
x_2 + 5x_3 = 0 \implies x_2 = -5x_3
$$

   Substituting $x_2 = -5x_3$ into Row 1:

$$
x_1 + 2(-5x_3) + 3x_3 = 0 \implies x_1 - 7x_3 = 0 \implies x_1 = 7x_3
$$

   Choosing $x_3 = 1$ yields the non-zero vector $v = (7, -5, 1)^T$.
   Computing the product $Av$:

$$
Av =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 5
\end{pmatrix}
\begin{pmatrix}
7 \\
-5 \\
1
\end{pmatrix}
$$

$$
Av =
\begin{pmatrix}
1(7) + 2(-5) + 3(1) \\
2(7) + 4(-5) + 6(1) \\
0(7) + 1(-5) + 5(1)
\end{pmatrix}
= \begin{pmatrix}
7 - 10 + 3 \\
14 - 20 + 6 \\
0 - 5 + 5
\end{pmatrix}
= \begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$

   Because $A v = 0$ for $v \neq 0$, the matrix has a non-trivial null space, verifying non-invertibility.

---

## Why This Exercise Matters

- **Recognizing Redundancy by Inspection:** Developing the ability to spot proportional rows or columns avoids tedious arithmetic in linear algebra examinations and engineering calculations.
- **The Core of the Invertible Matrix Theorem:** Linear dependence of rows, linear dependence of columns, zero determinant, rank deficiency, and non-trivial null space are all equivalent statements of matrix singularity.
- **Ill-Conditioned Systems in Numerical Analysis:** In numerical computation, when rows are nearly proportional, the determinant is close to zero, leading to severe numerical instability and rounding errors when solving linear systems.
