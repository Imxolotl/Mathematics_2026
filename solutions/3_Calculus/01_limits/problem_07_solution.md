# Problem 7: Limit at a Point and Canceling a Factor

## Question

Compute

$$
\lim_{x\to3}\frac{x^2-4x+3}{x-3}.
$$

Explain why the value of the function at $x=3$ is not needed to compute the limit.

---

## Solution

### 1. Detecting the $\frac{0}{0}$ Indeterminate Form

Let

$$
f(x) = \frac{x^2 - 4x + 3}{x - 3}
$$

Evaluating the numerator and the denominator separately as $x \to 3$:
- Numerator at $x = 3$: $3^2 - 4(3) + 3 = 9 - 12 + 3 = 0$
- Denominator at $x = 3$: $3 - 3 = 0$

This produces an indeterminate form of type $\frac{0}{0}$. By the Factor Theorem, because the quadratic polynomial $x^2 - 4x + 3$ vanishes at $x = 3$, it must contain $(x - 3)$ as an exact linear factor.

---

### 2. Factoring the Numerator and Canceling the Common Factor

We factor the quadratic numerator $x^2 - 4x + 3$ by finding two numbers whose product is $3$ and whose sum is $-4$ (namely $-1$ and $-3$):

$$
x^2 - 4x + 3 = (x - 1)(x - 3)
$$

Substituting this factorization into $f(x)$ gives:

$$
\frac{x^2 - 4x + 3}{x - 3} = \frac{(x - 1)(x - 3)}{x - 3}
$$

When taking the limit as $x \to 3$, we consider values of $x$ arbitrarily close to $3$ **but strictly different from $3$** ($x \neq 3$). Because $x \neq 3$, the factor $x - 3$ is non-zero ($x - 3 \neq 0$), so we can legitimately divide both numerator and denominator by $x - 3$:

$$
\frac{(x - 1)(x - 3)}{x - 3} = x - 1 \qquad \mathrm{for\ all}\ x \neq 3
$$

---

### 3. Passing to the Limit as $x \to 3$

Because the rational expression $\frac{x^2 - 4x + 3}{x - 3}$ and the linear polynomial $x - 1$ are equal at every point $x \neq 3$, they have the exact same limit as $x \to 3$. Since $g(x) = x - 1$ is a continuous polynomial, its limit at $x = 3$ is found by direct substitution:

$$
\begin{aligned}
\lim_{x\to3}\frac{x^2 - 4x + 3}{x - 3} &= \lim_{x\to3}\frac{(x - 1)(x - 3)}{x - 3} \\
&= \lim_{x\to3}(x - 1) \\
&= 3 - 1 \\
&= 2
\end{aligned}
$$

---

### 4. Why the Value of the Function at $x = 3$ Is Not Needed

1. **Definition of a Limit Uses a Punctured Neighborhood ($0 < |x - 3| < \delta$):**
   By definition, $\lim_{x\to a} f(x) = L$ means that $f(x)$ can be made arbitrarily close to $L$ for all $x$ satisfying $0 < |x - a| < \delta$. The strict inequality $0 < |x - 3|$ explicitly excludes the point $x = 3$ itself. A limit describes how $f(x)$ behaves *near* $x = 3$, never *at* $x = 3$.

2. **The Function $f(x)$ Is Not Even Defined at $x = 3$:**
   At $x = 3$, the expression $\frac{x^2 - 4x + 3}{x - 3}$ involves division by zero, so $3$ is not in the domain of $f$. Geometrically, the graph of $y = \frac{x^2 - 4x + 3}{x - 3}$ is the straight line $y = x - 1$ with a single missing point (a **removable discontinuity** or "puncture") at $(3, 2)$.

3. **Limits Are Invariant Under Changes at a Single Point:**
   Whether $f(3)$ is left undefined, defined to be $100$, or defined to be $2$, the values of $f(x)$ for $x \neq 3$ remain $x - 1$, so $\lim_{x\to3} f(x) = 2$ is completely unaffected.

---

## Verification and Consistency Checks

### Numerical Approach from Both Sides of $x = 3$

Evaluating $f(x) = \frac{x^2 - 4x + 3}{x - 3}$ for $x$ approaching $3$ from the left ($x < 3$) and from the right ($x > 3$):

| $x$ (from the left, $x \to 3^-$) | $f(x) = \frac{x^2-4x+3}{x-3}$ | $x$ (from the right, $x \to 3^+$) | $f(x) = \frac{x^2-4x+3}{x-3}$ |
| :--- | :--- | :--- | :--- |
| $2.9$ | $1.9$ | $3.1$ | $2.1$ |
| $2.99$ | $1.99$ | $3.01$ | $2.01$ |
| $2.999$ | $1.999$ | $3.001$ | $2.001$ |
| $2.9999$ | $1.9999$ | $3.0001$ | $2.0001$ |

Both one-sided approaches converge linearly to $2$.

---

## Why This Exercise Matters

- **Why Cancellation Is Valid Inside a Limit:** Canceling $\frac{x - 3}{x - 3} = 1$ is algebraically valid inside $\lim_{x\to3}$ precisely because the limit operation only inspects points where $x \neq 3$.
- **Foundation of the Derivative:** Every difference quotient $\lim_{h\to0}\frac{f(x_0 + h) - f(x_0)}{h}$ in differential calculus is a $\frac{0}{0}$ limit where $h = 0$ is excluded from the domain.
