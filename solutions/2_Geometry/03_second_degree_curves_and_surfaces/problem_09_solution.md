# Problem 9: Ellipsoid and Its Cross-Sections

## Question

Consider

$$
\frac{x^2}{9}+\frac{y^2}{4}+\frac{z^2}{16}=1.
$$

Give the semiaxis lengths, describe the cross-section $z=0$, and explain how the cross-sections $z=c$ change for $|c|<4$.

---

## Solution

### 1. Semiaxis Lengths of the Ellipsoid

The canonical equation of an ellipsoid centered at the origin $(0, 0, 0)$ is:

$$
\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c_0^2} = 1
$$

Writing the denominators of the given equation as squares:

$$
\frac{x^2}{3^2} + \frac{y^2}{2^2} + \frac{z^2}{4^2} = 1
$$

We read off the three semiaxis lengths along the coordinate axes:
- **Semiaxis along the $x$-axis ($Ox$):**

$$
a = \sqrt{9} = 3 \qquad (\mathrm{vertices\ at\ } (\pm 3, 0, 0))
$$

- **Semiaxis along the $y$-axis ($Oy$):**

$$
b = \sqrt{4} = 2 \qquad (\mathrm{vertices\ at\ } (0, \pm 2, 0))
$$

- **Semiaxis along the $z$-axis ($Oz$):**

$$
c_0 = \sqrt{16} = 4 \qquad (\mathrm{vertices\ at\ } (0, 0, \pm 4))
$$

Because $c_0 = 4$ is the largest semiaxis, the ellipsoid is most elongated vertically along the $z$-axis.

---

### 2. Description of the Cross-Section $z = 0$

Setting $z = 0$ in the ellipsoid equation gives its intersection with the horizontal $xy$-coordinate plane:

$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{0^2}{16} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1, \qquad z = 0
$$

- **Geometric Description:** The cross-section $z = 0$ is an **ellipse** in the $xy$-plane centered at the origin $(0, 0, 0)$, with:
  - Horizontal semiaxis $a = 3$ along the $x$-axis (passing through $(\pm 3, 0, 0)$),
  - Semiaxis $b = 2$ along the $y$-axis (passing through $(0, \pm 2, 0)$).

---

### 3. Behavior of the Horizontal Cross-Sections $z = c$ for $|c| < 4$

To find the intersection of the ellipsoid with a horizontal plane $z = c$, we substitute $z = c$ into the surface equation and move the constant term to the right-hand side:

$$
\frac{x^2}{9} + \frac{y^2}{4} + \frac{c^2}{16} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{c^2}{16}
$$

For $|c| < 4$, we have $c^2 < 16$, so the right-hand side is strictly positive:

$$
1 - \frac{c^2}{16} > 0
$$

Dividing both sides by $1 - \frac{c^2}{16}$ puts the equation of the cross-section in the plane $z = c$ into canonical ellipse form:

$$
\frac{x^2}{9\left(1 - \frac{c^2}{16}\right)} + \frac{y^2}{4\left(1 - \frac{c^2}{16}\right)} = 1, \qquad z = c
$$

#### How the Cross-Sections Change as $c$ Varies in $(-4, 4)$:

1. **Every Cross-Section for $|c| < 4$ Is an Ellipse:**
   In the horizontal plane $z = c$, the cross-section is an ellipse centered on the $z$-axis at $(0, 0, c)$ with semiaxes:

$$
a(c) = 3\sqrt{1 - \frac{c^2}{16}}, \qquad b(c) = 2\sqrt{1 - \frac{c^2}{16}}
$$

2. **All Cross-Sections Have the Same Shape (Similar Ellipses):**
   Every cross-section $z = c$ is a scaled copy of the equatorial ellipse $z = 0$ multiplied by the scaling factor $k(c) = \sqrt{1 - \frac{c^2}{16}} \in (0, 1]$. The ratio of the semiaxes remains constant at every height:

$$
\frac{a(c)}{b(c)} = \frac{3}{2}
$$

3. **Maximum Size at $c = 0$ and Symmetric Shrinking as $|c| \to 4$:**
   - **At $c = 0$ (equator):** The scaling factor is maximal ($k(0) = 1$), producing the **largest** ellipse with semiaxes $a(0) = 3$ and $b(0) = 2$.
   - **As $|c|$ increases from $0$ toward $4$:** Whether moving upward ($c \to +4$) or symmetrically downward ($c \to -4$), the term $\frac{c^2}{16}$ increases toward $1$, so the scaling factor $\sqrt{1 - \frac{c^2}{16}}$ decreases continuously toward $0$. Thus, the elliptical cross-sections **shrink monotonically** as we move away from the $xy$-plane.
   - **Boundary and Exterior Behavior ($|c| \ge 4$):** At the poles $c = 4$ and $c = -4$, we get $\frac{x^2}{9} + \frac{y^2}{4} = 0$, so the ellipse shrinks to a **single point** $(0, 0, \pm 4)$. For $|c| > 4$, $1 - \frac{c^2}{16} < 0$, so there are **no real intersection points** (the plane misses the ellipsoid).

---

## Verification and Consistency Checks

### Sample Cross-Section Evaluation at $c = \pm 2$

At height $z = c = \pm 2$ (halfway to the poles):

$$
1 - \frac{c^2}{16} = 1 - \frac{4}{16} = \frac{3}{4}
$$

The cross-section is the ellipse:

$$
\frac{x^2}{9(3/4)} + \frac{y^2}{4(3/4)} = 1 \iff \frac{x^2}{(3\sqrt{3}/2)^2} + \frac{y^2}{(\sqrt{3})^2} = 1
$$

Its semiaxes are $a(\pm 2) = \frac{3\sqrt{3}}{2} \approx 2.60 < 3$ and $b(\pm 2) = \sqrt{3} \approx 1.73 < 2$, confirming that the ellipse has shrunk while keeping the ratio $\frac{a(\pm 2)}{b(\pm 2)} = \frac{3}{2}$.

---

## Why This Exercise Matters

- **Understanding 3D Surfaces via 2D Slices (Method of Cross-Sections):** Just as a medical CT scan reconstructs a 3D organ from a stack of 2D horizontal slices $z = c$, fixing one variable to a constant $c$ reduces a three-variable surface equation to a familiar two-variable curve.
