# Problem 2: Formula for a 2x2 Matrix

## Question

Find the inverse of

$$
A=
\begin{pmatrix}
3 & 2 \\
5 & 4
\end{pmatrix}
$$

using the formula for a $2\times2$ matrix. At the end, check the result by computing one product with $A$.

---

## Solution

### 1. The 2x2 Matrix Inversion Formula

For a general $2 \times 2$ matrix

$$
M =
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$

the matrix is invertible if and only if its determinant is non-zero:

$$
\det M = ad - bc \neq 0
$$

When $\det M \neq 0$, the inverse is given explicitly by:

$$
M^{-1} = \frac{1}{\det M}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}
$$

The construction involves four steps:
- Compute the determinant $\det M = ad - bc$.
- Swap the main diagonal entries: $a \leftrightarrow d$.
- Negate the off-diagonal entries: $b \to -b$ and $c \to -c$.
- Multiply the resulting matrix by the scalar factor $\frac{1}{\det M}$.

---

### 2. Computing the Determinant of $A$

For matrix $A$:
- $a = 3$
- $b = 2$
- $c = 5$
- $d = 4$

The determinant is:

$$
\begin{aligned}
\det A &= ad - bc \\
       &= (3)(4) - (2)(5) \\
       &= 12 - 10 \\
       &= 2
\end{aligned}
$$

Since $\det A = 2 \neq 0$, matrix $A$ is invertible, and $A^{-1}$ exists.

---

### 3. Applying the Formula to Find $A^{-1}$

Swapping the diagonal entries and negating the off-diagonal entries gives the adjugate matrix:

$$
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}
= \begin{pmatrix}
4 & -2 \\
-5 & 3
\end{pmatrix}
$$

Multiplying by $\frac{1}{\det A} = \frac{1}{2}$:

$$
A^{-1} = \frac{1}{2}
\begin{pmatrix}
4 & -2 \\
-5 & 3
\end{pmatrix}
= \begin{pmatrix}
2 & -1 \\
-\frac{5}{2} & \frac{3}{2}
\end{pmatrix}
$$

Both scalar-factored and entrywise forms represent the exact inverse matrix.

---

### 4. Verification by Multiplication

We verify the result by computing the product $A A^{-1}$:

$$
A A^{-1} =
\begin{pmatrix}
3 & 2 \\
5 & 4
\end{pmatrix}
\left[ \frac{1}{2}
\begin{pmatrix}
4 & -2 \\
-5 & 3
\end{pmatrix}
\right]
$$

Pulling the scalar factor $\frac{1}{2}$ to the front:

$$
A A^{-1} = \frac{1}{2}
\left[
\begin{pmatrix}
3 & 2 \\
5 & 4
\end{pmatrix}
\begin{pmatrix}
4 & -2 \\
-5 & 3
\end{pmatrix}
\right]
$$

Computing each entry of the product:
- Entry (1, 1): $(3)(4) + (2)(-5) = 12 - 10 = 2$
- Entry (1, 2): $(3)(-2) + (2)(3) = -6 + 6 = 0$
- Entry (2, 1): $(5)(4) + (4)(-5) = 20 - 20 = 0$
- Entry (2, 2): $(5)(-2) + (4)(3) = -10 + 12 = 2$

Multiplying by $\frac{1}{2}$:

$$
A A^{-1} = \frac{1}{2}
\begin{pmatrix}
2 & 0 \\
0 & 2
\end{pmatrix}
= \begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
= I_2
$$

The product equals the identity matrix, confirming that our calculated inverse is correct.

---

## Verification and Consistency Checks

### Check 1: Left-Multiplication ($A^{-1} A$)

Computing the product in reverse order:

$$
A^{-1} A = \frac{1}{2}
\begin{pmatrix}
4 & -2 \\
-5 & 3
\end{pmatrix}
\begin{pmatrix}
3 & 2 \\
5 & 4
\end{pmatrix}
$$

Evaluating entries:
- Row 1 · Column 1: $(4)(3) + (-2)(5) = 12 - 10 = 2$
- Row 1 · Column 2: $(4)(2) + (-2)(4) = 8 - 8 = 0$
- Row 2 · Column 1: $(-5)(3) + (3)(5) = -15 + 15 = 0$
- Row 2 · Column 2: $(-5)(2) + (3)(4) = -10 + 12 = 2$

$$
A^{-1} A = \frac{1}{2}
\begin{pmatrix}
2 & 0 \\
0 & 2
\end{pmatrix}
= I_2
$$

Both left and right multiplication yield $I_2$.

### Check 2: Determinant of the Inverse

Using the determinant property $\det(A^{-1}) = \frac{1}{\det A}$:

$$
\det(A^{-1}) = (2)\left(\frac{3}{2}\right) - (-1)\left(-\frac{5}{2}\right) = 3 - \frac{5}{2} = \frac{1}{2} = \frac{1}{\det A}
$$

The determinant of the inverse exactly equals $\frac{1}{2}$.

---

## Why This Exercise Matters

- **Algorithmic Simplicity:** The $2 \times 2$ formula is the fastest way to invert small matrices, forming an essential tool for differential equations, dynamical systems, and linear geometry.
- **Role of the Determinant:** Shows explicitly why the determinant appears in the denominator, illustrating why invertibility fails when $\det = 0$.
- **Adjugate Connection:** The matrix $\mathrm{adj}(M)$ formed by swapping diagonals and negating off-diagonals is the classical adjugate (transpose of the cofactor matrix), introducing the general formula $M^{-1} = \frac{1}{\det M} \mathrm{adj}(M)$.
