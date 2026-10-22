# Problem 1: Determinant of a 2x2 Matrix

## Question

Compute

$$
\det
\begin{pmatrix}
3 & -2 \\
5 & 4 \\
\end{pmatrix},\qquad \det
\begin{pmatrix}
1 & 7 \\
2 & 14 \\
\end{pmatrix}.
$$

Which matrix is invertible? Justify your answer.

---

## Solution

### 1. Formula for the Determinant of a 2x2 Matrix

For a general $2 \times 2$ matrix

$$
M =
\begin{pmatrix}
a & b \\
c & d \\
\end{pmatrix}
$$

the determinant is defined as the difference between the product of the main diagonal entries and the product of the anti-diagonal entries:

$$
\det M = ad - bc
$$

A square matrix $M$ is invertible (non-singular) if and only if its determinant is non-zero:

$$
\det M \neq 0
$$

If $\det M = 0$, the matrix is singular and has no inverse.

---

### 2. Computation for the First Matrix

Let

$$
A =
\begin{pmatrix}
3 & -2 \\
5 & 4 \\
\end{pmatrix}
$$

The entries are:
- $a_{11} = 3$
- $a_{12} = -2$
- $a_{21} = 5$
- $a_{22} = 4$

Applying the determinant formula:

$$
\begin{aligned}
\det A &= (3)(4) - (-2)(5) \\
       &= 12 - (-10) \\
       &= 12 + 10 \\
       &= 22
\end{aligned}
$$

---

### 3. Computation for the Second Matrix

Let

$$
B =
\begin{pmatrix}
1 & 7 \\
2 & 14 \\
\end{pmatrix}
$$

The entries are:
- $b_{11} = 1$
- $b_{12} = 7$
- $b_{21} = 2$
- $b_{22} = 14$

Applying the determinant formula:

$$
\begin{aligned}
\det B &= (1)(14) - (7)(2) \\
       &= 14 - 14 \\
       &= 0
\end{aligned}
$$

---

### 4. Invertibility Analysis and Justification

1. **Matrix $A$:**
   Since $\det A = 22 \neq 0$, matrix $A$ is **invertible**. Its inverse exists and is explicitly given by:

$$
A^{-1} = \frac{1}{\det A}
\begin{pmatrix}
4 & 2 \\
-5 & 3 \\
\end{pmatrix}
= \frac{1}{22}
\begin{pmatrix}
4 & 2 \\
-5 & 3 \\
\end{pmatrix}
$$

2. **Matrix $B$:**
   Since $\det B = 0$, matrix $B$ is **not invertible** (singular).

**Geometric and Algebraic Justification for Matrix $B$:**
- Examining the rows of $B$:
  - Row 1: $r_1 = (1, 7)$
  - Row 2: $r_2 = (2, 14) = 2 \cdot (1, 7) = 2 r_1$
- The second row is an exact scalar multiple of the first row. The rows (and columns) are linearly dependent.
- A square matrix with linearly dependent rows has rank strictly less than its dimension ($\mathrm{rank}(B) = 1 < 2$), which guarantees $\det B = 0$ and non-invertibility.

---

## Verification and Consistency Checks

1. **Explicit Inverse Multiplication for $A$:**
   Multiplying $A$ by $A^{-1}$:

$$
\begin{aligned}
A A^{-1} &=
\begin{pmatrix}
3 & -2 \\
5 & 4 \\
\end{pmatrix}
\left[ \frac{1}{22}
\begin{pmatrix}
4 & 2 \\
-5 & 3 \\
\end{pmatrix}
\right] \\
&= \frac{1}{22}
\begin{pmatrix}
(3)(4) + (-2)(-5) & (3)(2) + (-2)(3) \\
(5)(4) + (4)(-5) & (5)(2) + (4)(3) \\
\end{pmatrix} \\
&= \frac{1}{22}
\begin{pmatrix}
12 + 10 & 6 - 6 \\
20 - 20 & 10 + 12 \\
\end{pmatrix} \\
&= \frac{1}{22}
\begin{pmatrix}
22 & 0 \\
0 & 22 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix} \\
&= I_2
\end{aligned}
$$

   This confirms both $\det A = 22$ and the invertibility of $A$.

2. **Kernel (Null Space) Check for $B$:**
   If $B$ is singular, there must exist a non-zero vector $v$ such that $B v = 0$:

$$
\begin{aligned}
\begin{pmatrix}
1 & 7 \\
2 & 14 \\
\end{pmatrix}
\begin{pmatrix}
-7 \\
1 \\
\end{pmatrix}
&=
\begin{pmatrix}
1(-7) + 7(1) \\
2(-7) + 14(1) \\
\end{pmatrix} \\
&=
\begin{pmatrix}
0 \\
0 \\
\end{pmatrix}
\end{aligned}
$$

   Because the kernel is non-trivial ($\ker B \neq \{0\}$), $B$ cannot be injective or invertible, confirming $\det B = 0$.

---

## Why This Exercise Matters

- **Foundational Formula:** The formula $\det = ad - bc$ is the building block for all higher-order determinant evaluations (via minors and cofactors).
- **Invertibility Criterion:** The condition $\det M \neq 0$ serves as the primary algebraic test for whether a linear system $M x = b$ has a unique solution.
- **Linear Dependence Detection:** A determinant of zero detects proportional rows or columns immediately without requiring full Gaussian elimination.
