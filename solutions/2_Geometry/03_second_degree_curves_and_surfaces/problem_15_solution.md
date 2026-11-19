# Problem 15: Recognition and Sketch Without a Given Name

## Question

Consider the two equations:

$$
4x^2+9y^2-8x+36y+4=0,
$$

$$
4x^2+y^2=z^2.
$$

For the first equation, reduce it to canonical form, recognize the curve, give its most important features, and make a sketch.

For the second equation, do not begin by using a ready-made name for the surface. First describe the cross-sections $z=c$ and the cross-sections by the planes $x=0$ and $y=0$, paying attention to the different scales along the axes. Only then identify the surface and make a sketch.

---

## Solution

### Part 1: First Equation ($4x^2 + 9y^2 - 8x + 36y + 4 = 0$)

#### 1. Reduction to Canonical Form by Completing the Square

We group the $x$-terms and $y$-terms and move the constant term $+4$ to the right-hand side:

$$
(4x^2 - 8x) + (9y^2 + 36y) = -4
$$

Factor out the quadratic coefficients $4$ and $9$ from each group:

$$
4(x^2 - 2x) + 9(y^2 + 4y) = -4
$$

Complete the square inside each parenthesis:
- For $x^2 - 2x$: Half of $-2$ is $-1$, and $(-1)^2 = 1$, so $x^2 - 2x + 1 = (x - 1)^2$. Because of the outer factor $4$, adding $1$ inside adds $4 \cdot 1 = 4$ to the left-hand side.
- For $y^2 + 4y$: Half of $4$ is $2$, and $2^2 = 4$, so $y^2 + 4y + 4 = (y + 2)^2$. Because of the outer factor $9$, adding $4$ inside adds $9 \cdot 4 = 36$ to the left-hand side.

Adding $4$ and $36$ to both sides:

$$
4(x^2 - 2x + 1) + 9(y^2 + 4y + 4) = -4 + 4 + 36
$$

$$
4(x - 1)^2 + 9(y + 2)^2 = 36
$$

Dividing both sides by $36$ gives the canonical form:

$$
\frac{(x - 1)^2}{9} + \frac{(y + 2)^2}{4} = 1 \qquad \mathrm{or} \qquad \frac{(x - 1)^2}{3^2} + \frac{(y - (-2))^2}{2^2} = 1
$$

#### 2. Recognition and Most Important Features

- **Type of Curve:** Shifted Ellipse in $\mathbb{R}^2$.
- **Center:** $C = (1, -2)$
- **Horizontal semiaxis (major semiaxis, parallel to $Ox$):** $a = \sqrt{9} = 3$ (full major axis length $2a = 6$).
- **Vertical semiaxis (minor semiaxis, parallel to $Oy$):** $b = \sqrt{4} = 2$ (full minor axis length $2b = 4$).
- **Horizontal major vertices:** $(1 \pm 3, -2)$, which gives $V_1 = (-2, -2)$ and $V_2 = (4, -2)$.
- **Vertical minor co-vertices:** $(1, -2 \pm 2)$, which gives $B_1 = (1, -4)$ and $B_2 = (1, 0)$.
- **Axis Tangency and Intercepts:** Because the top co-vertex is $B_2 = (1, 0)$, the ellipse is tangent to the $x$-axis at $(1, 0)$. Setting $x = 0$ gives $\frac{1}{9} + \frac{(y + 2)^2}{4} = 1$, so $y = -2 \pm \frac{4\sqrt{2}}{3}$, giving two $y$-intercepts at approximately $(0, -0.11)$ and $(0, -3.89)$.
- **Foci:** $c = \sqrt{a^2 - b^2} = \sqrt{9 - 4} = \sqrt{5} \approx 2.24$, located at $F_1 = (1 - \sqrt{5}, -2)$ and $F_2 = (1 + \sqrt{5}, -2)$.

#### 3. Sketch of the Shifted Ellipse

```text
               y
               ^
               |   B2(1,0)
        -------+-----*-------------> x
           . - | - - : - - .
        . '    |     :      ' .
(-2,-2)*-------+-----*---------* (4,-2)
      V1       |   C(1,-2)     V2
        ' .    |     :      . '
           ' - | - - * - - '
               |   B1(1,-4)
```

---

### Part 2: Second Equation ($4x^2 + y^2 = z^2$)

Following the instructions, we analyze the planar cross-sections first before naming the surface.

#### 1. Horizontal Cross-Sections $z = c$ (Parallel to the $xy$-Plane)

Substituting $z = c$ ($c \in \mathbb{R}$) into $4x^2 + y^2 = z^2$:

$$
4x^2 + y^2 = c^2, \qquad z = c
$$

#### Case $c = 0$ (in the $xy$-plane)

$$
4x^2 + y^2 = 0
$$

Because both $4x^2 \ge 0$ and $y^2 \ge 0$, their sum vanishes only when $x = 0$ and $y = 0$. Thus, the slice $z = 0$ is a single point $(0, 0, 0)$.

