# Problem 11: An n-th Root

## Question

Compute

$$
\lim_{n\to\infty}\sqrt[n]{5^n+2^n}.
$$

Explain which term dominates and why the transformation looks different from the case of a quotient of polynomials.

---

## Solution

### 1. Identifying the Dominant Exponential Term

Inside the $n$-th root $\sqrt[n]{5^n + 2^n}$, there are two exponential terms: $5^n$ and $2^n$. Because the base $5$ is strictly larger than the base $2$ ($5 > 2 > 0$), the term $5^n$ grows exponentially faster than $2^n$:

$$
\frac{2^n}{5^n} = \left(\frac{2}{5}\right)^n \to 0 \qquad \mathrm{as}\ n \to \infty
$$

Therefore, $5^n$ is the **dominant term** inside the radical.

---

### 2. Method 1: Algebraic Transformation by Factoring Out $5^n$

Factoring the dominant exponential term $5^n$ out from under the $n$-th root and using the radical property $\sqrt[n]{A \cdot B} = \sqrt[n]{A}\,\sqrt[n]{B}$ (for $A, B > 0$) gives:

$$
\begin{aligned}
\sqrt[n]{5^n + 2^n} &= \sqrt[n]{5^n\left(1 + \frac{2^n}{5^n}\right)} \\
&= \sqrt[n]{5^n} \cdot \sqrt[n]{1 + \left(\frac{2}{5}\right)^n} \\
&= 5 \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n}
\end{aligned}
$$

As $n \to \infty$:
- Since $0 < \frac{2}{5} < 1$, the geometric sequence $\left(\frac{2}{5}\right)^n \to 0$, so the base inside the parenthesis approaches $1 + 0 = 1$.
- The exponent $\frac{1}{n}$ approaches $0$.
- Because a base approaching $1$ raised to an exponent approaching $0$ is a determinate form $1^0 = 1$, we obtain:

$$
\lim_{n\to\infty}\left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} = 1^0 = 1
$$

Multiplying by the extracted factor $5$:

$$
\begin{aligned}
\lim_{n\to\infty}\sqrt[n]{5^n + 2^n} &= 5 \cdot \lim_{n\to\infty}\left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} \\
&= 5 \cdot 1 \\
&= 5
\end{aligned}
$$

---

### 3. Method 2: Rigorous Justification via the Squeeze Theorem

To make the convergence $\left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} \to 1$ completely elementary without appealing to two-variable power continuity, bound $5^n + 2^n$ from below and above using $2^n > 0$ and $2^n < 5^n$:

$$
5^n < 5^n + 2^n < 5^n + 5^n = 2 \cdot 5^n
$$

Taking the $n$-th root across the entire inequality (which preserves the inequality signs because $t \mapsto \sqrt[n]{t}$ is strictly increasing for $t > 0$):

$$
\sqrt[n]{5^n} < \sqrt[n]{5^n + 2^n} < \sqrt[n]{2 \cdot 5^n}
$$

$$
5 < \sqrt[n]{5^n + 2^n} < 5 \cdot \sqrt[n]{2}
$$

Since $\lim_{n\to\infty}\sqrt[n]{2} = 1$, both the lower bound and the upper bound converge to $5$:

$$
\lim_{n\to\infty} 5 = 5, \qquad \lim_{n\to\infty}\left(5\sqrt[n]{2}\right) = 5 \cdot 1 = 5
$$

By the Squeeze Theorem:

$$
\lim_{n\to\infty}\sqrt[n]{5^n + 2^n} = 5
$$

---

### 4. Why the Transformation Looks Different from a Quotient of Polynomials

| Feature | Quotient of Polynomials (e.g., $\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7}$) | $n$-th Root of Exponentials ($\sqrt[n]{5^n + 2^n}$) |
| :--- | :--- | :--- |
| **Structure of expression** | Fraction $\frac{P(n)}{Q(n)}$ | Radical $\left(a^n + b^n\right)^{1/n}$ |
| **How terms compete** | Fixed exponents ($n^2$ vs. $n^1$); variable base $n$ | Fixed bases ($5$ vs. $2$); variable exponent $n$ |
| **Dominant term** | Highest power $n^2$ | Largest base $5^n$ |
| **How the dominant term simplifies** | $n^2$ cancels between numerator and denominator ($\frac{n^2}{n^2} = 1$) | $5^n$ exits the $n$-th root as $\sqrt[n]{5^n} = 5$ |
| **How subleading terms vanish** | Power ratios $\frac{1}{n^k} \to 0$ inside numerator and denominator | Geometric ratio $\left(\frac{2}{5}\right)^n \to 0$ under the $n$-th root |

In short:
- In a **quotient of polynomials**, we factor out the highest power $n^d$ so that $n^d$ **cancels by division** ($\frac{n^d}{n^d} = 1$), leaving the ratio of leading coefficients.
- In an **$n$-th root of a sum of exponentials**, there is no denominator; instead, we factor out the largest base $a^n$ so that the $n$-th root **neutralizes the $n$-th power** ($\sqrt[n]{a^n} = a$), leaving the largest base $a = \max(5, 2) = 5$.

---

## Verification and Consistency Checks

### Numerical Evaluation for Small Values of $n$

Because $\left(\frac{2}{5}\right)^n = (0.4)^n$ decays exponentially fast and the $n$-th root further compresses $1 + (0.4)^n$ toward $1$, the sequence converges to $5$ remarkably quickly:

| $n$ | $5^n + 2^n$ | $\sqrt[n]{5^n + 2^n}$ (to 6 decimal places) | Upper Squeeze Bound $5\sqrt[n]{2}$ |
| :--- | :--- | :--- | :--- |
| $1$ | $5 + 2 = 7$ | $7.000000$ | $10.000000$ |
| $2$ | $25 + 4 = 29$ | $5.385165$ | $7.071068$ |
| $5$ | $3125 + 32 = 3157$ | $5.010209$ | $5.743492$ |
| $10$ | $9765625 + 1024 = 9766649$ | $5.000052$ | $5.358867$ |
| $20$ | $5^{20} + 2^{20}$ | $5.000000$ | $5.176325$ |

By $n = 10$, $\sqrt[n]{5^n + 2^n}$ is already within $0.000053$ of the limit $5$.

---

## Why This Exercise Matters

- **Maximum-Base Rule:** For any positive constants $a_1, a_2, \dots, a_k > 0$, factoring out the largest base $M = \max(a_1, \dots, a_k)$ immediately yields $\lim_{n\to\infty}\sqrt[n]{a_1^n + a_2^n + \dots + a_k^n} = \max(a_1, \dots, a_k)$.
- **Matching the Operation to the Structure:** Cancellation of dominant terms uses division ($\frac{n^d}{n^d} = 1$) in fractions, but root extraction ($\sqrt[n]{a^n} = a$) in $n$-th roots.
