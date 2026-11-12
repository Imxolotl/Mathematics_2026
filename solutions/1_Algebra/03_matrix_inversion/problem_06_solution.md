# Problem 6: Solving a System Using the Inverse

## Question

Solve

$$
Ax=b,
$$

where

$$
A=
\begin{pmatrix}
2 & 1 \\
1 & 3
\end{pmatrix},\qquad b=
\begin{pmatrix}
5 \\
7
\end{pmatrix},
$$

using $x=A^{-1}b$. Then substitute the resulting vector back into the equation and check the result.

---

## Solution

### 1. Matrix Inversion Formulation for Linear Systems

Given a linear system of $n$ equations in $n$ unknowns written in matrix form:

$$
Ax = b
$$

If the coefficient matrix $A$ is invertible ($\det A \neq 0$), we multiply both sides of the equation on the left by $A^{-1}$:

$$
A^{-1}(Ax) = A^{-1}b
$$

Since matrix multiplication is associative and $A^{-1}A = I_n$:

$$
I_n x = A^{-1}b \implies x = A^{-1}b
$$

This yields the unique solution vector $x$.

---

### 2. Finding the Inverse Matrix $A^{-1}$

For the $2 \times 2$ coefficient matrix

$$
A=
\begin{pmatrix}
2 & 1 \\
1 & 3
\end{pmatrix}
$$

#### Step 1: Compute the Determinant

$$
\begin{aligned}
\det A &= (2)(3) - (1)(1) \\
       &= 6 - 1 \\
       &= 5
\end{aligned}
$$

Since $\det A = 5 \neq 0$, matrix $A$ is invertible and $A^{-1}$ exists.

#### Step 2: Apply the 2x2 Inversion Formula

For a $2 \times 2$ matrix, the inverse is:

$$
M^{-1} = \frac{1}{\det M}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}
$$

Applying this to matrix $A$:

$$
A^{-1} = \frac{1}{5}
\begin{pmatrix}
3 & -1 \\
-1 & 2
\end{pmatrix}
$$

In entrywise fractional form:

$$
A^{-1} =
\begin{pmatrix}
\frac{3}{5} & -\frac{1}{5} \\
-\frac{1}{5} & \frac{2}{5}
\end{pmatrix}
$$

---

### 3. Computing the Solution Vector $x = A^{-1}b$

Now we multiply $A^{-1}$ by the right-hand side vector $b$:

$$
b =
\begin{pmatrix}
5 \\
7
\end{pmatrix}
$$

Evaluating the product $x = A^{-1}b$:

$$
x = \frac{1}{5}
\begin{pmatrix}
3 & -1 \\
-1 & 2
\end{pmatrix}
\begin{pmatrix}
5 \\
7
\end{pmatrix}
$$

Multiplying the matrix by the vector:
- First entry $x_1$: $(3)(5) + (-1)(7) = 15 - 7 = 8$
- Second entry $x_2$: $(-1)(5) + (2)(7) = -5 + 14 = 9$

Multiplying by the scalar factor $\frac{1}{5}$:

$$
x = \frac{1}{5}
\begin{pmatrix}
8 \\
9
\end{pmatrix}
= \begin{pmatrix}
\frac{8}{5} \\
\frac{9}{5}
\end{pmatrix}
$$

The unique solution to the system is $x_1 = \frac{8}{5}$ and $x_2 = \frac{9}{5}$.

---

### 4. Verification: Substituting Back into $Ax = b$

We substitute the computed solution vector:

$$
x =
\begin{pmatrix}
\frac{8}{5} \\
\frac{9}{5}
\end{pmatrix}
$$

back into the original matrix equation $Ax$:

$$
Ax =
\begin{pmatrix}
2 & 1 \\
1 & 3
\end{pmatrix}
\begin{pmatrix}
\frac{8}{5} \\
\frac{9}{5}
\end{pmatrix}
$$

Factoring out $\frac{1}{5}$ to simplify the arithmetic:

$$
Ax = \frac{1}{5}
\left[
\begin{pmatrix}
2 & 1 \\
1 & 3
\end{pmatrix}
\begin{pmatrix}
8 \\
9
\end{pmatrix}
\right]
$$

Evaluating each row:
- Row 1: $(2)(8) + (1)(9) = 16 + 9 = 25$
- Row 2: $(1)(8) + (3)(9) = 8 + 27 = 35$

Multiplying by $\frac{1}{5}$:

$$
Ax = \frac{1}{5}
\begin{pmatrix}
25 \\
35
\end{pmatrix}
= \begin{pmatrix}
5 \\
7
\end{pmatrix}
= b
$$

The result matches $b$ entry-by-entry, confirming that $x$ is the exact solution.

---

## Verification and Consistency Checks

### Check 1: Standard Elimination / Substitution

Writing the system in scalar form:

$$
\begin{aligned}
2x_1 + x_2 &= 5 \\
x_1 + 3x_2 &= 7
\end{aligned}
$$

From the first equation, express $x_2$ in terms of $x_1$:

$$
x_2 = 5 - 2x_1
$$

Substitute into the second equation:

$$
x_1 + 3(5 - 2x_1) = 7 \implies x_1 + 15 - 6x_1 = 7 \implies -5x_1 = -8 \implies x_1 = \frac{8}{5}
$$

Now determine $x_2$:

$$
x_2 = 5 - 2\left(\frac{8}{5}\right) = \frac{25 - 16}{5} = \frac{9}{5}
$$

Both methods yield the identical solution vector.

### Check 2: Cramer's Rule

The denominator determinant is $\det A = 5$. Computing determinants with replaced columns:

$$
\det A_1 = \det
\begin{pmatrix}
5 & 1 \\
7 & 3
\end{pmatrix}
= (5)(3) - (1)(7) = 15 - 7 = 8 \implies x_1 = \frac{\det A_1}{\det A} = \frac{8}{5}
$$

$$
\det A_2 = \det
\begin{pmatrix}
2 & 5 \\
1 & 7
\end{pmatrix}
= (2)(7) - (5)(1) = 14 - 5 = 9 \implies x_2 = \frac{\det A_2}{\det A} = \frac{9}{5}
$$

Cramer's rule provides a third independent confirmation.

---

## Why This Exercise Matters

- **The Primary Purpose of Matrix Inversion:** Connects abstract matrix inverses to their practical origin: solving square linear equations in a single algebraic step.
- **Multiple Right-Hand Sides:** Once $A^{-1}$ is computed, solving $Ax = b$ for any number of different vectors $b$ requires only a single matrix-vector multiplication rather than repeating Gaussian elimination from scratch.
- **Left Multiplication Requirement:** Reinforces that because matrix multiplication is non-commutative, multiplying $Ax = b$ on the left by $A^{-1}$ gives $x = A^{-1}b$, whereas multiplying on the right by $A^{-1}$ would produce $AxA^{-1}$, which does not simplify to $x$.
