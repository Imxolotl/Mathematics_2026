# Problem 11: Two Similar Surfaces

## Question

Compare

$$
x^2+y^2-z^2=1
$$

and

$$
x^2+y^2-z^2=-1.
$$

For several values $z=c$, check whether the cross-section exists and what its radius is. Based on this, describe qualitatively the difference between the surfaces and make sketches.

---

## Solution

### 1. Surface 1: $x^2 + y^2 - z^2 = 1$ (Hyperboloid of One Sheet)

#### Horizontal Cross-Sections $z = c$

Substituting $z = c$ into $x^2 + y^2 - z^2 = 1$ and isolating $x^2 + y^2$:

$$
x^2 + y^2 = 1 + c^2
$$

Because $c^2 \ge 0$ for every real number $c \in \mathbb{R}$, the right-hand side is always at least $1$:

$$
1 + c^2 \ge 1 > 0
$$

- **Existence:** A real cross-section exists at every height $c \in \mathbb{R}$.
- **Shape and Radius:** Every horizontal cross-section $z = c$ is a circle centered on the $z$-axis at $(0, 0, c)$ with radius:

$$
r_1(c) = \sqrt{1 + c^2}
$$

#### Testing Specific Values of $z = c$

- For $c = 0$: $x^2 + y^2 = 1 + 0 = 1$, a circle of minimum radius $r_1(0) = 1$ (the narrowest waist of the surface in the $xy$-plane).
- For $c = \pm 1$: $x^2 + y^2 = 1 + 1 = 2$, circles of radius $r_1(\pm 1) = \sqrt{2} \approx 1.414$.
- For $c = \pm 2$: $x^2 + y^2 = 1 + 4 = 5$, circles of radius $r_1(\pm 2) = \sqrt{5} \approx 2.236$.
- For $c = \pm 3$: $x^2 + y^2 = 1 + 9 = 10$, circles of radius $r_1(\pm 3) = \sqrt{10} \approx 3.162$.

Vertical cross-sections: Setting $x = 0$ gives $y^2 - z^2 = 1$, and setting $y = 0$ gives $x^2 - z^2 = 1$, which are hyperbolas opening left and right with vertices at distance $1$ from the $z$-axis.

#### Sketch of $x^2 + y^2 - z^2 = 1$ (One Connected Sheet — Cooling Tower)

```text
               z
               ^
      . - - - -|- - - - .      <- Circle of radius sqrt(1+c^2) at z = c
    (   ' - - -+- - - '   )
     \         |         /
      \        |        /
       )   . - * - .   (       <- Narrowest waist circle (radius r = 1 at z = 0)
      /  (    /|\    )  \------------> y
     /     ' - | - '     \
    (   . - - -+- - - .   )
      ' - - - -|- - - - '      <- Circle of radius sqrt(1+c^2) at z = -c
              /
             v
            x
```

---

### 2. Surface 2: $x^2 + y^2 - z^2 = -1$ (Hyperboloid of Two Sheets)

#### Horizontal Cross-Sections $z = c$

Substituting $z = c$ into $x^2 + y^2 - z^2 = -1$ and isolating $x^2 + y^2$:

$$
x^2 + y^2 = c^2 - 1
$$

Because $x^2 + y^2 \ge 0$ for all real $(x, y)$, a real cross-section exists if and only if:

$$
c^2 - 1 \ge 0
$$

which holds when $c^2 \ge 1$ ($c \le -1$ or $c \ge 1$).

- **For $-1 < c < 1$:** $c^2 - 1 < 0$, so $x^2 + y^2 = c^2 - 1$ has no real solutions (the cross-section is empty).
- **For $c = 1$ and $c = -1$:** $x^2 + y^2 = 0$, which gives $(x, y) = (0, 0)$, so the cross-sections degenerate to single points $(0, 0, 1)$ and $(0, 0, -1)$ with radius $r_2(\pm 1) = 0$.
- **For $c^2 > 1$:** The cross-section is a circle centered at $(0, 0, c)$ with radius:

