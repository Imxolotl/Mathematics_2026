# Problem 10: Continuity of a Piecewise Function

## Question

Find $a$ so that

$$
f(x)=
\begin{cases}
ax+1, & x<2, \\
x^2-1, & x\ge2
\end{cases}
$$

is continuous at $x=2$. Explicitly compare the left-hand limit, right-hand limit, and function value.

---

## Solution

### 1. Definition of Continuity at a Point

A function $f$ defined on an open interval containing $x_0 = 2$ is **continuous at $x = 2$** if and only if the following three conditions hold simultaneously:
1. The function value $f(2)$ is defined.
2. Both the left-hand limit $\lim_{x\to2^-} f(x)$ and the right-hand limit $\lim_{x\to2^+} f(x)$ exist and are finite.
3. All three quantities are equal:

$$
\lim_{x\to2^-} f(x) = \lim_{x\to2^+} f(x) = f(2)
$$

---

### 2. Computing the Three Quantities at $x = 2$

#### 1. Function Value at $x = 2$

At $x = 2$, the condition $x \ge 2$ applies, so we use the second branch $f(x) = x^2 - 1$:

$$
f(2) = 2^2 - 1 = 4 - 1 = 3
$$

#### 2. Right-Hand Limit ($\lim_{x\to2^+} f(x)$)

When $x$ approaches $2$ from the right ($x > 2$), we have $x \ge 2$, so $f(x)$ is given by the polynomial formula $x^2 - 1$:

$$
\begin{aligned}
\lim_{x\to2^+} f(x) &= \lim_{x\to2^+} (x^2 - 1) \\
&= 2^2 - 1 \\
&= 3
\end{aligned}
$$

Notice that the right-hand limit automatically agrees with the function value ($\lim_{x\to2^+} f(x) = f(2) = 3$) because the second branch applies for all $x \ge 2$ and $x^2 - 1$ is continuous.

#### 3. Left-Hand Limit ($\lim_{x\to2^-} f(x)$)

When $x$ approaches $2$ from the left ($x < 2$), $f(x)$ is given by the first branch $ax + 1$:

$$
\begin{aligned}
\lim_{x\to2^-} f(x) &= \lim_{x\to2^-} (ax + 1) \\
&= a(2) + 1 \\
&= 2a + 1
\end{aligned}
$$

---

### 3. Explicit Comparison and Solving for $a$

Collecting the three quantities for side-by-side comparison:
- **Left-hand limit:** $\lim_{x\to2^-} f(x) = 2a + 1$
- **Right-hand limit:** $\lim_{x\to2^+} f(x) = 3$
- **Function value:** $f(2) = 3$

For $f$ to be continuous at $x = 2$, the left-hand limit must equal the common value of the right-hand limit and the function value:

$$
\lim_{x\to2^-} f(x) = \lim_{x\to2^+} f(x) = f(2)
$$

Substituting the expressions computed above gives the linear equation:

$$
2a + 1 = 3
$$

Subtracting $1$ from both sides and dividing by $2$:

$$
\begin{aligned}
2a &= 3 - 1 \\
2a &= 2 \\
a &= 1
\end{aligned}
$$

Thus, the unique value of the parameter that makes $f$ continuous at $x = 2$ is:

$$
a = 1
$$

---

## Verification and Consistency Checks

### Checking the Resulting Piecewise Function for $a = 1$

Substituting $a = 1$ into the formula for $f(x)$ yields:

$$
f(x) =
\begin{cases}
x + 1, & x < 2, \\
x^2 - 1, & x \ge 2.
\end{cases}
$$

Re-evaluating the three quantities at $x = 2$:
1. **Left-hand limit:**

$$
\lim_{x\to2^-} f(x) = \lim_{x\to2^-} (x + 1) = 2 + 1 = 3
$$

2. **Right-hand limit:**

$$
\lim_{x\to2^+} f(x) = \lim_{x\to2^+} (x^2 - 1) = 2^2 - 1 = 3
$$

3. **Function value:**

$$
f(2) = 2^2 - 1 = 3
$$

Because $3 = 3 = 3$, the two branches meet seamlessly at the point $(2, 3)$ with no jump discontinuity. (For any $a \neq 1$, the graph has a vertical jump of size $|(2a + 1) - 3| = 2|a - 1|$ at $x = 2$.)

---

## Why This Exercise Matters

- **Three-Part Checklist for Continuity:** Continuity at a boundary point $x = x_0$ of a piecewise function always reduces to computing three numbers — $\lim_{x\to x_0^-} f(x)$, $\lim_{x\to x_0^+} f(x)$, and $f(x_0)$ — and enforcing their equality.
- **Geometric Meaning (Gluing Curves Together):** Choosing $a = 1$ adjusts the slope of the half-line $y = ax + 1$ ($x < 2$) so that its right endpoint approaches $(2, 3)$, matching the starting point $(2, 3)$ of the parabolic branch $y = x^2 - 1$ ($x \ge 2$).
