## Question

Compute $\int(2e^x+3\cos x-4\sin x)\,dx$, match each term to a known derivative, and verify the result.

## Solution

We use $(e^x)'=e^x$, $(\sin x)'=\cos x$, and $(\cos x)'=-\sin x$. Therefore termwise integration gives

$$\int(2e^x+3\cos x-4\sin x)\,dx
=2e^x+3\sin x+4\cos x+C.$$

The sign in the last term is positive because differentiating $4\cos x$ produces $-4\sin x$. Differentiating the whole result checks it at once:

$$(2e^x+3\sin x+4\cos x+C)'=2e^x+3\cos x-4\sin x.$$
