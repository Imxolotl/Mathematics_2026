# Problem 6: Projection and Perpendicular Component

## Question

Find the projection of $u=(4,2)$ onto the direction $v=(1,1)$. Then compute

$$
r=u-\mathrm{proj}_v\,u
$$

and verify that $r\cdot v=0$. Explain this result geometrically.

---

## Solution

### 1. Orthogonal Projection Formula

For a vector $u$ and a nonzero direction vector $v$, the orthogonal projection of $u$ onto $v$ is defined by:

$$
\mathrm{proj}_v\,u = \frac{u \cdot v}{v \cdot v} v = \frac{u \cdot v}{\|v\|^2} v
$$

---

### 2. Computation of $\mathrm{proj}_v\,u$

Given $u = (4, 2)$ and $v = (1, 1)$:

1. **Compute the dot product $u \cdot v$:**

$$
u \cdot v = (4)(1) + (2)(1) = 4 + 2 = 6
$$

2. **Compute the squared norm $v \cdot v = \|v\|^2$:**

$$
v \cdot v = (1)(1) + (1)(1) = 1 + 1 = 2
$$

3. **Substitute into the projection formula:**

$$
\begin{aligned}
\mathrm{proj}_v\,u &= \frac{6}{2} (1, 1) \\
                   &= 3(1, 1) \\
                   &= (3, 3)
\end{aligned}
$$

---

### 3. Computation of the Residual Vector $r = u - \mathrm{proj}_v\,u$

Subtracting the projection $\mathrm{proj}_v\,u = (3, 3)$ from $u = (4, 2)$:

$$
\begin{aligned}
r &= u - \mathrm{proj}_v\,u \\
  &= (4, 2) - (3, 3) \\
  &= (4 - 3, \; 2 - 3) \\
  &= (1, -1)
\end{aligned}
$$

---

### 4. Verification that $r \cdot v = 0$

We compute the dot product of $r = (1, -1)$ and $v = (1, 1)$:

$$
\begin{aligned}
r \cdot v &= (1, -1) \cdot (1, 1) \\
          &= (1)(1) + (-1)(1) \\
          &= 1 - 1 \\
          &= 0
\end{aligned}
$$

Since $r \cdot v = 0$, the vector $r$ is orthogonal (perpendicular) to $v$.

We can also see why this holds algebraically for any vectors $u$ and $v \neq 0$:

$$
\begin{aligned}
r \cdot v &= \left( u - \frac{u \cdot v}{v \cdot v} v \right) \cdot v \\
          &= u \cdot v - \frac{u \cdot v}{v \cdot v} (v \cdot v) \\
          &= u \cdot v - u \cdot v \\
          &= 0
\end{aligned}
$$

---

### 5. Geometric Explanation

Geometrically, this calculation decomposes the vector $u = (4, 2)$ into two mutually perpendicular components relative to the line $L$ spanned by $v = (1, 1)$ (the diagonal line $y = x$ in $\mathbb{R}^2$):

1. **Parallel Component ($\mathrm{proj}_v\,u = (3, 3)$):**
   Imagine shining a light perpendicular to the line $y = x$. The vector $\mathrm{proj}_v\,u = (3, 3)$ is the orthogonal shadow of $u$ cast onto the line spanned by $v$. Because $\mathrm{proj}_v\,u = 3v$, it lies strictly along the line of $v$.

2. **Perpendicular Component ($r = (1, -1)$):**
   The vector $r = u - \mathrm{proj}_v\,u$ points from the tip of the shadow at $(3, 3)$ on the line $y = x$ directly to the tip of $u$ at $(4, 2)$. By the definition of an orthogonal projection (dropping an altitude from $(4, 2)$ onto the line $y = x$), this connecting segment must meet the line at a $90^\circ$ right angle, which is what $r \cdot v = 0$ expresses.

3. **Right-Triangle Decomposition ($u = \mathrm{proj}_v\,u + r$):**
   The vectors $\mathrm{proj}_v\,u$ and $r$ form the two perpendicular legs of a right triangle whose hypotenuse is $u$:

$$
u = \mathrm{proj}_v\,u + r = (3, 3) + (1, -1) = (4, 2)
$$

---

## Verification and Consistency Checks

### Check: Pythagorean Theorem for Orthogonal Decomposition

Because $\mathrm{proj}_v\,u$ and $r$ are perpendicular ($(\mathrm{proj}_v\,u) \cdot r = 3(r \cdot v) = 0$), their squared lengths must sum to the squared length of the hypotenuse $u$:

$$
\|\mathrm{proj}_v\,u\|^2 + \|r\|^2 = \|u\|^2
$$

Computing each term:
- $\|\mathrm{proj}_v\,u\|^2 = 3^2 + 3^2 = 9 + 9 = 18$
- $\|r\|^2 = 1^2 + (-1)^2 = 1 + 1 = 2$
- $\|u\|^2 = 4^2 + 2^2 = 16 + 4 = 20$

Checking the sum:

$$
18 + 2 = 20
$$

The equality holds, confirming both the projection $(3, 3)$ and the perpendicular residual $(1, -1)$.

---

## Why This Exercise Matters

- **Orthogonal Decomposition:** Breaking a vector into a component parallel to a reference direction and a component perpendicular to it is fundamental in physics (e.g., decomposing gravity on an inclined plane into tangential and normal forces).
- **Least-Squares Approximation:** The point $\mathrm{proj}_v\,u = (3, 3)$ is the point on the line spanned by $v$ closest to $u$, and $\|r\| = \sqrt{2}$ is the minimum distance from $(4, 2)$ to the line $y = x$.
- **Gram–Schmidt Orthogonalization:** Subtracting $\mathrm{proj}_v\,u$ from $u$ to produce a vector $r \perp v$ is the exact mechanism used to construct orthogonal bases in linear algebra.
