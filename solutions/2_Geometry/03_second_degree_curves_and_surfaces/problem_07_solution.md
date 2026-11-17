# Problem 7: Classifying a Second-Degree Equation

## Question

Determine the type of object described by:

1. $4x^2+9y^2=36$,
2. $x^2-y^2=1$,
3. $x^2-4y=0$,
4. $x^2+y^2+1=0$.

In the last case, explain why there are no real points.

---

## Solution

### 1. Equation 1: $4x^2 + 9y^2 = 36$ — Ellipse

To bring the equation into canonical form, we divide both sides by the right-hand side constant $36$:

$$
\frac{4x^2}{36} + \frac{9y^2}{36} = \frac{36}{36}
$$

Simplifying the fractions:

$$
\frac{x^2}{9} + \frac{y^2}{4} = 1 \qquad \mathrm{or} \qquad \frac{x^2}{3^2} + \frac{y^2}{2^2} = 1
$$

- **Classification:** **Ellipse** in the real plane $\mathbb{R}^2$.
- **Why:** Both $x^2$ and $y^2$ have positive coefficients (with unequal denominators $9 \neq 4$) and their sum equals a positive constant ($1$).
- **Key Features:** Centered at $(0, 0)$, with horizontal major semiaxis $a = 3$ (vertices $(\pm 3, 0)$) and vertical minor semiaxis $b = 2$ (co-vertices $(0, \pm 2)$).

---

### 2. Equation 2: $x^2 - y^2 = 1$ — Hyperbola

This equation is already in canonical form with $a^2 = 1$ and $b^2 = 1$:

$$
\frac{x^2}{1^2} - \frac{y^2}{1^2} = 1
$$

- **Classification:** **Hyperbola** (specifically a **rectangular / equilateral hyperbola** because $a = b = 1$).
- **Why:** Both $x^2$ and $y^2$ appear to the second power, but with **opposite signs** ($+x^2$ and $-y^2$).
- **Key Features:** Centered at $(0, 0)$, opening left and right with vertices at $(-1, 0)$ and $(1, 0)$, and having perpendicular asymptotes $y = x$ and $y = -x$.

---

### 3. Equation 3: $x^2 - 4y = 0$ — Parabola

Isolating the squared term on one side (or solving for $y$):

$$
x^2 = 4y \qquad \mathrm{or} \qquad y = \frac{1}{4} x^2
$$

- **Classification:** **Parabola**.
- **Why:** Only one variable is squared ($x^2$), while the other variable appears linearly ($4y$).
- **Key Features:** Vertex at $(0, 0)$, symmetric about the $y$-axis ($x = 0$), and opening upward ($y \ge 0$) with focus at $(0, 1)$ and directrix $y = -1$.

---

### 4. Equation 4: $x^2 + y^2 + 1 = 0$ — Empty Set (No Real Points)

Moving the constant term to the right-hand side gives:

$$
x^2 + y^2 = -1
$$

- **Classification:** **Empty set** $\emptyset$ in $\mathbb{R}^2$ (an *imaginary circle* with no real points).

#### Explanation: Why There Are No Real Points

1. **Non-Negativity of Real Squares:**
   For every real number $t \in \mathbb{R}$, its square is always greater than or equal to zero ($t^2 \ge 0$). Consequently, for any point $(x, y) \in \mathbb{R}^2$:

$$
x^2 \ge 0 \qquad \mathrm{and} \qquad y^2 \ge 0
$$

   Adding these two non-negative numbers implies that the sum of squares is never negative:

$$
x^2 + y^2 \ge 0 \quad \mathrm{for\ all} \quad (x, y) \in \mathbb{R}^2
$$

2. **Contradiction in $x^2 + y^2 + 1 = 0$:**
   Adding $1$ to both sides of $x^2 + y^2 \ge 0$ shows that for every point $(x, y) \in \mathbb{R}^2$:

$$
x^2 + y^2 + 1 \ge 0 + 1 = 1 > 0
$$

   The left-hand side $x^2 + y^2 + 1$ takes its minimum possible value of $1$ at $(x, y) = (0, 0)$ and is strictly positive everywhere in $\mathbb{R}^2$. Because a number that is at least $1$ can never equal $0$ (equivalently, $x^2 + y^2 \ge 0$ can never equal $-1$), **no pair of real numbers $(x, y)$ satisfies the equation**.

---

## Summary Comparison Table

| Given Equation | Canonical Form | Signs / Degrees of $x$ and $y$ | Geometric Object in $\mathbb{R}^2$ |
| :--- | :--- | :--- | :--- |
| $4x^2 + 9y^2 = 36$ | $\frac{x^2}{3^2} + \frac{y^2}{2^2} = 1$ | $+x^2, +y^2$, RHS $= +1 > 0$ | Ellipse ($a = 3, b = 2$) |
| $x^2 - y^2 = 1$ | $\frac{x^2}{1^2} - \frac{y^2}{1^2} = 1$ | $+x^2, -y^2$ (opposite signs) | Rectangular Hyperbola ($a = b = 1$) |
| $x^2 - 4y = 0$ | $x^2 = 4y$ | $x^2$ quadratic, $y$ linear | Parabola opening upward |
| $x^2 + y^2 + 1 = 0$ | $x^2 + y^2 = -1$ | $+x^2, +y^2$, RHS $= -1 < 0$ | Empty set $\emptyset$ (no real points) |

---

## Why This Exercise Matters

- **Checking the Sign of the Constant Term:** Having $+x^2$ and $+y^2$ with equal or positive coefficients is **not** enough to guarantee a circle or an ellipse! After completing the square into $A(x - x_0)^2 + B(y - y_0)^2 = K$ (with $A, B > 0$), three distinct cases occur depending on the sign of $K$:
  - $K > 0$: real ellipse (or circle if $A = B$),
  - $K = 0$: a single point $(x_0, y_0)$,
  - $K < 0$: the empty set $\emptyset$ (no real points).
