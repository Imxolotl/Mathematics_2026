## Question

Compute $\int xe^{x^2}\,dx$ and compare its structure with Problem 4, explaining the common substitution mechanism.

## Solution

As in Problem 4, the integrand is a function of an inner expression multiplied by a constant multiple of that inner expression's derivative. Here the inner expression is $x^2$, whose derivative is $2x$.

Set $u=x^2$, so $du=2x\,dx$ and $x\,dx=\tfrac12du$. Then

$$\int xe^{x^2}\,dx=\frac12\int e^u\,du
=\frac12e^u+C
=\frac12e^{x^2}+C.$$

The differentiation check is

$$\frac{d}{dx}\left(\frac12e^{x^2}+C\right)
=\frac12e^{x^2}(2x)=xe^{x^2},$$

so the antiderivative is correct. The outer functions differ between Problems 4 and 5, but the shared structure is an outer function evaluated at an inner function together with the inner derivative, which permits substitution.
