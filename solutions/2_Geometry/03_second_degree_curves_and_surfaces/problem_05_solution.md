# Problem 5: Hyperbola and Asymptotes

## Question

For

$$
\frac{x^2}{16}-\frac{y^2}{9}=1,
$$

find the intercepts with the $x$-axis, the asymptotes, and make a sketch. Explain why the asymptotes describe the behavior of the curve far from the center.

---

## Solution

### 1. Canonical Parameters and $x$-Axis Intercepts (Vertices)

The canonical equation of a horizontal hyperbola centered at the origin $(0, 0)$ is:

$$
\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1
$$

Writing the denominators as squares:

$$
\frac{x^2}{4^2} - \frac{y^2}{3^2} = 1
$$

We identify the semiaxes:
- **Transverse semiaxis (along the $x$-axis):** $a = \sqrt{16} = 4$
- **Conjugate semiaxis (along the $y$-axis):** $b = \sqrt{9} = 3$

#### Finding the $x$-axis intercepts (set $y = 0$):

$$
\frac{x^2}{16} - \frac{0^2}{9} = 1 \implies \frac{x^2}{16} = 1 \implies x^2 = 16 \implies x = \pm 4
$$

Thus, the intercepts with the $x$-axis (the **vertices** of the hyperbola) are:

$$
V_1 = (-4, 0), \qquad V_2 = (4, 0)
$$

*(Note: Setting $x = 0$ gives $-\frac{y^2}{9} = 1 \implies y^2 = -9$, which has no real solutions. Indeed, $\frac{x^2}{16} = 1 + \frac{y^2}{9} \ge 1 \implies |x| \ge 4$, so no part of the hyperbola lies in the vertical strip $-4 < x < 4$.)*

---

### 2. Finding the Asymptotes

The asymptotes of the hyperbola $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$ are obtained by replacing the constant $1$ on the right-hand side with $0$:

$$
\frac{x^2}{16} - \frac{y^2}{9} = 0
$$

Factoring as a difference of squares or solving for $y$:

$$
\frac{y^2}{9} = \frac{x^2}{16} \implies \frac{y}{3} = \pm \frac{x}{4} \implies y = \pm \frac{3}{4} x
$$

Thus, the two asymptote lines are:

$$
L_1: y = \frac{3}{4} x, \qquad L_2: y = -\frac{3}{4} x
$$

Geometrically, these two lines pass through the origin $(0, 0)$ and are the extended diagonals of the **fundamental reference rectangle** $[-4, 4] \times [-3, 3]$ with corners at $(\pm 4, \pm 3)$.

---

### 3. Sketch of the Hyperbola and Its Asymptotes

```text
      \      y      /
       \     ^     /   y = (3/4)x
   \    \   (0,3) /    /
    \    \ .-+-. /    /
     |    |  |  |    |
-----+----*--+--*----+-----> x
(-4,0)    | (0,0)    (4,0)
     |    |  |  |    |
    /    / '-+-' \    \
   /    /  (0,-3) \    \
       /           \   y = -(3/4)x
      /             \
```

- The left branch passes through $V_1 = (-4, 0)$ and opens to the left ($x \le -4$), approaching $y = \pm \frac{3}{4}x$.
- The right branch passes through $V_2 = (4, 0)$ and opens to the right ($x \ge 4$), approaching $y = \pm \frac{3}{4}x$.

---

### 4. Explanation: Why the Asymptotes Describe the Behavior Far from the Center

#### 1. Relative Negligibility of the Constant $1$ at Large $|x|$ and $|y|$
In the equation $\frac{x^2}{16} - \frac{y^2}{9} = 1$, when $|x|$ and $|y|$ are very large (far from the center $(0, 0)$), both $\frac{x^2}{16}$ and $\frac{y^2}{9}$ are huge numbers (e.g., $10^6$), yet their difference is fixed at $1$. Relative to $10^6$, the constant $1$ is negligible, so $\frac{x^2}{16} \approx \frac{y^2}{9}$.

More explicitly, solving $\frac{x^2}{16} - \frac{y^2}{9} = 1$ for $y$ when $|x| \ge 4$:

$$
\frac{y^2}{9} = \frac{x^2}{16} - 1 = \frac{x^2}{16} \left( 1 - \frac{16}{x^2} \right)
$$

Taking square roots gives:

$$
y = \pm \frac{3}{4} x \sqrt{1 - \frac{16}{x^2}}
$$

As $|x| \to \infty$, the fraction $\frac{16}{x^2} \to 0$, so the square root factor approaches $\sqrt{1 - 0} = 1$, and $y$ behaves like $\pm \frac{3}{4} x$.

#### 2. Exact Proof that the Vertical Distance Shrinks to Zero
In the first quadrant ($x \ge 4, y \ge 0$), the vertical gap between the asymptote line $y_{\mathrm{asym}} = \frac{3}{4} x$ and the hyperbola branch $y_{\mathrm{hyp}} = \frac{3}{4} \sqrt{x^2 - 16}$ is:

$$
\begin{aligned}
y_{\mathrm{asym}} - y_{\mathrm{hyp}} &= \frac{3}{4} \left( x - \sqrt{x^2 - 16} \right) \\
                                     &= \frac{3}{4} \cdot \frac{\left(x - \sqrt{x^2 - 16}\right)\left(x + \sqrt{x^2 - 16}\right)}{x + \sqrt{x^2 - 16}} \\
                                     &= \frac{3}{4} \cdot \frac{x^2 - (x^2 - 16)}{x + \sqrt{x^2 - 16}} \\
                                     &= \frac{12}{x + \sqrt{x^2 - 16}}
\end{aligned}
$$

- Because $x + \sqrt{x^2 - 16} > 0$, we always have $y_{\mathrm{asym}} > y_{\mathrm{hyp}}$ (in the first quadrant, the hyperbola stays strictly below its asymptote).
- As $x \to +\infty$, the denominator $x + \sqrt{x^2 - 16} \to +\infty$, so the vertical distance $\frac{12}{x + \sqrt{x^2 - 16}} \to 0$.

---

## Verification and Consistency Checks

### Numerical Check of Asymptotic Convergence

Let us compare $y_{\mathrm{hyp}} = \frac{3}{4}\sqrt{x^2 - 16}$ and $y_{\mathrm{asym}} = \frac{3}{4}x$ at increasing values of $x$:

- **At $x = 5$:**
  - Hyperbola: $y_{\mathrm{hyp}} = \frac{3}{4}\sqrt{25 - 16} = \frac{3}{4}(3) = \frac{9}{4} = 2.25$ (exact point $(5, 2.25)$ on the curve).
  - Asymptote: $y_{\mathrm{asym}} = \frac{3}{4}(5) = \frac{15}{4} = 3.75$ (gap $= 1.50$).
- **At $x = 40$:**
  - Hyperbola: $y_{\mathrm{hyp}} = \frac{3}{4}\sqrt{1600 - 16} \approx 29.850$.
  - Asymptote: $y_{\mathrm{asym}} = \frac{3}{4}(40) = 30.000$ (gap $\approx 0.150$).

As $x$ increases by a factor of $8$, the vertical gap shrinks by a factor of $10$, illustrating rapid convergence toward the asymptote.

---

## Why This Exercise Matters

- **Global Shape from Two Lines and Two Points:** To sketch any hyperbola accurately, you do not need to plot dozens of points: draw the reference box $[-a, a] \times [-b, b]$, extend its diagonals to form the asymptotes $y = \pm \frac{b}{a}x$, mark the vertices $(\pm a, 0)$, and draw smooth branches curving from the vertices toward the asymptotes.
