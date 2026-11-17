# Problem 4: Plane Through Three Points

## Question

Find the equation of the plane through

$$
A=(1,0,0),\quad B=(0,1,0),\quad C=(0,0,1).
$$

First construct two vectors lying in the plane, and then use the cross product. Check the resulting equation on all three points.

---

## Solution

### 1. Constructing Two Vectors Lying in the Plane

Because the points $A = (1, 0, 0)$, $B = (0, 1, 0)$, and $C = (0, 0, 1)$ lie in the plane, the displacement vectors connecting $A$ to $B$ and $A$ to $C$ also lie entirely within the plane:

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                    &= (0 - 1, \; 1 - 0, \; 0 - 0) \\
                    &= (-1, 1, 0)
\end{aligned}
$$

$$
\begin{aligned}
\overrightarrow{AC} &= C - A \\
                    &= (0 - 1, \; 0 - 0, \; 1 - 0) \\
                    &= (-1, 0, 1)
\end{aligned}
$$

Since $\overrightarrow{AB} = (-1, 1, 0)$ and $\overrightarrow{AC} = (-1, 0, 1)$ are not scalar multiples of each other, the three points are not collinear and uniquely determine a plane.

---

### 2. Finding a Normal Vector Using the Cross Product

A normal vector $n$ to the plane must be perpendicular to both $\overrightarrow{AB}$ and $\overrightarrow{AC}$. We construct $n$ by taking their cross product:

$$
n = \overrightarrow{AB} \times \overrightarrow{AC}
$$

For $\overrightarrow{AB} = (-1, 1, 0)$ and $\overrightarrow{AC} = (-1, 0, 1)$, we compute each component of the cross product:

- **First component ($x$-coordinate):**

$$
(1)(1) - (0)(0) = 1 - 0 = 1
$$

- **Second component ($y$-coordinate):**

$$
(0)(-1) - (-1)(1) = 0 + 1 = 1
$$

- **Third component ($z$-coordinate):**

$$
(-1)(0) - (1)(-1) = 0 + 1 = 1
$$

Combining the components gives the normal vector:

$$
n = (1, 1, 1)
$$

---

### 3. Writing the Equation of the Plane

Using the point-normal form $n \cdot (X - A) = 0$ with $n = (1, 1, 1)$ and the point $A = (1, 0, 0)$:

$$
1(x - 1) + 1(y - 0) + 1(z - 0) = 0
$$

Expanding and simplifying:

$$
x + y + z - 1 = 0 \qquad \mathrm{or} \qquad x + y + z = 1
$$

---

### 4. Checking the Equation on All Three Points

We substitute each of the three given points into the equation $x + y + z = 1$:

#### 1. Point $A = (1, 0, 0)$:

$$
1 + 0 + 0 = 1
$$

#### 2. Point $B = (0, 1, 0)$:

$$
0 + 1 + 0 = 1
$$

#### 3. Point $C = (0, 0, 1)$:

$$
0 + 0 + 1 = 1
$$

All three points satisfy $x + y + z = 1$, confirming that this is the exact equation of the plane passing through $A$, $B$, and $C$.

---

## Verification and Consistency Checks

### Check 1: Orthogonality of $n = (1, 1, 1)$ to the Plane's Vectors

We verify that $n = (1, 1, 1)$ is perpendicular to $\overrightarrow{AB}$, $\overrightarrow{AC}$, and also the third triangle side $\overrightarrow{BC} = C - B = (0, -1, 1)$:

$$
n \cdot \overrightarrow{AB} = (1)(-1) + (1)(1) + (1)(0) = -1 + 1 + 0 = 0
$$

$$
n \cdot \overrightarrow{AC} = (1)(-1) + (1)(0) + (1)(1) = -1 + 0 + 1 = 0
$$

$$
n \cdot \overrightarrow{BC} = (1)(0) + (1)(-1) + (1)(1) = 0 - 1 + 1 = 0
$$

### Check 2: Intercept Form of a Plane

A plane intersecting the coordinate axes at $(a, 0, 0)$, $(0, b, 0)$, and $(0, 0, c)$ (with $a, b, c \neq 0$) has the standard **intercept equation**:

$$
\frac{x}{a} + \frac{y}{b} + \frac{z}{c} = 1
$$

Here $a = 1$, $b = 1$, and $c = 1$, which immediately gives $x + y + z = 1$, matching our cross-product derivation.

---

## Why This Exercise Matters

- **Standard Three-Point Plane Algorithm:** Any three non-collinear points $A, B, C \in \mathbb{R}^3$ determine a unique plane via the three-step pipeline:
  1. Form two in-plane vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
  2. Compute the normal vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$.
  3. Write the point-normal equation $n \cdot (X - A) = 0$.
- **Symmetry:** Because $A = (1, 0, 0)$, $B = (0, 1, 0)$, and $C = (0, 0, 1)$ are symmetric under any permutation of the $x, y, z$ axes, the normal vector $n = (1, 1, 1)$ and the plane equation $x + y + z = 1$ are likewise completely symmetric in $x$, $y$, and $z$.
