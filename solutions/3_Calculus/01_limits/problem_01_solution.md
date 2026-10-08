### Exercise 1. Dominant Terms in a Sequence

Compute

$$
\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}.
$$

Explain why the highest-degree terms determine the result.

> **Why this exercise:** introduces the idea of a dominant term and teaches how to simplify the behavior of expressions for large arguments.

## Solution

For very large values of $n$, the terms with the highest powers of $n$ dominate the behavior of the expression. In the numerator, the dominant term is $4n^2$, and in the denominator, the dominant term is $2n^2$.

The lower-order terms $-3n$, $1$, $5n$, and $-7$ become negligible compared with $n^2$ as $n\to\infty$.

A clean way to see this is to divide both the numerator and denominator by $n^2$:

$$
\frac{4n^2-3n+1}{2n^2+5n-7}
=
\frac{4-\frac{3}{n}+\frac{1}{n^2}}{2+\frac{5}{n}-\frac{7}{n^2}}.
$$

As $n\to\infty$,

$$
\frac{1}{n}\to0,
\qquad
\frac{1}{n^2}\to0.
$$

Therefore,

$$
\lim_{n\to\infty}
\frac{4-\frac{3}{n}+\frac{1}{n^2}}
{2+\frac{5}{n}-\frac{7}{n^2}}
=
\frac{4-0+0}{2+0-0}
=
\frac{4}{2}
=
2.
$$

Hence,

$$
\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}=2.
$$

### Why the highest-degree terms determine the result

When $n$ is very large, powers of $n$ grow at different rates:

- $n^2$ is much larger than $n$.
- $n$ is much larger than a constant.
- Constants become insignificant compared with $n^2$.

Therefore, in a rational expression of this form, the ratio of the leading terms determines the limit:

$$
\frac{4n^2-3n+1}{2n^2+5n-7}
\sim
\frac{4n^2}{2n^2}
=
2.
$$

This is the key idea behind dominant terms: the highest-degree part controls the limit when the variable becomes very large.
