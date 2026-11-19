# Problem 13: Closest Point on a Plane

## Question

Find the point on the plane $x+2y+2z=4$ closest to $P=(3,0,0)$. Give the distance and check that the segment joining the two points is perpendicular to the plane.

---

## Solution

### 1. Geometric Strategy: Orthogonal Projection via the Normal Line

By the Pythagorean theorem, the unique point $Q$ on a plane $\Pi$ that minimizes the distance to an external point $P$ is the orthogonal projection of $P$ onto $\Pi$ (the foot of the perpendicular dropped from $P$ to $\Pi$).

From the plane equation $\Pi: 1x + 2y + 2z = 4$, we read off the normal vector:

$$
n = (1, 2, 2)
$$

The normal line $L$ passing through $P = (3, 0, 0)$ in the direction perpendicular to $\Pi$ has the parametric equation:

$$
(x, y, z) = P + t n = (3, 0, 0) + t(1, 2, 2)
$$

In coordinate form:

$$
\begin{cases}
x = 3 + t, \\
y = 2t, \\
z = 2t.
\end{cases}
$$

---

### 2. Finding the Closest Point $Q$ on the Plane

We find where the normal line intersects the plane $x + 2y + 2z = 4$ by substituting $x = 3 + t$, $y = 2t$, and $z = 2t$ into the plane equation:

$$
(3 + t) + 2(2t) + 2(2t) = 4
$$

Simplifying and solving for $t$:

$$
\begin{aligned}
3 + t + 4t + 4t &= 4 \\
3 + 9t &= 4 \\
9t &= 4 - 3 \\
9t &= 1 \\
t &= \frac{1}{9}
\end{aligned}
$$

Substituting $t = \frac{1}{9}$ back into the parametric equation of the normal line gives the closest point $Q$:

$$
\begin{aligned}
Q &= (3, 0, 0) + \frac{1}{9}(1, 2, 2) \\
  &= \left( 3 + \frac{1}{9}, \frac{2}{9}, \frac{2}{9} \right) \\
  &= \left( \frac{28}{9}, \frac{2}{9}, \frac{2}{9} \right)
\end{aligned}
$$

---

### 3. Computing the Minimum Distance

The minimum distance from $P = (3, 0, 0)$ to the plane $\Pi$ is the Euclidean length of the vector $\overrightarrow{PQ} = Q - P$:

$$
\overrightarrow{PQ} = Q - P = \left( \frac{28}{9} - 3, \frac{2}{9} - 0, \frac{2}{9} - 0 \right) = \left( \frac{1}{9}, \frac{2}{9}, \frac{2}{9} \right) = \frac{1}{9}(1, 2, 2)
$$

Taking the Euclidean length of $\overrightarrow{PQ}$:

$$
\begin{aligned}
\|\overrightarrow{PQ}\| &= \frac{1}{9} \sqrt{1^2 + 2^2 + 2^2} \\
                        &= \frac{1}{9} \sqrt{1 + 4 + 4} \\
                        &= \frac{1}{9} \sqrt{9} \\
                        &= \frac{3}{9} \\
                        &= \frac{1}{3}
\end{aligned}
$$

---

### 4. Checking that $Q$ Lies on the Plane and $PQ$ Is Perpendicular to the Plane

#### Check 1: Point $Q$ lies on the plane

Substituting the coordinates of $Q = \left(\frac{28}{9}, \frac{2}{9}, \frac{2}{9}\right)$ into $x + 2y + 2z$:

$$
\begin{aligned}
x + 2y + 2z &= \frac{28}{9} + 2\left(\frac{2}{9}\right) + 2\left(\frac{2}{9}\right) \\
            &= \frac{28 + 4 + 4}{9} \\
            &= \frac{36}{9} \\
            &= 4
\end{aligned}
$$

The point $Q$ lies on the plane $x + 2y + 2z = 4$.

#### Check 2: The segment $PQ$ is perpendicular to the plane

A segment is perpendicular to a plane if and only if its displacement vector $\overrightarrow{PQ}$ is parallel to the plane's normal vector $n = (1, 2, 2)$ (or equivalently, perpendicular to two linearly independent vectors lying in the plane).

First, comparing $\overrightarrow{PQ}$ directly with the normal vector $n$:

$$
\overrightarrow{PQ} = \left( \frac{1}{9}, \frac{2}{9}, \frac{2}{9} \right) = \frac{1}{9}(1, 2, 2) = \frac{1}{9} n
$$

Second, testing the dot product with two linearly independent vectors lying in the plane $x + 2y + 2z = 4$, namely $w_1 = (-2, 1, 0)$ and $w_2 = (-2, 0, 1)$:

$$
\overrightarrow{PQ} \cdot w_1 = \left(\frac{1}{9}\right)(-2) + \left(\frac{2}{9}\right)(1) + \left(\frac{2}{9}\right)(0) = -\frac{2}{9} + \frac{2}{9} = 0
$$

$$
\overrightarrow{PQ} \cdot w_2 = \left(\frac{1}{9}\right)(-2) + \left(\frac{2}{9}\right)(0) + \left(\frac{2}{9}\right)(1) = -\frac{2}{9} + \frac{2}{9} = 0
$$

Because $\overrightarrow{PQ}$ is perpendicular to two linearly independent directions in the plane, the segment $PQ$ is perpendicular to the plane.

---

## Verification and Consistency Checks

### Independent Distance Check Using the Point-to-Plane Distance Formula

Applying the distance formula to $P = (3, 0, 0)$ and $x + 2y + 2z - 4 = 0$:

$$
\begin{aligned}
d &= \frac{|1(3) + 2(0) + 2(0) - 4|}{\sqrt{1^2 + 2^2 + 2^2}} \\
  &= \frac{|-1|}{\sqrt{9}} \\
  &= \frac{1}{3}
\end{aligned}
$$

This matches our vector length calculation $\frac{1}{3}$.

---

## Why This Exercise Matters

- **Optimization via Geometry:** Finding the closest point on a plane $x + 2y + 2z = 4$ to $(3, 0, 0)$ minimizes the distance function $f(x, y, z) = \sqrt{(x - 3)^2 + y^2 + z^2}$ subject to $x + 2y + 2z = 4$. Using the normal vector solves this 3D constrained optimization problem without any calculus or partial derivatives.
