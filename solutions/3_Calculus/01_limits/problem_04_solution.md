# Problem 4: Powers and Oscillation

## Question

Analyze

$$
\left(\frac23\right)^n,\qquad \left(\frac32\right)^n,\qquad (-1)^n,\qquad \frac{(-1)^n}{n}.
$$

For each sequence, describe the type of behavior and justify your answer.

---

## Solution

### 1. Sequence 1: $a_n = \left(\frac{2}{3}\right)^n$ — Monotone Decay to $0$ (Convergent)

- **Limit and Behavior Type:**
  The sequence is positive, strictly decreasing, and converges to $0$:

$$
\lim_{n\to\infty}\left(\frac{2}{3}\right)^n = 0
$$

- **Justification:**
  This is a geometric sequence $q^n$ with common ratio $q = \frac{2}{3}$, which satisfies $0 < q < 1$.
  1. **Monotonicity:** Each successive term is obtained by multiplying the previous term by $\frac{2}{3} < 1$:

$$
a_{n+1} = \frac{2}{3} a_n < a_n
$$

  2. **Convergence to $0$:** Because $\frac{3}{2} = 1 + \frac{1}{2}$, Bernoulli's inequality $(1 + h)^n \ge 1 + nh$ (for $h = \frac{1}{2} > 0$) implies:

$$
\left(\frac{3}{2}\right)^n = \left(1 + \frac{1}{2}\right)^n \ge 1 + \frac{n}{2}
$$

  Taking reciprocals gives the squeeze bound:

$$
0 < \left(\frac{2}{3}\right)^n \le \frac{1}{1 + \frac{n}{2}} < \frac{2}{n}
$$

  Since $\lim_{n\to\infty}\frac{2}{n} = 0$, the Squeeze Theorem guarantees $\lim_{n\to\infty}\left(\frac{2}{3}\right)^n = 0$.

---

### 2. Sequence 2: $b_n = \left(\frac{3}{2}\right)^n$ — Monotone Unbounded Growth (Divergent to $+\infty$)

- **Limit and Behavior Type:**
  The sequence is positive, strictly increasing, and diverges to $+\infty$:

$$
\lim_{n\to\infty}\left(\frac{3}{2}\right)^n = \infty
$$

- **Justification:**
  This is a geometric sequence $q^n$ with base $q = \frac{3}{2} = 1.5 > 1$.
  1. **Monotonicity:** Multiplying by $\frac{3}{2} > 1$ increases the term at every step:

$$
b_{n+1} = \frac{3}{2} b_n > b_n
$$

  2. **Unbounded Growth:** By Bernoulli's inequality with $h = \frac{1}{2} > 0$:

$$
\left(\frac{3}{2}\right)^n = \left(1 + \frac{1}{2}\right)^n \ge 1 + \frac{n}{2}
$$

  Since $\lim_{n\to\infty}\left(1 + \frac{n}{2}\right) = \infty$, the comparison principle for infinite limits shows that $\left(\frac{3}{2}\right)^n \to \infty$.

---

### 3. Sequence 3: $c_n = (-1)^n$ — Persistent (Undamped) Oscillation (Divergent)

- **Limit and Behavior Type:**
  The sequence is bounded ($|c_n| = 1$ for all $n$), alternates endlessly between $-1$ and $1$, and **does not have a limit** (diverges by oscillation).

- **Justification:**
  Writing out the terms explicitly by parity of $n$:

$$
c_n = (-1)^n =
\begin{cases}
1, & \mathrm{if}\ n\ \mathrm{is\ even}, \\
-1, & \mathrm{if}\ n\ \mathrm{is\ odd}.
\end{cases}
$$

  Consider the even-indexed subsequence $c_{2k}$ and the odd-indexed subsequence $c_{2k-1}$:

$$
\lim_{k\to\infty} c_{2k} = \lim_{k\to\infty} 1 = 1
$$

$$
\lim_{k\to\infty} c_{2k-1} = \lim_{k\to\infty} (-1) = -1
$$

  A sequence converges to a limit $L$ if and only if every subsequence converges to the same limit $L$. Because the even and odd subsequences converge to two different values ($1 \neq -1$), the limit $\lim_{n\to\infty}(-1)^n$ does not exist.

---

### 4. Sequence 4: $d_n = \frac{(-1)^n}{n}$ — Damped Oscillation to $0$ (Convergent)

- **Limit and Behavior Type:**
  The sequence alternates in sign around $0$ with shrinking amplitude and **converges to $0$**:

$$
\lim_{n\to\infty}\frac{(-1)^n}{n} = 0
$$

- **Justification:**
  1. **Squeeze Theorem Argument:** Since $-1 \le (-1)^n \le 1$ for every positive integer $n$, dividing by $n > 0$ gives:

$$
-\frac{1}{n} \le \frac{(-1)^n}{n} \le \frac{1}{n}
$$

  Because both the lower bound and the upper bound converge to $0$:

$$
\lim_{n\to\infty}\left(-\frac{1}{n}\right) = 0, \qquad \lim_{n\to\infty}\frac{1}{n} = 0
$$

  the Squeeze Theorem implies $\lim_{n\to\infty}\frac{(-1)^n}{n} = 0$.

  2. **Absolute Value Argument:** The distance from $d_n$ to $0$ is $|d_n - 0| = \left|\frac{(-1)^n}{n}\right| = \frac{1}{n} \to 0$. Even though the terms jump back and forth across $0$ ($-1, \frac{1}{2}, -\frac{1}{3}, \frac{1}{4}, \dots$), both the even subsequence $\frac{1}{2k}$ and the odd subsequence $-\frac{1}{2k-1}$ approach the exact same number $0$.

---

## Summary Comparison Table

| Sequence | First Four Terms ($n=1,2,3,4$) | Bounded? | Monotone? | Oscillating? | Limit as $n\to\infty$ | Classification |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| $\left(\frac{2}{3}\right)^n$ | $\frac{2}{3},\ \frac{4}{9},\ \frac{8}{27},\ \frac{16}{81}$ | Yes | Decreasing | No | $0$ | Convergent |
| $\left(\frac{3}{2}\right)^n$ | $\frac{3}{2},\ \frac{9}{4},\ \frac{27}{8},\ \frac{81}{16}$ | No | Increasing | No | $\infty$ | Divergent to $\infty$ |
| $(-1)^n$ | $-1,\ 1,\ -1,\ 1$ | Yes | No | Yes (constant amplitude $1$) | Does not exist | Divergent |
| $\frac{(-1)^n}{n}$ | $-1,\ \frac{1}{2},\ -\frac{1}{3},\ \frac{1}{4}$ | Yes | No | Yes (amplitude $\frac{1}{n} \to 0$) | $0$ | Convergent |

---

## Why This Exercise Matters

- **Threshold $q = 1$ for Geometric Sequences:** For $q > 0$, the power sequence $q^n$ decays to $0$ when $0 < q < 1$ and explodes to $+\infty$ when $q > 1$.
- **Oscillation Does Not Prevent Convergence:** Comparing $(-1)^n$ with $\frac{(-1)^n}{n}$ shows that sign alternation only prevents convergence when the amplitude fails to decay to $0$. Multiplying any bounded sequence (such as $(-1)^n$) by a sequence tending to $0$ (such as $\frac{1}{n}$) always produces a sequence converging to $0$.
