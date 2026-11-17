# Problem 2: Circle by Completing the Square

## Question

Reduce

$$
x^2+y^2-6x+4y-3=0
$$

to canonical form. Find the center and radius, then substitute two simple points from the circle into both forms of the equation.

---

## Solution

### 1. Grouping Variables and Completing the Square

We start from the general equation:

$$
x^2 + y^2 - 6x + 4y - 3 = 0
$$

#### Step 1: Group the $x$-terms and $y$-terms and move the constant term to the right-hand side

$$
(x^2 - 6x) + (y^2 + 4y) = 3
$$

#### Step 2: Complete the square for the $x$-terms

For $x^2 - 6x$, half of the linear coefficient $-6$ is $-3$, and its square is $(-3)^2 = 9$:

$$
x^2 - 6x + 9 = (x - 3)^2
$$

#### Step 3: Complete the square for the $y$-terms

For $y^2 + 4y$, half of the linear coefficient $4$ is $2$, and its square is $2^2 = 4$:

$$
y^2 + 4y + 4 = (y + 2)^2
$$

#### Step 4: Add $9$ and $4$ to both sides of the equation

To preserve equality, we add $9 + 4 = 13$ to both the left-hand and right-hand sides:

$$
(x^2 - 6x + 9) + (y^2 + 4y + 4) = 3 + 9 + 4
$$

Factoring the perfect squares on the left and summing on the right gives the **canonical form** of the circle:

$$
(x - 3)^2 + (y + 2)^2 = 16
$$

or equivalently:

$$
(x - 3)^2 + (y - (-2))^2 = 4^2
$$

---

### 2. Finding the Center and Radius

Comparing $(x - 3)^2 + (y - (-2))^2 = 4^2$ with the standard circle equation $(x - x_0)^2 + (y - y_0)^2 = r^2$:

- **Center of the circle:**

$$
C = (x_0, y_0) = (3, -2)
$$

- **Radius of the circle:**

$$
r = \sqrt{16} = 4
$$

---

### 3. Finding Two Simple Points on the Circle and Checking Both Equations

Starting at the center $C = (3, -2)$ and moving a distance $r = 4$ along the horizontal and vertical coordinate directions gives four simple cardinal points on the circle:
- Moving $4$ units right: $P_1 = (3 + 4, \; -2) = (7, -2)$
- Moving $4$ units up: $P_2 = (3, \; -2 + 4) = (3, 2)$
- (Also $4$ units left: $(-1, -2)$, and $4$ units down: $(3, -6)$.)

Let us substitute $P_1 = (7, -2)$ and $P_2 = (3, 2)$ into **both** the canonical form and the original general form.

#### Check for Point 1: $P_1 = (7, -2)$

1. **In the canonical form $(x - 3)^2 + (y + 2)^2 = 16$:**

$$
\begin{aligned}
(7 - 3)^2 + (-2 + 2)^2 &= 4^2 + 0^2 \\
                       &= 16 + 0 \\
                       &= 16
\end{aligned}
$$

2. **In the original general form $x^2 + y^2 - 6x + 4y - 3 = 0$:**

$$
\begin{aligned}
7^2 + (-2)^2 - 6(7) + 4(-2) - 3 &= 49 + 4 - 42 - 8 - 3 \\
                                &= 53 - 53 \\
                                &= 0
\end{aligned}
$$

Both equations are satisfied by $P_1 = (7, -2)$.

#### Check for Point 2: $P_2 = (3, 2)$

1. **In the canonical form $(x - 3)^2 + (y + 2)^2 = 16$:**

$$
\begin{aligned}
(3 - 3)^2 + (2 + 2)^2 &= 0^2 + 4^2 \\
                      &= 0 + 16 \\
                      &= 16
\end{aligned}
$$

2. **In the original general form $x^2 + y^2 - 6x + 4y - 3 = 0$:**

$$
\begin{aligned}
3^2 + 2^2 - 6(3) + 4(2) - 3 &= 9 + 4 - 18 + 8 - 3 \\
                            &= 21 - 21 \\
                            &= 0
\end{aligned}
$$

Both equations are satisfied by $P_2 = (3, 2)$.

---

## Verification and Consistency Checks

### Direct Algebraic Expansion of the Canonical Form

Expanding $(x - 3)^2 + (y + 2)^2 = 16$ back out:

$$
\begin{aligned}
(x^2 - 6x + 9) + (y^2 + 4y + 4) &= 16 \\
x^2 + y^2 - 6x + 4y + 13 - 16 &= 0 \\
x^2 + y^2 - 6x + 4y - 3 &= 0
\end{aligned}
$$

This recovers the original equation identically, confirming no arithmetic mistakes were made while completing the square.

---

## Why This Exercise Matters

- **Algebraic Translation to Geometric Center:** Linear terms $-6x$ and $+4y$ in a quadratic equation indicate that the center of symmetry has been shifted away from the origin. Completing the square absorbs these linear terms into shifted coordinates $(x - 3)$ and $(y + 2)$, revealing the center $(3, -2)$ and radius $r = 4$ directly.
- **Two-Point Verification:** Testing two distinct points from the canonical circle in the original equation verifies both the center coordinates and the radius simultaneously.
