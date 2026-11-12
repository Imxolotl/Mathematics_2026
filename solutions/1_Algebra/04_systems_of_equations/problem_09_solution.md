# Problem 9: A System from a Sum Condition

## Question

Find numbers $x,y$ satisfying

$$
x+y=10,\qquad 2x+5y=32.
$$

Solve the system and explain geometrically why the solution is unique.

---

## Solution

### 1. Set Up the System and Augmented Matrix

We write the system of equations:

$$
\begin{cases}
x + y = 10, \\
2x + 5y = 32
\end{cases}
$$

The corresponding augmented matrix $[A \mid b]$ is:

$$
\begin{pmatrix}
1 & 1 & \mid & 10 \\
2 & 5 & \mid & 32 \\
\end{pmatrix}
$$

---

### 2. Elimination

Use the first row to eliminate $x$ from the second row using $R_2 \leftarrow R_2 - 2R_1$:

$$
R_2 - 2R_1 = (2 - 2(1), \; 5 - 2(1) \mid 32 - 2(10)) = (0, \; 3 \mid 12)
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 10 \\
0 & 3 & \mid & 12 \\
\end{pmatrix}
$$

---

### 3. Back-Substitution

1. **Solve for $y$ from row 2:**

$$
3y = 12 \implies y = \frac{12}{3} = 4
$$

2. **Solve for $x$ from row 1:**

$$
x + y = 10 \implies x + 4 = 10 \implies x = 6
$$

The unique pair of numbers is:

$$
\begin{pmatrix}
x \\
y \\
\end{pmatrix}
= \begin{pmatrix}
6 \\
4 \\
\end{pmatrix}
$$

or simply $(x, y) = (6, 4)$.

---

## Geometric Explanation of Uniqueness

Each linear equation in two variables defines a straight line in the Cartesian plane $\mathbb{R}^2$:

### Line 1 ($L_1$): $x + y = 10$

Solving for $y$ in slope-intercept form ($y = mx + c$):

$$
y = -x + 10
$$

- Slope: $m_1 = -1$
- $y$-intercept: $(0, 10)$
- $x$-intercept: $(10, 0)$

### Line 2 ($L_2$): $2x + 5y = 32$

Solving for $y$:

$$
5y = -2x + 32 \implies y = -\frac{2}{5}x + \frac{32}{5} = -0.4x + 6.4
$$

- Slope: $m_2 = -\frac{2}{5} = -0.4$
- $y$-intercept: $(0, 6.4)$
- $x$-intercept: $(16, 0)$

### Why the intersection is unique:

1. **Different Slopes:**
   The slopes are strictly unequal:

$$
m_1 = -1 \neq -0.4 = m_2
$$

2. **Geometric Consequence:**
   In two-dimensional Euclidean geometry, two lines with different slopes are neither parallel nor coincident. Any two non-parallel lines in the plane must intersect at **exactly one single point**.

3. **Normal Vectors:**
   The normal vectors to the lines are:

$$
n_1 =
\begin{pmatrix}
1 \\
1 \\
\end{pmatrix},
\qquad
n_2 =
\begin{pmatrix}
2 \\
5 \\
\end{pmatrix}
$$

   Since $n_1$ and $n_2$ are not scalar multiples of each other, they point in non-parallel directions. The lines they define cross each other at precisely one point: $(6, 4)$.

---

## Verification and Consistency Checks

### Check 1: Substitution into Original Equations

- **Equation 1:**

$$
x + y = 6 + 4 = 10 \quad \checkmark
$$

- **Equation 2:**

$$
2x + 5y = 2(6) + 5(4) = 12 + 20 = 32 \quad \checkmark
$$

Both conditions are satisfied simultaneously.

### Check 2: Determinant of the Coefficient Matrix

$$
\det A =
\det
\begin{pmatrix}
1 & 1 \\
2 & 5 \\
\end{pmatrix}
= (1)(5) - (1)(2) = 5 - 2 = 3
$$

Since $\det A = 3 \neq 0$, the coefficient matrix is non-singular and invertible. By Cramer's rule / the Invertible Matrix Theorem, the system is guaranteed to possess a unique solution for any right-hand side.

---

## Why This Exercise Matters

1. **Concrete Word-to-Math Bridge:** Linear systems frequently arise from combining distinct linear constraints (e.g., total count of items $x+y=10$ and total value $2x+5y=32$).
2. **Visualizing Linear Systems:** Connecting algebraic solutions $(x, y)$ to the geometric intersection of straight lines provides an intuitive spatial model for linear algebra.
3. **Slope Condition for Uniqueness:** Understanding that $m_1 \neq m_2$ guarantees uniqueness in $\mathbb{R}^2$ is the direct geometric analogue of the non-vanishing determinant $\det A \neq 0$.
