# Problem 3: Plane Through a Point with a Given Normal Vector

## Question

Find the equation of the plane through $P=(1,-2,3)$ and perpendicular to $n=(2,1,-1)$. Check the result by substituting the point $P$ and explain the role of the normal vector.

---

## Solution

### 1. Point-Normal Equation of a Plane

Let $\Pi$ be the plane passing through the given point $P = (x_0, y_0, z_0)$ and perpendicular to the nonzero normal vector $n = (A, B, C)$.

An arbitrary point $X = (x, y, z) \in \mathbb{R}^3$ lies on the plane $\Pi$ if and only if the displacement vector $\overrightarrow{PX}$ lying in the plane,

$$
\overrightarrow{PX} = X - P = (x - x_0, \; y - y_0, \; z - z_0)
$$

is orthogonal to the normal vector $n$:

$$
n \cdot \overrightarrow{PX} = 0
$$

In coordinate form, this is the **point-normal equation** of the plane:

$$
A(x - x_0) + B(y - y_0) + C(z - z_0) = 0
$$

---

### 2. Constructing the Equation of the Plane

Substituting the point $P = (1, -2, 3)$ and the normal vector $n = (2, 1, -1)$ into the point-normal equation:

$$
2(x - 1) + 1(y - (-2)) + (-1)(z - 3) = 0
$$

Simplifying the signs and expanding the parentheses:

$$
\begin{aligned}
2(x - 1) + (y + 2) - (z - 3) &= 0 \\
2x - 2 + y + 2 - z + 3 &= 0 \\
2x + y - z + 3 &= 0
\end{aligned}
$$

Moving the constant term to the right-hand side gives the equivalent standard form:

$$
2x + y - z = -3
$$

*(Note: This can also be written directly as $n \cdot X = n \cdot P$, where $n \cdot P = 2(1) + 1(-2) + (-1)(3) = 2 - 2 - 3 = -3$.)*

---

### 3. Checking the Result by Substituting Point $P$

We substitute the coordinates of $P = (1, -2, 3)$ ($x = 1$, $y = -2$, $z = 3$) into the left-hand side of the general equation $2x + y - z + 3 = 0$:

$$
\begin{aligned}
2(1) + (-2) - (3) + 3 &= 2 - 2 - 3 + 3 \\
                      &= 0
\end{aligned}
$$

Similarly, for the form $2x + y - z = -3$:

$$
2(1) + (-2) - 3 = -3
$$

The equality holds, confirming that the plane passes through $P = (1, -2, 3)$.

---

### 4. Explanation: The Role of the Normal Vector

1. **Uniquely Defining the Plane's Orientation in $\mathbb{R}^3$:**
   In three-dimensional space, the set of all directions perpendicular to a single nonzero vector $n$ forms a two-dimensional subspace (a plane through the origin). Thus, specifying a single normal vector $n = (2, 1, -1)$ completely locks in the **tilt (orientation)** of the plane in $\mathbb{R}^3$ without needing to specify two separate spanning vectors inside the plane.

2. **Determining the Coefficients of $x$, $y$, and $z$:**
   In the general equation of a plane,

$$
Ax + By + Cz + D = 0
$$

   the coefficients $(A, B, C) = (2, 1, -1)$ of the variables $x, y, z$ are the exact coordinates of the normal vector $n$. All planes parallel to $\Pi$ share the same left-hand side $2x + y - z$ and differ only in the constant $D$.

3. **Separating Orientation from Position:**
   - The **normal vector $n = (2, 1, -1)$** determines the orientation of the family of parallel planes $2x + y - z = d$.
   - The **point $P = (1, -2, 3)$** selects the unique plane from this parallel family that passes through $P$ by fixing the constant $d = n \cdot P = -3$.

---

## Verification and Consistency Checks

### Finding a Second Point on the Plane and Testing Orthogonality

Let us pick another point $Q$ satisfying $2x + y - z = -3$ by setting $x = 0$ and $y = 0$, which gives $-z = -3 \implies z = 3$, so $Q = (0, 0, 3)$.

The vector connecting $P = (1, -2, 3)$ to $Q = (0, 0, 3)$ lies inside the plane:

$$
\overrightarrow{PQ} = Q - P = (0 - 1, \; 0 - (-2), \; 3 - 3) = (-1, 2, 0)
$$

Taking the dot product of $\overrightarrow{PQ}$ with the normal vector $n = (2, 1, -1)$:

$$
n \cdot \overrightarrow{PQ} = (2)(-1) + (1)(2) + (-1)(0) = -2 + 2 + 0 = 0
$$

This confirms that vectors connecting points on the plane $2x + y - z + 3 = 0$ are indeed perpendicular to $n = (2, 1, -1)$.

---

## Why This Exercise Matters

- **Most Compact Description of a Plane:** While a parametric description of a plane requires a point and *two* linearly independent direction vectors, the normal description requires only a point and *one* normal vector, yielding a single scalar equation.
- **Instant Geometric Readout:** Whenever you encounter a linear equation in three variables such as $2x + y - z + 3 = 0$, you can read off its perpendicular normal direction $n = (2, 1, -1)$ by inspection.
