# Problem 6: Angle Between Planes

## Question

Given

$$
\Pi_1:x+y+z=1,\qquad \Pi_2:x-y=2.
$$

First use the normal vectors to decide whether the planes are parallel. If not, compute the angle between them and explain why the normal vectors alone are enough for this calculation.

---

## Solution

### 1. Reading Off the Normal Vectors

For a plane written in general form $Ax + By + Cz = D$, the vector of coefficients $n = (A, B, C)$ is a normal vector perpendicular to the plane:

- **For $\Pi_1: 1x + 1y + 1z = 1$:**

$$
n_1 = (1, 1, 1)
$$

- **For $\Pi_2: 1x - 1y + 0z = 2$:**

$$
n_2 = (1, -1, 0)
$$

---

### 2. Deciding Whether the Planes Are Parallel

Two planes $\Pi_1$ and $\Pi_2$ are parallel if and only if their normal vectors $n_1$ and $n_2$ are collinear (proportional), meaning $n_1 = \lambda n_2$ for some nonzero scalar $\lambda \in \mathbb{R}$.

Comparing $n_1 = (1, 1, 1)$ and $n_2 = (1, -1, 0)$:
- Matching the first coordinates requires $\lambda = 1$.
- However, $1 \cdot n_2 = (1, -1, 0) \neq (1, 1, 1) = n_1$ (the second and third coordinates do not match).

Because $n_1$ is not a scalar multiple of $n_2$, the normal vectors point in different directions. Therefore, the planes $\Pi_1$ and $\Pi_2$ are **not parallel**; they must intersect along a line.

---

### 3. Computing the Angle Between the Planes

The dihedral angle $\theta \in \left[0, \frac{\pi}{2}\right]$ between two planes $\Pi_1$ and $\Pi_2$ is given by the acute angle between their normal vectors $n_1$ and $n_2$:

$$
\cos\theta = \frac{|n_1 \cdot n_2|}{\|n_1\|\,\|n_2\|}
$$

#### Step 1: Compute the dot product $n_1 \cdot n_2$

$$
\begin{aligned}
n_1 \cdot n_2 &= (1, 1, 1) \cdot (1, -1, 0) \\
              &= (1)(1) + (1)(-1) + (1)(0) \\
              &= 1 - 1 + 0 \\
              &= 0
\end{aligned}
$$

#### Step 2: Compute $\cos\theta$ and $\theta$

For completeness, the norms of the normal vectors are:

$$
\|n_1\| = \sqrt{1^2 + 1^2 + 1^2} = \sqrt{3}, \qquad \|n_2\| = \sqrt{1^2 + (-1)^2 + 0^2} = \sqrt{2}
$$

Since $n_1 \cdot n_2 = 0$:

$$
\cos\theta = \frac{|0|}{\sqrt{3} \cdot \sqrt{2}} = 0
$$

Therefore, the angle between the planes is:

$$
\theta = \arccos(0) = \frac{\pi}{2}\,\mathrm{rad} = 90^\circ
$$

The planes $\Pi_1$ and $\Pi_2$ are **mutually perpendicular (orthogonal)**.

---

### 4. Explanation: Why the Normal Vectors Alone Are Enough

1. **90-Degree Rotation in the Cross-Sectional Plane:**
   When two planes intersect along a line $L$, the dihedral angle $\theta$ between them is measured in any plane $\Sigma$ perpendicular to $L$. Both normal vectors $n_1$ and $n_2$ are perpendicular to $L$, so they lie inside this cross-sectional plane $\Sigma$. Within $\Sigma$, $n_1$ is rotated by $90^\circ$ from $\Pi_1$ and $n_2$ is rotated by $90^\circ$ from $\Pi_2$. Rotating two lines in a plane by the same angle ($90^\circ$) leaves the angle between them completely unchanged.

2. **Independence from Translation (Right-Hand Side Constants):**
   The constants on the right-hand side ($1$ in $\Pi_1$ and $2$ in $\Pi_2$) only shift the planes parallel to themselves without changing their tilt. Because parallel translation does not alter angles, the angle between $\Pi_1$ and $\Pi_2$ depends solely on the normal vectors $n_1$ and $n_2$, without needing to find any points on the planes or the equation of their line of intersection.

---

## Verification and Consistency Checks

### Geometric Check: Finding In-Plane Directions

On $\Pi_2: x - y = 2$, the $z$-coordinate is completely free, so the vertical unit vector $e_3 = (0, 0, 1)$ lies along $\Pi_2$, and the horizontal vector $u_2 = (1, 1, 0)$ also lies along $\Pi_2$ (since $1 - 1 = 0$).

Notice that the normal to $\Pi_1$, $n_1 = (1, 1, 1) = (1, 1, 0) + (0, 0, 1) = u_2 + e_3$, is a linear combination of two vectors lying inside $\Pi_2$! Because $\Pi_2$ contains the normal vector $n_1$ of $\Pi_1$, the plane $\Pi_2$ is perpendicular to $\Pi_1$ ($\theta = 90^\circ$).

---

## Why This Exercise Matters

- **Reduction of 3D Plane Problems to 1D Normal Vectors:** Measuring the angle between two two-dimensional surfaces in $\mathbb{R}^3$ reduces immediately to computing a single dot product between their one-dimensional normal vectors.
- **Zero Dot Product Shortcut:** Whenever $n_1 \cdot n_2 = 0$, we immediately conclude that the planes are perpendicular ($\theta = 90^\circ$) without even needing to evaluate $\|n_1\|$ or $\|n_2\|$.
