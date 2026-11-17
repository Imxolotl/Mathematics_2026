# Problem 4: Parabola

## Question

For

$$
y^2=12x,
$$

identify the vertex, axis of symmetry, and opening direction. Find points on the parabola for $x=3$ and use them to make a sketch.

---

## Solution

### 1. Identifying the Vertex, Axis of Symmetry, and Opening Direction

We analyze the equation $y^2 = 12x$ directly from its algebraic structure:

1. **Opening Direction (Domain Check):**
   For any real number $y \in \mathbb{R}$, its square is non-negative ($y^2 \ge 0$). Therefore, the right-hand side must also be non-negative:

$$
12x \ge 0 \implies x \ge 0
$$

   No real points exist for $x < 0$, and as $x$ increases toward $+\infty$, $|y| = \sqrt{12x}$ grows without bound. Hence, the parabola **opens to the right** (in the direction of the positive $x$-axis).

2. **Vertex:**
   The smallest possible value of $x$ on the curve occurs when $y^2 = 0 \implies y = 0$, which gives $12x = 0 \implies x = 0$. Thus, the turning point (**vertex**) of the parabola is at the origin:

$$
V = (0, 0)
$$

3. **Axis of Symmetry:**
   Because $y$ appears only as an even power ($y^2$), replacing $y$ with $-y$ leaves the equation unchanged:

$$
(-y)^2 = y^2 = 12x
$$

   For every point $(x, y)$ on the parabola, the reflected point $(x, -y)$ across the $x$-axis also lies on the parabola. Therefore, the **axis of symmetry** is the **$x$-axis** (the line $y = 0$).

---

### 2. Finding Points on the Parabola for $x = 3$

Substituting $x = 3$ into the equation $y^2 = 12x$:

$$
\begin{aligned}
y^2 &= 12(3) \\
y^2 &= 36 \\
y &= \pm\sqrt{36} \\
y &= \pm 6
\end{aligned}
$$

Thus, for $x = 3$, we obtain two symmetric points on the parabola:

$$
P_1 = (3, 6), \qquad P_2 = (3, -6)
$$

*(Geometric note: Comparing $y^2 = 12x$ with the standard focal equation $y^2 = 4cx$ gives $4c = 12 \implies c = 3$. Hence, $F = (3, 0)$ is the **focus** of the parabola, and the segment joining $P_1 = (3, 6)$ and $P_2 = (3, -6)$ is the **latus rectum** of length $4c = 12$, which defines the width of the parabola at its focus.)*

---

### 3. Sketch of the Parabola $y^2 = 12x$

Plotting the vertex $V = (0, 0)$, the axis of symmetry along the $x$-axis, and the symmetric guide points $P_1 = (3, 6)$ and $P_2 = (3, -6)$:

```text
        y
        ^             . * P1(3,6)
        |         . '   :
        |     . '       :
        |  . '          :
  V(0,0)*---------------+------> x (Axis of symmetry: y = 0)
        |  ' .        (3,0)
        |     ' .       :
        |         ' .   :
        |             ' * P2(3,-6)
```

---

## Verification and Consistency Checks

### Check 1: Substitution of $P_1 = (3, 6)$ and $P_2 = (3, -6)$

- **For $P_1 = (3, 6)$:**
  - Left-hand side: $y^2 = 6^2 = 36$
  - Right-hand side: $12x = 12(3) = 36$
  - Since $36 = 36$, $P_1$ lies on the curve.

- **For $P_2 = (3, -6)$:**
  - Left-hand side: $y^2 = (-6)^2 = 36$
  - Right-hand side: $12x = 12(3) = 36$
  - Since $36 = 36$, $P_2$ lies on the curve.

### Check 2: Focus–Directrix Distance Property

With focus $F = (3, 0)$ and directrix $L: x = -3$, every point on the parabola is equidistant from $F$ and $L$. Testing $P_1 = (3, 6)$:
- Distance to focus $F = (3, 0)$:

$$
d(P_1, F) = \sqrt{(3 - 3)^2 + (6 - 0)^2} = 6
$$

- Perpendicular distance to directrix $x = -3$:

$$
d(P_1, L) = |3 - (-3)| = 6
$$

The two distances are equal ($6 = 6$).

---

## Why This Exercise Matters

- **Role of the Linear Variable:** In a parabola equation with no shifts, the **linear variable** ($x$ in $y^2 = 12x$) always designates the **axis of symmetry**, and the **sign of its coefficient** ($+12 > 0$) designates whether the parabola opens in the positive or negative direction of that axis.
- **Scale Setting via One Cross-Section:** Finding the two symmetric points at a single value of $x$ (such as $x = 3 \implies y = \pm 6$) fixes the vertical opening width and prevents drawing the parabola too narrow or too flat.
