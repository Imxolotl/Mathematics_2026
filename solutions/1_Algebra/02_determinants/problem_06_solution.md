# Problem 6: Parameter and Invertibility

## Question

For

$$
A(t) =
\begin{pmatrix}
t & 1 \\
2 & t
\end{pmatrix}
$$

find all values of $t$ for which the matrix is not invertible. Explain how your answer is related to the determinant being zero.

---

## Solution

### 1. Invertibility Criterion for Square Matrices

A square matrix $M$ is invertible if and only if its determinant is non-zero:

$$
\det M \neq 0
$$

Conversely, $M$ fails to be invertible (is singular) precisely when its determinant is zero:

$$
\det M = 0
$$

---

### 2. Computation of the Determinant $\det A(t)$

For the $2 \times 2$ parameter-dependent matrix

$$
A(t) =
\begin{pmatrix}
t & 1 \\
2 & t
\end{pmatrix}
$$

the determinant is computed as the product of the main diagonal entries minus the product of the anti-diagonal entries:

$$
\begin{aligned}
\det A(t) &= (t)(t) - (1)(2) \\
          &= t^2 - 2
\end{aligned}
$$

---

### 3. Finding the Values of $t$ for Non-Invertibility

Setting the determinant equal to zero:

$$
t^2 - 2 = 0
$$

Solving this quadratic equation for $t$:

$$
t^2 = 2 \implies t = \pm\sqrt{2}
$$

The two values of $t$ for which the matrix $A(t)$ is not invertible are:

$$
t_1 = \sqrt{2}, \qquad t_2 = -\sqrt{2}
$$

For all real values $t \in \mathbb{R} \setminus \{-\sqrt{2}, \sqrt{2}\}$, $\det A(t) \neq 0$ and the matrix $A(t)$ is invertible.

---

### 4. Explanation: Connection Between Non-Invertibility and $\det A(t) = 0$

The condition $\det A(t) = 0$ is fundamentally tied to the failure of invertibility through three perspectives:

#### Perspective 1: Algebraic Formula for the 2x2 Inverse

For a general $2 \times 2$ matrix $M$:

$$
M =
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$

the explicit inverse formula is:

$$
M^{-1} = \frac{1}{\det M}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}
$$

When $t = \pm\sqrt{2}$, $\det A(t) = 0$. Evaluating this formula requires dividing by zero, which is undefined. Hence, no inverse matrix $A(t)^{-1}$ can exist.

#### Perspective 2: Linear Dependence of Rows and Columns

A square matrix has determinant zero if and only if its rows (and columns) are linearly dependent.

**Case 1: $t = \sqrt{2}$**

$$
A(\sqrt{2}) =
\begin{pmatrix}
\sqrt{2} & 1 \\
2 & \sqrt{2}
\end{pmatrix}
$$

Row 2 is a scalar multiple of row 1:

$$
r_2 = (2, \sqrt{2}) = \sqrt{2} \cdot (\sqrt{2}, 1) = \sqrt{2} r_1
$$

**Case 2: $t = -\sqrt{2}$**

$$
A(-\sqrt{2}) =
\begin{pmatrix}
-\sqrt{2} & 1 \\
2 & -\sqrt{2}
\end{pmatrix}
$$

Row 2 is a scalar multiple of row 1:

$$
r_2 = (2, -\sqrt{2}) = -\sqrt{2} \cdot (-\sqrt{2}, 1) = -\sqrt{2} r_1
$$

In both cases, the rows lie on the same line in $\mathbb{R}^2$, meaning the rank of $A(t)$ is $1 < 2$. A matrix whose rank is strictly less than its dimension cannot have full rank and is therefore singular.

#### Perspective 3: Geometric Collapse of Area

The absolute value of the determinant $|\det A(t)|$ represents the area of the parallelogram formed by the column vectors of $A(t)$ in the plane $\mathbb{R}^2$.
- When $t = \pm\sqrt{2}$, the area is $|\det A(t)| = 0$.
- The linear transformation $x \mapsto A(t)x$ collapses the entire two-dimensional plane $\mathbb{R}^2$ onto a one-dimensional line (the span of the column vectors).
- Because a map that reduces dimension cannot be one-to-one (injective) or onto (surjective), it cannot be inverted.

---

## Verification and Consistency Checks

1. **Kernel (Null Space) Non-Triviality Check for $t = \sqrt{2}$:**
   If $A(\sqrt{2})$ is singular, there must exist a non-zero vector $v \in \mathbb{R}^2$ satisfying $A(\sqrt{2})v = 0$.
   Testing $v = (1, -\sqrt{2})^T$:

$$
A(\sqrt{2})v =
\begin{pmatrix}
\sqrt{2} & 1 \\
2 & \sqrt{2}
\end{pmatrix}
\begin{pmatrix}
1 \\
-\sqrt{2}
\end{pmatrix}
$$

   Performing the multiplication:

$$
A(\sqrt{2})v =
\begin{pmatrix}
\sqrt{2}(1) + 1(-\sqrt{2}) \\
2(1) + \sqrt{2}(-\sqrt{2})
\end{pmatrix}
= \begin{pmatrix}
0 \\
0
\end{pmatrix}
$$

   Since $v \neq 0$ is in the kernel, $\ker A(\sqrt{2}) \neq \{0\}$, confirming non-invertibility.

2. **Kernel (Null Space) Non-Triviality Check for $t = -\sqrt{2}$:**
   Testing $w = (1, \sqrt{2})^T$:

$$
A(-\sqrt{2})w =
\begin{pmatrix}
-\sqrt{2} & 1 \\
2 & -\sqrt{2}
\end{pmatrix}
\begin{pmatrix}
1 \\
\sqrt{2}
\end{pmatrix}
$$

   Performing the multiplication:

$$
A(-\sqrt{2})w =
\begin{pmatrix}
-\sqrt{2}(1) + 1(\sqrt{2}) \\
2(1) - \sqrt{2}(\sqrt{2})
\end{pmatrix}
= \begin{pmatrix}
0 \\
0
\end{pmatrix}
$$

   Since $w \neq 0$ is in the kernel, $\ker A(-\sqrt{2}) \neq \{0\}$, confirming non-invertibility.

3. **Invertible Case Test ($t = 0$):**
   Evaluating at $t = 0$:

$$
A(0) =
\begin{pmatrix}
0 & 1 \\
2 & 0
\end{pmatrix}
\implies \det A(0) = 0^2 - 2 = -2 \neq 0
$$

   The explicit inverse is:

$$
A(0)^{-1} = -\frac{1}{2}
\begin{pmatrix}
0 & -1 \\
-2 & 0
\end{pmatrix}
= \begin{pmatrix}
0 & \frac{1}{2} \\
1 & 0
\end{pmatrix}
$$

   Multiplying confirms $A(0) A(0)^{-1} = I_2$, verifying that for any $t \neq \pm\sqrt{2}$, the matrix is indeed invertible.

---

## Why This Exercise Matters

- **Characteristic Polynomials and Eigenvalues:** The equation $\det(A(t)) = 0$ illustrates how determinants are polynomials in matrix parameters, directly preparing students for the eigenvalue equation $\det(A - \lambda I) = 0$.
- **Parameter Bifurcation:** In engineering, economics, and physics, systems often depend on continuous parameters. The determinant identifies the exact threshold values where a system transitions from having a unique solution to having either no solution or infinitely many solutions.
- **Invertibility Theorem Equivalences:** Demonstrates the equivalence between $\det M = 0$, $\mathrm{rank}(M) < n$, $\ker M \neq \{0\}$, and linear dependence of rows/columns.
