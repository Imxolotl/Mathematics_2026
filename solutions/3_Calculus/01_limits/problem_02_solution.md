# Problem 2: Different Growth Rates

## Question

Compute

$$
\lim_{n\to\infty}\frac{3n+1}{n^2+4},\qquad \lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}.
$$

Compare the two cases and formulate a general observation about the degrees of the polynomials in the numerator and denominator.

---

## Solution

### 1. First Limit: Denominator Has Higher Degree

Consider the sequence

$$
a_n = \frac{3n + 1}{n^2 + 4}
$$

Here, the numerator is a polynomial of degree $1$, while the denominator is a polynomial of degree $2$. Factoring out the highest power of the denominator, $n^2$, from both numerator and denominator gives:

$$
\begin{aligned}
\frac{3n + 1}{n^2 + 4} &= \frac{n^2\left(\frac{3}{n} + \frac{1}{n^2}\right)}{n^2\left(1 + \frac{4}{n^2}\right)} \\
&= \frac{\frac{3}{n} + \frac{1}{n^2}}{1 + \frac{4}{n^2}}
\end{aligned}
$$

As $n \to \infty$, we have $\frac{3}{n} \to 0$, $\frac{1}{n^2} \to 0$, and $\frac{4}{n^2} \to 0$. Applying the quotient rule for limits:

$$
\begin{aligned}
\lim_{n\to\infty}\frac{3n + 1}{n^2 + 4} &= \frac{0 + 0}{1 + 0} \\
&= \frac{0}{1} \\
&= 0
\end{aligned}
$$

---

### 2. Second Limit: Numerator Has Higher Degree

Consider the sequence

$$
b_n = \frac{2n^3 - n}{5n^2 + 1}
$$

Here, the numerator has degree $3$ and the denominator has degree $2$. Factoring out $n^2$ (the highest power in the denominator) from both numerator and denominator gives:

$$
\begin{aligned}
\frac{2n^3 - n}{5n^2 + 1} &= \frac{n^2\left(2n - \frac{1}{n}\right)}{n^2\left(5 + \frac{1}{n^2}\right)} \\
&= \frac{2n - \frac{1}{n}}{5 + \frac{1}{n^2}}
\end{aligned}
$$

Equivalently, factoring out the dominant term of the numerator ($n^3$) and the dominant term of the denominator ($n^2$) separately shows the net power of $n$:

$$
\frac{2n^3 - n}{5n^2 + 1} = n \cdot \frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}}
$$

As $n \to \infty$:
- The first factor grows without bound: $n \to \infty$.
- The second factor converges to a positive constant:

$$
\lim_{n\to\infty}\frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}} = \frac{2 - 0}{5 + 0} = \frac{2}{5} > 0
$$

Because the product of a sequence diverging to $+\infty$ and a sequence converging to a positive limit $\frac{2}{5} > 0$ grows without bound:

$$
\lim_{n\to\infty}\frac{2n^3 - n}{5n^2 + 1} = \infty
$$

---

### 3. Comparison of the Two Cases

1. **First Case ($\deg P = 1 < \deg Q = 2$):**
   The denominator $n^2 + 4$ grows quadratically while the numerator $3n + 1$ grows only linearly. After canceling $n$, a factor of $n$ remains in the denominator ($\frac{3n + 1}{n^2 + 4} \sim \frac{3}{n}$), pulling the entire fraction down to $0$.

2. **Second Case ($\deg P = 3 > \deg Q = 2$):**
   The numerator $2n^3 - n$ grows cubically while the denominator $5n^2 + 1$ grows quadratically. After canceling $n^2$, an uncompensated factor of $n$ remains in the numerator ($\frac{2n^3 - n}{5n^2 + 1} \sim \frac{2}{5}n$), driving the quotient to $+\infty$.

---

### 4. General Observation on Polynomial Degrees

Let $P(n) = a_p n^p + \dots + a_0$ and $Q(n) = b_q n^q + \dots + b_0$ be polynomials of degrees $p$ and $q$ with leading coefficients $a_p \neq 0$ and $b_q \neq 0$. Factoring out $n^p$ from the numerator and $n^q$ from the denominator yields:

$$
\frac{P(n)}{Q(n)} = n^{p - q} \cdot \frac{a_p + \frac{a_{p-1}}{n} + \dots + \frac{a_0}{n^p}}{b_q + \frac{b_{q-1}}{n} + \dots + \frac{b_0}{n^q}}
$$

As $n \to \infty$, the second fraction approaches $\frac{a_p}{b_q} \neq 0$, so the behavior is governed entirely by the sign of the degree difference $p - q$:

| Degree Relationship | Exponent $p - q$ | Behavior of $n^{p-q}$ | Limit $\lim_{n\to\infty}\frac{P(n)}{Q(n)}$ |
| :--- | :--- | :--- | :--- |
| $p < q$ ($\deg P < \deg Q$) | $p - q < 0$ | $n^{p-q} = \frac{1}{n^{q-p}} \to 0$ | $0$ |
| $p = q$ ($\deg P = \deg Q$) | $p - q = 0$ | $n^0 = 1$ | $\frac{a_p}{b_q}$ (finite non-zero constant) |
| $p > q$ ($\deg P > \deg Q$) | $p - q > 0$ | $n^{p-q} \to +\infty$ | $+\infty$ if $\frac{a_p}{b_q} > 0$, or $-\infty$ if $\frac{a_p}{b_q} < 0$ |

---

## Verification and Consistency Checks

### Numerical Comparison for Increasing $n$

| $n$ | $a_n = \frac{3n+1}{n^2+4}$ | Asymptotic Approximation $\frac{3}{n}$ | $b_n = \frac{2n^3-n}{5n^2+1}$ | Asymptotic Approximation $\frac{2}{5}n$ |
| :--- | :--- | :--- | :--- | :--- |
| $10$ | $\frac{31}{104} \approx 0.2981$ | $0.3000$ | $\frac{1990}{501} \approx 3.9721$ | $4.0000$ |
| $100$ | $\frac{301}{10004} \approx 0.0301$ | $0.0300$ | $\frac{1999900}{50001} \approx 39.9972$ | $40.0000$ |
| $1{,}000$ | $\frac{3001}{1000004} \approx 0.0030$ | $0.0030$ | $\frac{1999999000}{5000001} \approx 399.9997$ | $400.0000$ |

The numerical values confirm that $a_n \to 0$ at rate $\frac{3}{n}$ while $b_n \to \infty$ at rate $0.4n$.

---

## Why This Exercise Matters

- **Hierarchy of Polynomial Growth:** For large $n$, $n^3$ outgrows $n^2$, and $n^2$ outgrows $n$, regardless of the multiplicative constants ($3n$ vs. $1n^2$, or $2n^3$ vs. $5n^2$).
- **Three-Case Classification:** Combining Exercise 1 ($p = q$) with Exercise 2 ($p < q$ and $p > q$) gives the complete classification for the limit at infinity of any rational expression.
