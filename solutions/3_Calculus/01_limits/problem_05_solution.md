# Problem 5: The Classical Limit Leading to the Number $e$

## Question

Compute

$$
\lim_{n\to\infty}\left(1+\frac1n\right)^n.
$$

Calculate several values for increasing $n$ and compare the observed behavior with the value of the limit. Explain why a few values do not constitute a proof.

---

## Solution

### 1. Value of the Classical Limit

Consider the sequence

$$
e_n = \left(1 + \frac{1}{n}\right)^n
$$

As $n \to \infty$, the base $1 + \frac{1}{n}$ approaches $1$ from above while the exponent $n$ grows to $\infty$, creating an indeterminate form of type $1^{\infty}$:
- The shrinking fraction $\frac{1}{n} \to 0$ pulls the base toward $1$ (which, taken to any fixed power, would stay near $1$).
- The growing exponent $n \to \infty$ pushes a number greater than $1$ upward toward $\infty$.

The balance between these two competing effects converges to a finite irrational constant, Euler's number $e$:

$$
\lim_{n\to\infty}\left(1 + \frac{1}{n}\right)^n = e \approx 2.718281828459\dots
$$

---

### 2. Why the Sequence Converges (Analytical Justification)

To prove rigorously that $e_n = \left(1 + \frac{1}{n}\right)^n$ converges to a finite limit without relying on numerical tables, one establishes two properties using the Binomial Theorem:

#### 1. The Sequence Is Strictly Increasing ($e_n < e_{n+1}$)

Expanding $e_n$ by the Binomial Theorem gives:

$$
\begin{aligned}
e_n &= \sum_{k=0}^{n} \binom{n}{k}\frac{1}{n^k} \\
    &= 1 + 1 + \frac{1}{2!}\left(1 - \frac{1}{n}\right) + \frac{1}{3!}\left(1 - \frac{1}{n}\right)\left(1 - \frac{2}{n}\right) + \dots + \frac{1}{n!}\left(1 - \frac{1}{n}\right)\cdots\left(1 - \frac{n-1}{n}\right)
\end{aligned}
$$

When $n$ increases to $n + 1$, every factor $\left(1 - \frac{j}{n}\right)$ increases to $\left(1 - \frac{j}{n+1}\right)$, and one additional positive term is appended at the end. Therefore, $e_n < e_{n+1}$ for all $n \ge 1$.

#### 2. The Sequence Is Bounded Above ($2 \le e_n < 3$)

Since each factor $\left(1 - \frac{j}{n}\right)$ lies in $(0, 1)$ and $k! = 1 \cdot 2 \cdot 3 \cdots k \ge 2^{k-1}$ for all $k \ge 2$:

$$
\begin{aligned}
e_n &< 1 + 1 + \frac{1}{2!} + \frac{1}{3!} + \dots + \frac{1}{n!} \\
    &\le 1 + 1 + \frac{1}{2} + \frac{1}{2^2} + \dots + \frac{1}{2^{n-1}} \\
    &= 1 + \left(2 - \frac{1}{2^{n-1}}\right) \\
    &< 3
\end{aligned}
$$

By the **Monotone Convergence Theorem**, every sequence that is both strictly increasing and bounded above converges to a finite limit $e \in (2, 3)$.

---

### 3. Numerical Values for Increasing $n$ and Comparison with $e$

Evaluating $e_n = \left(1 + \frac{1}{n}\right)^n$ for progressively larger values of $n$ and comparing with $e \approx 2.7182818$:

| $n$ | Expression $\left(1 + \frac{1}{n}\right)^n$ | Decimal Value $e_n$ (to 6 decimal places) | Error $e - e_n$ |
| :--- | :--- | :--- | :--- |
| $1$ | $\left(1 + 1\right)^1 = 2^1$ | $2.000000$ | $0.718282$ |
| $2$ | $\left(1 + \frac{1}{2}\right)^2 = \left(\frac{3}{2}\right)^2 = \frac{9}{4}$ | $2.250000$ | $0.468282$ |
| $5$ | $\left(1 + \frac{1}{5}\right)^5 = (1.2)^5$ | $2.488320$ | $0.229962$ |
| $10$ | $\left(1 + \frac{1}{10}\right)^{10} = (1.1)^{10}$ | $2.593742$ | $0.124539$ |
| $100$ | $(1.01)^{100}$ | $2.704814$ | $0.013468$ |
| $1{,}000$ | $(1.001)^{1000}$ | $2.716924$ | $0.001358$ |
| $10{,}000$ | $(1.0001)^{10000}$ | $2.718146$ | $0.000136$ |
| $100{,}000$ | $(1.00001)^{100000}$ | $2.718268$ | $0.000014$ |
| $\infty$ (limit) | $e$ | $2.718282$ | $0.000000$ |

#### Observed Behavior

1. **Monotone Increase:** As $n$ grows from $1$ to $100{,}000$, the values $e_n$ increase steadily from $2$ toward $e \approx 2.718282$, never exceeding $e$.
2. **Slow $O\left(\frac{1}{n}\right)$ Rate of Convergence:** Each factor-of-$10$ increase in $n$ yields roughly one additional correct decimal digit of $e$ (because $e - e_n \approx \frac{e}{2n}$).

---

### 4. Why a Few Numerical Values Do Not Constitute a Proof

Computing $e_n$ for a finite set of indices (such as $n = 1, 2, 10, 100, 100{,}000$) is useful for building intuition and checking calculations, but it **cannot prove** that the limit exists or equals $e$ for four fundamental reasons:

1. **A Limit Is an Infinite Tail Property:**
   Convergence depends on the behavior of $e_n$ for *all* infinitely many indices $n \ge N$, not on any finite sample. Any finite table leaves infinitely many untested terms beyond the largest computed $n$.
2. **Slow Divergence Can Imitate Convergence:**
   Some divergent sequences grow so slowly across the first $10^5$ terms that a finite table looks bounded. For example, the harmonic partial sums $H_n = \sum_{k=1}^{n}\frac{1}{k}$ or $\ln(\ln(n + 10))$ change imperceptibly between $n = 10{,}000$ and $n = 100{,}000$, yet both diverge to $+\infty$.
3. **Late-Onset Changes in Behavior:**
   A sequence such as $s_n = e_n + 10^{-12}n$ agrees with $e_n$ to multiple decimal places for $n \le 10^5$, appearing to stabilize near $2.718$, yet for $n > 10^{12}$ the linear term takes over and drives $s_n \to \infty$.
4. **Finite Precision Cannot Identify an Exact Real Number:**
   Even if a table suggests stabilization near $2.71828$, numerical sampling cannot distinguish $e$ from a nearby rational number such as $\frac{271828}{100000}$. Only an analytical proof (such as the Monotone Convergence Theorem above) establishes convergence for all $n \to \infty$.

---

## Why This Exercise Matters

- **Prototype of the $1^{\infty}$ Indeterminate Form:** The limit $\lim_{n\to\infty}\left(1 + \frac{1}{n}\right)^n = e$ is the foundation for all exponential limits in calculus, compound-interest formulas in finance, and the derivative of $\ln x$ and $e^x$.
- **Distinction Between Numerical Evidence and Mathematical Proof:** Numerical experiments reveal patterns and detect errors, whereas rigorous proofs guarantee that the pattern holds all the way to infinity.
