# Problem 8: Intersection Point of a Line and a Plane

## Question

Find the intersection point of

$$
(x,y,z)=(1,0,2)+t(1,2,-1)
$$

with the plane $x+y+z=4$. Check the result by substituting it into both descriptions.

---

## Solution

### 1. Parametric Coordinates of a Point on the Line

Any point on the line $L: (x, y, z) = (1, 0, 2) + t(1, 2, -1)$ has coordinates given in terms of the parameter $t \in \mathbb{R}$ by:

$$
\begin{cases}
x = 1 + t, \\
y = 2t, \\
z = 2 - t.
\end{cases}
$$

*(Preliminary check: The direction vector $v = (1, 2, -1)$ and the plane's normal vector $n = (1, 1, 1)$ have dot product $v \cdot n = 1 + 2 - 1 = 2 \neq 0$, guaranteeing a single unique intersection point.)*

---

### 2. Substituting the Line into the Plane Equation

A point on the line lies on the plane $x + y + z = 4$ if and only if its coordinates $(x(t), y(t), z(t))$ satisfy the plane's equation:

$$
(1 + t) + (2t) + (2 - t) = 4
$$

Grouping the constant terms and the $t$-terms:

$$
\begin{aligned}
(1 + 2) + (t + 2t - t) &= 4 \\
3 + 2t &= 4 \\
2t &= 4 - 3 \\
2t &= 1 \\
t &= \frac{1}{2}
\end{aligned}
$$

Thus, the line intersects the plane at the unique parameter value $t = \frac{1}{2}$.

---

### 3. Computing the Coordinates of the Intersection Point

Substituting $t = \frac{1}{2}$ back into the parametric equations of the line:

- **$x$-coordinate:**

$$
x = 1 + \frac{1}{2} = \frac{3}{2}
$$

- **$y$-coordinate:**

$$
y = 2\left(\frac{1}{2}\right) = 1
$$

- **$z$-coordinate:**

$$
z = 2 - \frac{1}{2} = \frac{3}{2}
$$

Therefore, the intersection point is:

$$
I = \left( \frac{3}{2}, \; 1, \; \frac{3}{2} \right) = (1.5, \; 1, \; 1.5)
$$

---

### 4. Checking the Result in Both Descriptions

#### 1. Check in the Plane Description ($x + y + z = 4$):

Substituting $x = \frac{3}{2}$, $y = 1$, and $z = \frac{3}{2}$ into the left-hand side of $x + y + z = 4$:

$$
\begin{aligned}
x + y + z &= \frac{3}{2} + 1 + \frac{3}{2} \\
          &= \frac{3 + 3}{2} + 1 \\
          &= 3 + 1 \\
          &= 4
\end{aligned}
$$

The plane equation is satisfied.

#### 2. Check in the Line Description ($(x, y, z) = (1, 0, 2) + t(1, 2, -1)$):

We verify that the displacement from the line's reference point $P_0 = (1, 0, 2)$ to $I = \left(\frac{3}{2}, 1, \frac{3}{2}\right)$ is a scalar multiple of the direction vector $v = (1, 2, -1)$:

$$
\begin{aligned}
I - P_0 &= \left( \frac{3}{2} - 1, \; 1 - 0, \; \frac{3}{2} - 2 \right) \\
        &= \left( \frac{1}{2}, \; 1, \; -\frac{1}{2} \right) \\
        &= \frac{1}{2} (1, 2, -1) \\
        &= \frac{1}{2} v
\end{aligned}
$$

Reconstructing $I$ from $P_0 + \frac{1}{2} v$:

$$
(1, 0, 2) + \frac{1}{2}(1, 2, -1) = \left( 1 + \frac{1}{2}, \; 0 + 1, \; 2 - \frac{1}{2} \right) = \left( \frac{3}{2}, \; 1, \; \frac{3}{2} \right) = I
$$

Since $I$ satisfies both the equation of the plane and the parametric equation of the line, $I = \left(\frac{3}{2}, 1, \frac{3}{2}\right)$ is verified as the intersection point.

---

## Why This Exercise Matters

- **One-Variable Reduction:** Because the line is given parametrically in terms of a single variable $t$ and the plane is given by a single linear equation $Ax + By + Cz = D$, substituting the line into the plane always reduces a 3D intersection problem to a single linear equation in $t$.
- **Foundation for Orthogonal Projection:** Finding where a line pierces a plane is the core computational step for projecting points onto planes and computing reflections across planes (as in Exercise 10).
