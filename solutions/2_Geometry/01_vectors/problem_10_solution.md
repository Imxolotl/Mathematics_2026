# Problem 10: Triangle Area from Vectors

## Question

The points $A=(0,0,0)$, $B=(2,1,0)$, and $C=(1,3,2)$ form a triangle. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$, compute the area of the parallelogram using the cross product, and then find the area of the triangle. Explain the factor $\frac12$.

---

## Solution

### 1. Construction of the Side Vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Given the vertices $A = (0, 0, 0)$, $B = (2, 1, 0)$, and $C = (1, 3, 2)$, we construct the two side vectors starting from the common vertex $A$:

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                    &= (2 - 0, \; 1 - 0, \; 0 - 0) \\
                    &= (2, 1, 0)
\end{aligned}
$$

$$
\begin{aligned}
\overrightarrow{AC} &= C - A \\
                    &= (1 - 0, \; 3 - 0, \; 2 - 0) \\
                    &= (1, 3, 2)
\end{aligned}
$$

---

### 2. Computation of the Cross Product $\overrightarrow{AB} \times \overrightarrow{AC}$

For $\overrightarrow{AB} = (2, 1, 0)$ and $\overrightarrow{AC} = (1, 3, 2)$, the cross product is:

- **First component ($x$-coordinate):**

$$
(1)(2) - (0)(3) = 2 - 0 = 2
$$

- **Second component ($y$-coordinate):**

$$
(0)(1) - (2)(2) = 0 - 4 = -4
$$

- **Third component ($z$-coordinate):**

$$
(2)(3) - (1)(1) = 6 - 1 = 5
$$

Thus:

$$
\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)
$$

---

### 3. Area of the Parallelogram

Geometrically, the length (Euclidean norm) of the cross product $\overrightarrow{AB} \times \overrightarrow{AC}$ equals the area of the parallelogram spanned by the adjacent side vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$:

$$
\begin{aligned}
S_{\mathrm{parallelogram}} &= \|\overrightarrow{AB} \times \overrightarrow{AC}\| \\
                           &= \sqrt{2^2 + (-4)^2 + 5^2} \\
                           &= \sqrt{4 + 16 + 25} \\
                           &= \sqrt{45} \\
                           &= \sqrt{9 \cdot 5} \\
                           &= 3\sqrt{5} \approx 6.708
\end{aligned}
$$

---

### 4. Area of the Triangle $\triangle ABC$

The area of triangle $\triangle ABC$ is half the area of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$:

$$
\begin{aligned}
S_{\triangle ABC} &= \frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\| \\
                  &= \frac{1}{2} \sqrt{45} \\
                  &= \frac{3\sqrt{5}}{2} \approx 3.354
\end{aligned}
$$

---

### 5. Explanation of the Factor $\frac{1}{2}$

The factor $\frac{1}{2}$ arises for two equivalent geometric reasons:

#### 1. Diagonal Division into Congruent Triangles
The vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ form two adjacent sides of a parallelogram $ABDC$, where the fourth vertex is $D = A + \overrightarrow{AB} + \overrightarrow{AC} = (3, 4, 2)$.
- The segment $BC$ connecting the tips of $\overrightarrow{AB}$ and $\overrightarrow{AC}$ is a diagonal of this parallelogram.
- A diagonal divides any parallelogram into **two congruent triangles** ($\triangle ABC \cong \triangle DCB$ by Side-Side-Side congruence, since opposite sides of a parallelogram have equal length and the diagonal $BC$ is shared).
- Because the two congruent triangles have equal area and together tile the entire parallelogram without overlap, the area of $\triangle ABC$ is exactly $\frac{1}{2}$ of the parallelogram's area.

#### 2. Base-Times-Height Formula ($S = \frac{1}{2} b h$)
Let $\theta$ be the angle between $\overrightarrow{AB}$ and $\overrightarrow{AC}$. Taking $b = \|\overrightarrow{AB}\|$ as the base of the triangle, the perpendicular altitude from $C$ to the line of $AB$ is:

$$
h = \|\overrightarrow{AC}\| \sin\theta
$$

- The area of the parallelogram is "base times height":

$$
S_{\mathrm{parallelogram}} = b h = \|\overrightarrow{AB}\|\,\|\overrightarrow{AC}\| \sin\theta = \|\overrightarrow{AB} \times \overrightarrow{AC}\|
$$

- The area of the triangle with the same base $b$ and altitude $h$ is "one-half base times height":

$$
S_{\triangle ABC} = \frac{1}{2} b h = \frac{1}{2} \|\overrightarrow{AB}\|\,\|\overrightarrow{AC}\| \sin\theta = \frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\|
$$

---

## Verification and Consistency Checks

### Check 1: Orthogonality of $\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)$

Before trusting the area calculation, we verify that $(2, -4, 5)$ is orthogonal to both side vectors:
- Dot product with $\overrightarrow{AB} = (2, 1, 0)$:

$$
(2, -4, 5) \cdot (2, 1, 0) = (2)(2) + (-4)(1) + (5)(0) = 4 - 4 + 0 = 0
$$

- Dot product with $\overrightarrow{AC} = (1, 3, 2)$:

$$
(2, -4, 5) \cdot (1, 3, 2) = (2)(1) + (-4)(3) + (5)(2) = 2 - 12 + 10 = 0
$$

### Check 2: Area via Dot Product and Trigonometric Identity

We can also compute the triangle area without the cross product using $\sin\theta = \sqrt{1 - \cos^2\theta}$:
- $\|\overrightarrow{AB}\| = \sqrt{2^2 + 1^2 + 0^2} = \sqrt{5}$
- $\|\overrightarrow{AC}\| = \sqrt{1^2 + 3^2 + 2^2} = \sqrt{14}$
- $\overrightarrow{AB} \cdot \overrightarrow{AC} = (2)(1) + (1)(3) + (0)(2) = 5$

Using the identity $S_{\triangle ABC} = \frac{1}{2} \sqrt{\|\overrightarrow{AB}\|^2 \|\overrightarrow{AC}\|^2 - (\overrightarrow{AB} \cdot \overrightarrow{AC})^2}$:

$$
\begin{aligned}
S_{\triangle ABC} &= \frac{1}{2} \sqrt{(5)(14) - 5^2} \\
                  &= \frac{1}{2} \sqrt{70 - 25} \\
                  &= \frac{1}{2} \sqrt{45} \\
                  &= \frac{3\sqrt{5}}{2}
\end{aligned}
$$

Both methods yield the exact same area $\frac{3\sqrt{5}}{2}$.

---

## Why This Exercise Matters

- **3D Area Without Angles or Heights:** In three-dimensional space, finding the altitude of an oblique triangle directly is tedious. The cross product computes the area of any triangle in $\mathbb{R}^3$ purely from vertex coordinates via $\frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\|$.
- **Collinearity Test:** Three points $A, B, C \in \mathbb{R}^3$ are collinear if and only if the triangle they form has zero area, i.e., $\overrightarrow{AB} \times \overrightarrow{AC} = 0$.
