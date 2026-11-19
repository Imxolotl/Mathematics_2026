# Problem 14: Cone and Cylinder

## Question

Compare

$$
x^2+y^2=z^2
$$

and

$$
x^2+y^2=4.
$$

For each surface, describe the cross-sections $z=c$, $x=0$, and $y=0$, make a sketch, and explain why the radius of the cross-section depends on $z$ in the first case but is constant in the second.

---

## Solution

### 1. Surface 1: $x^2 + y^2 = z^2$ (Circular Cone)

#### Horizontal Cross-Sections $z = c$

Substituting $z = c$ ($c \in \mathbb{R}$) gives:

$$
x^2 + y^2 = c^2, \qquad z = c
$$

- **For $c = 0$:** $x^2 + y^2 = 0$, which gives $(x, y) = (0, 0)$, a single point $(0, 0, 0)$ (the vertex / apex of the cone).
- **For $c \neq 0$:** This is a circle in the plane $z = c$ centered at $(0, 0, c)$ with radius:

$$
r_1(c) = \sqrt{c^2} = |c|
$$

The radius grows linearly in proportion to the distance $|c|$ from the $xy$-plane.

#### Vertical Cross-Section $x = 0$ (in the $yz$-plane)

Substituting $x = 0$ gives $y^2 = z^2$, which factors as:

$$
(z - y)(z + y) = 0
$$

$$
z = y \qquad \mathrm{or} \qquad z = -y
$$

This is a pair of intersecting straight lines ($z = y$ and $z = -y$) in the $yz$-plane crossing at the origin $(0, 0, 0)$ at slopes $+1$ and $-1$.

#### Vertical Cross-Section $y = 0$ (in the $xz$-plane)

Substituting $y = 0$ gives $x^2 = z^2$, which factors as:

$$
(z - x)(z + x) = 0
$$

$$
z = x \qquad \mathrm{or} \qquad z = -x
$$

This is an identical pair of intersecting straight lines ($z = x$ and $z = -x$) in the $xz$-plane crossing at $(0, 0, 0)$.

#### Sketch of $x^2 + y^2 = z^2$ (Double Circular Cone)

```text
               z
               ^
      . - - - -|- - - - .      <- Circle of radius r = |c| at z = c > 0
     \  ' - - -+- - - '  /
      \        |        /      <- Straight generator lines z = +-x, z = +-y
       \       |       /
        \      |      /
         \     |     /
          ' .  |  . '
             ' * ' ----------> y   <- Vertex (0,0,0) at z = 0 (r = 0)
          . ' /|\ ' .
         /   / | \   \
        /      |      \
       /       |       \
      / . - - -+- - - . \
     / ' - - - | - - - ' \     <- Circle of radius r = |c| at z = c < 0
              v
             x
```

---

### 2. Surface 2: $x^2 + y^2 = 4$ (Circular Cylinder)

In three-dimensional space $\mathbb{R}^3$, the equation $x^2 + y^2 = 4$ implicitly allows $z$ to take any real value ($x^2 + y^2 + 0 \cdot z = 4$).

#### Horizontal Cross-Sections $z = c$

Substituting $z = c$ into $x^2 + y^2 = 4$ leaves the equation completely unchanged:

$$
x^2 + y^2 = 4 = 2^2, \qquad z = c
$$

For every $c \in \mathbb{R}$, the cross-section in the plane $z = c$ is a circle centered at $(0, 0, c)$ with constant radius:

$$
r_2(c) = \sqrt{4} = 2
$$

#### Vertical Cross-Section $x = 0$ (in the $yz$-plane)

Substituting $x = 0$ into $x^2 + y^2 = 4$ (with $z \in \mathbb{R}$ arbitrary) gives $y^2 = 4$:

$$
y = 2 \qquad \mathrm{or} \qquad y = -2
$$

Because $z$ is unrestricted, this consists of two parallel vertical lines ($x = 0, y = 2$ and $x = 0, y = -2$) in the $yz$-plane at distance $2$ on either side of the $z$-axis.

