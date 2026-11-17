# Problem 2: Distance as the Length of a Vector

## Question

The points are $A=(1,2,3)$ and $B=(4,-2,6)$.

1. Construct $\overrightarrow{AB}$.
2. Compute its length.
3. Compute the distance between the points using the coordinate formula.
4. Explain why both calculations give the same result.

---

## Solution

### 1. Construction of the Vector $\overrightarrow{AB}$

Given the initial point $A = (x_A, y_A, z_A) = (1, 2, 3)$ and the terminal point $B = (x_B, y_B, z_B) = (4, -2, 6)$, the directed displacement vector $\overrightarrow{AB}$ is obtained by subtracting the coordinates of the initial point $A$ from the coordinates of the terminal point $B$ ("terminal minus initial"):

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                    &= (x_B - x_A, \; y_B - y_A, \; z_B - z_A) \\
                    &= (4 - 1, \; -2 - 2, \; 6 - 3) \\
                    &= (3, -4, 3)
\end{aligned}
$$

In column vector notation:

$$
\overrightarrow{AB} =
\begin{pmatrix}
4 - 1 \\
-2 - 2 \\
6 - 3 \\
\end{pmatrix}
= \begin{pmatrix}
3 \\
-4 \\
3 \\
\end{pmatrix}
$$

---

### 2. Computation of the Vector Length $\|\overrightarrow{AB}\|$

The Euclidean length (norm) of a vector $v = (v_1, v_2, v_3) \in \mathbb{R}^3$ is defined by:

$$
\|v\| = \sqrt{v_1^2 + v_2^2 + v_3^2}
$$

Applying this formula to $\overrightarrow{AB} = (3, -4, 3)$:

$$
\begin{aligned}
\|\overrightarrow{AB}\| &= \sqrt{3^2 + (-4)^2 + 3^2} \\
                        &= \sqrt{9 + 16 + 9} \\
                        &= \sqrt{34} \approx 5.831
\end{aligned}
$$

---

### 3. Computation of the Distance $d(A, B)$ Using the Coordinate Formula

The Euclidean distance between two points $A = (x_A, y_A, z_A)$ and $B = (x_B, y_B, z_B)$ in $\mathbb{R}^3$ is given by the three-dimensional distance formula:

$$
d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}
$$

Substituting the coordinates of $A = (1, 2, 3)$ and $B = (4, -2, 6)$ directly:

$$
\begin{aligned}
d(A, B) &= \sqrt{(4 - 1)^2 + (-2 - 2)^2 + (6 - 3)^2} \\
        &= \sqrt{3^2 + (-4)^2 + 3^2} \\
        &= \sqrt{9 + 16 + 9} \\
        &= \sqrt{34} \approx 5.831
\end{aligned}
$$

---

### 4. Explanation: Why Both Calculations Give the Same Result

Both calculations produce the exact same number $\sqrt{34}$ because the coordinate distance formula is **defined** as the length of the displacement vector connecting the two points:

$$
d(A, B) = \|B - A\| = \|\overrightarrow{AB}\|
$$

#### Geometric Interpretation (3D Pythagorean Theorem):
- Moving from point $A$ to point $B$ involves three mutually perpendicular coordinate displacements along the $x$-, $y$-, and $z$-axes:

$$
\Delta x = x_B - x_A = 3, \qquad \Delta y = y_B - y_A = -4, \qquad \Delta z = z_B - z_A = 3
$$

- These three displacements form the edges of a rectangular box (cuboid) of dimensions $|3| \times |-4| \times |3|$ with $A$ and $B$ at opposite corners.
- By applying the Pythagorean theorem twice — first in the horizontal plane ($\sqrt{(\Delta x)^2 + (\Delta y)^2} = \sqrt{3^2 + (-4)^2} = 5$) and then with the vertical displacement $\Delta z = 3$ — the length of the space diagonal from $A$ to $B$ is:

$$
\sqrt{5^2 + 3^2} = \sqrt{25 + 9} = \sqrt{34}
$$

- Whether we first package $(\Delta x, \Delta y, \Delta z)$ into the vector $\overrightarrow{AB}$ and take its norm, or substitute the differences directly into $d(A, B)$, we are computing the exact same sum of squared coordinate differences.

---

## Verification and Consistency Checks

### Check 1: Endpoint Reconstruction ($A + \overrightarrow{AB} = B$)

Adding the displacement vector $\overrightarrow{AB} = (3, -4, 3)$ to the starting point $A = (1, 2, 3)$:

$$
A + \overrightarrow{AB} = (1 + 3, \; 2 + (-4), \; 3 + 3) = (4, -2, 6) = B
$$

This confirms that $\overrightarrow{AB}$ was constructed with the correct signs.

### Check 2: Symmetry of Distance ($\|\overrightarrow{BA}\| = \|\overrightarrow{AB}\|$)

Reversing the order gives the opposite vector:

$$
\overrightarrow{BA} = A - B = (-3, 4, -3) = -\overrightarrow{AB}
$$

Its length is:

$$
\|\overrightarrow{BA}\| = \sqrt{(-3)^2 + 4^2 + (-3)^2} = \sqrt{9 + 16 + 9} = \sqrt{34}
$$

Because squaring eliminates signs, distance is symmetric: $d(A, B) = d(B, A)$.

---

## Why This Exercise Matters

- **Unifying Points and Vectors:** Bridging the gap between static points in space and displacement vectors allows geometric distance problems to be solved using vector algebra.
- **Origin of the Distance Formula:** Students do not need to memorize the coordinate distance formula as an isolated rule; it is simply the norm $\|B - A\|$.
- **Direction vs. Distance:** While $d(A, B) = \sqrt{34}$ retains only the scalar separation, the vector $\overrightarrow{AB} = (3, -4, 3)$ retains both the distance and the exact three-dimensional direction from $A$ to $B$.
