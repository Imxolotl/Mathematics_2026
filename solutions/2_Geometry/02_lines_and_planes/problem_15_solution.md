# Problem 15: Complete Classification of a Line Relative to a Plane

## Question

Let

$$
L:p+tv,\qquad \Pi:n\cdot x=d.
$$

State the conditions distinguishing the three cases: one intersection point, parallel with no common points, and the line contained in the plane. Then illustrate each case with your own simple numerical example.

---

## Solution

### 1. Algebraic Derivation of the Classification Criterion

Let $L$ be a line in $\mathbb{R}^3$ passing through a reference point $p$ with nonzero direction vector $v \neq 0$, and let $\Pi$ be a plane with nonzero normal vector $n \neq 0$ and scalar constant $d \in \mathbb{R}$.

A point $x(t) = p + tv$ on the line $L$ lies on the plane $\Pi$ if and only if it satisfies the plane equation $n \cdot x = d$:

$$
n \cdot (p + tv) = d
$$

Using the distributivity and linearity of the dot product:

$$
n \cdot p + t(n \cdot v) = d
$$

Isolating the term containing the parameter $t$:

$$
(n \cdot v) t = d - n \cdot p
$$

This is a single linear equation of the form $A t = B$ in one real unknown $t \in \mathbb{R}$, with coefficient $A = n \cdot v$ and right-hand side $B = d - n \cdot p$. The number of solutions for $t$ is completely determined by whether $n \cdot v$ and $d - n \cdot p$ are zero or nonzero.

---

### 2. Conditions Distinguishing the Three Cases

#### Case 1: One Unique Intersection Point

Necessary and sufficient condition:

$$
n \cdot v \neq 0
$$

The value of $n \cdot p$ can be arbitrary.

Because $n \cdot v \neq 0$, the line's direction vector $v$ is not perpendicular to the plane's normal vector $n$, meaning $L$ is not parallel to $\Pi$. Dividing by $n \cdot v$ gives the unique parameter value:

$$
t_0 = \frac{d - n \cdot p}{n \cdot v}
$$

Substituting $t_0$ into $p + tv$ yields the single intersection point:

$$
x_0 = p + \left( \frac{d - n \cdot p}{n \cdot v} \right) v
$$

#### Case 2: Parallel with No Common Points

Necessary and sufficient conditions:

$$
n \cdot v = 0 \qquad \mathrm{and} \qquad n \cdot p \neq d
$$

- The condition $n \cdot v = 0$ means the direction of the line is perpendicular to $n$ and therefore parallel to the plane.
- The condition $n \cdot p \neq d$ means the reference point $p$ of the line does not lie on the plane.
- Algebraically, the equation $(n \cdot v) t = d - n \cdot p$ reduces to a contradiction:

$$
0 \cdot t = d - n \cdot p \neq 0
$$

which has no solution $t \in \mathbb{R}$. The line remains at a constant positive distance from the plane.

#### Case 3: Line Contained in the Plane

Necessary and sufficient conditions:

$$
n \cdot v = 0 \qquad \mathrm{and} \qquad n \cdot p = d
$$

- The condition $n \cdot p = d$ means the starting point $p$ of the line already lies on the plane $\Pi$.
- The condition $n \cdot v = 0$ means the line moves from $p$ in a direction parallel to $\Pi$, so it never leaves $\Pi$.
- Algebraically, the equation $(n \cdot v) t = d - n \cdot p$ reduces to the identity:

$$
0 \cdot t = 0
$$

which is satisfied for every $t \in \mathbb{R}$, so all infinitely many points of $L$ belong to $\Pi$.

---

### 3. Simple Numerical Examples Illustrating Each Case

To make the geometry transparent, we use the horizontal $xy$-coordinate plane $\Pi: z = 0$ for all three examples, where:

$$
n = (0, 0, 1), \qquad d = 0
$$

#### Example 1: One Unique Intersection Point

Choose the vertical line (the $z$-axis) passing through $p = (0, 0, 1)$ with direction vector $v = (0, 0, 1)$:

$$
(x, y, z) = (0, 0, 1) + t(0, 0, 1) = (0, 0, 1 + t)
$$

Checking the condition:

$$
n \cdot v = (0, 0, 1) \cdot (0, 0, 1) = 1 \neq 0
$$

Solving $1 + t = 0$ gives $t = -1$, yielding the unique intersection point $(0, 0, 0)$ on the plane $z = 0$.

#### Example 2: Parallel with No Common Points

Choose the horizontal line at height $z = 2$ passing through $p = (0, 0, 2)$ in the $x$-direction $v = (1, 0, 0)$:

$$
(x, y, z) = (0, 0, 2) + t(1, 0, 0) = (t, 0, 2)
$$

Checking the conditions:

$$
n \cdot v = (0, 0, 1) \cdot (1, 0, 0) = 0
$$

$$
n \cdot p = (0, 0, 1) \cdot (0, 0, 2) = 2 \neq 0 = d
$$

Substituting $(t, 0, 2)$ into $z = 0$ gives the contradiction $2 = 0$, so $L_2$ and $\Pi$ have no common points.

#### Example 3: Line Contained in the Plane

Choose the $x$-axis passing through $p = (0, 0, 0)$ with direction vector $v = (1, 0, 0)$:

$$
(x, y, z) = (0, 0, 0) + t(1, 0, 0) = (t, 0, 0)
$$

Checking the conditions:

$$
n \cdot v = (0, 0, 1) \cdot (1, 0, 0) = 0
$$

$$
n \cdot p = (0, 0, 1) \cdot (0, 0, 0) = 0 = d
$$

Every point $(t, 0, 0)$ on $L_3$ has $z = 0$, so $L_3$ lies completely inside the plane $\Pi: z = 0$ for all $t \in \mathbb{R}$.

---

## Summary Classification Table

| Case | Condition on Direction | Condition on Point | Linear Equation | Number of Common Points |
| :--- | :--- | :--- | :--- | :--- |
| **1. Intersecting at one point** | $n \cdot v \neq 0$ | Any value | Unique solution $t = \frac{d - n \cdot p}{n \cdot v}$ | Exactly $1$ |
| **2. Parallel (disjoint)** | $n \cdot v = 0$ | $n \cdot p \neq d$ | Contradiction $0 \cdot t = c \neq 0$ | $0$ (none) |
| **3. Line lies in plane** | $n \cdot v = 0$ | $n \cdot p = d$ | Identity $0 \cdot t = 0$ | Infinitely many |

---

## Why This Exercise Matters

- **Complete Correspondence with 1D Linear Equations:** A line–plane intersection in $\mathbb{R}^3$ reduces to the elementary 1D linear equation $A t = B$, whose three cases ($A \neq 0$; $A = 0, B \neq 0$; $A = 0, B = 0$) correspond one-to-one with transverse intersection, strict parallelism, and containment.
