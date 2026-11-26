# Problem 8: A Square Root in a Function Limit

## Question

Compute

$$
\lim_{x\to4}\frac{\sqrt{x}-2}{x-4}
$$

by rationalizing the numerator. Compare the idea with Exercise 3 involving a sequence.

---

## Solution

### 1. Detecting the $\frac{0}{0}$ Indeterminate Form

Let

$$
f(x) = \frac{\sqrt{x} - 2}{x - 4}
$$

for $x \ge 0$, $x \neq 4$. As $x \to 4$:
- Numerator: $\sqrt{4} - 2 = 2 - 2 = 0$
- Denominator: $4 - 4 = 0$

This is an indeterminate form of type $\frac{0}{0}$. The zero in the numerator comes from $\sqrt{x} - 2$, while the zero in the denominator comes from $x - 4$.

---

### 2. Rationalizing the Numerator via the Conjugate

To expose the hidden common factor $x - 4$ in the numerator, multiply both the numerator and the denominator by the conjugate of $\sqrt{x} - 2$, which is $\sqrt{x} + 2$ (note that near $x = 4$, $\sqrt{x} + 2 \approx 4 \neq 0$):

$$
\begin{aligned}
\frac{\sqrt{x} - 2}{x - 4} &= \frac{\sqrt{x} - 2}{x - 4} \cdot \frac{\sqrt{x} + 2}{\sqrt{x} + 2} \\
&= \frac{(\sqrt{x})^2 - 2^2}{(x - 4)(\sqrt{x} + 2)} \\
&= \frac{x - 4}{(x - 4)(\sqrt{x} + 2)}
\end{aligned}
$$

For all $x \neq 4$ (with $x \ge 0$), the factor $x - 4$ is non-zero and cancels between the numerator and denominator:

$$
\frac{x - 4}{(x - 4)(\sqrt{x} + 2)} = \frac{1}{\sqrt{x} + 2} \qquad \mathrm{for\ all}\ x \ge 0,\ x \neq 4
$$

---

### 3. Passing to the Limit as $x \to 4$

In the simplified expression $\frac{1}{\sqrt{x} + 2}$, the denominator no longer vanishes at $x = 4$. By the continuity of $\sqrt{x}$ at $x = 4$:

$$
\begin{aligned}
\lim_{x\to4}\frac{\sqrt{x} - 2}{x - 4} &= \lim_{x\to4}\frac{1}{\sqrt{x} + 2} \\
&= \frac{1}{\sqrt{4} + 2} \\
&= \frac{1}{2 + 2} \\
&= \frac{1}{4}
\end{aligned}
$$

---

### 4. Comparison with Exercise 3

| Feature | Exercise 3: $\lim_{n\to\infty}\left(\sqrt{n^2 + 5n} - n\right)$ | Exercise 8: $\lim_{x\to4}\frac{\sqrt{x} - 2}{x - 4}$ |
| :--- | :--- | :--- |
| **Type of limit** | Sequence limit at infinity ($n \to \infty$) | Function limit at a finite point ($x \to 4$) |
| **Indeterminate form** | $\infty - \infty$ | $\frac{0}{0}$ |
| **Conjugate multiplier** | $\frac{\sqrt{n^2 + 5n} + n}{\sqrt{n^2 + 5n} + n}$ | $\frac{\sqrt{x} + 2}{\sqrt{x} + 2}$ |
| **Algebraic identity used** | $(u - v)(u + v) = u^2 - v^2$ | $(u - v)(u + v) = u^2 - v^2$ |
| **Result of squaring** | $(n^2 + 5n) - n^2 = 5n$ (cancels dominant $n^2$) | $x - 4$ (exposes vanishing factor $x - 4$) |
| **Final cancellation** | Divide numerator and denominator by $n$ | Cancel $(x - 4)$ from numerator and denominator |

#### Key Conceptual Connection

In both exercises, a difference involving a square root ($\sqrt{A} - B$) causes near-cancellation:
- In Exercise 3, $\sqrt{n^2 + 5n}$ and $n$ both approach $\infty$, so their difference is $\infty - \infty$.
- In Exercise 8, $\sqrt{x}$ and $2$ both approach $2$ as $x \to 4$, so their difference approaches $2 - 2 = 0$ and creates a $\frac{0}{0}$ quotient.

In both cases, multiplying by the conjugate $\sqrt{A} + B$ uses $(u - v)(u + v) = u^2 - v^2$ to square away the radical in the difference while placing a well-behaved sum $\sqrt{A} + B$ (whose limit is non-zero) in the denominator.

---

## Verification and Consistency Checks

### Check 1: Direct Factorization of $x - 4$ as a Difference of Squares

Viewing $x = (\sqrt{x})^2$ and $4 = 2^2$ for $x \ge 0$, we can factor the denominator directly:

$$
x - 4 = (\sqrt{x} - 2)(\sqrt{x} + 2)
$$

Then for $x \neq 4$:

$$
\frac{\sqrt{x} - 2}{x - 4} = \frac{\sqrt{x} - 2}{(\sqrt{x} - 2)(\sqrt{x} + 2)} = \frac{1}{\sqrt{x} + 2} \to \frac{1}{4} \qquad \mathrm{as}\ x \to 4
$$

### Check 2: Interpretation as a Derivative

The limit $\lim_{x\to4}\frac{\sqrt{x} - \sqrt{4}}{x - 4}$ is the definition of the derivative of $g(x) = \sqrt{x}$ at $x_0 = 4$. Since $g'(x) = \frac{1}{2\sqrt{x}}$, evaluating at $x_0 = 4$ gives $g'(4) = \frac{1}{2\sqrt{4}} = \frac{1}{4}$, matching our result.

---

## Why This Exercise Matters

- **Portability of Algebraic Techniques:** Rationalizing via the conjugate resolves both $\infty - \infty$ sequence limits (Exercise 3) and $\frac{0}{0}$ function limits (Exercise 8).
- **Direct Link to Differentiation:** Computing $\lim_{x\to4}\frac{\sqrt{x} - 2}{x - 4} = \frac{1}{4}$ calculates from first principles the slope of the tangent line to $y = \sqrt{x}$ at $(4, 2)$.
