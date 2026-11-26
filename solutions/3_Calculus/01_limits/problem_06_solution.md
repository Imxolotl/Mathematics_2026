# Problem 6: From a Sequence to a Function — Limit at Infinity

## Question

Compute

$$
\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2}.
$$

Compare the method with Exercise 1. Explain what changes when moving from $n$ to a real variable $x$, and what stays the same.

---

## Solution

### 1. Algebraic Transformation and Limit Computation

As $x \to \infty$, both the numerator $3x^2 - x + 1$ and the denominator $5x^2 + 4x - 2$ grow without bound, yielding an indeterminate form of type $\frac{\infty}{\infty}$.

For all sufficiently large real numbers $x > 0$ (in particular, for every $x \neq 0$), we factor out the highest power $x^2$ from both the numerator and the denominator:

$$
\begin{aligned}
\frac{3x^2 - x + 1}{5x^2 + 4x - 2} &= \frac{x^2\left(3 - \frac{x}{x^2} + \frac{1}{x^2}\right)}{x^2\left(5 + \frac{4x}{x^2} - \frac{2}{x^2}\right)} \\
&= \frac{3 - \frac{1}{x} + \frac{1}{x^2}}{5 + \frac{4}{x} - \frac{2}{x^2}}
\end{aligned}
$$

As the real variable $x \to \infty$, the reciprocal powers decay to $0$:

$$
\lim_{x\to\infty}\frac{1}{x} = 0, \qquad \lim_{x\to\infty}\frac{1}{x^2} = 0
$$

Since the denominator approaches $5 + 0 - 0 = 5 \neq 0$, the limit laws for continuous algebraic operations give:

$$
\begin{aligned}
\lim_{x\to\infty}\frac{3x^2 - x + 1}{5x^2 + 4x - 2} &= \lim_{x\to\infty}\frac{3 - \frac{1}{x} + \frac{1}{x^2}}{5 + \frac{4}{x} - \frac{2}{x^2}} \\
&= \frac{3 - 0 + 0}{5 + 0 - 0} \\
&= \frac{3}{5}
\end{aligned}
$$

---

### 2. Comparison with Exercise 1

#### What Stays the Same

1. **Identical Algebraic Technique:**
   In both Exercise 1 ($\lim_{n\to\infty}\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} = 2$) and Exercise 6, the indeterminate form is $\frac{\infty}{\infty}$, and the resolution consists of factoring out the highest degree power ($n^2$ or $x^2$) from numerator and denominator.
2. **Reciprocal Vanishing Principle:**
   In both settings, terms of the form $\frac{c}{n^k}$ and $\frac{c}{x^k}$ ($k > 0$) converge to $0$ as the argument tends to $+\infty$.
3. **Dominant-Term Rule:**
   Because the numerator and denominator are both quadratic polynomials (degree $2$), the limit in both exercises equals the ratio of the leading coefficients ($\frac{4}{2} = 2$ in Exercise 1; $\frac{3}{5}$ in Exercise 6).

#### What Changes When Moving from $n \in \mathbb{N}$ to $x \in \mathbb{R}$

1. **Continuous Domain vs. Discrete Domain:**
   - In Exercise 1, the variable $n$ takes only discrete positive integer values $n \in \{1, 2, 3, \dots\}$. Visually, the sequence is a set of isolated points $(n, a_n)$.
   - In Exercise 6, the variable $x$ varies continuously over all real numbers in an unbounded interval $(M, \infty) \subset \mathbb{R}$ (not merely integers, but also fractional and irrational values). Visually, the function forms a continuous curve with horizontal asymptote $y = \frac{3}{5}$.
2. **Domain Restrictions (Zeros of the Denominator):**
   - For a function of a real variable $x$, the denominator $5x^2 + 4x - 2 = 0$ has real roots $x = \frac{-2 \pm \sqrt{14}}{5}$ (approximately $-1.148$ and $0.348$) where $f(x)$ is undefined. However, when computing $\lim_{x\to\infty} f(x)$, we only consider $x$ large (for instance, $x > 1$), where the denominator is strictly positive and well away from its roots.
3. **Direction of Infinity ($x \to +\infty$ vs. $x \to -\infty$):**
   - A sequence index $n$ can only tend to $+\infty$.
   - A real variable $x$ can tend to either $+\infty$ or $-\infty$. For a rational function, the exact same factorization works as $x \to -\infty$ as well, showing that $y = \frac{3}{5}$ is a horizontal asymptote in both directions.

---

## Verification and Consistency Checks

### Link Between Function Limits and Sequence Limits (Heine's Definition)

If $\lim_{x\to\infty} f(x) = \frac{3}{5}$ holds for all real $x \to \infty$, then restricting $x$ to integer values $x = n$ must produce a sequence with the exact same limit $\frac{3}{5}$. Checking representative real values confirms rapid convergence to $\frac{3}{5} = 0.6$:

| $x \in \mathbb{R}$ | $f(x) = \frac{3x^2 - x + 1}{5x^2 + 4x - 2}$ | Decimal Value | Difference $0.6 - f(x)$ |
| :--- | :--- | :--- | :--- |
| $10.0$ | $\frac{291}{538}$ | $0.540892$ | $0.059108$ |
| $50.5$ | $\frac{7601.25}{12949.25}$ | $0.586999$ | $0.013001$ |
| $100\pi \approx 314.16$ | $\frac{295773.3}{494735.1}$ | $0.597842$ | $0.002158$ |
| $10{,}000.0$ | $\frac{299990001}{500039998}$ | $0.599932$ | $0.000068$ |

---

## Why This Exercise Matters

- **Unified Toolkit Across Sequences and Functions:** Algebraic techniques learned for sequences ($n \to \infty$) transfer directly without change to rational function limits as $x \to \infty$.
- **Geometric Meaning (Horizontal Asymptotes):** While $\lim_{n\to\infty} a_n = L$ describes the long-term stabilization of discrete sequence terms, $\lim_{x\to\infty} f(x) = \frac{3}{5}$ identifies the horizontal line $y = \frac{3}{5}$ as a horizontal asymptote of the graph $y = f(x)$.
