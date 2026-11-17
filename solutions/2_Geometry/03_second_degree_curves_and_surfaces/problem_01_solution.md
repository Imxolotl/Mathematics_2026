# Problem 1: Recognizing Curves from Canonical Form

## Question

Recognize the curves

$$
x^2+y^2=9,
$$

$$
\frac{x^2}{16}+\frac{y^2}{9}=1,
$$

$$
y^2=8x,
$$

$$
\frac{x^2}{9}-\frac{y^2}{4}=1.
$$

For each one, identify the most important features and make a sketch. Explain which parts of the equation let you recognize the type of curve.

---

## Solution

### 1. How to Recognize the Type of Curve from the Equation

Before analyzing each curve individually, we summarize the structural dictionary that links a second-degree equation in $x$ and $y$ to its geometric family:

1. **Both $x^2$ and $y^2$ present, same sign, equal coefficients ($x^2 + y^2 = r^2$):**
   The distance from the origin is isotropic (the same in every direction), which defines a **circle**.
2. **Both $x^2$ and $y^2$ present, same sign, unequal denominators ($\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ with $a \neq b$):**
   The sum of normalized squares is bounded by $1$, producing a closed bounded curve stretched differently along the $x$- and $y$-axes — an **ellipse**.
3. **Only one variable is squared and the other is linear ($y^2 = 2px$ or $x^2 = 2py$):**
   Because one variable appears to the first power and the other to the second power, the curve is unbounded and symmetric about a single axis — a **parabola**.
4. **Both $x^2$ and $y^2$ present with opposite signs ($\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$):**
   A difference of squares equal to $1$ allows both $|x|$ and $|y|$ to grow without bound along two separate branches — a **hyperbola**.

---

### 2. Curve 1: $x^2 + y^2 = 9$ — Circle

$$
x^2 + y^2 = 3^2
$$

- **How It Is Recognized:** Both $x^2$ and $y^2$ have the same positive coefficient $1$, and the right-hand side is $9 = 3^2 > 0$. This is the canonical equation $x^2 + y^2 = r^2$ of a circle centered at the origin.
- **Key Geometric Features:**
  - **Center:** $(0, 0)$
  - **Radius:** $r = \sqrt{9} = 3$
  - **$x$-intercepts ($y = 0$):** $(-3, 0)$ and $(3, 0)$
  - **$y$-intercepts ($x = 0$):** $(0, -3)$ and $(0, 3)$
  - **Domain and Range:** $x \in [-3, 3]$, $y \in [-3, 3]$
  - **Symmetry:** Symmetric with respect to the $x$-axis, the $y$-axis, the origin, and every line through $(0, 0)$.

#### Sketch of $x^2 + y^2 = 9$:

```text
            y
            ^
            |    (0,3)
         . - * - .
       '     |     '
      /      |      \
(-3,0)*------+------* (3,0) ---> x
      \     (0,0)   /
       .     |     .
         ' - * - '
            |   (0,-3)
```

---

### 3. Curve 2: $\frac{x^2}{16} + \frac{y^2}{9} = 1$ — Ellipse

$$
\frac{x^2}{4^2} + \frac{y^2}{3^2} = 1
$$

- **How It Is Recognized:** Both $x^2$ and $y^2$ are positive and their sum equals $1$, but the denominators are unequal ($16 \neq 9$). This is the canonical equation $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ of an ellipse centered at the origin.
- **Key Geometric Features:**
  - **Center:** $(0, 0)$
  - **Horizontal semiaxis (major semiaxis):** $a = \sqrt{16} = 4$ along the $x$-axis
  - **Vertical semiaxis (minor semiaxis):** $b = \sqrt{9} = 3$ along the $y$-axis
  - **Vertices on the $x$-axis ($y = 0$):** $(-4, 0)$ and $(4, 0)$
  - **Vertices on the $y$-axis ($x = 0$):** $(0, -3)$ and $(0, 3)$
  - **Orientation:** Because $16 > 9$ ($a = 4 > 3 = b$), the ellipse is elongated horizontally along the $x$-axis.
  - **Foci:** $c = \sqrt{a^2 - b^2} = \sqrt{16 - 9} = \sqrt{7} \approx 2.65$, located at $(-\sqrt{7}, 0)$ and $(\sqrt{7}, 0)$.

#### Sketch of $\frac{x^2}{16} + \frac{y^2}{9} = 1$:

```text
               y
               ^
               |    (0,3)
         . - - * - - .
      . '      |      ' .
    /          |          \
(-4,0)*--------+--------* (4,0) ---> x
    \        (0,0)        /
      ' .      |      . '
         ' - - * - - '
               |   (0,-3)
```

