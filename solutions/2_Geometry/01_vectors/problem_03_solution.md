# Problem 3: Vector Normalization

## Question

For $v=(3,4)$ find a unit vector $e$ with the same direction and orientation. Check that $\|e\|=1$, reconstruct $v$ in the form $v=\|v\|e$, and explain what changes during normalization and what remains unchanged.

---

## Solution

### 1. Computation of the Length $\|v\|$

For a vector $v = (v_1, v_2) \in \mathbb{R}^2$, its Euclidean length (norm) is:

$$
\|v\| = \sqrt{v_1^2 + v_2^2}
$$

Substituting $v = (3, 4)$:

$$
\begin{aligned}
\|v\| &= \sqrt{3^2 + 4^2} \\
      &= \sqrt{9 + 16} \\
      &= \sqrt{25} \\
      &= 5
\end{aligned}
$$

Since $\|v\| = 5 \neq 0$, the vector is non-zero and can be normalized.

---

### 2. Finding the Unit Vector $e$ (Normalization)

To obtain a unit vector $e$ with the exact same direction and orientation as $v$, we divide $v$ by its positive length $\|v\|$ (equivalently, multiply $v$ by the positive scalar $\frac{1}{\|v\|}$):

$$
\begin{aligned}
e &= \frac{1}{\|v\|} v \\
  &= \frac{1}{5} (3, 4) \\
  &= \left( \frac{3}{5}, \; \frac{4}{5} \right) \\
  &= (0.6, \; 0.8)
\end{aligned}
$$

In column vector notation:

$$
e =
\begin{pmatrix}
\frac{3}{5} \\
\frac{4}{5} \\
\end{pmatrix}
$$

---

### 3. Checking that $\|e\| = 1$

We compute the Euclidean norm of $e = \left(\frac{3}{5}, \frac{4}{5}\right)$ directly from its coordinates:

$$
\begin{aligned}
\|e\| &= \sqrt{\left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2} \\
      &= \sqrt{\frac{9}{25} + \frac{16}{25}} \\
      &= \sqrt{\frac{9 + 16}{25}} \\
      &= \sqrt{\frac{25}{25}} \\
      &= \sqrt{1} \\
      &= 1
\end{aligned}
$$

This confirms that $e$ is a unit vector (it lies on the unit circle $x^2 + y^2 = 1$).

---

### 4. Reconstructing $v$ as $v = \|v\| e$

Multiplying the unit direction vector $e$ by the original magnitude $\|v\| = 5$:

$$
\begin{aligned}
\|v\| e &= 5 \left( \frac{3}{5}, \; \frac{4}{5} \right) \\
        &= \left( 5 \cdot \frac{3}{5}, \; 5 \cdot \frac{4}{5} \right) \\
        &= (3, 4) \\
        &= v
\end{aligned}
$$

This decomposition $v = \|v\| e$ cleanly separates the vector into two independent pieces of information:
- **Magnitude (scalar length):** $\|v\| = 5$
- **Pure direction (unit vector):** $e = \left(\frac{3}{5}, \frac{4}{5}\right)$

---

### 5. Explanation: What Changes and What Remains Unchanged

#### What Changes During Normalization:
1. **Length (Magnitude):** The length is rescaled from $\|v\| = 5$ to $\|e\| = 1$.
2. **Coordinate Values:** Both coordinates are scaled by the factor $\frac{1}{\|v\|} = \frac{1}{5}$, changing from $(3, 4)$ to $\left(\frac{3}{5}, \frac{4}{5}\right)$.

#### What Remains Unchanged During Normalization:
1. **Direction (Line of Action):** The ratio of the coordinates (the slope of the vector) is preserved:

$$
\frac{e_2}{e_1} = \frac{4/5}{3/5} = \frac{4}{3} = \frac{v_2}{v_1}
$$

2. **Orientation (Sense):** Because $\frac{1}{\|v\|} = \frac{1}{5} > 0$ is strictly positive, scalar multiplication does not flip the arrow. Both $v$ and $e$ point into the first quadrant at the exact same angle $\theta = \arctan\left(\frac{4}{3}\right) \approx 53.13^\circ$ from the positive $x$-axis.
3. **Direction Cosines:** The cosines of the angles that the vector makes with the coordinate axes are invariant: $\cos\alpha = \frac{3}{5}$ and $\cos\beta = \frac{4}{5}$.

---

## Verification and Consistency Checks

### Check: Alignment via the Cosine of the Angle Between $v$ and $e$

Using the dot product formula for the angle $\theta$ between $v$ and $e$:

$$
\begin{aligned}
\cos\theta &= \frac{v \cdot e}{\|v\|\,\|e\|} \\
           &= \frac{3\left(\frac{3}{5}\right) + 4\left(\frac{4}{5}\right)}{5 \cdot 1} \\
           &= \frac{\frac{9}{5} + \frac{16}{5}}{5} \\
           &= \frac{5}{5} \\
           &= 1
\end{aligned}
$$

Since $\cos\theta = 1$, the angle between $v$ and $e$ is $\theta = 0^\circ$, confirming that $e$ has the exact same direction and orientation as $v$.

---

## Why This Exercise Matters

- **Decoupling Magnitude and Direction:** Writing $v = \|v\| e$ is the vector analogue of writing a nonzero real number as $x = |x| \cdot \mathrm{sgn}(x)$.
- **Directional Derivatives and Projections:** In multivariable calculus and physics, unit vectors isolate pure direction so that rates of change or force components can be measured without being distorted by the length of the reference vector.
- **Orthonormal Bases:** Normalization is a core step in the Gram–Schmidt process for constructing orthonormal basis vectors.
