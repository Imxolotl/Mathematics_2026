# Problem 14: Contrast: Intersection and Parallelism

## Question

From the point $P=(0,0,1)$, two lines are drawn with direction vectors

$$
v_1=(2,1,-1),\qquad v_2=(2,1,0).
$$

For each line, analyze its position relative to the plane $z=0$.

For the line that intersects the plane, find the intersection point. For the other line, explain how you can recognize parallelism without solving an equation.

---

## Solution

### 1. Parametric Equations of the Two Lines and Normal of the Plane

The plane $\Pi: z = 0$ (which can be written as $0x + 0y + 1z = 0$) is the horizontal $xy$-coordinate plane, and its unit normal vector is the vertical vector:

$$
n = (0, 0, 1)
$$

Both lines start at the point $P = (0, 0, 1)$ (located $1$ unit above the $xy$-plane on the $z$-axis).

First line $L_1$ (with direction vector $v_1 = (2, 1, -1)$):

$$
(x, y, z) = (0, 0, 1) + t(2, 1, -1) = (2t, t, 1 - t)
$$

Second line $L_2$ (with direction vector $v_2 = (2, 1, 0)$):

$$
(x, y, z) = (0, 0, 1) + s(2, 1, 0) = (2s, s, 1)
$$

---

### 2. Analysis of Line $L_1$: Intersection with $z = 0$

#### Position Analysis

The dot product of $v_1 = (2, 1, -1)$ with the plane's normal vector $n = (0, 0, 1)$ is the $z$-component of $v_1$:

$$
v_1 \cdot n = (2)(0) + (1)(0) + (-1)(1) = -1 \neq 0
$$

Because $v_1$ has a nonzero vertical component ($-1$), moving along $L_1$ changes the height $z$. Therefore, $L_1$ is not parallel to the plane $z = 0$ and must intersect it at a single point.

#### Finding the Intersection Point

Setting the $z$-coordinate of $L_1$ equal to $0$:

$$
1 - t = 0
$$

Solving for $t$ gives $t = 1$. Substituting $t = 1$ into the equation of $L_1$:

$$
\begin{aligned}
I &= (0, 0, 1) + 1(2, 1, -1) \\
  &= (2, 1, 0)
\end{aligned}
$$

Thus, $L_1$ intersects the plane $z = 0$ at the unique point:

$$
I = (2, 1, 0)
$$

---

### 3. Analysis of Line $L_2$: Recognizing Parallelism Without Solving an Equation

Line $L_2$ is strictly parallel to the plane $z = 0$ (having no intersection points with it).

#### 1. Inspection of the Vertical Component of $v_2 = (2, 1, 0)$

The plane $z = 0$ is horizontal; a point lies on it if and only if its third coordinate ($z$) is $0$. Looking at the direction vector $v_2 = (2, 1, 0)$, its third component is $0$. This means that travelling along $v_2$ produces horizontal motion in the $x$- and $y$-directions while producing zero change in height $z$.

#### 2. Orthogonality to the Normal Vector

Equivalently, the dot product of $v_2 = (2, 1, 0)$ with the plane's normal $n = (0, 0, 1)$ is immediately zero by inspection:

$$
v_2 \cdot n = (2)(0) + (1)(0) + (0)(1) = 0
$$

Because $v_2 \cdot n = 0$, the direction of $L_2$ is parallel to the plane $z = 0$.

#### 3. Constant Nonzero Altitude ($z = 1 \neq 0$)

Because the line starts at $P = (0, 0, 1)$ where $z = 1$, and its direction vector has zero vertical component, every point on $L_2$ maintains the constant height $z = 1$ forever. A line that stays at height $z = 1$ lies entirely in the horizontal plane $z = 1$ and can never touch the plane $z = 0$.

---

## Verification and Consistency Checks

### Side-by-Side Comparison of the Two Lines

| Property | Line $L_1$ | Line $L_2$ |
| :--- | :--- | :--- |
| **Starting point** | $(0, 0, 1)$ (height $z = 1$) | $(0, 0, 1)$ (height $z = 1$) |
| **Direction vector** | $v_1 = (2, 1, -1)$ | $v_2 = (2, 1, 0)$ |
| **Vertical rate** | $v_1 \cdot n = -1 \neq 0$ (descends $1$ unit per unit $t$) | $v_2 \cdot n = 0$ (horizontal motion only) |
| **Height along line** | $z(t) = 1 - t$ (reaches $0$ at $t = 1$) | $z(s) = 1$ (constant for all $s \in \mathbb{R}$) |
| **Position relative to plane** | Intersects at $I = (2, 1, 0)$ | Strictly parallel (no common points) |

---

## Why This Exercise Matters

- **Sensitivity to a Single Zero Coordinate:** The vectors $v_1 = (2, 1, -1)$ and $v_2 = (2, 1, 0)$ share the exact same $x$- and $y$-components, yet changing the $z$-component from $-1$ to $0$ eliminates the vertical descent and switches the geometry from a transverse intersection to strict parallelism.
