# Problem 5: Relative Position of Two Lines

## Question

Analyze the position of

$$
L_1:(x,y,z)=(1,1,0)+t(1,2,1),
$$

$$
L_2:(x,y,z)=(2,0,1)+s(0,1,-1).
$$

If they intersect, give the intersection point. If not, determine whether they are parallel or skew. Justify the classification.

---

## Solution

### 1. Extracting Reference Points and Direction Vectors

From the parametric equations of the two lines:

- **Line $L_1$:**
  - Reference point: $P_1 = (1, 1, 0)$
  - Direction vector: $v_1 = (1, 2, 1)$

- **Line $L_2$:**
  - Reference point: $P_2 = (2, 0, 1)$
  - Direction vector: $v_2 = (0, 1, -1)$

---

### 2. Step 1: Test for Parallelism

Two lines in $\mathbb{R}^3$ are parallel (or identical) if and only if their direction vectors $v_1$ and $v_2$ are proportional ($v_1 = \lambda v_2$ for some scalar $\lambda \in \mathbb{R}$).

Comparing $v_1 = (1, 2, 1)$ and $v_2 = (0, 1, -1)$:
- The first component of $v_2$ is $0$, whereas the first component of $v_1$ is $1 \neq 0$.
- For any $\lambda \in \mathbb{R}$, the first component of $\lambda v_2$ is $\lambda \cdot 0 = 0 \neq 1$.

Therefore, $v_1$ and $v_2$ are **not proportional**, so the lines $L_1$ and $L_2$ are **not parallel**. Consequently, only two possibilities remain: either $L_1$ and $L_2$ **intersect at a single point**, or they are **skew**.

---

### 3. Step 2: Test for Intersection

An intersection point exists if and only if there is a pair of parameter values $(t, s) \in \mathbb{R}^2$ for which both lines produce the same point $(x, y, z)$:

$$
(1, 1, 0) + t(1, 2, 1) = (2, 0, 1) + s(0, 1, -1)
$$

Writing this vector equation coordinate by coordinate gives a system of three equations in two unknowns $t$ and $s$:

$$
\begin{cases}
1 + t = 2, \\
1 + 2t = s, \\
t = 1 - s.
\end{cases}
$$

#### Solve the first two equations for $t$ and $s$:

1. From the first equation ($x$-coordinates):

$$
1 + t = 2 \implies t = 1
$$

2. Substitute $t = 1$ into the second equation ($y$-coordinates):

$$
s = 1 + 2(1) = 3
$$

Thus, $(t, s) = (1, 3)$ is the **only** parameter pair for which the $x$- and $y$-coordinates of the two lines agree (at $x = 2, y = 3$).

#### Check consistency with the third equation ($z$-coordinates):

Substitute $t = 1$ and $s = 3$ into the third equation $t = 1 - s$:
- **Left-hand side ($z$ on $L_1$ at $t = 1$):**

$$
z_1 = t = 1
$$

- **Right-hand side ($z$ on $L_2$ at $s = 3$):**

$$
z_2 = 1 - s = 1 - 3 = -2
$$

Comparing the two values:

$$
1 \neq -2
$$

This is a contradiction ($1 = -2$). At the horizontal location $(x, y) = (2, 3)$ where the vertical projections of the two lines cross, $L_1$ is at height $z_1 = 1$ while $L_2$ passes underneath at height $z_2 = -2$.

Therefore, the system has **no solution**, and the lines $L_1$ and $L_2$ **do not intersect**.

---

### 4. Final Classification and Justification

Because the lines $L_1$ and $L_2$ are:
1. **Not parallel** ($v_1$ is not a scalar multiple of $v_2$), and
2. **Non-intersecting** (the system of coordinate equations is inconsistent),

the lines $L_1$ and $L_2$ are **skew lines** (they do not lie in any common plane).

---

## Verification and Consistency Checks

### Coplanarity Check via the Cross Product and Dot Product

Two lines with points $P_1, P_2$ and direction vectors $v_1, v_2$ lie in a common plane if and only if the connecting vector $\overrightarrow{P_1 P_2}$ is perpendicular to the normal $v_1 \times v_2$:

$$
\overrightarrow{P_1 P_2} \cdot (v_1 \times v_2) = 0
$$

1. **Compute the displacement vector $\overrightarrow{P_1 P_2}$:**

$$
\overrightarrow{P_1 P_2} = P_2 - P_1 = (2 - 1, \; 0 - 1, \; 1 - 0) = (1, -1, 1)
$$

2. **Compute the cross product $v_1 \times v_2$ for $v_1 = (1, 2, 1)$ and $v_2 = (0, 1, -1)$:**

$$
\begin{aligned}
v_1 \times v_2 &= (2(-1) - 1(1), \; 1(0) - 1(-1), \; 1(1) - 2(0)) \\
               &= (-2 - 1, \; 0 + 1, \; 1 - 0) \\
               &= (-3, 1, 1)
\end{aligned}
$$

3. **Compute the scalar triple product $\overrightarrow{P_1 P_2} \cdot (v_1 \times v_2)$:**

$$
\begin{aligned}
\overrightarrow{P_1 P_2} \cdot (v_1 \times v_2) &= (1)(-3) + (-1)(1) + (1)(1) \\
                                                &= -3 - 1 + 1 \\
                                                &= -3 \neq 0
\end{aligned}
$$

Because the scalar triple product is nonzero ($-3 \neq 0$), the three vectors $\overrightarrow{P_1 P_2}, v_1, v_2$ span a non-degenerate three-dimensional parallelepiped of volume $|-3| = 3$. Hence, $L_1$ and $L_2$ cannot lie in a single plane, confirming independently that they are **skew**.

---

## Why This Exercise Matters

- **Three Dimensions Introduce Skewness:** In $\mathbb{R}^2$, two non-parallel lines must always intersect. In $\mathbb{R}^3$, an overdetermined system of $3$ coordinate equations in $2$ parameters $(t, s)$ generically has no solution, making **skew lines** the most common relationship between non-parallel lines in space.
- **Two-Stage Decision Tree:**
  1. Compare direction vectors $v_1, v_2$: if proportional $\implies$ parallel or identical; if not proportional $\implies$ intersecting or skew.
  2. Solve two coordinate equations for $(t, s)$ and test the third coordinate: if satisfied $\implies$ intersecting; if contradictory $\implies$ skew.