$$
r_2(c) = \sqrt{c^2 - 1}
$$

#### Testing Specific Values of $z = c$

- For $c = 0$: $x^2 + y^2 = 0 - 1 = -1 < 0$, so the cross-section does not exist.
- For $c = \pm \frac{1}{2}$: $x^2 + y^2 = \frac{1}{4} - 1 = -\frac{3}{4} < 0$, so the cross-section does not exist.
- For $c = \pm 1$: $x^2 + y^2 = 1 - 1 = 0$, a single point $(0, 0, \pm 1)$ of radius $r_2(\pm 1) = 0$.
- For $c = \pm 2$: $x^2 + y^2 = 4 - 1 = 3$, a circle of radius $r_2(\pm 2) = \sqrt{3} \approx 1.732$.
- For $c = \pm 3$: $x^2 + y^2 = 9 - 1 = 8$, a circle of radius $r_2(\pm 3) = \sqrt{8} = 2\sqrt{2} \approx 2.828$.

Vertical cross-sections: Setting $x = 0$ gives $z^2 - y^2 = 1$, and setting $y = 0$ gives $z^2 - x^2 = 1$, which are hyperbolas opening upward for $z \ge 1$ and downward for $z \le -1$.

#### Sketch of $x^2 + y^2 - z^2 = -1$ (Two Separate Sheets)

```text
               z
               ^
      . - - - -|- - - - .      <- Upper bowl (z >= 1): circle radius sqrt(c^2-1)
     \  ' - - -+- - - '  /
      ' .      |      . '
          ' - -*- - '          <- Upper vertex (0,0,1) at z = 1
               |
               |               <- Empty gap (-1 < z < 1): no points!
               +-------------> y
              /| (0,0,0)
          . - -*- - .          <- Lower vertex (0,0,-1) at z = -1
      . '      |      ' .
     /  . - - -+- - - .  \
      ' - - - -|- - - - '      <- Lower bowl (z <= -1): circle radius sqrt(c^2-1)
              v
             x
```

---

### 3. Qualitative Comparison of the Two Surfaces

| Property | $x^2 + y^2 - z^2 = 1$ (One Sheet) | $x^2 + y^2 - z^2 = -1$ (Two Sheets) |
| :--- | :--- | :--- |
| **Horizontal slice equation** | $x^2 + y^2 = c^2 + 1$ | $x^2 + y^2 = c^2 - 1$ |
| **Heights where slice exists** | All real $c$ | Only $c^2 \ge 1$ ($c \le -1$ or $c \ge 1$) |
| **Radius of circle** | $r_1(c) = \sqrt{c^2 + 1} \ge 1$ | $r_2(c) = \sqrt{c^2 - 1} \ge 0$ (for $c^2 \ge 1$) |
| **Slice in the $xy$-plane** | Waist circle of radius $1$ | Empty (gap between sheets) |
| **Intersection with $z$-axis** | None ($-z^2 = 1$ impossible) | Two vertices $(0, 0, 1)$ and $(0, 0, -1)$ |
| **Connectedness** | **1 connected piece** (hourglass tube) | **2 disconnected pieces** (two separate bowls) |

- **Asymptotic Cone Sharing:** For very large $|c|$, the $+1$ and $-1$ constants become negligible compared to $c^2$, so both radii approach $\sqrt{c^2} = |c|$. Both hyperboloids approach the exact same asymptotic cone $x^2 + y^2 - z^2 = 0$ from opposite sides.

---

## Why This Exercise Matters

- **Deducing Topology from Elementary Algebra:** You never need to memorize which sign gives one sheet and which gives two sheets: simply set $z = 0$. In $x^2 + y^2 - z^2 = 1$, $z = 0$ gives the circle $x^2 + y^2 = 1$, so the surface connects continuously across the $xy$-plane (one sheet). In $x^2 + y^2 - z^2 = -1$, $z = 0$ gives $x^2 + y^2 = -1$ (impossible), proving the $xy$-plane separates the surface into two disconnected sheets.
