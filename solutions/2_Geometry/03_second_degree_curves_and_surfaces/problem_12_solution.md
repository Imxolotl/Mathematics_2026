# Problem 12: Recognizing a Surface from Cross-Sections

## Question

A certain surface has the following properties:
- the cross-section $z=0$ is a point,
- for $z>0$, the cross-sections $z=\mathrm{const}$ are circles with increasing radius,
- vertical cross-sections through the $Oz$ axis are parabolas.

Propose a simple equation for such a surface and justify your choice.

---

## Solution

### 1. Proposed Equation

The simplest equation describing a surface with all three properties is the circular paraboloid:

$$
z = x^2 + y^2
$$

More generally, any equation of the form $z = a(x^2 + y^2)$ with a positive constant $a > 0$ satisfies all three conditions; choosing $a = 1$ gives the simplest canonical form.

---

### 2. Step-by-Step Justification of the Choice

We show how each geometric requirement dictates a specific part of the algebraic equation $z = x^2 + y^2$, and verify that all three properties hold.

#### 1. Why $x$ and $y$ Must Appear as $x^2 + y^2$ (Circular Horizontal Cross-Sections)

For a horizontal plane $z = c$ to intersect the surface in a circle centered on the $Oz$ axis, the equation at fixed $z = c$ must take the form:

$$
x^2 + y^2 = r(c)^2
$$

This requires $x$ and $y$ to appear symmetrically as the sum of squares $x^2 + y^2$ with equal positive coefficients.

#### 2. Why $z$ Must Be Linear rather than Quadratic (Parabolic Vertical Cross-Sections)

Compare two candidate rotationally symmetric surfaces that have a single point at $z = 0$ and expanding circular cross-sections for $z > 0$:
- **Candidate A (Upper Cone):** $x^2 + y^2 = z^2$ (with $z \ge 0$). In the vertical plane $y = 0$, this gives $x^2 = z^2$, so $z = |x|$, which consists of two straight half-lines meeting at a sharp corner, not a smooth parabola.
- **Candidate B (Circular Paraboloid):** $z = x^2 + y^2$. Because $z$ appears to the first power while $x$ and $y$ appear to the second power, slicing by any vertical plane through the $Oz$ axis keeps $z$ linear and the horizontal coordinate quadratic, producing a parabola.

---

### 3. Verification of Each Given Property for $z = x^2 + y^2$

#### Check of Property 1: The cross-section $z = 0$ is a point

Substituting $z = 0$ into $z = x^2 + y^2$:

$$
x^2 + y^2 = 0
$$

Since $x^2 \ge 0$ and $y^2 \ge 0$ for all real numbers $x, y \in \mathbb{R}$, their sum equals $0$ if and only if both $x = 0$ and $y = 0$. Therefore, the cross-section in the plane $z = 0$ is the single point:

$$
(0, 0, 0)
$$

#### Check of Property 2: For $z > 0$, the cross-sections $z = \mathrm{const}$ are circles with increasing radius

Substituting $z = c$ with $c > 0$ into $z = x^2 + y^2$:

$$
x^2 + y^2 = c = (\sqrt{c})^2, \qquad z = c
$$

For each $c > 0$, this is the equation of a circle in the horizontal plane $z = c$, centered at $(0, 0, c)$ on the $Oz$ axis, with radius:

$$
r(c) = \sqrt{c}
$$

Because the square root function $r(c) = \sqrt{c}$ is strictly increasing for $c > 0$, the radius of the circular cross-section increases as $z = c$ increases.

#### Check of Property 3: Vertical cross-sections through the $Oz$ axis are parabolas

First, in the coordinate planes through the $Oz$ axis ($y = 0$ and $x = 0$):

$$
z = x^2 \qquad (y = 0)
$$

$$
z = y^2 \qquad (x = 0)
$$

Both curves are standard upward-opening parabolas with vertex at $(0, 0, 0)$.

Second, in any arbitrary vertical plane containing the $Oz$ axis, we can parameterize the horizontal direction by a fixed angle $\alpha$ and a signed radial coordinate $u \in \mathbb{R}$:

$$
x = u \cos\alpha, \qquad y = u \sin\alpha
$$

Substituting these into $z = x^2 + y^2$:

$$
\begin{aligned}
z &= (u \cos\alpha)^2 + (u \sin\alpha)^2 \\
  &= u^2 (\cos^2\alpha + \sin^2\alpha) \\
  &= u^2
\end{aligned}
$$

Thus, in every vertical plane through the $Oz$ axis, the cross-section is a congruent parabola $z = u^2$ with vertex at the origin.

---

## Why This Exercise Matters

- **Synthesizing Equations from Geometric Specs:** Instead of starting with an equation and slicing it, this exercise practices the inverse problem: translating horizontal slice geometry ($x^2 + y^2$) and vertical slice geometry ($z = u^2$) into the surface equation $z = x^2 + y^2$.
- **Distinguishing Paraboloids from Cones:** Both $z = x^2 + y^2$ and the upper cone $z = \sqrt{x^2 + y^2}$ have a point at $z = 0$ and expanding circles for $z > 0$; it is the vertical cross-section (parabola $z = u^2$ vs. V-shaped lines $z = |u|$) that distinguishes a smooth paraboloid from a sharp cone.