#### Vertical Cross-Section $y = 0$ (in the $xz$-plane)

Substituting $y = 0$ into $x^2 + y^2 = 4$ (with $z \in \mathbb{R}$ arbitrary) gives $x^2 = 4$:

$$
x = 2 \qquad \mathrm{or} \qquad x = -2
$$

This consists of two parallel vertical lines ($x = 2, y = 0$ and $x = -2, y = 0$) in the $xz$-plane at distance $2$ on either side of the $z$-axis.

#### Sketch of $x^2 + y^2 = 4$ (Vertical Circular Cylinder)

```text
               z
               ^
       . - - - | - - - .       <- Circle of radius r = 2 at z = c > 0
      |  ' - - + - - '  |
      |        |        |
      |        |        |      <- Parallel vertical walls x = +-2, y = +-2
      |  . - - * - - .  |
      | (     /|\     ) |-----> y  <- Circle of radius r = 2 at z = 0
      |  ' - - | - - '  |
      |        |        |
      |  . - - + - - .  |
       ' - - - | - - - '       <- Circle of radius r = 2 at z = c < 0
              /
             v
            x
```

---

### 3. Explanation: Why the Radius Depends on $z$ in the Cone but Is Constant in the Cylinder

In $\mathbb{R}^3$, the quantity $\sqrt{x^2 + y^2}$ is the horizontal radial distance $r$ of a point $(x, y, z)$ from the vertical $z$-axis:

$$
r = \sqrt{x^2 + y^2}
$$

#### 1. In the Cone ($x^2 + y^2 = z^2$)

The variable $z$ appears explicitly on the right-hand side as $z^2$. Rewriting the equation in terms of $r = \sqrt{x^2 + y^2}$ gives $r^2 = z^2$, so:

$$
r = |z|
$$

This equation directly couples a point's distance $r$ from the $z$-axis to its vertical height $|z|$. When we slice at height $z = c$, the right-hand side changes to $c^2$, forcing the cross-sectional radius $r_1(c) = |c|$ to vary with $z$.

#### 2. In the Cylinder ($x^2 + y^2 = 4$)

The variable $z$ is completely absent from the equation, while the right-hand side is the fixed constant $4 = 2^2$. Rewriting in terms of $r = \sqrt{x^2 + y^2}$ gives $r^2 = 4$, so:

$$
r = 2
$$

Whether a point is at $z = 0$, $z = 10$, or $z = -100$, the condition $x^2 + y^2 = 4$ imposes the exact same requirement on $(x, y)$ and no condition at all on $z$. Geometrically, any equation in $\mathbb{R}^3$ missing one coordinate variable (such as $F(x, y) = 0$) describes a cylinder generated by translating the 2D curve $F(x, y) = 0$ unchanged along the missing axis ($Oz$).

---

## Side-by-Side Comparison Table

| Feature | Cone ($x^2 + y^2 = z^2$) | Cylinder ($x^2 + y^2 = 4$) |
| :--- | :--- | :--- |
| **Role of $z$ in equation** | Present as $z^2$ on RHS | Absent ($z$ is completely free) |
| **Horizontal slice** | Circle $x^2 + y^2 = c^2$ (point at $c=0$) | Circle $x^2 + y^2 = 4$ for all $c \in \mathbb{R}$ |
| **Radius at height $z = c$** | $r_1(c) = \sqrt{c^2}$ (depends linearly on $z$) | $r_2(c) = 2$ (constant for all $z$) |
| **Vertical slice $x = 0$** | Two intersecting lines $z = \pm y$ | Two parallel vertical lines $y = \pm 2$ |
| **Vertical slice $y = 0$** | Two intersecting lines $z = \pm x$ | Two parallel vertical lines $x = \pm 2$ |

---

## Why This Exercise Matters

- **Missing-Variable Rule in 3D Geometry:** Whenever one of the three coordinates $(x, y, z)$ is missing from a surface equation in $\mathbb{R}^3$, every cross-section perpendicular to the missing axis is an identical translated copy of the 2D curve, forming a cylinder parallel to that axis.
