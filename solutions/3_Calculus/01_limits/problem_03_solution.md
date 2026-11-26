# Problem 3: A Square Root and Removing an Indeterminate Form

## Question

Compute

$$
\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right).
$$

Use the conjugate expression and explain why this transformation removes the difficulty.

---

## Solution

### 1. Recognizing the $\infty - \infty$ Indeterminate Form

As $n \to \infty$, both terms in the difference grow without bound:

$$
\sqrt{n^2 + 5n} \to \infty, \qquad n \to \infty
$$

Therefore, the expression $\sqrt{n^2 + 5n} - n$ is an indeterminate form of type $\infty - \infty$. Note that one cannot simply drop $5n$ inside the square root and write $\sqrt{n^2} - n = n - n = 0$, because the two leading $n$ terms cancel each other out, leaving the subleading $5n$ term to determine the finite limit.

---

### 2. Multiplying by the Conjugate Expression

For an expression of the form $\sqrt{A} - B$, the **conjugate expression** is $\sqrt{A} + B$. Using the difference-of-squares identity $(u - v)(u + v) = u^2 - v^2$, multiplying and dividing by $\sqrt{n^2 + 5n} + n$ eliminates the square root from the numerator:

$$
\begin{aligned}
\sqrt{n^2 + 5n} - n &= \left(\sqrt{n^2 + 5n} - n\right) \cdot \frac{\sqrt{n^2 + 5n} + n}{\sqrt{n^2 + 5n} + n} \\
&= \frac{\left(\sqrt{n^2 + 5n}\right)^2 - n^2}{\sqrt{n^2 + 5n} + n} \\
&= \frac{(n^2 + 5n) - n^2}{\sqrt{n^2 + 5n} + n} \\
&= \frac{5n}{\sqrt{n^2 + 5n} + n}
\end{aligned}
$$

---

### 3. Factoring Out the Dominant Power $n$ and Computing the Limit

For every positive integer $n \ge 1$, we have $n > 0$, so $\sqrt{n^2} = n$. Factoring $n^2$ out of the expression under the radical gives:

$$
\sqrt{n^2 + 5n} = \sqrt{n^2\left(1 + \frac{5}{n}\right)} = n\sqrt{1 + \frac{5}{n}}
$$

Substituting this into the denominator and factoring $n$ out of both the numerator and denominator yields:

$$
\begin{aligned}
\frac{5n}{\sqrt{n^2 + 5n} + n} &= \frac{5n}{n\sqrt{1 + \frac{5}{n}} + n} \\
&= \frac{5n}{n\left(\sqrt{1 + \frac{5}{n}} + 1\right)} \\
&= \frac{5}{\sqrt{1 + \frac{5}{n}} + 1}
\end{aligned}
$$

As $n \to \infty$, we have $\frac{5}{n} \to 0$. By the continuity of the square root function at $1$:

$$
\lim_{n\to\infty}\sqrt{1 + \frac{5}{n}} = \sqrt{1 + 0} = 1
$$

Consequently:

$$
\begin{aligned}
\lim_{n\to\infty}\left(\sqrt{n^2 + 5n} - n\right) &= \lim_{n\to\infty}\frac{5}{\sqrt{1 + \frac{5}{n}} + 1} \\
&= \frac{5}{1 + 1} \\
&= \frac{5}{2}
\end{aligned}
$$

---

### 4. Why the Conjugate Transformation Removes the Difficulty

1. **Exact Cancellation of the Leading $n^2$ Terms:**
   In the original difference $\sqrt{n^2 + 5n} - n$, the competing terms $\sqrt{n^2 + 5n}$ and $n$ both grow like $n$, and the square root prevents direct subtraction. Squaring each term via $(u - v)(u + v) = u^2 - v^2$ removes the radical in the numerator and allows the leading quadratic terms $n^2$ and $-n^2$ to cancel algebraically: $(n^2 + 5n) - n^2 = 5n$.

2. **Conversion of Subtraction in the Numerator into Addition in the Denominator:**
   In the denominator $\sqrt{n^2 + 5n} + n$, the minus sign is replaced by a plus sign. Instead of nearly canceling, the two terms reinforce each other ($\sqrt{n^2 + 5n} + n \sim n + n = 2n$). This transforms the unstable $\infty - \infty$ difference into a clean $\frac{\infty}{\infty}$ quotient $\frac{5n}{\approx 2n}$ in which the common factor $n$ cancels immediately.

---

## Verification and Consistency Checks

### Check 1: Completing the Square Inside the Radical

Notice that $n^2 + 5n$ can be compared to the perfect square $\left(n + \frac{5}{2}\right)^2$:

$$
\left(n + \frac{5}{2}\right)^2 = n^2 + 5n + \frac{25}{4}
$$

For all $n \ge 1$, this gives the tight two-sided inequality:

$$
\sqrt{n^2 + 5n} < \sqrt{n^2 + 5n + \frac{25}{4}} = n + \frac{5}{2}
$$

showing immediately that $\sqrt{n^2 + 5n} - n$ approaches $\frac{5}{2}$ from below as the constant $\frac{25}{4}$ becomes negligible compared to $n^2 + 5n$.

### Check 2: Numerical Evaluation

| $n$ | $\sqrt{n^2 + 5n}$ | $\sqrt{n^2 + 5n} - n$ | Limit $\frac{5}{2} = 2.5$ |
| :--- | :--- | :--- | :--- |
| $10$ | $\sqrt{150} \approx 12.2474$ | $2.2474$ | $2.5000$ |
| $100$ | $\sqrt{10500} \approx 102.4695$ | $2.4695$ | $2.5000$ |
| $1{,}000$ | $\sqrt{1005000} \approx 1002.4969$ | $2.4969$ | $2.5000$ |
| $10{,}000$ | $\sqrt{100050000} \approx 10002.4997$ | $2.4997$ | $2.5000$ |

---

## Why This Exercise Matters

- **Warning Against Premature Approximation:** Dropping $5n$ inside $\sqrt{n^2 + 5n}$ before resolving the subtraction would falsely suggest a limit of $0$ instead of the true limit $\frac{5}{2}$.
- **Conjugation Technique:** Multiplying by the conjugate is the standard algebraic method whenever a limit involves a difference of square roots whose leading terms agree.
