# Problem 15: Observation Versus Proof

## Question

Choose one sequence and one function from this set. For the sequence, compute several values for increasingly large $n$. For the function, prepare a table of values with arguments approaching the limit point from the left and right. Sketch the behavior of both objects.

Compare the observation with the analytical result and explain why a finite number of calculations or a sketch does not constitute a proof that the limit exists.

---

## Solution

### 1. Choice of One Sequence and One Function from the Set

We select two representative examples from this exercise set:
1. **Sequence (from Exercise 3):**

$$
a_n = \sqrt{n^2 + 5n} - n \qquad (n \to \infty)
$$

   Analytical limit proved in Exercise 3: $\lim_{n\to\infty}\left(\sqrt{n^2 + 5n} - n\right) = \frac{5}{2} = 2.5$.

2. **Function (from Exercise 7):**

$$
f(x) = \frac{x^2 - 4x + 3}{x - 3} \qquad (x \to 3)
$$

   Analytical limit proved in Exercise 7: $\lim_{x\to3}\frac{x^2 - 4x + 3}{x - 3} = 2$.

---

### 2. Numerical Investigation and Sketch of the Chosen Sequence

#### Table of Sequence Values for Increasingly Large $n$

Evaluating $a_n = \sqrt{n^2 + 5n} - n$ across several orders of magnitude of $n$:

| $n$ | $n^2 + 5n$ | $\sqrt{n^2 + 5n}$ (approx.) | $a_n = \sqrt{n^2 + 5n} - n$ | Analytical Limit $L = 2.5$ | Error $2.5 - a_n$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $1$ | $6$ | $2.449490$ | $1.449490$ | $2.500000$ | $1.050510$ |
| $2$ | $14$ | $3.741657$ | $1.741657$ | $2.500000$ | $0.758343$ |
| $5$ | $50$ | $7.071068$ | $2.071068$ | $2.500000$ | $0.428932$ |
| $10$ | $150$ | $12.247449$ | $2.247449$ | $2.500000$ | $0.252551$ |
| $50$ | $2{,}750$ | $52.440442$ | $2.440442$ | $2.500000$ | $0.059558$ |
| $100$ | $10{,}500$ | $102.469508$ | $2.469508$ | $2.500000$ | $0.030492$ |
| $1{,}000$ | $1{,}005{,}000$ | $1002.496883$ | $2.496883$ | $2.500000$ | $0.003117$ |
| $10{,}000$ | $100{,}050{,}000$ | $10002.499688$ | $2.499688$ | $2.500000$ | $0.000312$ |

#### Sketch of the Sequence $a_n = \sqrt{n^2 + 5n} - n$

```text
    a_n
     ^
 2.5 + - - - - - - - - - - - - - - - - - - - - - - - - - - -   <- Horizontal asymptote L = 5/2 = 2.5
     |                                       *       *
 2.0 +                       *       *
     |               *
 1.5 +       *
     |
 1.0 +
     |
 0.0 +-------+-------+-------+-------+-------+-------+-----> n
     0       1       2       5      10      50     100
```

---

### 3. Numerical Investigation and Sketch of the Chosen Function

#### Table of Function Values Approaching $x = 3$ from the Left and Right

Evaluating $f(x) = \frac{x^2 - 4x + 3}{x - 3}$ as $x \to 3^-$ and $x \to 3^+$ (note that $f(3)$ is undefined because $\frac{0}{0}$ occurs at $x = 3$):

| Left Approach ($x \to 3^-$) | Value $f(x)$ | Right Approach ($x \to 3^+$) | Value $f(x)$ | Distance from $2$ |
| :--- | :--- | :--- | :--- | :--- |
| $2.5$ | $1.5$ | $3.5$ | $2.5$ | $0.5$ |
| $2.9$ | $1.9$ | $3.1$ | $2.1$ | $0.1$ |
| $2.99$ | $1.99$ | $3.01$ | $2.01$ | $0.01$ |
| $2.999$ | $1.999$ | $3.001$ | $2.001$ | $0.001$ |
| $2.9999$ | $1.9999$ | $3.0001$ | $2.0001$ | $0.0001$ |

