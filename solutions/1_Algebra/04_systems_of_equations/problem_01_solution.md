# Problem 1: From a System to a Matrix

## Question

Write the system

$$
\begin{cases}
2x-y+z=4, \\
x+3y-2z=1, \\
3x+y+z=7.
\end{cases}
$$

in the form $Ax=b$.
Identify the coefficient matrix, the vector of unknowns, and the right-hand side vector. Explain how each row of the matrix corresponds to one equation.

---

## Solution

### 1. Matrix Form $Ax = b$

A system of $m$ linear equations in $n$ unknowns can be written compactly as the matrix equation:

$$
Ax = b
$$

For the given system:

$$
\begin{pmatrix}
2 & -1 & 1 \\
1 & 3 & -2 \\
3 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
= \begin{pmatrix}
4 \\
1 \\
7
\end{pmatrix}
$$

---

### 2. Identification of the Components

1. **Coefficient Matrix $A$:**
   The $3 \times 3$ matrix formed by collecting the numerical coefficients of the variables $x, y, z$ in each equation:

$$
A =
\begin{pmatrix}
2 & -1 & 1 \\
1 & 3 & -2 \\
3 & 1 & 1
\end{pmatrix}
$$

2. **Vector of Unknowns $x$ (or $u$):**
   The $3 \times 1$ column vector containing the unknown variables:

$$
x =
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
$$

3. **Right-Hand Side Vector $b$:**
   The $3 \times 1$ column vector containing the constant terms from the right-hand sides of the equations:

$$
b =
\begin{pmatrix}
4 \\
1 \\
7
\end{pmatrix}
$$

---

### 3. Explanation: Correspondence Between Matrix Rows and Equations

The matrix-vector product $Ax$ is defined row by row. Each entry of the resulting column vector is the dot product of a row of $A$ with the vector of unknowns $x$:

- **Row 1 of $A$:**
  The row vector is $(2, -1, 1)$. Taking its dot product with the column vector $(x, y, z)^T$:

$$
(2)(x) + (-1)(y) + (1)(z) = 2x - y + z
$$

  Setting this equal to the first entry of $b$ ($b_1 = 4$) reconstructs the first equation:

$$
2x - y + z = 4
$$

- **Row 2 of $A$:**
  The row vector is $(1, 3, -2)$. Taking its dot product with $(x, y, z)^T$:

$$
(1)(x) + (3)(y) + (-2)(z) = x + 3y - 2z
$$

  Setting this equal to the second entry of $b$ ($b_2 = 1$) reconstructs the second equation:

$$
x + 3y - 2z = 1
$$

- **Row 3 of $A$:**
  The row vector is $(3, 1, 1)$. Taking its dot product with $(x, y, z)^T$:

$$
(3)(x) + (1)(y) + (1)(z) = 3x + y + z
$$

  Setting this equal to the third entry of $b$ ($b_3 = 7$) reconstructs the third equation:

$$
3x + y + z = 7
$$

Thus, row $i$ of the coefficient matrix $A$ holds the scalar weights with which the variables enter the $i$-th equation, and entry $b_i$ specifies the required value of that linear combination.

---

## Verification and Consistency Checks

### Check 1: Dimension Compatibility

- Matrix $A$ has size $3 \times 3$.
- Vector $x$ has size $3 \times 1$.
- The inner dimensions match ($3 = 3$), so the product $Ax$ is well-defined and has size $3 \times 1$.
- Vector $b$ has size $3 \times 1$, matching the size of $Ax$.

### Check 2: Row-by-Row Expansion

Evaluating the matrix product directly:

$$
Ax =
\begin{pmatrix}
2 & -1 & 1 \\
1 & 3 & -2 \\
3 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
= \begin{pmatrix}
2x - y + z \\
x + 3y - 2z \\
3x + y + z
\end{pmatrix}
$$

Equating this result to $b = (4, 1, 7)^T$ yields:

$$
\begin{pmatrix}
2x - y + z \\
x + 3y - 2z \\
3x + y + z
\end{pmatrix}
= \begin{pmatrix}
4 \\
1 \\
7
\end{pmatrix}
$$

Two vectors are equal if and only if their corresponding entries are equal, which exactly recovers the original three scalar equations.

---

## Why This Exercise Matters

- **Foundation for Linear Algebra:** Translating scalar systems into matrix form replaces systems of equations with a single equation $Ax = b$, allowing algebraic tools like matrix inversion, LU decomposition, and elimination to be applied uniformly.
- **Row Perspective:** Each row represents a plane (hyperplane) in $\mathbb{R}^3$, and the solution $(x, y, z)$ is the geometric intersection of the three planes.
- **Column Perspective:** The system expresses the right-hand side vector $b$ as a linear combination of the column vectors of $A$:

$$
\begin{aligned}
x \begin{pmatrix} 2 \\ 1 \\ 3 \end{pmatrix}
-y \begin{pmatrix} -1 \\ 3 \\ 1 \end{pmatrix}
-z \begin{pmatrix} 1 \\ -2 \\ 1 \end{pmatrix}
&=
\begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix}
\end{aligned}
$$
