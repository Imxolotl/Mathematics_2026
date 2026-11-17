# Problem 1: Line Through Two Points

## Question

Find the equation of the line through $A=(1,2)$ and $B=(4,-1)$ in parametric and general form. Identify a direction vector and an example of a normal vector. Check that both points satisfy the equation you obtain.

---

## Solution

### 1. Direction Vector of the Line

A line passing through two distinct points $A = (1, 2)$ and $B = (4, -1)$ has a natural direction vector given by the displacement vector $\overrightarrow{AB}$:

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                    &= (4 - 1, \; -1 - 2) \\
                    &= (3, -3)
\end{aligned}
$$

Any nonzero scalar multiple of $\overrightarrow{AB}$ is also a valid direction vector for the same line. Dividing by $3$ gives a simpler direction vector:

$$
v = \frac{1}{3} \overrightarrow{AB} = (1, -1)
$$

Both $\overrightarrow{AB} = (3, -3)$ and $v = (1, -1)$ are valid direction vectors.

---

### 2. Parametric Form of the Line

The vector parametric equation of a line passing through $A = (x_0, y_0)$ with direction vector $d = (d_1, d_2)$ is:

$$
(x, y) = A + t d, \qquad t \in \mathbb{R}
$$

#### Option A: Using $d = \overrightarrow{AB} = (3, -3)$

$$
(x, y) = (1, 2) + t(3, -3), \qquad t \in \mathbb{R}
$$

In coordinate system form:

$$
\begin{cases}
x = 1 + 3t, \\
y = 2 - 3t,
\end{cases}
\qquad t \in \mathbb{R}
$$

#### Option B: Using the simplified direction vector $v = (1, -1)$

$$
(x, y) = (1, 2) + s(1, -1), \qquad s \in \mathbb{R}
$$

In coordinate system form:

$$
\begin{cases}
x = 1 + s, \\
y = 2 - s,
\end{cases}
\qquad s \in \mathbb{R}
$$

---

### 3. Normal Vector and General Form of the Line

#### 1. Finding a Normal Vector $n$

A normal vector $n = (a, b)$ to a line in $\mathbb{R}^2$ must be perpendicular to the line's direction vector $v = (v_1, v_2)$, satisfying $n \cdot v = 0$. In $\mathbb{R}^2$, swapping the coordinates of $v = (v_1, v_2)$ and negating one of them produces an orthogonal vector $(-v_2, v_1)$.

For $v = (1, -1)$, we obtain the normal vector:

$$
n = (1, 1)
$$

(Alternatively, using $\overrightarrow{AB} = (3, -3)$ gives the normal vector $n_1 = (3, 3) = 3(1, 1)$.)

Let us verify orthogonality via the dot product:

$$
n \cdot v = (1)(1) + (1)(-1) = 1 - 1 = 0
$$

#### 2. Constructing the General Form $ax + by + c = 0$

A point $X = (x, y)$ lies on the line through $A = (1, 2)$ with normal vector $n = (1, 1)$ if and only if the displacement vector $\overrightarrow{AX} = (x - 1, y - 2)$ is perpendicular to $n$:

$$
n \cdot (X - A) = 0
$$

Substituting $n = (1, 1)$ and $A = (1, 2)$:

$$
1(x - 1) + 1(y - 2) = 0
$$

Expanding and simplifying:

$$
x + y - 3 = 0 \qquad \mathrm{or} \qquad x + y = 3
$$

*(Note: Eliminating the parameter $t$ from the parametric equations $x = 1 + 3t$ and $y = 2 - 3t$ by adding them directly gives $x + y = (1 + 3t) + (2 - 3t) = 3$, which yields the exact same general equation $x + y - 3 = 0$.)*

---

### 4. Checking that Both Points Satisfy the Equations

#### Check in the General Form $x + y - 3 = 0$:

- **Point $A = (1, 2)$:**

$$
1 + 2 - 3 = 3 - 3 = 0
$$

- **Point $B = (4, -1)$:**

$$
4 + (-1) - 3 = 3 - 3 = 0
$$

Both points satisfy the general equation $x + y - 3 = 0$.

#### Check in the Parametric Form $(x, y) = (1, 2) + t(3, -3)$:

- **For $t = 0$:**

$$
(x, y) = (1, 2) + 0(3, -3) = (1, 2) = A
$$

- **For $t = 1$:**

$$
(x, y) = (1, 2) + 1(3, -3) = (1 + 3, \; 2 - 3) = (4, -1) = B
$$

Both points lie on the parameterized line.

---

## Verification and Consistency Checks

### Slope-Intercept Comparison

Rewriting the general equation $x + y - 3 = 0$ in slope-intercept form $y = mx + b$:

$$
y = -x + 3
$$

- The slope is $m = -1$, which matches the ratio of the direction vector components $\frac{v_2}{v_1} = \frac{-1}{1} = -1$.
- Evaluating at $x = 1$ gives $y = -1 + 3 = 2$ (point $A$), and evaluating at $x = 4$ gives $y = -4 + 3 = -1$ (point $B$).

---

## Why This Exercise Matters

- **Two Dual Descriptions of a Line in $\mathbb{R}^2$:**
  - The **parametric form** generates points on the line dynamically by moving from a starting point $A$ along a **direction vector** $v$.
  - The **general form** $ax + by + c = 0$ tests whether a point $(x, y)$ belongs to the line by requiring $(x - x_0, y - y_0)$ to be orthogonal to the **normal vector** $n = (a, b)$.
- **Reading Vectors Directly from Equations:** From $(x, y) = (1, 2) + t(1, -1)$ we immediately read the direction vector $v = (1, -1)$, while from $1x + 1y - 3 = 0$ we immediately read the normal vector $n = (1, 1)$.
