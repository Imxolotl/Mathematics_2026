# Problem 1: Dominant Terms in a Sequence

## Question

Compute

$$
\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}.
$$

Explain why the highest-degree terms determine the result.

---

## Solution

### 1. Identifying the Indeterminate Form and the Dominant Power

As $n \to \infty$, both the numerator $4n^2 - 3n + 1$ and the denominator $2n^2 + 5n - 7$ grow without bound:

$$
4n^2 - 3n + 1 \to \infty, \qquad 2n^2 + 5n - 7 \to \infty
$$

Direct substitution produces an indeterminate form of type $\frac{\infty}{\infty}$. To resolve this form algebraically, inspect the highest power of $n$ appearing in the denominator (and numerator), which is $n^2$.

---

### 2. Factoring Out the Highest Power $n^2$

For every positive integer $n \ge 1$, we have $n^2 \neq 0$. Factoring $n^2$ out of both the numerator and the denominator (or equivalently, dividing every term in the numerator and denominator by $n^2$) gives:

$$
\begin{aligned}
\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} &= \frac{n^2\left(4 - \frac{3n}{n^2} + \frac{1}{n^2}\right)}{n^2\left(2 + \frac{5n}{n^2} - \frac{7}{n^2}\right)} \\
&= \frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}}
\end{aligned}
$$

---

### 3. Passing to the Limit as $n \to \infty$

By the elementary reciprocal limit rule, for any fixed positive power $k > 0$:

$$
\lim_{n\to\infty}\frac{1}{n^k} = 0
$$

Therefore, each lower-order fraction vanishes as $n \to \infty$:

$$
\lim_{n\to\infty}\frac{3}{n} = 0, \qquad \lim_{n\to\infty}\frac{1}{n^2} = 0, \qquad \lim_{n\to\infty}\frac{5}{n} = 0, \qquad \lim_{n\to\infty}\frac{7}{n^2} = 0
$$

Since the limit of the transformed denominator is $2 + 0 - 0 = 2 \neq 0$, the limit laws for sums, differences, and quotients apply directly:

$$
\begin{aligned}
\lim_{n\to\infty}\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} &= \lim_{n\to\infty}\frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}} \\
&= \frac{4 - 0 + 0}{2 + 0 - 0} \\
&= \frac{4}{2} \\
&= 2
\end{aligned}
$$

---

### 4. Why the Highest-Degree Terms Determine the Result

#### 1. Relative Negligibility of Lower-Degree Terms

In a polynomial $P(n) = a_2 n^2 + a_1 n + a_0$ with $a_2 \neq 0$, the ratio of the linear and constant terms to the quadratic term is:

$$
\frac{-3n + 1}{4n^2} = -\frac{3}{4n} + \frac{1}{4n^2} \to 0 \qquad \mathrm{as}\ n \to \infty
$$

Although $-3n + 1$ grows large in absolute value when $n$ is large, its contribution becomes an arbitrarily small percentage of $4n^2$. For instance, at $n = 1000$:
- Leading term in the numerator: $4n^2 = 4{,}000{,}000$
- Remaining terms in the numerator: $-3n + 1 = -2{,}999$ (less than $0.08\%$ of $4n^2$)

#### 2. Asymptotic Equivalence to the Ratio of Leading Terms

Because the relative error approaches zero in both the numerator and the denominator, the fraction behaves for large $n$ just like the quotient of its highest-degree terms alone:

$$
\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} \sim \frac{4n^2}{2n^2} = \frac{4}{2} = 2
$$

After $n^2$ cancels between numerator and denominator, only the ratio of the leading coefficients $\frac{4}{2} = 2$ survives.

---

## Verification and Consistency Checks

### Numerical Convergence Table

Evaluating $a_n = \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7}$ for increasing values of $n$ confirms the convergence toward $2$:

| $n$ | Numerator $4n^2 - 3n + 1$ | Denominator $2n^2 + 5n - 7$ | Quotient $a_n$ (approx.) | Difference $2 - a_n$ |
| :--- | :--- | :--- | :--- | :--- |
| $10$ | $371$ | $243$ | $1.5267$ | $0.4733$ |
| $100$ | $39{,}701$ | $20{,}493$ | $1.9373$ | $0.0627$ |
| $1{,}000$ | $3{,}997{,}001$ | $2{,}004{,}993$ | $1.9935$ | $0.0065$ |
| $10{,}000$ | $399{,}970{,}001$ | $200{,}049{,}993$ | $1.9994$ | $0.0006$ |

Each factor-of-$10$ increase in $n$ reduces the distance from $2$ by roughly a factor of $10$, matching the $O\left(\frac{1}{n}\right)$ decay of the subleading terms.

---

## Why This Exercise Matters

- **Dominant-Term Extraction:** Factoring out the highest power converts an indeterminate $\frac{\infty}{\infty}$ ratio into a determinate expression where all lower-degree terms become $\frac{c}{n^k} \to 0$.
- **Equal-Degree Rational Rule:** Whenever two polynomials in $n$ have the exact same degree $d$, the limit of their quotient as $n \to \infty$ is the ratio of their leading coefficients.

