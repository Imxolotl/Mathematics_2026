## Question

Compute $\int(2\sqrt{x}+3/x^2-x^{1/3})\,dx$, first rewriting powers and determining the original domain, then verify by differentiation.

## Solution

The integrand can be written as

$$2x^{1/2}+3x^{-2}-x^{1/3}.$$

The square root requires $x\geq0$, while the term $3/x^2$ requires $x\ne0$. Their intersection is therefore $x>0$, which is the domain of the original expression.

Applying the power rule term by term,

$$\int\left(2x^{1/2}+3x^{-2}-x^{1/3}\right)dx
=\frac43x^{3/2}-\frac3x-\frac34x^{4/3}+C.$$

On differentiating,

$$\left(\frac43x^{3/2}-\frac3x-\frac34x^{4/3}+C\right)'
=2x^{1/2}+3x^{-2}-x^{1/3},$$

which recovers the integrand for $x>0$.
