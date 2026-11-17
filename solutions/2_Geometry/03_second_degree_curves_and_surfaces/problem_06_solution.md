# Problem 6: Shifted Ellipse

## Question

Reduce

$$
4x^2+9y^2-16x+18y-11=0
$$

to canonical form. Give the center and semiaxis lengths. Check that substituting the coordinates of the center into the left-hand side gives a value consistent with the form you obtained.

---

## Solution

### 1. Reducing the Equation to Canonical Form by Completing the Square

We start from the given equation:

$$
4x^2 + 9y^2 - 16x + 18y - 11 = 0
$$

#### Step 1: Group the $x$-terms and $y$-terms and move the constant to the right-hand side

$$
(4x^2 - 16x) + (9y^2 + 18y) = 11
$$

#### Step 2: Factor out the quadratic coefficients $4$ and $9$ from each group

Before completing the square, the coefficient of $x^2$ and $y^2$ inside each parenthesis must be $1$:

$$
4(x^2 - 4x) + 9(y^2 + 2y) = 11
$$

#### Step 3: Complete the square inside each parenthesis

- **For the $x$-group $x^2 - 4x$:**
  Half of $-4$ is $-2$, and $(-2)^2 = 4$, so $x^2 - 4x + 4 = (x - 2)^2$.
  Because this group is multiplied by $4$, adding $4$ inside the parenthesis adds $4 \cdot 4 = 16$ to the left-hand side.

- **For the $y$-group $y^2 + 2y$:**
  Half of $2$ is $1$, and $1^2 = 1$, so $y^2 + 2y + 1 = (y + 1)^2$.
  Because this group is multiplied by $9$, adding $1$ inside the parenthesis adds $9 \cdot 1 = 9$ to the left-hand side.

Adding $16$ and $9$ to both sides of the equation:

$$
4(x^2 - 4x + 4) + 9(y^2 + 2y + 1) = 11 + 16 + 9
$$

$$
4(x - 2)^2 + 9(y + 1)^2 = 36
$$

#### Step 4: Divide both sides by $36$ to make the right-hand side equal to $1$

$$
\frac{4(x - 2)^2}{36} + \frac{9(y + 1)^2}{36} = \frac{36}{36}
$$

Simplifying the fractions $\frac{4}{36} = \frac{1}{9}$ and $\frac{9}{36} = \frac{1}{4}$ gives the **canonical form** of the shifted ellipse:

$$
\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1
$$

or equivalently:

$$
\frac{(x - 2)^2}{3^2} + \frac{(y - (-1))^2}{2^2} = 1
$$

---

### 2. Center and Semiaxis Lengths

Comparing $\frac{(x - 2)^2}{3^2} + \frac{(y - (-1))^2}{2^2} = 1$ with the standard shifted ellipse equation $\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$:

- **Center of the ellipse:**

$$
C = (x_0, y_0) = (2, -1)
$$

- **Horizontal semiaxis length (major semiaxis, parallel to the $x$-axis):**

$$
a = \sqrt{9} = 3
$$

- **Vertical semiaxis length (minor semiaxis, parallel to the $y$-axis):**

$$
b = \sqrt{4} = 2
$$

---

### 3. Consistency Check Using the Coordinates of the Center

Let $F(x, y)$ denote the left-hand side of the original equation:

$$
F(x, y) = 4x^2 + 9y^2 - 16x + 18y - 11
$$

From our completed-square derivation ($4(x - 2)^2 + 9(y + 1)^2 = 36$), we rewrote the polynomial $F(x, y)$ as the algebraic identity:

$$
F(x, y) = 4(x - 2)^2 + 9(y + 1)^2 - 36
$$

#### 1. Value predicted by the completed-square form at the center $C = (2, -1)$:

When we substitute the center $(x, y) = (2, -1)$ into the completed-square form, both squared terms vanish:

$$
4(2 - 2)^2 + 9(-1 + 1)^2 - 36 = 4(0) + 9(0) - 36 = -36
$$

(Equivalently, in the normalized form $\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1$, the left-hand side evaluates to $0 + 0 = 0$ at the center, which is $1$ less than the right-hand side, corresponding to $-36$ before dividing by $36$.)

#### 2. Direct evaluation of the original left-hand side $F(x, y)$ at $C = (2, -1)$:

Substituting $x = 2$ and $y = -1$ directly into $4x^2 + 9y^2 - 16x + 18y - 11$:

$$
\begin{aligned}
F(2, -1) &= 4(2)^2 + 9(-1)^2 - 16(2) + 18(-1) - 11 \\
         &= 4(4) + 9(1) - 32 - 18 - 11 \\
         &= 16 + 9 - 32 - 18 - 11 \\
         &= 25 - 61 \\
         &= -36
\end{aligned}
$$

Both expressions yield the exact same value $-36$, confirming that the completed square and the constant $36$ are algebraically consistent.

*(Note: Notice also that $F(2, -1) = -36 < 0$, which geometrically reflects the fact that the center $C = (2, -1)$ lies **strictly inside** the ellipse $F(x, y) = 0$, not on its boundary curve.)*

---

## Verification and Consistency Checks

### Checking the Four Vertices of the Shifted Ellipse

From center $C = (2, -1)$ with $a = 3$ and $b = 2$:
- Horizontal vertices: $(2 \pm 3, -1) \implies V_1 = (-1, -1)$ and $V_2 = (5, -1)$.
- Vertical co-vertices: $(2, -1 \pm 2) \implies B_1 = (2, -3)$ and $B_2 = (2, 1)$.

Testing $V_2 = (5, -1)$ and $B_2 = (2, 1)$ in the original equation $4x^2 + 9y^2 - 16x + 18y - 11 = 0$:

- **At $V_2 = (5, -1)$:**

$$
4(5)^2 + 9(-1)^2 - 16(5) + 18(-1) - 11 = 100 + 9 - 80 - 18 - 11 = 109 - 109 = 0
$$

- **At $B_2 = (2, 1)$:**

$$
4(2)^2 + 9(1)^2 - 16(2) + 18(1) - 11 = 16 + 9 - 32 + 18 - 11 = 43 - 43 = 0
$$

Both vertices satisfy the original equation.

---

## Why This Exercise Matters

- **Factoring Before Completing the Square:** When the coefficients of $x^2$ and $y^2$ are not $1$ (here $4$ and $9$), you must factor out $4$ and $9$ first and remember to multiply the added constants by $4$ and $9$ ($4 \cdot 4 = 16$ and $9 \cdot 1 = 9$) when balancing the right-hand side.
- **Coordinate Shift Interpretation:** Defining shifted coordinates $\tilde{x} = x - 2$ and $\tilde{y} = y + 1$ places the new origin $(\tilde{x}, \tilde{y}) = (0, 0)$ at the center $(2, -1)$, turning the equation into the unshifted ellipse $\frac{\tilde{x}^2}{9} + \frac{\tilde{y}^2}{4} = 1$.
