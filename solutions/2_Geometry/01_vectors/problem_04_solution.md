# Problem 4: Dot Product and Perpendicularity

## Question

For $u=(1,2,-1)$ and $v=(2,-1,3)$ compute $u\cdot v$ and determine whether the vectors are perpendicular. Then find $a$ so that $w=(2,-1,a)$ is perpendicular to $u$, and check the result.

---

## Solution

### 1. Definition of the Dot Product and Orthogonality Criterion

For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, the algebraic dot product (scalar product) is defined as the sum of the products of their corresponding coordinates:

$$
u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3
$$

Geometrically, the dot product is related to the angle $\theta \in [0, \pi]$ between the vectors by:

$$
u \cdot v = \|u\|\,\|v\| \cos\theta
$$

For nonzero vectors $u$ and $v$, $\cos\theta = 0$ if and only if $\theta = \frac{\pi}{2} = 90^\circ$. This gives the fundamental **orthogonality (perpendicularity) criterion**:

$$
u \perp v \iff u \cdot v = 0
$$

---

### 2. Computation of $u \cdot v$ and Perpendicularity Test

Given $u = (1, 2, -1)$ and $v = (2, -1, 3)$:

$$
\begin{aligned}
u \cdot v &= (1)(2) + (2)(-1) + (-1)(3) \\
          &= 2 - 2 - 3 \\
          &= -3
\end{aligned}
$$

**Conclusion:**
Since $u \cdot v = -3 \neq 0$, the vectors $u$ and $v$ are **not perpendicular**. (Furthermore, because $u \cdot v < 0$, the angle between $u$ and $v$ is obtuse, i.e., $\theta > 90^\circ$.)

---

### 3. Finding Parameter $a$ so that $w \perp u$

We are given $w = (2, -1, a)$ and $u = (1, 2, -1)$. For $w$ to be perpendicular to $u$, their dot product must vanish:

$$
u \cdot w = 0
$$

Expressing $u \cdot w$ in terms of $a$:

$$
\begin{aligned}
u \cdot w &= (1)(2) + (2)(-1) + (-1)(a) \\
          &= 2 - 2 - a \\
          &= -a
\end{aligned}
$$

Setting this equal to zero:

$$
-a = 0 \implies a = 0
$$

Therefore, the required value of the parameter is $a = 0$, which yields the vector:

$$
w = (2, -1, 0)
$$

---

### 4. Checking the Result

Substituting $a = 0$ gives $w = (2, -1, 0)$. We recompute the dot product $u \cdot w$ directly:

$$
\begin{aligned}
u \cdot w &= (1, 2, -1) \cdot (2, -1, 0) \\
          &= (1)(2) + (2)(-1) + (-1)(0) \\
          &= 2 - 2 + 0 \\
          &= 0
\end{aligned}
$$

Since $u \cdot w = 0$ and both $u$ and $w$ are nonzero vectors, $w = (2, -1, 0)$ is indeed perpendicular to $u$.

---

## Verification and Consistency Checks

### Check: Pythagorean Theorem in $\mathbb{R}^3$

Two vectors $u$ and $w$ are perpendicular if and only if they satisfy the Pythagorean identity:

$$
\|u - w\|^2 = \|u\|^2 + \|w\|^2
$$

Let us compute each squared norm independently:

- Squared length of $u = (1, 2, -1)$:

$$
\|u\|^2 = 1^2 + 2^2 + (-1)^2 = 1 + 4 + 1 = 6
$$

- Squared length of $w = (2, -1, 0)$:

$$
\|w\|^2 = 2^2 + (-1)^2 + 0^2 = 4 + 1 + 0 = 5
$$

- Difference vector $u - w$:

$$
u - w = (1 - 2, \; 2 - (-1), \; -1 - 0) = (-1, 3, -1)
$$

- Squared length of $u - w$:

$$
\|u - w\|^2 = (-1)^2 + 3^2 + (-1)^2 = 1 + 9 + 1 = 11
$$

Comparing the two sides:

$$
\|u\|^2 + \|w\|^2 = 6 + 5 = 11 = \|u - w\|^2
$$

The Pythagorean theorem holds with equality, providing an independent geometric confirmation that $u \perp w$.

---

## Why This Exercise Matters

- **Dual Role of the Dot Product:** In the first part, the dot product serves as a *diagnostic test* ($u \cdot v \neq 0$). In the second part, it serves as a *constructive equation* ($u \cdot w = 0$) to solve for an unknown coordinate.
- **Equation of a Plane:** The condition $u \cdot (x, y, z) = x + 2y - z = 0$ defines the entire plane of vectors perpendicular to $u = (1, 2, -1)$ passing through the origin. Choosing $x = 2$ and $y = -1$ uniquely forces $z = a = 0$ to lie on that plane.
