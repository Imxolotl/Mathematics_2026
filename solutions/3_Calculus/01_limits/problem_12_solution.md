# Problem 12: Exponential Function Limit

## Question

Compute

$$
\lim_{x\to0}(1+3x)^{1/x}.
$$

Connect the result with the limit from Exercise 5 and show the appropriate transformation.

---

## Solution

### 1. Recognizing the $1^{\infty}$ Indeterminate Form and Connection with Exercise 5

As $x \to 0$:
- The base $1 + 3x$ approaches $1 + 0 = 1$.
- The exponent $\frac{1}{x}$ grows without bound in magnitude ($\frac{1}{x} \to +\infty$ as $x \to 0^+$ and $\frac{1}{x} \to -\infty$ as $x \to 0^-$).

This is an indeterminate form of type $1^{\infty}$, the continuous counterpart of the sequence limit from Exercise 5:

$$
\lim_{n\to\infty}\left(1 + \frac{1}{n}\right)^n = e
$$

More generally, replacing the discrete integer $n \to \infty$ by a real variable $t \to \pm\infty$ gives the continuous exponential limit pattern:

$$
\lim_{t\to\pm\infty}\left(1 + \frac{1}{t}\right)^t = e
$$

and in terms of the reciprocal infinitesimal $u = \frac{1}{t} \to 0$:

$$
\lim_{u\to0}(1 + u)^{1/u} = e
$$

---

### 2. Transformation 1: Algebraic Matching of the Exponent

In the pattern $(1 + u)^{1/u}$, the exponent must be the exact reciprocal of the small quantity $u$ added to $1$. In our expression $(1 + 3x)^{1/x}$, the term added to $1$ is $3x$, so its reciprocal is $\frac{1}{3x}$.

We rewrite the exponent $\frac{1}{x}$ as $3 \cdot \frac{1}{3x}$ and apply the power-of-a-power rule $a^{bc} = \left(a^b\right)^c$ (valid for $1 + 3x > 0$, i.e., $|x| < \frac{1}{3}$, $x \neq 0$):

$$
\begin{aligned}
(1 + 3x)^{1/x} &= (1 + 3x)^{3 \cdot \frac{1}{3x}} \\
&= \left((1 + 3x)^{1/(3x)}\right)^3
\end{aligned}
$$

Now introduce the substitution $u = 3x$. As $x \to 0$ (with $x \neq 0$), we have $u = 3x \to 0$ (with $u \neq 0$), so the inner expression reduces directly to the classical limit for $e$:

$$
\lim_{x\to0}(1 + 3x)^{1/(3x)} = \lim_{u\to0}(1 + u)^{1/u} = e
$$

Because the cubing function $s \mapsto s^3$ is continuous everywhere on $\mathbb{R}$, we can pass the limit inside the outer exponent $3$:

$$
\begin{aligned}
\lim_{x\to0}(1 + 3x)^{1/x} &= \lim_{x\to0}\left((1 + 3x)^{1/(3x)}\right)^3 \\
&= \left(\lim_{x\to0}(1 + 3x)^{1/(3x)}\right)^3 \\
&= e^3
\end{aligned}
$$

---

### 3. Transformation 2: Direct Substitution $t = \frac{1}{3x}$ Back to Exercise 5

Alternatively, set

$$
\frac{1}{t} = 3x \iff t = \frac{1}{3x} \iff \frac{1}{x} = 3t
$$

As $x \to 0^+$, we have $t \to +\infty$, and as $x \to 0^-$, we have $t \to -\infty$. Substituting $3x = \frac{1}{t}$ and $\frac{1}{x} = 3t$ transforms $(1 + 3x)^{1/x}$ directly into the form of Exercise 5:

$$
\begin{aligned}
\lim_{x\to0}(1 + 3x)^{1/x} &= \lim_{t\to\pm\infty}\left(1 + \frac{1}{t}\right)^{3t} \\
&= \lim_{t\to\pm\infty}\left(\left(1 + \frac{1}{t}\right)^t\right)^3 \\
&= e^3
\end{aligned}
$$

---

## Verification and Consistency Checks

### Check 1: Logarithmic-Exponential Rewrite

For $1 + 3x > 0$, we can write $(1 + 3x)^{1/x} = e^{\frac{\ln(1+3x)}{x}}$. Using the standard logarithmic limit $\lim_{u\to0}\frac{\ln(1+u)}{u} = 1$ with $u = 3x$:

$$
\lim_{x\to0}\frac{\ln(1 + 3x)}{x} = \lim_{x\to0}\left(3 \cdot \frac{\ln(1 + 3x)}{3x}\right) = 3 \cdot 1 = 3
$$

By continuity of the exponential function $e^s$, $\lim_{x\to0}(1 + 3x)^{1/x} = e^3$.

### Check 2: Numerical Evaluation from Both Sides of $x = 0$

Comparing $(1 + 3x)^{1/x}$ for small positive and negative values of $x$ with $e^3 \approx 20.085537$:

| $x$ | $1 + 3x$ | Exponent $\frac{1}{x}$ | $(1 + 3x)^{1/x}$ | Target $e^3 \approx 20.085537$ |
| :--- | :--- | :--- | :--- | :--- |
| $-0.01$ | $0.97$ | $-100$ | $21.003417$ | $20.085537$ |
| $-0.001$ | $0.997$ | $-1{,}000$ | $20.176293$ | $20.085537$ |
| $-0.0001$ | $0.9997$ | $-10{,}000$ | $20.094579$ | $20.085537$ |
| $+0.0001$ | $1.0003$ | $+10{,}000$ | $20.076501$ | $20.085537$ |
| $+0.001$ | $1.003$ | $+1{,}000$ | $19.995527$ | $20.085537$ |
| $+0.01$ | $1.03$ | $+100$ | $19.218632$ | $20.085537$ |

Both the left-hand values ($x \to 0^-$) and the right-hand values ($x \to 0^+$) pinch together toward $e^3 \approx 20.085537$.

---

## Why This Exercise Matters

- **General Exponential Pattern:** For any real constant $k \in \mathbb{R}$, matching the exponent via $(1 + kx)^{1/x} = \left((1 + kx)^{1/(kx)}\right)^k$ yields the universal formula:

$$
\lim_{x\to0}(1 + kx)^{1/x} = e^k, \qquad \lim_{n\to\infty}\left(1 + \frac{k}{n}\right)^n = e^k
$$

- **Reciprocal-Matching Technique:** Whenever a $1^{\infty}$ limit has the form $(1 + \alpha(x))^{\beta(x)}$ with $\alpha(x) \to 0$, forcing the inner exponent to be $\frac{1}{\alpha(x)}$ reduces the base to $e$ and leaves $\lim \alpha(x)\beta(x)$ in the outer exponent.
