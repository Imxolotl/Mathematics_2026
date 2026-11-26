# Problem 13: Fundamental Trigonometric Limit

## Question

Using

$$
\lim_{x\to0}\frac{\sin x}{x}=1,
$$

compute

$$
\lim_{x\to0}\frac{\sin5x}{x},\qquad \lim_{x\to0}\frac{\sin2x}{\sin3x}.
$$

In each case, show how you reduce the expression to the fundamental limit.

---

## Solution

### 1. Structure of the Fundamental Trigonometric Limit

The fundamental trigonometric limit

$$
\lim_{u\to0}\frac{\sin u}{u} = 1
$$

states that as any non-zero angle $u$ (measured in radians) approaches $0$, the ratio of the sine of the angle to the **exact same angle** in the denominator approaches $1$ (and consequently its reciprocal $\frac{u}{\sin u}$ also approaches $1$).

To reduce a trigonometric limit to this pattern, whenever $\sin(kx)$ appears, we multiply and divide by its argument $kx$ so that the matched ratio $\frac{\sin(kx)}{kx}$ is formed.

---

### 2. First Limit: $\lim_{x\to0}\frac{\sin 5x}{x}$

#### Step 1: Match the Argument $5x$ in the Denominator

In $\frac{\sin 5x}{x}$, the argument inside the sine function is $5x$, whereas the denominator is $x$. For all $x \neq 0$, multiply both numerator and denominator by $5$:

$$
\frac{\sin 5x}{x} = 5 \cdot \frac{\sin 5x}{5x}
$$

#### Step 2: Apply the Substitution $u = 5x$ and Pass to the Limit

Let $u = 5x$. As $x \to 0$ (with $x \neq 0$), we have $u = 5x \to 0$ (with $u \neq 0$). Applying the constant multiple law for limits and the fundamental limit $\lim_{u\to0}\frac{\sin u}{u} = 1$:

$$
\begin{aligned}
\lim_{x\to0}\frac{\sin 5x}{x} &= \lim_{x\to0}\left(5 \cdot \frac{\sin 5x}{5x}\right) \\
&= 5 \cdot \lim_{u\to0}\frac{\sin u}{u} \\
&= 5 \cdot 1 \\
&= 5
\end{aligned}
$$

---

### 3. Second Limit: $\lim_{x\to0}\frac{\sin 2x}{\sin 3x}$

#### Step 1: Match Both Arguments $2x$ and $3x$

Here, both the numerator $\sin 2x$ and the denominator $\sin 3x$ vanish at $x = 0$, giving a $\frac{0}{0}$ indeterminate form. For $x$ near $0$ with $x \neq 0$, we multiply and divide by $2x$ and $3x$ to pair each sine with its own argument:

$$
\begin{aligned}
\frac{\sin 2x}{\sin 3x} &= \frac{\sin 2x}{2x} \cdot \frac{3x}{\sin 3x} \cdot \frac{2x}{3x} \\
&= \frac{2}{3} \cdot \frac{\frac{\sin 2x}{2x}}{\frac{\sin 3x}{3x}}
\end{aligned}
$$

#### Step 2: Evaluate Each Matched Ratio and Pass to the Limit

As $x \to 0$ (with $x \neq 0$), both $u = 2x \to 0$ and $v = 3x \to 0$. Therefore, both fundamental ratios converge to $1$:

$$
\lim_{x\to0}\frac{\sin 2x}{2x} = \lim_{u\to0}\frac{\sin u}{u} = 1
$$

$$
\lim_{x\to0}\frac{\sin 3x}{3x} = \lim_{v\to0}\frac{\sin v}{v} = 1
$$

Since the denominator limit is $1 \neq 0$, the quotient rule for limits yields:

$$
\begin{aligned}
\lim_{x\to0}\frac{\sin 2x}{\sin 3x} &= \frac{2}{3} \cdot \frac{\lim_{x\to0}\frac{\sin 2x}{2x}}{\lim_{x\to0}\frac{\sin 3x}{3x}} \\
&= \frac{2}{3} \cdot \frac{1}{1} \\
&= \frac{2}{3}
\end{aligned}
$$

---

## Verification and Consistency Checks

### Small-Angle Approximation ($\sin u \approx u$ for $|u| \ll 1$)

Geometrically, for a very small angle $u$ in radians, the vertical leg $\sin u$ and the circular arc length $u$ are almost indistinguishable ($\sin u \approx u$):
1. For the first expression:

$$
\frac{\sin 5x}{x} \approx \frac{5x}{x} = 5
$$

2. For the second expression:

$$
\frac{\sin 2x}{\sin 3x} \approx \frac{2x}{3x} = \frac{2}{3}
$$

### Numerical Check Near $x = 0$ (in Radians)

| $x$ (radians) | $\frac{\sin 5x}{x}$ | Limit $5$ | $\frac{\sin 2x}{\sin 3x}$ | Limit $\frac{2}{3} \approx 0.666667$ |
| :--- | :--- | :--- | :--- | :--- |
| $\pm 0.1$ | $4.794255$ | $5.000000$ | $0.672582$ | $0.666667$ |
| $\pm 0.01$ | $4.997917$ | $5.000000$ | $0.666722$ | $0.666667$ |
| $\pm 0.001$ | $4.999979$ | $5.000000$ | $0.666667$ | $0.666667$ |

---

## Why This Exercise Matters

- **Argument-Matching Principle:** You may never cancel constants directly through the sine function ($\sin 5x \neq 5\sin x$ and $\frac{\sin 2x}{\sin 3x} \neq \frac{\sin 2}{\sin 3}$). Instead, you match the denominator to the argument inside $\sin(\cdot)$ so that $\frac{\sin u}{u} \to 1$ applies legitimately.
- **General Formula for Sine Ratios:** By the exact same derivation, for any non-zero constants $a, b \neq 0$:

$$
\lim_{x\to0}\frac{\sin(ax)}{x} = a, \qquad \lim_{x\to0}\frac{\sin(ax)}{\sin(bx)} = \frac{a}{b}
$$
