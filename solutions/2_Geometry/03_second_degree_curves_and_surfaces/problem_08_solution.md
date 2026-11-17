# Problem 8: Sphere

## Question

Reduce

$$
x^2+y^2+z^2-4x+2y-6z-2=0
$$

to canonical form. Find the center and radius. Give two points on the sphere and check them in the equation.

---

## Solution

### 1. Reducing the Equation to Canonical Form by Completing the Square

We start from the given general equation of the sphere:

$$
x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0
$$

#### Step 1: Group the $x$-, $y$-, and $z$-terms and move the constant term to the right-hand side

$$
(x^2 - 4x) + (y^2 + 2y) + (z^2 - 6z) = 2
$$

#### Step 2: Complete the square for each of the three variables

1. **For the $x$-terms ($x^2 - 4x$):**
   Half of $-4$ is $-2$, and $(-2)^2 = 4$:

$$
x^2 - 4x + 4 = (x - 2)^2
$$

2. **For the $y$-terms ($y^2 + 2y$):**
   Half of $2$ is $1$, and $1^2 = 1$:

$$
y^2 + 2y + 1 = (y + 1)^2
$$

3. **For the $z$-terms ($z^2 - 6z$):**
   Half of $-6$ is $-3$, and $(-3)^2 = 9$:

$$
z^2 - 6z + 9 = (z - 3)^2
$$

#### Step 3: Add $4$, $1$, and $9$ to both sides of the equation

Adding $4 + 1 + 9 = 14$ to both sides preserves the equality:

$$
(x^2 - 4x + 4) + (y^2 + 2y + 1) + (z^2 - 6z + 9) = 2 + 4 + 1 + 9
$$

Factoring the three perfect squares on the left and summing on the right gives the **canonical form** of the sphere:

$$
(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16
$$

or equivalently:

$$
(x - 2)^2 + (y - (-1))^2 + (z - 3)^2 = 4^2
$$

---

### 2. Finding the Center and Radius

Comparing $(x - 2)^2 + (y - (-1))^2 + (z - 3)^2 = 4^2$ with the standard sphere equation $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = r^2$:

- **Center of the sphere:**

$$
C = (x_0, y_0, z_0) = (2, -1, 3)
$$

- **Radius of the sphere:**

$$
r = \sqrt{16} = 4
$$

---

### 3. Finding Two Points on the Sphere and Checking Them in the Equation

Starting from the center $C = (2, -1, 3)$ and stepping a distance $r = 4$ along the coordinate axes gives simple points on the sphere:

- **Point 1 (moving $4$ units in the $+x$ direction from $C$):**

$$
P_1 = (2 + 4, \; -1, \; 3) = (6, -1, 3)
$$

- **Point 2 (moving $4$ units in the $+z$ direction from $C$):**

$$
P_2 = (2, \; -1, \; 3 + 4) = (2, -1, 7)
$$

*(Other simple cardinal points are $(-2, -1, 3)$, $(2, 3, 3)$, $(2, -5, 3)$, and $(2, -1, -1)$.)*

#### Check for Point 1: $P_1 = (6, -1, 3)$

1. **In the original equation $x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$:**

$$
\begin{aligned}
6^2 + (-1)^2 + 3^2 - 4(6) + 2(-1) - 6(3) - 2 &= 36 + 1 + 9 - 24 - 2 - 18 - 2 \\
                                             &= 46 - 46 \\
                                             &= 0
\end{aligned}
$$

2. **In the canonical equation $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:**

$$
(6 - 2)^2 + (-1 + 1)^2 + (3 - 3)^2 = 4^2 + 0^2 + 0^2 = 16
$$

#### Check for Point 2: $P_2 = (2, -1, 7)$

1. **In the original equation $x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$:**

$$
\begin{aligned}
2^2 + (-1)^2 + 7^2 - 4(2) + 2(-1) - 6(7) - 2 &= 4 + 1 + 49 - 8 - 2 - 42 - 2 \\
                                             &= 54 - 54 \\
                                             &= 0
\end{aligned}
$$

2. **In the canonical equation $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:**

$$
(2 - 2)^2 + (-1 + 1)^2 + (7 - 3)^2 = 0^2 + 0^2 + 4^2 = 16
$$

Both points satisfy both forms of the sphere's equation.

---

## Verification and Consistency Checks

### Expanding the Canonical Form Back to General Form

Expanding $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:

$$
\begin{aligned}
(x^2 - 4x + 4) + (y^2 + 2y + 1) + (z^2 - 6z + 9) &= 16 \\
x^2 + y^2 + z^2 - 4x + 2y - 6z + 14 - 16 &= 0 \\
x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 &= 0
\end{aligned}
$$

This recovers the original equation identically.

---

## Why This Exercise Matters

- **Seamless Extension from $\mathbb{R}^2$ to $\mathbb{R}^3$:** A sphere is the three-dimensional analogue of a circle: the set of all points $(x, y, z) \in \mathbb{R}^3$ at a fixed Euclidean distance $r$ from the center $(x_0, y_0, z_0)$, which by squaring the distance formula becomes $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = r^2$.
- **Independent Variable Grouping:** Because there are no cross terms ($xy, xz, yz$), completing the square in $\mathbb{R}^3$ simply performs the 1D completing-the-square step three independent times.