---

### 4. Curve 3: $y^2 = 8x$ — Parabola

- **How It Is Recognized:** The variable $y$ is squared ($y^2$), whereas the variable $x$ appears only to the first power ($8x$).
- **Key Geometric Features:**
  - **Vertex:** $(0, 0)$
  - **Axis of Symmetry:** The $x$-axis ($y = 0$), because replacing $y$ by $-y$ leaves $y^2 = 8x$ unchanged.
  - **Opening Direction:** Opens to the **right** (along the positive $x$-axis), because $y^2 \ge 0$ forces $8x \ge 0 \implies x \ge 0$.
  - **Focus and Directrix:** Comparing $y^2 = 8x$ with $y^2 = 4cx$ gives $4c = 8 \implies c = 2$, so the focus is at $(2, 0)$ and the directrix is the vertical line $x = -2$.
  - **Sample Points (for $x = 2$):** $y^2 = 8(2) = 16 \implies y = \pm 4$, giving $(2, 4)$ and $(2, -4)$.

#### Sketch of $y^2 = 8x$:

```text
        y
        ^          . * (2,4)
        |      . '
        |   . '
        | /
  (0,0) *--------------> x
        | \
        |   ' .
        |      ' .
        |          ' * (2,-4)
```

---

### 5. Curve 4: $\frac{x^2}{9} - \frac{y^2}{4} = 1$ — Hyperbola

$$
\frac{x^2}{3^2} - \frac{y^2}{2^2} = 1
$$

- **How It Is Recognized:** Both $x^2$ and $y^2$ appear to the second power, but with **opposite signs** ($+$ on $\frac{x^2}{9}$ and $-$ on $\frac{y^2}{4}$).
- **Key Geometric Features:**
  - **Center:** $(0, 0)$
  - **Transverse semiaxis:** $a = \sqrt{9} = 3$ (along the $x$-axis, which carries the positive sign)
  - **Conjugate semiaxis:** $b = \sqrt{4} = 2$ (along the $y$-axis)
  - **Vertices ($x$-intercepts at $y = 0$):** $(-3, 0)$ and $(3, 0)$
  - **$y$-intercepts ($x = 0$):** None, since $-\frac{y^2}{4} = 1 \implies y^2 = -4$ has no real solutions.
  - **Domain:** $\frac{x^2}{9} = 1 + \frac{y^2}{4} \ge 1 \implies |x| \ge 3$, so $x \in (-\infty, -3] \cup [3, \infty)$ (two separate branches opening left and right).
  - **Asymptotes:** Replacing $1$ by $0$ gives $\frac{x^2}{9} - \frac{y^2}{4} = 0 \implies y = \pm \frac{b}{a} x = \pm \frac{2}{3} x$.

#### Sketch of $\frac{x^2}{9} - \frac{y^2}{4} = 1$:

```text
      \     y     /
       \    ^    /   y = (2/3)x
    \   \   |   /   /
     \   \  |  /   /
      |   \ | /   |
------+----\+/----+------> x
 (-3,0)*   /|\   *(3,0)
      |   / | \   |
     /   /  |  \   \
    /   /   |   \   \
       /         \   y = -(2/3)x
```

---

## Summary Comparison Table

| Equation | Algebraic Signature | Curve Type | Center / Vertex | Key Scale Parameters |
| :--- | :--- | :--- | :--- | :--- |
| $x^2 + y^2 = 9$ | $x^2, y^2$ same sign, equal coefficients | Circle | Center $(0,0)$ | Radius $r = 3$ |
| $\frac{x^2}{16} + \frac{y^2}{9} = 1$ | $x^2, y^2$ same sign, unequal denominators | Ellipse | Center $(0,0)$ | Semiaxes $a = 4, b = 3$ |
| $y^2 = 8x$ | One squared ($y^2$), one linear ($x$) | Parabola | Vertex $(0,0)$ | Opens right ($x \ge 0$) |
| $\frac{x^2}{9} - \frac{y^2}{4} = 1$ | $x^2, y^2$ opposite signs | Hyperbola | Center $(0,0)$ | Vertices $(\pm 3, 0)$, asymptotes $y = \pm\frac{2}{3}x$ |

---

## Why This Exercise Matters

- **Structural Pattern Recognition:** Before computing any points, the degrees and signs of $x$ and $y$ immediately classify the curve as bounded (circle/ellipse) or unbounded (parabola/hyperbola).
- **Building Blocks for 3D Quadric Surfaces:** Recognizing circles, ellipses, parabolas, and hyperbolas in 2D is essential for analyzing 3D surfaces via planar cross-sections (Exercises 9–15).
