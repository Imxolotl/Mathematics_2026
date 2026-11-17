# Problem 7: Linear Dependence Without Heavy Computation

## Question

Given

$$
u=(1,2,3),\qquad v=(2,4,6),\qquad w=(0,1,1).
$$

Identify a specific relation between $u$ and $v$, decide whether the three vectors can be linearly independent, and explain why no long calculation is needed.

---

## Solution

### 1. Specific Relation Between $u$ and $v$

Comparing the coordinates of $u = (1, 2, 3)$ and $v = (2, 4, 6)$ term by term:

$$
\begin{aligned}
v &= (2, 4, 6) \\
  &= (2 \cdot 1, \; 2 \cdot 2, \; 2 \cdot 3) \\
  &= 2(1, 2, 3) \\
  &= 2u
\end{aligned}
$$

Thus, $v$ is an exact scalar multiple of $u$:

$$
v = 2u \iff 2u - v = 0
$$

Geometrically, $u$ and $v$ are **collinear** (parallel) vectors that lie along the same line through the origin.

---

### 2. Decision on Linear Independence of $\{u, v, w\}$

By definition, three vectors $u, v, w \in \mathbb{R}^3$ are **linearly independent** if and only if the homogeneous vector equation

$$
c_1 u + c_2 v + c_3 w = 0
$$

has **only the trivial solution** $c_1 = c_2 = c_3 = 0$. If there exists any choice of scalars $(c_1, c_2, c_3) \neq (0, 0, 0)$ satisfying the equation, the vectors are **linearly dependent**.

Using the relation $2u - v = 0$, we can include $w$ with a coefficient of zero:

$$
2u + (-1)v + 0w = 0
$$

Here, the coefficients are:

$$
c_1 = 2, \qquad c_2 = -1, \qquad c_3 = 0
$$

Because $(c_1, c_2, c_3) = (2, -1, 0) \neq (0, 0, 0)$, we have exhibited an explicit non-trivial linear combination equal to the zero vector.

**Conclusion:**
The three vectors $u, v, w$ **cannot be linearly independent**; they are **linearly dependent**.

---

### 3. Why No Long Calculation Is Needed

No Gaussian elimination, row reduction, or $3 \times 3$ determinant calculation is needed for two fundamental reasons:

#### 1. Algebraic Principle (Supersets of Dependent Sets)
If a subset of vectors $\{u, v\}$ is already linearly dependent ($2u - v = 0$), then **any larger set** $\{u, v, w\}$ containing them is automatically linearly dependent, completely regardless of the entries of $w$. One can always multiply the extra vector $w$ by $0$ so that it contributes nothing to the sum while preserving the non-trivial relation between $u$ and $v$.

#### 2. Geometric Principle (Loss of Dimension)
To be linearly independent in $\mathbb{R}^3$, three vectors must point in three independent spatial directions so that they span a three-dimensional volume (a non-degenerate parallelepiped).
- Because $v = 2u$, the vectors $u$ and $v$ point along the **same 1D line**.
- Adding a third vector $w = (0, 1, 1)$ can at most expand their span from a 1D line to a **2D plane**.
- Since all three vectors lie in a single plane, they cannot span $\mathbb{R}^3$ and are necessarily coplanar (linearly dependent).

---

## Verification and Consistency Checks

### Check 1: Direct Substitution of $(c_1, c_2, c_3) = (2, -1, 0)$

Evaluating $2u - v + 0w$ coordinate by coordinate:

$$
\begin{aligned}
2u - v + 0w &= 2(1, 2, 3) - (2, 4, 6) + 0(0, 1, 1) \\
            &= (2, 4, 6) - (2, 4, 6) + (0, 0, 0) \\
            &= (0, 0, 0)
\end{aligned}
$$

### Check 2: Determinant Property of Proportional Rows

If we place $u, v, w$ as the rows of a $3 \times 3$ matrix $M$:

$$
M =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 1 \\
\end{pmatrix}
$$

Because row 2 is twice row 1 ($r_2 = 2r_1$), a standard property of determinants immediately gives:

$$
\det M = 0
$$

without expanding a single cofactor. A zero determinant confirms that the three vectors are linearly dependent.

---

## Why This Exercise Matters

- **Inspect Before Computing:** Before launching into mechanical Gaussian elimination or Sarrus' rule, inspecting the vectors for zero vectors or proportional pairs often solves the problem in seconds.
- **Structural Understanding of Dependence:** Reinforces that linear dependence is a property of the *collection* of vectors: a single redundant pair makes the entire set dependent.