#### Case $c \neq 0$ (above or below the $xy$-plane)

Dividing both sides by $c^2 > 0$ puts the cross-section into canonical form:

$$
\frac{4x^2}{c^2} + \frac{y^2}{c^2} = 1
$$

$$
\frac{x^2}{(c/2)^2} + \frac{y^2}{c^2} = 1, \qquad z = c
$$

This is an ellipse in the horizontal plane $z = c$ centered at $(0, 0, c)$ on the $z$-axis, with semiaxis lengths along the $x$-axis and $y$-axis given by:

$$
a(c) = \frac{|c|}{2}, \qquad b(c) = |c|
$$

- **Different Scales Along the Axes:** At every nonzero height $z = c$, the $y$-semiaxis is twice as long as the $x$-semiaxis ($b(c) = 2 a(c)$). For example, at $z = \pm 2$, the ellipse is $\frac{x^2}{1^2} + \frac{y^2}{2^2} = 1$, extending to $\pm 1$ along $Ox$ and $\pm 2$ along $Oy$. Both semiaxes grow linearly with $|c|$ as we move away from $z = 0$.

#### 2. Vertical Cross-Sections by the Planes $x = 0$ and $y = 0$

#### Cross-section by the plane $x = 0$ (in the $yz$-plane)

Setting $x = 0$ in $4x^2 + y^2 = z^2$ gives $y^2 = z^2$, which factors as:

$$
(z - y)(z + y) = 0
$$

$$
z = y \qquad \mathrm{or} \qquad z = -y
$$

This consists of two intersecting straight lines passing through the origin $(0, 0, 0)$ with slopes $\pm 1$ (forming $45^\circ$ angles with the $y$- and $z$-axes).

#### Cross-section by the plane $y = 0$ (in the $xz$-plane)

Setting $y = 0$ in $4x^2 + y^2 = z^2$ gives $4x^2 = z^2$, which factors as:

$$
(z - 2x)(z + 2x) = 0
$$

$$
z = 2x \qquad \mathrm{or} \qquad z = -2x
$$

This also consists of two intersecting straight lines passing through the origin $(0, 0, 0)$, but with steeper slopes $\pm 2$ (making a narrower opening angle with the vertical $z$-axis than the lines in the $yz$-plane).

- **Connection Between Vertical Slopes and Horizontal Scales:** In the $xz$-plane ($y = 0$), the lines $z = \pm 2x$ rise twice as steeply ($|z| = 2|x|$), so at height $|z| = |c|$ the surface only reaches $|x| = \frac{|c|}{2}$. In the $yz$-plane ($x = 0$), the lines $z = \pm y$ rise more gently ($|z| = |y|$), so at height $|z| = |c|$ the surface reaches twice as far out to $|y| = |c|$.

#### 3. Identification of the Surface and Sketch

Combining our cross-sectional findings:
1. A single apex point at $(0, 0, 0)$ for $z = 0$,
2. Straight-line generators passing through $(0, 0, 0)$ in every vertical plane through the $z$-axis ($z = \pm y$ and $z = \pm 2x$),
3. Linearly expanding elliptical cross-sections $\frac{x^2}{(c/2)^2} + \frac{y^2}{c^2} = 1$ at height $z = c \neq 0$,

we identify the surface as a **double elliptic cone** with vertex at the origin $(0, 0, 0)$ and axis along the $z$-axis, stretched twice as wide in the $y$-direction as in the $x$-direction.

#### Sketch of $4x^2 + y^2 = z^2$ (Elliptic Cone)

```text
                  z
                  ^
     . - - - - - -|- - - - - - .      <- Ellipse at z = c > 0:
   (   ' - - - - -+- - - - - '   )       narrower along x (a = |c|/2),
    \             |             /        wider along y (b = |c|)
     \  z = -y    |    z = y   /
      \           |           /
       ' .        |        . '
          ' .     |     . '
             ' .  |  . '
                ' * ' --------------> y (wider opening: z = +-y)
             . ' /|\ ' .
          . '   / | \   ' .
       . '     /  |  \     ' .
      /           |           \
     / . - - - - -+- - - - - . \
   (   ' - - - - -|- - - - - '   )    <- Ellipse at z = c < 0
     ' - - - - - -|- - - - - - '
                 /
                v
               x (narrower opening: z = +-2x)
```

---

## Why This Exercise Matters

- **Completing the Square:** Translates shifted second-degree equations ($4x^2 + 9y^2 - 8x + 36y + 4 = 0$) into canonical form where center and semiaxes are visible immediately.
- **Cross-Sectional Analysis:** Reveals the exact 3D geometry and anisotropic scaling ($a(c) = \frac{|c|}{2}$ vs. $b(c) = |c|$) of a quadric surface ($4x^2 + y^2 = z^2$) from first principles without relying on memorized formulas.
