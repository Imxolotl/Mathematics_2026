## Question

Compute $\int 2x(x^2+1)^4\,dx$ by substitution, identify $u$ and its derivative, and verify the result.

## Solution

The expression $x^2+1$ is the inner function, and its derivative $2x$ is exactly the remaining factor in the integrand. This recognizes the substitution as reversing the chain rule. Let $u=x^2+1$, so $du=2x\,dx$. Then

$$\int 2x(x^2+1)^4\,dx=\int u^4\,du=\frac{u^5}{5}+C
=\frac{(x^2+1)^5}{5}+C.$$

Differentiation verifies the result:

$$\frac{d}{dx}\left(\frac{(x^2+1)^5}{5}+C\right)
=\frac15\cdot5(x^2+1)^4\cdot2x
=2x(x^2+1)^4.$$
