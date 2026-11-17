# Problem 7: A Line Relative to a Plane

## Question

For

$$
L:(x,y,z)=(1,1,0)+t(1,-1,0),\qquad \Pi:x+y+z=2,
$$

determine whether the line intersects the plane at one point, is parallel to it, or lies in it. Explain the role of the dot product of the direction vector and the normal vector.

---

## Solution

### 1. Extracting the Vectors and Reference Point

From the given equations:

- **Line $L$:**
  - Reference point (at $t = 0$): $P_0 = (1, 1, 0)$
  - Direction vector: $v = (1, -1, 0)$

- **Plane $\Pi: 1x + 1y + 1z = 2$:**
  - Normal vector: $n = (1, 1, 1)$

---

### 2. Testing the Dot Product $v \cdot n$

We compute the dot product of the line's direction vector $v = (1, -1, 0)$ and the plane's normal vector $n = (1, 1, 1)$:

$$
\begin{aligned}
v \cdot n &= (1)(1) + (-1)(1) + (0)(1) \\
          &= 1 - 1 + 0 \\
          &= 0
\end{aligned}
$$

Because $v \cdot n = 0$, the direction vector $v$ is perpendicular to the normal vector $n$ ($v \perp n$). Since every direction perpendicular to the normal vector $n$ is parallel to the plane $\Pi$, the line $L$ does **not** cross $\Pi$ at a single point. Instead, $L$ is either:
1. **Strictly parallel** to $\Pi$ (with no common points), or
2. **Contained entirely within** $\Pi$ (every point of $L$ lies on $\Pi$).

---

### 3. Testing Whether the Line Lies in the Plane

To distinguish between being strictly parallel and lying inside the plane, we check whether the reference point $P_0 = (1, 1, 0)$ of $L$ satisfies the plane equation $x + y + z = 2$:

$$
1 + 1 + 0 = 2
$$

Since $2 = 2$, the point $P_0 = (1, 1, 0)$ lies on the plane $\Pi$.

We can also see this by substituting the general point $(x, y, z) = (1 + t, \; 1 - t, \; 0)$ of $L$ into the equation of $\Pi$:

$$
\begin{aligned}
x + y + z &= (1 + t) + (1 - t) + 0 \\
          &= (1 + 1) + (t - t) \\
          &= 2
\end{aligned}
$$

The parameter $t$ cancels out and leaves the identity $2 = 2$, which holds for **every** $t \in \mathbb{R}$.

**Conclusion:**
The line $L$ **lies entirely in the plane $\Pi$** ($L \subset \Pi$).

---

### 4. Explanation: The Role of the Dot Product $v \cdot n$

When we substitute a parametric line $X(t) = P_0 + tv$ into a plane equation $n \cdot X = d$, we get the linear equation in $t$:

$$
n \cdot (P_0 + tv) = d \iff (v \cdot n) t = d - n \cdot P_0
$$

The dot product $v \cdot n$ is the **coefficient of the parameter $t$**, measuring the rate at which the line moves in the direction perpendicular to the plane:

1. **Case 1: $v \cdot n \neq 0$ (Unique Intersection Point)**
   The direction vector $v$ is not perpendicular to $n$, so moving along $L$ changes the signed height above the plane. We can divide by $v \cdot n$ to find the unique parameter value $t = \frac{d - n \cdot P_0}{v \cdot n}$, so the line intersects the plane at **exactly one point**.

2. **Case 2: $v \cdot n = 0$ and $n \cdot P_0 \neq d$ (Strictly Parallel — No Common Points)**
   The direction vector $v$ is perpendicular to $n$, so the line moves parallel to the plane at a constant nonzero distance from it. The equation becomes $0 \cdot t = d - n \cdot P_0 \neq 0$, which is a contradiction (no solution).

3. **Case 3: $v \cdot n = 0$ and $n \cdot P_0 = d$ (Line Contained in the Plane)**
   The line starts at a point $P_0$ already on the plane ($n \cdot P_0 = d$) and moves in a direction $v$ parallel to the plane ($v \cdot n = 0$), so it never leaves the plane. The equation becomes $0 \cdot t = 0$, which holds for all $t \in \mathbb{R}$.

---

## Verification and Consistency Checks

### Testing a Second Point on $L$

Let us pick another point on $L$, say at $t = 3$:

$$
P_3 = (1, 1, 0) + 3(1, -1, 0) = (4, -2, 0)
$$

Substituting $P_3 = (4, -2, 0)$ into the plane $\Pi: x + y + z = 2$:

$$
4 + (-2) + 0 = 2
$$

Point $P_3$ also lies on $\Pi$. Since a straight line is uniquely determined by two distinct points ($P_0$ and $P_3$) and a plane is flat (convex/affine), any line with two distinct points in $\Pi$ must lie entirely in $\Pi$.

---

## Why This Exercise Matters

- **Opposite Roles of $v$ and $n$:** A line is described by a *parallel* direction vector $v$, whereas a plane is described by a *perpendicular* normal vector $n$. Because of this $90^\circ$ difference in how they are defined, **parallelism between a line and a plane corresponds to orthogonality between $v$ and $n$ ($v \cdot n = 0$)**.
- **Universal Algebraic Criterion:** Evaluating $v \cdot n$ and $n \cdot P_0$ classifies any line–plane pair in $\mathbb{R}^3$ immediately.
