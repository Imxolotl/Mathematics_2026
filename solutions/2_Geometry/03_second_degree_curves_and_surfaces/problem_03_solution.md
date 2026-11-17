# Problem 3: Ellipse

## Question

For

$$
\frac{x^2}{25}+\frac{y^2}{9}=1,
$$

find the semiaxis lengths, the intercepts with the coordinate axes, and make a sketch. Explain along which axis the ellipse is more stretched and how this is visible in the equation.

---

## Solution

### 1. Semiaxis Lengths

The canonical equation of an ellipse centered at the origin $(0, 0)$ is:

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
$$

Writing the given denominators as squares:

$$
\frac{x^2}{5^2} + \frac{y^2}{3^2} = 1
$$

We read off the semiaxis lengths directly:
- **Horizontal semiaxis length (along the $x$-axis):**

$$
a = \sqrt{25} = 5
$$

  (The full major axis has length $2a = 10$.)
- **Vertical semiaxis length (along the $y$-axis):**

$$
b = \sqrt{9} = 3
$$

  (The full minor axis has length $2b = 6$.)

---

### 2. Intercepts with the Coordinate Axes (Vertices)

#### 1. Intercepts with the $x$-axis (set $y = 0$):

$$
\frac{x^2}{25} + \frac{0^2}{9} = 1 \implies \frac{x^2}{25} = 1 \implies x^2 = 25 \implies x = \pm 5
$$

The $x$-intercepts (major vertices) are:

$$
V_1 = (-5, 0), \qquad V_2 = (5, 0)
$$

#### 2. Intercepts with the $y$-axis (set $x = 0$):

$$
\frac{0^2}{25} + \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = 1 \implies y^2 = 9 \implies y = \pm 3
$$

The $y$-intercepts (minor co-vertices) are:

$$
B_1 = (0, -3), \qquad B_2 = (0, 3)
$$

---

### 3. Sketch of the Ellipse

```text
                y
                ^
                |    (0,3)
          . - - * - - .
      . '       |       ' .
    /           |           \
(-5,0)*---------+---------* (5,0) ---> x
    \         (0,0)         /
      ' .       |       . '
          ' - - * - - '
                |   (0,-3)
```

- **Bounding Box:** The ellipse is inscribed inside the rectangle $[-5, 5] \times [-3, 3]$, touching the midpoints of its four sides at $(\pm 5, 0)$ and $(0, \pm 3)$.

---

### 4. Explanation: Along Which Axis the Ellipse Is More Stretched

The ellipse is **more stretched horizontally along the $x$-axis** (its horizontal width is $2a = 10$, whereas its vertical height is $2b = 6$).

This is immediately visible in the equation $\frac{x^2}{25} + \frac{y^2}{9} = 1$ in three ways:

1. **Larger Denominator Under $x^2$:**
   Comparing the denominators, $25 > 9$ (so $a = 5 > 3 = b$). In canonical form $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$, the variable with the **larger denominator** always corresponds to the **longer axis** (the major axis).

2. **Upper Bound on Each Variable:**
   Because squares of real numbers are non-negative ($\frac{x^2}{25} \ge 0$ and $\frac{y^2}{9} \ge 0$) and their sum equals $1$, neither term can exceed $1$:

$$
\frac{x^2}{25} \le 1 \implies x^2 \le 25 \implies -5 \le x \le 5
$$

$$
\frac{y^2}{9} \le 1 \implies y^2 \le 9 \implies -3 \le y \le 3
$$

   Because $x^2$ is divided by a larger number ($25$), $|x|$ must grow to $5$ before $\frac{x^2}{25}$ reaches $1$, whereas $|y|$ only grows to $3$ before $\frac{y^2}{9}$ reaches $1$.

3. **Stretching the Unit Circle:**
   If we define normalized coordinates $u = \frac{x}{5}$ and $v = \frac{y}{3}$, the equation becomes the unit circle $u^2 + v^2 = 1$. Since $x = 5u$ and $y = 3v$, the ellipse is obtained by stretching the unit circle by a factor of $5$ along the $x$-axis and by a factor of $3$ along the $y$-axis.

---

## Verification and Consistency Checks

### Foci and Focal Property Check

For an ellipse elongated along the $x$-axis ($a = 5 > b = 3$), the focal distance $c$ from the center to each focus on the $x$-axis satisfies:

$$
c = \sqrt{a^2 - b^2} = \sqrt{25 - 9} = \sqrt{16} = 4
$$

Thus, the foci lie on the $x$-axis at $F_1 = (-4, 0)$ and $F_2 = (4, 0)$.
- For the top vertex $B_2 = (0, 3)$, the sum of distances to the two foci is:

$$
d(B_2, F_1) + d(B_2, F_2) = \sqrt{(-4 - 0)^2 + (0 - 3)^2} + \sqrt{(4 - 0)^2 + (0 - 3)^2} = 5 + 5 = 10 = 2a
$$

- For the right vertex $V_2 = (5, 0)$, the sum of distances to the two foci is:

$$
d(V_2, F_1) + d(V_2, F_2) = (5 - (-4)) + (5 - 4) = 9 + 1 = 10 = 2a
$$

Both vertices satisfy the geometric definition of an ellipse ($d(P, F_1) + d(P, F_2) = 2a = 10$).

---

## Why This Exercise Matters

- **Avoiding the Common Denominator Trap:** A frequent beginner mistake is to think that dividing $x^2$ by $25$ makes the $x$-direction smaller. Rewriting the equation as $\left(\frac{x}{5}\right)^2 + \left(\frac{y}{3}\right)^2 = 1$ makes it crystal clear that $5$ and $3$ are the scale units along the $x$- and $y$-axes.
