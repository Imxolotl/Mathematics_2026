# Problem 12: Intersection Line of Two Planes

## Question

Find a parametric equation of the line that is the intersection of

$$
x+y+z=3,\qquad x-y+z=1.
$$

Find its direction vector in two ways: from the system of equations and from the cross product of the normal vectors. Compare the results.

---

## Solution

### 1. Method 1: Solving the System of Equations (Algebraic Approach)

A point $(x, y, z)$ lies on the intersection line $L$ of the two planes $\Pi_1$ and $\Pi_2$ if and only if it satisfies both plane equations simultaneously:

$$
\begin{cases}
x + y + z = 3, \\
x - y + z = 1.
\end{cases}
$$

#### Step 1: Eliminate $x$ and $z$ by subtracting the second equation from the first

$$
(x + y + z) - (x - y + z) = 3 - 1
$$

$$
2y = 2
$$

Dividing by $2$ gives $y = 1$.

#### Step 2: Substitute $y = 1$ into the first equation

$$
x + 1 + z = 3
$$

Subtracting $1$ from both sides gives:

$$
x + z = 2
$$

#### Step 3: Introduce a free parameter $t \in \mathbb{R}$

Since $y = 1$ is fixed and $x + z = 2$ relates the remaining two variables, we have one free variable. Setting $z = t$ ($t \in \mathbb{R}$) gives $x = 2 - t$:

$$
x = 2 - t, \qquad y = 1, \qquad z = t
$$

Writing $(x, y, z)$ in vector parametric form:

$$
(x, y, z) = (2 - t, 1, t) = (2, 1, 0) + t(-1, 0, 1)
$$

From this parametric equation, we read off the point $A = (2, 1, 0)$ (at $t = 0$) and the direction vector $v_1$ obtained from the system of equations:

$$
v_1 = (-1, 0, 1)
$$

---

### 2. Method 2: Cross Product of the Normal Vectors (Geometric Approach)

#### Step 1: Read off the normal vectors of the two planes

From the first plane $\Pi_1: 1x + 1y + 1z = 3$, the normal vector is:

$$
n_1 = (1, 1, 1)
$$

From the second plane $\Pi_2: 1x - 1y + 1z = 1$, the normal vector is:

$$
n_2 = (1, -1, 1)
$$

#### Step 2: Explain why the cross product gives the direction of the intersection line

Because the intersection line $L$ lies inside $\Pi_1$, its direction vector must be perpendicular to $n_1$. Because $L$ also lies inside $\Pi_2$, its direction vector must simultaneously be perpendicular to $n_2$. In $\mathbb{R}^3$, the cross product $n_1 \times n_2$ is perpendicular to both $n_1$ and $n_2$, so it points along the intersection line $L$.

#### Step 3: Compute the cross product

For $n_1 = (1, 1, 1)$ and $n_2 = (1, -1, 1)$, we compute each coordinate of $v_2 = n_1 \times n_2$.

First component ($x$-coordinate):

$$
(1)(1) - (1)(-1) = 1 + 1 = 2
$$

Second component ($y$-coordinate):

$$
(1)(1) - (1)(1) = 1 - 1 = 0
$$

Third component ($z$-coordinate):

$$
(1)(-1) - (1)(1) = -1 - 1 = -2
$$

Thus, the direction vector obtained from the cross product is:

$$
v_2 = n_1 \times n_2 = (2, 0, -2)
$$

---

### 3. Comparison of the Two Direction Vectors

Comparing the direction vector from the linear system, $v_1 = (-1, 0, 1)$, with the direction vector from the cross product, $v_2 = (2, 0, -2)$:

$$
v_2 = (2, 0, -2) = -2(-1, 0, 1) = -2 v_1
$$

- **Collinearity (Equivalence of Direction):** The two vectors are nonzero scalar multiples of each other ($v_2 = -2 v_1$). A line's direction vector is defined up to a nonzero scalar factor: multiplying a direction vector by $-2$ traverses the exact same geometric line in the opposite orientation at twice the parameter speed.
- **Geometric Consistency:** The factor of $2$ in $v_2 = (2, 0, -2)$ arises because adding and subtracting the two plane equations eliminates variables with a coefficient of $2$ ($2y = 2$ and $2x + 2z = 4$). Both methods describe the exact same line in $\mathbb{R}^3$.

---

## Verification and Consistency Checks

### Check 1: Substitution into Both Planes

Substituting $x = 2 - t$, $y = 1$, and $z = t$ into the first plane $x + y + z = 3$:

$$
(2 - t) + 1 + t = 3 + 0t = 3
$$

Substituting $x = 2 - t$, $y = 1$, and $z = t$ into the second plane $x - y + z = 1$:

$$
(2 - t) - 1 + t = 1 + 0t = 1
$$

Both plane equations are satisfied for every $t \in \mathbb{R}$.

### Check 2: Orthogonality of $v_1$ to Both Normals

$$
v_1 \cdot n_1 = (-1)(1) + (0)(1) + (1)(1) = -1 + 0 + 1 = 0
$$

$$
v_1 \cdot n_2 = (-1)(1) + (0)(-1) + (1)(1) = -1 + 0 + 1 = 0
$$

---

## Why This Exercise Matters

- **Algebraic vs. Geometric Duality:** Solving a system of two linear equations in three unknowns with one free variable is the algebraic counterpart of intersecting two non-parallel planes in $\mathbb{R}^3$.
- **Fast Direction Shortcut:** When a problem only asks for the direction of the line of intersection of two planes (and not a specific point on it), computing $n_1 \times n_2$ gives the direction vector immediately without solving any equations.
