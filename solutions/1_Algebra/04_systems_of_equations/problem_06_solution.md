# Problem 6: A System with a Parameter — Which Cases Actually Occur?

## Question

Analyze, depending on the parameter $a$, the system

$$
\begin{cases}
x+y=2, \\
ax+ay=4.
\end{cases}
$$

Among the three possibilities — exactly one solution, infinitely many solutions, no solution — determine which actually occur and for which values of $a$. If one type cannot occur, explain why.

---

## Solution

### 1. Set Up the Augmented Matrix

We write the system as an augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
a & a & \mid & 4 \\
\end{pmatrix}
$$

---

### 2. Elimination

We use row 1 to eliminate the variable $x$ from row 2 using the elementary row operation $R_2 \leftarrow R_2 - aR_1$:

$$
R_2 - aR_1 = (a - a(1), \; a - a(1) \mid 4 - a(2)) = (0, \; 0 \mid 4 - 2a)
$$

The augmented matrix in echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 0 & \mid & 4 - 2a \\
\end{pmatrix}
$$

The second row represents the equation:

$$
0x + 0y = 4 - 2a
$$

or simply:

$$
0 = 4 - 2a
$$

The behavior of the system depends entirely on whether the right-hand side $4 - 2a$ is zero or non-zero.

---

### 3. Case Analysis

#### Case 1: $4 - 2a = 0 \iff a = 2$

When $a = 2$, the augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 0 & \mid & 0 \\
\end{pmatrix}
$$

The second equation is $0 = 0$, which is satisfied for all $(x, y)$. The entire system reduces to the single equation:

$$
x + y = 2
$$

Setting $y = t$ ($t \in \mathbb{R}$) as the free variable, we get:

$$
x = 2 - t
$$

In vector form:

$$
\begin{aligned}
\begin{pmatrix} x \\ y \end{pmatrix}
&=
\begin{pmatrix} 2-t \\ t \end{pmatrix} \\[6pt]
&=
\begin{pmatrix} 2 \\ 0 \end{pmatrix}
+t\begin{pmatrix} -1 \\ 1 \end{pmatrix},
\quad t\in\mathbb{R}
\end{aligned}
$$

Therefore, when $a = 2$, the system has **infinitely many solutions**.

#### Case 2: $4 - 2a \neq 0 \iff a \neq 2$

When $a \neq 2$, the right-hand side $4 - 2a$ is non-zero, yielding the contradiction:

$$
0 = 4 - 2a \neq 0
$$

No pair of real numbers $(x, y)$ can satisfy $0 = c$ for $c \neq 0$.

Therefore, when $a \neq 2$, the system has **no solution** (it is inconsistent).

---

### 4. Why Exactly One Solution Cannot Occur

The case of **exactly one unique solution cannot occur for any value of $a$**.

#### Proof via Determinant:
A $2 \times 2$ linear system $Ax = b$ has a unique solution if and only if the coefficient matrix $A$ is invertible, which requires $\det A \neq 0$.

The coefficient matrix is:

$$
A =
\begin{pmatrix}
1 & 1 \\
a & a \\
\end{pmatrix}
$$

We compute its determinant:

$$
\det A = (1)(a) - (1)(a) = a - a = 0
$$

The determinant is identically $0$ for **all** real numbers $a$. Because $\det A = 0$ unconditionally, the rank of $A$ is at most $1$, meaning $A$ is never invertible. Consequently, the system can never have a unique solution regardless of the choice of $a$.

#### Proof via Geometry:
Each equation defines a straight line in $\mathbb{R}^2$:
- Line 1: $x + y = 2$ has normal vector $n_1 = (1, 1)^T$.
- Line 2: $ax + ay = 4$ has normal vector $n_2 = (a, a)^T = a(1, 1)^T$.

The normal vectors are always collinear. This means the two lines are always parallel.
- If $a = 2$, the lines coincide (they are the same line), producing infinitely many intersection points.
- If $a \neq 2$, the lines are strictly parallel with no intersection points.

Because two lines can intersect at a single point only if their normal vectors are linearly independent (non-parallel), an intersection at a single point is geometrically impossible here.

---

## Summary of Results

| Parameter Value | System Type | Solution Set |
| :--- | :--- | :--- |
| $a = 2$ | Consistent with free variable | Infinitely many solutions: $(x, y) = (2-t, t)$ |
| $a \neq 2$ | Inconsistent | No solution: $\emptyset$ |
| Any $a \in \mathbb{R}$ | Consistent with unique solution | **Cannot occur** |

---

## Why This Exercise Matters

1. **Parameter Awareness:** A parameter in a linear system can alter the consistency of the equations, but it cannot create degrees of freedom that the structure of the coefficient matrix does not permit.
2. **Not All Theoretical Cases Must Occur:** Standard linear algebra textbooks state that a linear system has either 0, 1, or $\infty$ solutions. This exercise emphasizes that in a specific parameterized system, one or more of these theoretical branches may be completely absent.
3. **Algebraic Invariance:** Recognizing that $\det A = 0$ for all $a$ immediately rules out the unique solution case before performing extensive case splits.
