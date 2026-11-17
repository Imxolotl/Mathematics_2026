# Problem 10: Projection of a Point onto a Plane

## Question

Find the orthogonal projection of $P=(2,1,3)$ onto the plane $x+y+z=3$, and then find the reflection of $P$ across this plane. Check that the midpoint of the segment joining the point and its reflection lies on the plane.

---

## Solution

### 1. Constructing the Normal Line Through $P$

Let $\Pi$ denote the plane $x + y + z = 3$. Its normal vector is read directly from the coefficients of $x, y, z$:

$$
n = (1, 1, 1)
$$

To find the orthogonal projection $P'$ of $P = (2, 1, 3)$ onto $\Pi$, we drop a perpendicular line $L_{\perp}$ from $P$ to the plane. Because $L_{\perp}$ is perpendicular to $\Pi$, its direction vector is the normal vector $n = (1, 1, 1)$:

$$
L_{\perp}: (x, y, z) = P + t n = (2, 1, 3) + t(1, 1, 1), \qquad t \in \mathbb{R}
$$

In coordinate parametric form:

$$
\begin{cases}
x = 2 + t, \\
y = 1 + t, \\
z = 3 + t,
\end{cases}
\qquad t \in \mathbb{R}
$$

---

### 2. Finding the Orthogonal Projection $P'$

The orthogonal projection $P'$ is the intersection point of the normal line $L_{\perp}$ with the plane $x + y + z = 3$. Substituting $x(t), y(t), z(t)$ into the plane equation:

$$
(2 + t) + (1 + t) + (3 + t) = 3
$$

Grouping terms and solving for $t$:

$$
\begin{aligned}
6 + 3t &= 3 \\
3t &= 3 - 6 \\
3t &= -3 \\
t &= -1
\end{aligned}
$$

Substituting $t = -1$ back into the equation of $L_{\perp}$ gives the orthogonal projection $P'$:

$$
\begin{aligned}
P' &= (2, 1, 3) + (-1)(1, 1, 1) \\
   &= (2 - 1, \; 1 - 1, \; 3 - 1) \\
   &= (1, 0, 2)
\end{aligned}
$$

Thus, the orthogonal projection of $P$ onto the plane is:

$$
P' = (1, 0, 2)
$$

---

### 3. Finding the Reflection $P''$ of $P$ Across the Plane

The displacement vector from $P$ to its orthogonal projection $P'$ on the plane is:

$$
\overrightarrow{PP'} = P' - P = (1 - 2, \; 0 - 1, \; 2 - 3) = (-1, -1, -1)
$$

Reflecting $P$ across the mirror plane $\Pi$ means moving from $P$ to $P'$ on the plane, and then continuing by the **exact same displacement** $\overrightarrow{PP'}$ to the opposite side of the plane (corresponding to $t = 2(-1) = -2$ along $L_{\perp}$):

$$
\begin{aligned}
P'' &= P + 2\overrightarrow{PP'} \\
    &= P' + \overrightarrow{PP'} \\
    &= 2P' - P
\end{aligned}
$$

Computing the coordinates of $P''$:

$$
\begin{aligned}
P'' &= 2(1, 0, 2) - (2, 1, 3) \\
    &= (2, 0, 4) - (2, 1, 3) \\
    &= (2 - 2, \; 0 - 1, \; 4 - 3) \\
    &= (0, -1, 1)
\end{aligned}
$$

Thus, the reflection of $P$ across the plane is:

$$
P'' = (0, -1, 1)
$$

---

### 4. Checking that the Midpoint Lies on the Plane

The midpoint $M$ of the segment joining $P = (2, 1, 3)$ and its reflection $P'' = (0, -1, 1)$ is given by the average of their coordinates:

$$
\begin{aligned}
M &= \frac{P + P''}{2} \\
  &= \left( \frac{2 + 0}{2}, \; \frac{1 + (-1)}{2}, \; \frac{3 + 1}{2} \right) \\
  &= \left( \frac{2}{2}, \; \frac{0}{2}, \; \frac{4}{2} \right) \\
  &= (1, 0, 2)
\end{aligned}
$$

Notice that $M = (1, 0, 2) = P'$ is precisely the orthogonal projection point found in Step 2.

Substituting $M = (1, 0, 2)$ into the plane equation $x + y + z = 3$:

$$
1 + 0 + 2 = 3
$$

The equation is satisfied ($3 = 3$), confirming that the midpoint $M$ of the segment $PP''$ lies on the plane.

---

## Verification and Consistency Checks

### Check 1: Perpendicularity of Segment $PP''$ to the Plane

The vector connecting $P = (2, 1, 3)$ to its reflection $P'' = (0, -1, 1)$ is:

$$
\overrightarrow{PP''} = P'' - P = (0 - 2, \; -1 - 1, \; 1 - 3) = (-2, -2, -2) = -2(1, 1, 1) = -2n
$$

Because $\overrightarrow{PP''}$ is a scalar multiple of the normal vector $n = (1, 1, 1)$, the segment $PP''$ is perpendicular to the plane $\Pi$.

### Check 2: Equal Distances from $P$ and $P''$ to the Plane

Using the point-to-plane distance formula $d(X, \Pi) = \frac{|x + y + z - 3|}{\sqrt{1^2 + 1^2 + 1^2}}$:

- Distance from $P = (2, 1, 3)$ to $\Pi$:

$$
d(P, \Pi) = \frac{|2 + 1 + 3 - 3|}{\sqrt{3}} = \frac{|3|}{\sqrt{3}} = \sqrt{3}
$$

- Distance from $P'' = (0, -1, 1)$ to $\Pi$:

$$
d(P'', \Pi) = \frac{|0 + (-1) + 1 - 3|}{\sqrt{3}} = \frac{|-3|}{\sqrt{3}} = \sqrt{3}
$$

Both $P$ and $P''$ lie at the exact same distance $\sqrt{3}$ from the plane, on opposite sides (since $2 + 1 + 3 - 3 = +3$ and $0 - 1 + 1 - 3 = -3$ have opposite signs).

---

## Why This Exercise Matters

- **Unified Construction for Projection and Reflection:** Once the parameter $t_0$ for the orthogonal projection $P' = P + t_0 n$ is found, the reflection is obtained immediately by doubling the step: $P'' = P + 2t_0 n$.
- **Geometric Characterization of Reflection:** A point $P''$ is the reflection of $P$ across a plane $\Pi$ if and only if two conditions hold simultaneously:
  1. The segment $PP''$ is perpendicular to $\Pi$ ($\overrightarrow{PP''} \parallel n$).
  2. The midpoint $M = \frac{P + P''}{2}$ lies on $\Pi$.
