# Problem 2: A Line in Space

## Question

Given

$$
L:(x,y,z)=(2,-1,3)+t(1,2,-2).
$$

State a point on the line and its direction vector, check whether $P=(4,3,-1)$ lies on $L$, and find the point corresponding to $t=-1$.

---

## Solution

### 1. Reading Off a Point on the Line and the Direction Vector

The general parametric equation of a line in $\mathbb{R}^3$ has the form:

$$
(x, y, z) = P_0 + t v, \qquad t \in \mathbb{R}
$$

where $P_0 = (x_0, y_0, z_0)$ is a reference point on the line (obtained at $t = 0$) and $v = (v_1, v_2, v_3)$ is the direction vector describing the rate and direction of displacement as $t$ varies.

Comparing this directly with $L: (x, y, z) = (2, -1, 3) + t(1, 2, -2)$:

- **A point on the line (for $t = 0$):**

$$
P_0 = (2, -1, 3)
$$

- **The direction vector of the line:**

$$
v = (1, 2, -2)
$$

Writing $L$ in component parametric form:

$$
\begin{cases}
x = 2 + t, \\
y = -1 + 2t, \\
z = 3 - 2t,
\end{cases}
\qquad t \in \mathbb{R}
$$

---

### 2. Checking Whether $P = (4, 3, -1)$ Lies on $L$

A point $P = (4, 3, -1)$ lies on the line $L$ if and only if there exists a **single** real parameter $t \in \mathbb{R}$ that simultaneously satisfies all three coordinate equations:

$$
\begin{cases}
2 + t = 4, \\
-1 + 2t = 3, \\
3 - 2t = -1.
\end{cases}
$$

We solve each equation for $t$:

1. **From the $x$-coordinate equation:**

$$
2 + t = 4 \implies t = 4 - 2 = 2
$$

2. **From the $y$-coordinate equation:**

$$
-1 + 2t = 3 \implies 2t = 4 \implies t = 2
$$

3. **From the $z$-coordinate equation:**

$$
3 - 2t = -1 \implies -2t = -4 \implies t = 2
$$

Because all three coordinates yield the **exact same parameter value** $t = 2$, the point $P = (4, 3, -1)$ **does lie on the line $L$**.

---

### 3. Finding the Point Corresponding to $t = -1$

Substituting $t = -1$ into the parametric equation of $L$:

$$
\begin{aligned}
Q &= (2, -1, 3) + (-1)(1, 2, -2) \\
  &= (2, -1, 3) + (-1, -2, 2) \\
  &= (2 - 1, \; -1 - 2, \; 3 + 2) \\
  &= (1, -3, 5)
\end{aligned}
$$

Thus, the point on $L$ corresponding to $t = -1$ is:

$$
Q = (1, -3, 5)
$$

---

## Verification and Consistency Checks

### Check 1: Collinearity of Displacement Vectors

If $P_0 = (2, -1, 3)$, $P = (4, 3, -1)$, and $Q = (1, -3, 5)$ all lie on the line $L$ with direction vector $v = (1, 2, -2)$, then the displacement vectors $\overrightarrow{P_0 P}$ and $\overrightarrow{P_0 Q}$ must be scalar multiples of $v$:

$$
\overrightarrow{P_0 P} = P - P_0 = (4 - 2, \; 3 - (-1), \; -1 - 3) = (2, 4, -4) = 2(1, 2, -2) = 2v
$$

$$
\overrightarrow{P_0 Q} = Q - P_0 = (1 - 2, \; -3 - (-1), \; 5 - 3) = (-1, -2, 2) = -1(1, 2, -2) = -v
$$

Both displacement vectors are exact scalar multiples of $v$ with factors $t = 2$ and $t = -1$, respectively.

### Check 2: Distance Along the Line

The Euclidean length of the direction vector $v = (1, 2, -2)$ is:

$$
\|v\| = \sqrt{1^2 + 2^2 + (-2)^2} = \sqrt{1 + 4 + 4} = \sqrt{9} = 3
$$

- At $t = 2$, point $P = (4, 3, -1)$ is at distance $|2| \cdot \|v\| = 2 \cdot 3 = 6$ from $P_0$ in the direction of $v$.
- At $t = -1$, point $Q = (1, -3, 5)$ is at distance $|-1| \cdot \|v\| = 1 \cdot 3 = 3$ from $P_0$ in the opposite direction $-v$.
- The distance between $Q$ and $P$ is $\|P - Q\| = \|(3, 6, -6)\| = \sqrt{9 + 36 + 36} = \sqrt{81} = 9 = 6 + 3$.

---

## Why This Exercise Matters

- **"Point + Direction" Structure:** In three-dimensional space $\mathbb{R}^3$, a single linear equation describes a plane, not a line. The parametric form $P_0 + tv$ is the most direct and universal way to represent a line in $\mathbb{R}^3$.
- **Point Membership Test:** To test whether a point lies on a parametric line, one must verify that **all three coordinates** produce the *same* value of $t$; if even one coordinate requires a different $t$, the point does not lie on the line.
