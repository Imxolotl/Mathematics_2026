# Problem 10: A Polynomial Through Three Points

## Question

Find a polynomial $p(x)=ax^2+bx+c$ whose graph passes through $(0,1)$, $(1,3)$, and $(2,9)$. Reduce the problem to a system of equations and check the result by substituting all three points.

---

## Solution

### 1. Formulating the System of Linear Equations

We seek coefficients $a, b, c \in \mathbb{R}$ such that the polynomial

$$
p(x) = ax^2 + bx + c
$$

satisfies the three point conditions $p(x_i) = y_i$:

1. **For point $(0, 1)$:**

$$
p(0) = a(0)^2 + b(0) + c = 1 \implies c = 1
$$

2. **For point $(1, 3)$:**

$$
p(1) = a(1)^2 + b(1) + c = 3 \implies a + b + c = 3
$$

3. **For point $(2, 9)$:**

$$
p(2) = a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9
$$

Writing these three conditions as a linear system in the unknowns $a, b, c$:

$$
\begin{cases}
a + b + c = 3, \\
4a + 2b + c = 9, \\
c = 1.
\end{cases}
$$

---

### 2. Matrix Representation

In matrix form $A u = y$ with unknown vector $u = (a, b, c)^T$:

$$
\begin{pmatrix}
1 & 1 & 1 \\
4 & 2 & 1 \\
0 & 0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
a \\
b \\
c \\
\end{pmatrix}
= \begin{pmatrix}
3 \\
9 \\
1 \\
\end{pmatrix}
$$

The augmented matrix is:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 3 \\
4 & 2 & 1 & \mid & 9 \\
0 & 0 & 1 & \mid & 1 \\
\end{pmatrix}
$$

---

### 3. Solving via Elimination

#### Step 1: Eliminate $a$ from row 2 using $R_2 \leftarrow R_2 - 4R_1$

$$
R_2 - 4R_1 = (4 - 4(1), \; 2 - 4(1), \; 1 - 4(1) \mid 9 - 4(3)) = (0, \; -2, \; -3 \mid -3)
$$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 3 \\
0 & -2 & -3 & \mid & -3 \\
0 & 0 & 1 & \mid & 1 \\
\end{pmatrix}
$$

The matrix is now in upper triangular row echelon form.

#### Step 2: Backward substitution

- **From row 3 (solve for $c$):**

$$
c = 1
$$

- **From row 2 (solve for $b$):**

$$
-2b - 3c = -3
$$

Substitute $c = 1$:

$$
-2b - 3(1) = -3 \implies -2b - 3 = -3 \implies -2b = 0 \implies b = 0
$$

- **From row 1 (solve for $a$):**

$$
a + b + c = 3
$$

Substitute $b = 0$ and $c = 1$:

$$
a + 0 + 1 = 3 \implies a + 1 = 3 \implies a = 2
$$

---

### 4. The Resulting Polynomial

The unique coefficients are:

$$
\begin{pmatrix}
a \\
b \\
c \\
\end{pmatrix}
= \begin{pmatrix}
2 \\
0 \\
1 \\
\end{pmatrix}
$$

The required polynomial is:

$$
p(x) = 2x^2 + 1
$$

---

## Verification and Consistency Checks

We substitute each of the three given $x$-coordinates into $p(x) = 2x^2 + 1$ and verify that the output matches the corresponding $y$-coordinate.

### Check 1: Point $(0, 1)$

$$
p(0) = 2(0)^2 + 1 = 0 + 1 = 1
$$

Output is $1$. The graph passes through $(0, 1) \quad \checkmark$

### Check 2: Point $(1, 3)$

$$
p(1) = 2(1)^2 + 1 = 2(1) + 1 = 3
$$

Output is $3$. The graph passes through $(1, 3) \quad \checkmark$

### Check 3: Point $(2, 9)$

$$
p(2) = 2(2)^2 + 1 = 2(4) + 1 = 8 + 1 = 9
$$

Output is $9$. The graph passes through $(2, 9) \quad \checkmark$

All three points lie exactly on the parabola.

---

## Why This Exercise Matters

1. **Polynomial Interpolation:** Finding a polynomial of degree $n$ passing through $n+1$ distinct points always reduces to solving a system of linear equations in the unknown coefficients $a_0, a_1, \dots, a_n$.
2. **Vandermonde Matrix Structure:** The coefficient matrix of a polynomial fitting problem is a Vandermonde matrix. Because all evaluation nodes $x_0 = 0, x_1 = 1, x_2 = 2$ are distinct, the matrix is guaranteed to be non-singular, ensuring a unique interpolating polynomial exists.
3. **Linearity in the Parameters:** Even though $p(x) = ax^2 + bx + c$ is non-linear in the variable $x$, it depends **linearly** on the unknown coefficients $a, b, c$. This fundamental distinction allows powerful linear algebra techniques to solve many non-linear curve-fitting problems.
