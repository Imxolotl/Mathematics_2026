# Problem 14: A $0/0$ Limit with Trigonometry

## Question

Compute

$$
\lim_{x\to0}\frac{1-\cos x}{x^2}.
$$

Justify the result without using l'Hôpital's rule, using a trigonometric identity and the fundamental limit.

---

## Solution

### 1. Detecting the $\frac{0}{0}$ Indeterminate Form

As $x \to 0$, we have $\cos x \to \cos 0 = 1$, so the numerator approaches $1 - 1 = 0$ while the denominator $x^2$ also approaches $0$. Thus, $\lim_{x\to0}\frac{1 - \cos x}{x^2}$ is an indeterminate form of type $\frac{0}{0}$.

To evaluate this limit without l'Hôpital's rule, we convert the difference $1 - \cos x$ into an expression involving $\sin(\cdot)$ so that the fundamental trigonometric limit $\lim_{u\to0}\frac{\sin u}{u} = 1$ can be applied. Below we present two standard trigonometric identity methods.

---

### 2. Method 1: Using the Half-Angle Identity $1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)$

#### Step 1: Apply the Half-Angle Identity

From the double-angle cosine formula $\cos x = 1 - 2\sin^2\left(\frac{x}{2}\right)$, rearranging terms gives the half-angle identity:

$$
1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)
$$

Substituting this into the quotient for $x \neq 0$:

$$
\frac{1 - \cos x}{x^2} = \frac{2\sin^2\left(\frac{x}{2}\right)}{x^2}
$$

#### Step 2: Match the Half-Angle Argument $\frac{x}{2}$ in the Denominator

Because the sine term is squared with argument $\frac{x}{2}$, we want $\left(\frac{x}{2}\right)^2 = \frac{x^2}{4}$ in the denominator. Rewriting $x^2 = 4\left(\frac{x}{2}\right)^2$ gives:

$$
\begin{aligned}
\frac{2\sin^2\left(\frac{x}{2}\right)}{x^2} &= \frac{2\sin^2\left(\frac{x}{2}\right)}{4\left(\frac{x}{2}\right)^2} \\
&= \frac{1}{2} \left(\frac{\sin\left(\frac{x}{2}\right)}{\frac{x}{2}}\right)^2
\end{aligned}
$$

#### Step 3: Apply the Fundamental Trigonometric Limit

Let $u = \frac{x}{2}$. As $x \to 0$ (with $x \neq 0$), we have $u \to 0$ (with $u \neq 0$), so:

$$
\lim_{x\to0}\frac{\sin\left(\frac{x}{2}\right)}{\frac{x}{2}} = \lim_{u\to0}\frac{\sin u}{u} = 1
$$

By the product and power rules for limits:

$$
\begin{aligned}
\lim_{x\to0}\frac{1 - \cos x}{x^2} &= \frac{1}{2} \left(\lim_{x\to0}\frac{\sin\left(\frac{x}{2}\right)}{\frac{x}{2}}\right)^2 \\
&= \frac{1}{2} \cdot 1^2 \\
&= \frac{1}{2}
\end{aligned}
$$

---

### 3. Method 2: Using the Pythagorean Identity $1 - \cos^2 x = \sin^2 x$ (Trigonometric Conjugate)

#### Step 1: Multiply by the Conjugate $1 + \cos x$

For $x$ near $0$, $\cos x \approx 1$, so $1 + \cos x \approx 2 \neq 0$. Multiplying numerator and denominator by $1 + \cos x$ and using $(1 - \cos x)(1 + \cos x) = 1 - \cos^2 x = \sin^2 x$:

$$
\begin{aligned}
\frac{1 - \cos x}{x^2} &= \frac{1 - \cos x}{x^2} \cdot \frac{1 + \cos x}{1 + \cos x} \\
&= \frac{1 - \cos^2 x}{x^2(1 + \cos x)} \\
&= \frac{\sin^2 x}{x^2(1 + \cos x)} \\
&= \left(\frac{\sin x}{x}\right)^2 \cdot \frac{1}{1 + \cos x}
\end{aligned}
$$

#### Step 2: Pass to the Limit as $x \to 0$

Using $\lim_{x\to0}\frac{\sin x}{x} = 1$ and the continuity of $\cos x$ at $x = 0$ ($\lim_{x\to0}\cos x = \cos 0 = 1$):

$$
\begin{aligned}
\lim_{x\to0}\frac{1 - \cos x}{x^2} &= \left(\lim_{x\to0}\frac{\sin x}{x}\right)^2 \cdot \lim_{x\to0}\frac{1}{1 + \cos x} \\
&= 1^2 \cdot \frac{1}{1 + 1} \\
&= \frac{1}{2}
\end{aligned}
$$

Both methods yield the exact same result $\frac{1}{2}$.

---

## Verification and Consistency Checks

### Numerical Check Near $x = 0$ (in Radians)

Because $\cos(-x) = \cos x$ and $(-x)^2 = x^2$, the function $f(x) = \frac{1 - \cos x}{x^2}$ is even ($f(-x) = f(x)$):

| $x$ (radians) | $1 - \cos x$ | $x^2$ | $\frac{1 - \cos x}{x^2}$ | Limit $\frac{1}{2} = 0.5$ |
| :--- | :--- | :--- | :--- | :--- |
| $\pm 0.2$ | $0.01993342$ | $0.04$ | $0.498336$ | $0.500000$ |
| $\pm 0.1$ | $0.00499583$ | $0.01$ | $0.499583$ | $0.500000$ |
| $\pm 0.01$ | $0.0000499996$ | $0.0001$ | $0.499996$ | $0.500000$ |

---

## Why This Exercise Matters

- **Quadratic Deviation of Cosine Near $0$:** While $\sin x$ vanishes linearly like $x$ ($\frac{\sin x}{x} \to 1$), $1 - \cos x$ vanishes quadratically like $\frac{1}{2}x^2$ ($\frac{1 - \cos x}{x^2} \to \frac{1}{2}$). Consequently, $\lim_{x\to0}\frac{1 - \cos x}{x} = \lim_{x\to0}\left(x \cdot \frac{1 - \cos x}{x^2}\right) = 0 \cdot \frac{1}{2} = 0$.
- **Foundation for Derivatives of $\sin x$ and $\cos x$:** This companion limit to $\lim_{x\to0}\frac{\sin x}{x} = 1$ is used directly in proving from the definition of the derivative that $(\sin x)' = \cos x$ and $(\cos x)' = -\sin x$.
