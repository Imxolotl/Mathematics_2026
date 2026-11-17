# Problem 5: Angle Between Vectors

## Question

Given $u=(1,1,0)$ and $v=(1,0,1)$:

1. Use the sign of $u\cdot v$ to predict the type of angle.
2. Compute the angle.
3. Compare the result with the prediction.

---

## Solution

### 1. Qualitative Prediction from the Sign of $u \cdot v$

From the geometric formula for the dot product of two nonzero vectors,

$$
u \cdot v = \|u\|\,\|v\| \cos\theta, \qquad \theta \in [0, \pi]
$$

because the lengths $\|u\| > 0$ and $\|v\| > 0$ are always strictly positive, the sign of $\cos\theta$ is identical to the sign of $u \cdot v$:

- If $u \cdot v > 0$, then $\cos\theta > 0$, so $0^\circ \le \theta < 90^\circ$ (**acute angle**).
- If $u \cdot v = 0$, then $\cos\theta = 0$, so $\theta = 90^\circ$ (**right angle**).
- If $u \cdot v < 0$, then $\cos\theta < 0$, so $90^\circ < \theta \le 180^\circ$ (**obtuse angle**).

Now we compute the dot product of $u = (1, 1, 0)$ and $v = (1, 0, 1)$:

$$
\begin{aligned}
u \cdot v &= (1)(1) + (1)(0) + (0)(1) \\
          &= 1 + 0 + 0 \\
          &= 1
\end{aligned}
$$

**Prediction:**
Since $u \cdot v = 1 > 0$, and $u$ and $v$ are not scalar multiples of each other, the angle $\theta$ between $u$ and $v$ must be **strictly acute** ($0^\circ < \theta < 90^\circ$).

---

### 2. Exact Computation of the Angle $\theta$

#### Step 1: Compute the lengths $\|u\|$ and $\|v\|$

For $u = (1, 1, 0)$:

$$
\|u\| = \sqrt{1^2 + 1^2 + 0^2} = \sqrt{1 + 1 + 0} = \sqrt{2}
$$

For $v = (1, 0, 1)$:

$$
\|v\| = \sqrt{1^2 + 0^2 + 1^2} = \sqrt{1 + 0 + 1} = \sqrt{2}
$$

#### Step 2: Compute $\cos\theta$

Substituting $u \cdot v = 1$, $\|u\| = \sqrt{2}$, and $\|v\| = \sqrt{2}$ into the cosine formula:

$$
\begin{aligned}
\cos\theta &= \frac{u \cdot v}{\|u\|\,\|v\|} \\
           &= \frac{1}{\sqrt{2} \cdot \sqrt{2}} \\
           &= \frac{1}{2}
\end{aligned}
$$

#### Step 3: Determine $\theta$

Since $\theta \in [0, \pi]$ and $\cos\theta = \frac{1}{2}$:

$$
\theta = \arccos\left(\frac{1}{2}\right) = \frac{\pi}{3}\,\mathrm{rad} = 60^\circ
$$

---

### 3. Comparison with the Prediction

- **Predicted angle type:** Acute ($0^\circ < \theta < 90^\circ$).
- **Computed angle:** $\theta = 60^\circ$ ($\frac{\pi}{3}$ radians).
- **Comparison:** Because $0^\circ < 60^\circ < 90^\circ$, the exact calculation is in complete agreement with our initial qualitative prediction.

---

## Verification and Consistency Checks

### Geometric Check: Equilateral Triangle on the Unit Cube

Consider the triangle in $\mathbb{R}^3$ with vertices at the origin $O = (0, 0, 0)$, the tip of $u$ at $U = (1, 1, 0)$, and the tip of $v$ at $V = (1, 0, 1)$:

1. Length of side $OU$:

$$
\|u\| = \sqrt{2}
$$

2. Length of side $OV$:

$$
\|v\| = \sqrt{2}
$$

3. Length of the third side $UV$, represented by the difference vector $u - v = (1 - 1, \; 1 - 0, \; 0 - 1) = (0, 1, -1)$:

$$
\|u - v\| = \sqrt{0^2 + 1^2 + (-1)^2} = \sqrt{2}
$$

All three sides of triangle $\triangle OUV$ have equal length $\sqrt{2}$ (each side is a face diagonal of the unit cube $[0, 1]^3$ meeting at the origin). Therefore, $\triangle OUV$ is an **equilateral triangle**, which immediately guarantees that the angle at vertex $O$ between $u$ and $v$ is:

$$
\theta = 60^\circ = \frac{\pi}{3}\,\mathrm{rad}
$$

---

## Why This Exercise Matters

- **Fast Sanity Checking:** Computing $u \cdot v$ requires only multiplication and addition (no square roots or inverse trigonometric functions). Checking its sign first prevents common sign mistakes in angle calculations.
- **3D Spatial Intuition:** Even though $u = (1, 1, 0)$ lies in the $xy$-plane and $v = (1, 0, 1)$ lies in the $xz$-plane (two perpendicular coordinate planes), the vectors themselves are **not** perpendicular because they share a common positive $x$-component ($u_1 = v_1 = 1$), pulling them closer together to a $60^\circ$ angle.
