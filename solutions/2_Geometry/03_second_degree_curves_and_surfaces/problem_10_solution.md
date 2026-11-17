# Problem 10: Paraboloids

## Question

Compare

$$
z=x^2+y^2
$$

and

$$
z=x^2-y^2.
$$

For each surface, describe the cross-sections $x=0$, $y=0$, and $z=c$, then make a qualitative sketch.

---

## Solution

### 1. Surface 1: $z = x^2 + y^2$ (Circular / Elliptic Paraboloid)

In $z = x^2 + y^2$, the variable $z$ is linear while both $x^2$ and $y^2$ appear with the **same positive sign**.

#### 1. Vertical Cross-Section $x = 0$ (in the $yz$-plane):

Substituting $x = 0$:

$$
z = y^2, \qquad x = 0
$$

- This is a **parabola** in the $yz$-plane with vertex at $(0, 0, 0)$, symmetric about the $z$-axis, opening **upward** ($z \ge 0$).

#### 2. Vertical Cross-Section $y = 0$ (in the $xz$-plane):

Substituting $y = 0$:

$$
z = x^2, \qquad y = 0
$$

- This is an identical **parabola** in the $xz$-plane with vertex at $(0, 0, 0)$, symmetric about the $z$-axis, opening **upward** ($z \ge 0$).

#### 3. Horizontal Cross-Sections $z = c$ (parallel to the $xy$-plane):

Substituting $z = c$:

$$
x^2 + y^2 = c, \qquad z = c
$$

Depending on the sign of $c$, three cases arise:
- **For $c < 0$:** **Empty set** $\emptyset$ (no real points, since $x^2 + y^2 \ge 0$ cannot equal a negative number). The surface never extends below $z = 0$.
- **For $c = 0$:** $x^2 + y^2 = 0 \implies (x, y) = (0, 0)$, a **single point** $(0, 0, 0)$ (the global minimum / vertex of the paraboloid).
- **For $c > 0$:** $x^2 + y^2 = (\sqrt{c})^2$, a **circle** of radius $r(c) = \sqrt{c}$ centered at $(0, 0, c)$ on the $z$-axis. As $c$ increases, the circular slices expand outward.

#### Qualitative Sketch of $z = x^2 + y^2$ (Upward Bowl):

```text
              z
              ^
       . - - -|- - - .       <- Circle x^2 + y^2 = c (z = c > 0)
    \ ' .     |     . ' /
     \   ' - -+- - '   /
      \       |       /      <- Parabolas z = x^2 and z = y^2
       \      |      /          both open UPWARD
        ' .   |   . '
           ' -*- ' ---------> y
            (0,0,0)
             /
            v
           x
```

---

### 2. Surface 2: $z = x^2 - y^2$ (Hyperbolic Paraboloid — Saddle Surface)

In $z = x^2 - y^2$, the variable $z$ is linear while $x^2$ and $y^2$ appear with **opposite signs** ($+x^2$ and $-y^2$).

#### 1. Vertical Cross-Section $x = 0$ (in the $yz$-plane):

Substituting $x = 0$:

$$
z = -y^2, \qquad x = 0
$$

- This is a **parabola** in the $yz$-plane with vertex at $(0, 0, 0)$, symmetric about the $z$-axis, opening **downward** ($z \le 0$).

#### 2. Vertical Cross-Section $y = 0$ (in the $xz$-plane):

Substituting $y = 0$:

$$
z = x^2, \qquad y = 0
$$

- This is a **parabola** in the $xz$-plane with vertex at $(0, 0, 0)$, symmetric about the $z$-axis, opening **upward** ($z \ge 0$).

#### 3. Horizontal Cross-Sections $z = c$ (parallel to the $xy$-plane):

Substituting $z = c$:

$$
x^2 - y^2 = c, \qquad z = c
$$

Unlike the elliptic paraboloid, real cross-sections exist for **every** $c \in \mathbb{R}$, changing orientation as $c$ passes through $0$:
- **For $c > 0$ (above the $xy$-plane):**

$$
\frac{x^2}{c} - \frac{y^2}{c} = 1
$$

  This is a **hyperbola** opening left and right along the **$x$-axis** (vertices at $(\pm\sqrt{c}, 0, c)$).
- **For $c = 0$ (in the $xy$-plane):**

$$
x^2 - y^2 = 0 \iff (x - y)(x + y) = 0 \iff y = x \quad \mathrm{or} \quad y = -x
$$

  This is a **pair of intersecting straight lines** through the origin $(0, 0, 0)$.
- **For $c < 0$ (below the $xy$-plane):**
  Writing $c = -|c|$ and multiplying by $-1$ gives:

$$
y^2 - x^2 = |c| \iff \frac{y^2}{|c|} - \frac{x^2}{|c|} = 1
$$

  This is a **hyperbola** opening along the **$y$-axis** (vertices at $(0, \pm\sqrt{|c|}, c)$).

#### Qualitative Sketch of $z = x^2 - y^2$ (Saddle):

```text
               z
               ^
      \        |        /     <- y = 0 trace: z = x^2 (opens UPWARD along x)
       \       |       /
        ' .    |    . '
           ' - * - ' -------> y
            . ' ' . (0,0,0) Saddle point
          /   / \   \
         /   /   \   \        <- x = 0 trace: z = -y^2 (opens DOWNWARD along y)
            v
           x
```

---

## Side-by-Side Comparison Summary

| Feature | $z = x^2 + y^2$ (Elliptic Paraboloid) | $z = x^2 - y^2$ (Hyperbolic Paraboloid) |
| :--- | :--- | :--- |
| **Signs of $x^2$ and $y^2$** | Same sign ($+x^2 + y^2$) | Opposite signs ($+x^2 - y^2$) |
| **Cross-section $x = 0$** | Parabola $z = y^2$ (opens **upward**) | Parabola $z = -y^2$ (opens **downward**) |
| **Cross-section $y = 0$** | Parabola $z = x^2$ (opens **upward**) | Parabola $z = x^2$ (opens **upward**) |
| **Cross-section $z = c > 0$** | Circle $x^2 + y^2 = c$ of radius $\sqrt{c}$ | Hyperbola $x^2 - y^2 = c$ along $x$-axis |
| **Cross-section $z = 0$** | Single point $(0, 0, 0)$ | Two intersecting lines $y = \pm x$ |
| **Cross-section $z = c < 0$** | Empty set $\emptyset$ | Hyperbola $y^2 - x^2 = |c|$ along $y$-axis |
| **Nature of Origin $(0,0,0)$** | Global minimum (bottom of bowl) | Saddle point (min along $x$, max along $y$) |

---

## Why This Exercise Matters

- **Why Both Are Called "Paraboloids":** Both surfaces have **parabolas** as their vertical cross-sections $x = 0$ and $y = 0$. The adjective (*elliptic* vs. *hyperbolic*) simply describes the shape of their horizontal cross-sections $z = c$ (*ellipses/circles* vs. *hyperbolas*).
- **Single Sign Flip Changes Bowl to Saddle:** Changing $+y^2$ to $-y^2$ flips the vertical parabola $x = 0$ from opening upward ($z = y^2$) to opening downward ($z = -y^2$), turning a minimum point into a saddle point.
