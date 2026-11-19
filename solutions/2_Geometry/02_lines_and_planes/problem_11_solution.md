# Problem 11: Plane Containing a Line and a Point

## Question

Find the equation of the plane containing

$$
(x,y,z)=(1,0,2)+t(1,1,-1)
$$

and the point $P=(0,2,1)$. Check that both the entire line and the point lie in the plane you obtain.

---

## Solution

### 1. Constructing Two Linearly Independent Vectors in the Plane

To determine the equation of the plane $\Pi$ containing the line $L: (x, y, z) = (1, 0, 2) + t(1, 1, -1)$ and the point $P = (0, 2, 1)$, we need two non-parallel vectors lying in $\Pi$.

#### Step 1: First vector in the plane (the direction vector of the line)

Because the entire line $L$ lies in the plane, its direction vector $v_1$ lies in the plane:

$$
v_1 = (1, 1, -1)
$$

#### Step 2: Second vector in the plane (connecting a point on the line to $P$)

Setting $t = 0$ in the equation of the line $L$ gives the point $A = (1, 0, 2)$ on $L$. Since both $A = (1, 0, 2)$ and $P = (0, 2, 1)$ lie in the plane $\Pi$, the vector $v_2 = \overrightarrow{AP} = P - A$ connecting them also lies in $\Pi$:

$$
\begin{aligned}
v_2 &= P - A \\
    &= (0 - 1, 2 - 0, 1 - 2) \\
    &= (-1, 2, -1)
\end{aligned}
$$

Since $v_1 = (1, 1, -1)$ and $v_2 = (-1, 2, -1)$ are not proportional, the point $P$ does not lie on the line $L$, and the two vectors uniquely determine the plane.

---

### 2. Finding a Normal Vector Using the Cross Product

A normal vector $n$ to the plane must be perpendicular to both $v_1 = (1, 1, -1)$ and $v_2 = (-1, 2, -1)$. We compute their cross product $n = v_1 \times v_2$.

First component ($x$-coordinate):

$$
(1)(-1) - (-1)(2) = -1 + 2 = 1
$$

Second component ($y$-coordinate):

$$
(-1)(-1) - (1)(-1) = 1 + 1 = 2
$$

Third component ($z$-coordinate):

$$
(1)(2) - (1)(-1) = 2 + 1 = 3
$$

Thus, a normal vector to the plane is:

$$
n = v_1 \times v_2 = (1, 2, 3)
$$

---

### 3. Writing the Equation of the Plane

Using the point-normal equation $n \cdot (X - A) = 0$ with normal vector $n = (1, 2, 3)$ and point $A = (1, 0, 2)$:

$$
1(x - 1) + 2(y - 0) + 3(z - 2) = 0
$$

Expanding and simplifying:

$$
\begin{aligned}
x - 1 + 2y + 3z - 6 &= 0 \\
x + 2y + 3z - 7 &= 0
\end{aligned}
$$

Moving the constant to the right-hand side gives the plane equation:

$$
x + 2y + 3z = 7
$$

---

### 4. Checking that Both the Entire Line and the Point Lie in the Plane

#### Check 1: Substituting the point $P = (0, 2, 1)$

Substituting $x = 0$, $y = 2$, and $z = 1$ into the left-hand side of $x + 2y + 3z = 7$:

$$
0 + 2(2) + 3(1) = 0 + 4 + 3 = 7
$$

The equation is satisfied ($7 = 7$), confirming that $P$ lies in the plane.

#### Check 2: Substituting the general point of the line $L$

An arbitrary point on the line $L$ has coordinates $x = 1 + t$, $y = t$, and $z = 2 - t$ for $t \in \mathbb{R}$. Substituting these coordinates into the left-hand side of $x + 2y + 3z = 7$:

$$
\begin{aligned}
x + 2y + 3z &= (1 + t) + 2(t) + 3(2 - t) \\
            &= 1 + t + 2t + 6 - 3t \\
            &= (1 + 6) + (1 + 2 - 3)t \\
            &= 7 + 0t \\
            &= 7
\end{aligned}
$$

Because $t$ cancels out completely and $7 = 7$ holds for all $t \in \mathbb{R}$, the entire line $L$ lies in the plane.

---

## Verification and Consistency Checks

### Orthogonality of $n$ to $v_1$ and $v_2$

Checking the dot product of $n = (1, 2, 3)$ with $v_1 = (1, 1, -1)$:

$$
n \cdot v_1 = (1)(1) + (2)(1) + (3)(-1) = 1 + 2 - 3 = 0
$$

Checking the dot product of $n = (1, 2, 3)$ with $v_2 = (-1, 2, -1)$:

$$
n \cdot v_2 = (1)(-1) + (2)(2) + (3)(-1) = -1 + 4 - 3 = 0
$$

Both dot products equal zero, confirming that $n$ is perpendicular to the plane.

---

## Why This Exercise Matters

- **Extracting Two Directions from Mixed Data:** Finding a plane's normal vector via the cross product requires two in-plane direction vectors. When given a line and an external point, one direction comes directly from the line's direction vector $v_1$, while the second direction $v_2 = P - A$ is constructed by connecting a point $A$ on the line to the external point $P$.
