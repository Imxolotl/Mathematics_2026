# Problem 13: Intersection of a Sphere and a Plane

## Question

Given the sphere

$$
x^2+y^2+z^2=25
$$

and the plane $z=3$, find the equation of the intersection curve and its radius. Then describe what happens for $z=c$ depending on $c$.

---

## Solution

### 1. Equation and Radius of the Intersection Curve for $z = 3$

The sphere $x^2 + y^2 + z^2 = 25 = 5^2$ is centered at the origin $O = (0, 0, 0)$ and has radius $R = 5$.

To find its intersection with the horizontal plane $z = 3$, we substitute $z = 3$ into the sphere's equation:

$$
\begin{aligned}
x^2 + y^2 + 3^2 &= 25 \\
x^2 + y^2 + 9 &= 25 \\
x^2 + y^2 &= 25 - 9 \\
x^2 + y^2 &= 16
\end{aligned}
$$

In three-dimensional space $\mathbb{R}^3$, the intersection curve is completely specified by the system of two equations:

$$
\begin{cases}
x^2 + y^2 = 16, \\
z = 3.
\end{cases}
$$

- **Geometric Description:** This curve is a circle lying in the horizontal plane $z = 3$, centered on the $z$-axis at $C = (0, 0, 3)$.
- **Radius of the Intersection Circle:**

$$
r = \sqrt{16} = 4
$$

#### Geometric Right-Triangle Interpretation

For any point $P = (x, y, 3)$ on the intersection circle, the sphere's center $O = (0, 0, 0)$, the circle's center $C = (0, 0, 3)$, and the point $P$ form a right triangle with right angle at $C$:
- Hypotenuse (sphere radius): $R = 5$
- Vertical leg (distance from $O$ to the plane $z = 3$): $h = 3$
- Horizontal leg (circle radius):

$$
r = \sqrt{R^2 - h^2} = \sqrt{5^2 - 3^2} = \sqrt{25 - 9} = \sqrt{16} = 4
$$

---

### 2. General Analysis for the Plane $z = c$ Depending on $c$

Substituting $z = c$ ($c \in \mathbb{R}$) into the sphere equation $x^2 + y^2 + z^2 = 25$ yields:

$$
x^2 + y^2 = 25 - c^2, \qquad z = c
$$

Because $x^2 + y^2 \ge 0$ for all real $(x, y)$, the nature of the intersection depends on the sign of $25 - c^2$, giving three distinct cases.

#### Case 1: $c^2 < 25$ ($-5 < c < 5$) — Circle of Positive Radius

When $|c| < 5$, we have $c^2 < 25$, so $25 - c^2 > 0$. The plane cuts through the interior of the sphere, and the intersection is a circle in the plane $z = c$ centered at $(0, 0, c)$ with radius:

$$
r(c) = \sqrt{25 - c^2} > 0
$$

- **At $c = 0$ (the equator):** The radius achieves its maximum value $r(0) = \sqrt{25 - 0} = 5 = R$ (a great circle of the sphere).
- **As $|c|$ increases from $0$ toward $5$:** The radius $r(c) = \sqrt{25 - c^2}$ shrinks monotonically from $5$ toward $0$ (for example, at $c = \pm 3$, $r(\pm 3) = 4$; at $c = \pm 4$, $r(\pm 4) = 3$).

#### Case 2: $c^2 = 25$ ($c = 5$ or $c = -5$) — Single Point (Tangency)

When $c = 5$ or $c = -5$, we have $c^2 = 25$, so the equation becomes:

$$
x^2 + y^2 = 0
$$

Because $x^2 + y^2 = 0$ holds only when $(x, y) = (0, 0)$, the intersection reduces to a single point (a degenerate circle of radius $r(\pm 5) = 0$):
- For $c = 5$: the north pole $(0, 0, 5)$, where the plane $z = 5$ is tangent to the top of the sphere.
- For $c = -5$: the south pole $(0, 0, -5)$, where the plane $z = -5$ is tangent to the bottom of the sphere.

#### Case 3: $c^2 > 25$ ($|c| > 5$) — Empty Set (No Intersection)

When $|c| > 5$, we have $c^2 > 25$, so the right-hand side is strictly negative:

$$
x^2 + y^2 = 25 - c^2 < 0
$$

Because a sum of two real squares $x^2 + y^2 \ge 0$ cannot equal a negative number, there are no real points satisfying the equation. Geometrically, the plane $z = c$ lies at a distance $|c| > 5 = R$ from the center of the sphere, so it passes completely above ($c > 5$) or below ($c < -5$) the sphere without touching it.

---

## Summary Table of Cross-Sections $z = c$

| Range of $c$ | Sign of $25 - c^2$ | Geometric Intersection in $z = c$ | Radius $r(c)$ |
| :--- | :--- | :--- | :--- |
| $c = 0$ | $25 > 0$ | Great circle (equator) centered at $(0,0,0)$ | $r(0) = 5$ (maximum) |
| $0 < c^2 < 25$ | $25 - c^2 > 0$ | Circle centered at $(0, 0, c)$ | $r(c) = \sqrt{25 - c^2}$ |
| $c^2 = 25$ ($c = \pm 5$) | $25 - c^2 = 0$ | Single tangent point $(0, 0, \pm 5)$ | $r(\pm 5) = 0$ |
| $c^2 > 25$ | $25 - c^2 < 0$ | Empty set (plane misses sphere) | Does not exist |

---

## Why This Exercise Matters

- **Algebraic Criterion for Sphere–Plane Relative Position:** A plane at distance $d = |c|$ from the center of a sphere of radius $R$ intersects the sphere in a circle of radius $\sqrt{R^2 - d^2}$ if $d < R$, is tangent at a single point if $d = R$, and is disjoint from the sphere if $d > R$.
