# Problem 9: One-Sided Limits and an Asymptote

## Question

Analyze the left-hand and right-hand limits of

$$
f(x)=\frac1{x-2}
$$

as $x\to2$. Does the two-sided limit exist? Interpret the result on a sketch of the graph and identify the vertical asymptote.

---

## Solution

### 1. Domain and Behavior Near $x = 2$

The function

$$
f(x) = \frac{1}{x - 2}
$$

is defined for all real numbers $x \neq 2$; its domain is $(-\infty, 2) \cup (2, \infty)$. As $x$ approaches $2$, the numerator remains constantly equal to $1 > 0$, while the denominator $x - 2$ approaches $0$. Because dividing a fixed non-zero constant by a number arbitrarily close to $0$ produces a quotient of arbitrarily large magnitude, $|f(x)| \to \infty$, and the sign of $f(x)$ is determined by the sign of $x - 2$.

---

### 2. Left-Hand Limit ($x \to 2^-$)

When $x$ approaches $2$ from the left ($x < 2$), the difference $x - 2$ is strictly negative ($x - 2 < 0$) and approaches $0$ through negative values (often denoted $0^-$):

$$
x < 2 \implies x - 2 < 0 \implies \frac{1}{x - 2} < 0
$$

As the negative denominator $x - 2$ shrinks toward $0$, the quotient $\frac{1}{x - 2}$ grows without bound in the negative direction:

$$
\lim_{x\to2^-}\frac{1}{x - 2} = -\infty
$$

---

### 3. Right-Hand Limit ($x \to 2^+$)

When $x$ approaches $2$ from the right ($x > 2$), the difference $x - 2$ is strictly positive ($x - 2 > 0$) and approaches $0$ through positive values (often denoted $0^+$):

$$
x > 2 \implies x - 2 > 0 \implies \frac{1}{x - 2} > 0
$$

As the positive denominator $x - 2$ shrinks toward $0$, the quotient $\frac{1}{x - 2}$ grows without bound in the positive direction:

$$
\lim_{x\to2^+}\frac{1}{x - 2} = +\infty
$$

---

### 4. Existence of the Two-Sided Limit

A two-sided limit $\lim_{x\to2} f(x)$ exists if and only if both the left-hand limit and the right-hand limit exist and are equal:

$$
\lim_{x\to2^-} f(x) = -\infty \neq +\infty = \lim_{x\to2^+} f(x)
$$

Because the left-hand limit is $-\infty$ and the right-hand limit is $+\infty$, the two-sided limit $\lim_{x\to2}\frac{1}{x - 2}$ **does not exist** (neither as a finite number nor as a single signed infinity).

---

### 5. Vertical Asymptote and Sketch of the Graph

#### Vertical Asymptote

A vertical line $x = a$ is a **vertical asymptote** of the graph $y = f(x)$ whenever at least one of the one-sided limits $\lim_{x\to a^-} f(x)$ or $\lim_{x\to a^+} f(x)$ is $+\infty$ or $-\infty$. Here, both one-sided limits are infinite, so the vertical line

$$
x = 2
$$

is a **vertical asymptote** of $f(x) = \frac{1}{x - 2}$. (In addition, since $\lim_{x\to\pm\infty}\frac{1}{x - 2} = 0$, the horizontal line $y = 0$ is a horizontal asymptote.)

#### Sketch of $f(x) = \frac{1}{x - 2}$

```text
               y
               ^
               |       :      |
               |       :      |   <- Right branch (x > 2):
               |       :       \     as x -> 2+, f(x) -> +infinity
               |       :        \
               |       :         ' .
               |       :             ' - - . _
        -------+-------+-----------------------> x
             0 | . - - : (2,0)
              /        :
            * (0,-1/2) :
           /   |       :
          |    |       :
          |    |       :   <- Left branch (x < 2):
          |    |       :      as x -> 2-, f(x) -> -infinity
                       ^
               Vertical asymptote x = 2
```

#### Geometric Interpretation on the Graph

- **Left of $x = 2$:** As a point $(x, f(x))$ moves rightward toward the dashed vertical line $x = 2$, the curve plunges steeply downward toward $-\infty$ without ever touching or crossing $x = 2$.
- **Right of $x = 2$:** As a point $(x, f(x))$ moves leftward toward the dashed vertical line $x = 2$, the curve shoots steeply upward toward $+\infty$ without ever touching $x = 2$.

---

## Verification and Consistency Checks

### Table of Values Near $x = 2$

| $x \to 2^-$ (left of $2$) | $x - 2$ | $f(x) = \frac{1}{x-2}$ | $x \to 2^+$ (right of $2$) | $x - 2$ | $f(x) = \frac{1}{x-2}$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $1.9$ | $-0.1$ | $-10$ | $2.1$ | $+0.1$ | $+10$ |
| $1.99$ | $-0.01$ | $-100$ | $2.01$ | $+0.01$ | $+100$ |
| $1.999$ | $-0.001$ | $-1{,}000$ | $2.001$ | $+0.001$ | $+1{,}000$ |
| $1.9999$ | $-0.0001$ | $-10{,}000$ | $2.0001$ | $+0.0001$ | $+10{,}000$ |

---

## Why This Exercise Matters

- **Non-Zero over Zero ($\frac{c}{0}$ with $c \neq 0$) vs. $\frac{0}{0}$:** Unlike Exercise 7 ($\frac{0}{0}$, where a shared factor cancels to give a finite limit), an expression of type $\frac{1}{0}$ has no canceling factor and forces infinite one-sided limits, producing a vertical asymptote rather than a removable hole.
- **Role of One-Sided Sign Analysis:** Because $(x - 2)$ changes sign across $x = 2$, the two one-sided limits diverge to opposite infinities ($-\infty$ vs. $+\infty$).