#### Sketch of the Function $f(x) = \frac{x^2 - 4x + 3}{x - 3}$

```text
               y
               ^
             3 +                             /
               |                           /
             2 + - - - - - - - - - - - - o     <- Punctured point (hole) at (3, 2):
               |                       / :        f(3) is undefined, limit is 2
             1 +                     /   :
               |                   /     :
             0 +---------+-------*-------+-----> x
              /0         1      2        3
            * (0,-1)
```

---

### 4. Comparison of Numerical Observation with Analytical Results

1. **Agreement of Numerical Trend and Analytical Proof:**
   - For $a_n = \sqrt{n^2 + 5n} - n$, the table shows the terms climbing monotonically from $1.449$ toward $2.5$, agreeing with the analytical rationalization $a_n = \frac{5}{\sqrt{1 + 5/n} + 1} \to \frac{5}{2} = 2.5$.
   - For $f(x) = \frac{x^2 - 4x + 3}{x - 3}$, the two-sided table shows $f(x)$ approaching $2$ symmetrically from below ($1.9, 1.99, 1.999$) and from above ($2.1, 2.01, 2.001$), agreeing with the analytical simplification $f(x) = x - 1$ for $x \neq 3$.

2. **Why the Analytical Transform Explains the Rate of Convergence:**
   - The analytical formula $a_n = \frac{5}{\sqrt{1 + 5/n} + 1}$ explains *why* the error $2.5 - a_n \approx \frac{25}{8n} = \frac{3.125}{n}$ shrinks by a factor of $10$ whenever $n$ grows by a factor of $10$ (at $n = 1{,}000$, the error is $0.003117$; at $n = 10{,}000$, it is $0.000312$).

---

### 5. Why a Finite Number of Calculations or a Sketch Is Not a Proof

Even when a table of values and a sketch look completely convincing, they **never constitute a mathematical proof** that a limit exists or equals a specific value:

1. **Unobserved Behavior Beyond the Sample Range (or Closer to the Limit Point):**
   A table tests only finitely many values of $n$ or $x$.
   - For a sequence, a behavior change can occur after the largest tested index (for example, $b_n = a_n + (10^{-8}n)^2$ looks close to $2.5$ for $n \le 1{,}000$ but diverges to $\infty$ as $n \to \infty$).
   - For a function, pathological behavior can hide inside an unexamined microscopic interval around the limit point (for example, $g(x) = (x - 1) + \sin\left(\frac{\pi}{x - 3}\right)$ equals $x - 1$ at every sample point $x = 3 \pm 10^{-k}$ in our table above, yet oscillates wildly between $1$ and $3$ infinitely many times as $x \to 3$, so its limit does not exist!).
2. **Inability to Distinguish Exact Real Numbers from Decimal Approximations:**
   Finite decimal tables and pixel-resolution graphs cannot distinguish whether a sequence converges to $\frac{5}{2} = 2.5$ or to $2.5 + 10^{-20}$, or whether a limit is an irrational number like $e$ versus a close rational fraction.
3. **Catastrophic Cancellation in Floating-Point Arithmetic:**
   In fact, if one evaluates $a_n = \sqrt{n^2 + 5n} - n$ on a standard 64-bit computer for very large $n$ such as $n = 10^{16}$, floating-point rounding loses the $5n$ term inside $n^2 + 5n$ and outputs $0$ instead of $2.5$! Only the analytical conjugate transformation $\frac{5}{\sqrt{1 + 5/n} + 1}$ proves that the true mathematical limit is $2.5$.

---

## Why This Exercise Matters

- **Complementary Roles of Intuition and Proof:** Tables and sketches are indispensable for forming conjectures, visualizing geometry, and catching algebraic mistakes, while analytical proofs provide certainty across all infinitely many values.
- **Awareness of Sampling Blind Spots:** Functions like $\sin\left(\frac{\pi}{x - 3}\right)$ demonstrate that sampling along a single regular grid $x = 3 \pm 10^{-k}$ can completely miss oscillations that destroy the existence of a limit.
