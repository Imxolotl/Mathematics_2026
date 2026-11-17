# Problem 8: Linear Combination and Checking the Result

## Question

Check whether $w=(5,1)$ can be written as

$$
w=au+bv,
$$

where $u=(1,1)$ and $v=(2,-1)$. If so, find $a,b$, reconstruct $w$ from them, and explain the geometric meaning of the existence of such coefficients.

---

## Solution

### 1. Setting Up the System of Linear Equations

Substituting $u = (1, 1)$, $v = (2, -1)$, and $w = (5, 1)$ into the vector equation $au + bv = w$:

$$
a(1, 1) + b(2, -1) = (5, 1)
$$

Performing the scalar multiplications and vector addition on the left-hand side:

$$
(a, a) + (2b, -b) = (5, 1)
$$

$$
(a + 2b, \; a - b) = (5, 1)
$$

Equating the first and second coordinates gives a system of two linear equations in the unknowns $a$ and $b$:

$$
\begin{cases}
a + 2b = 5, \\
a - b = 1.
\end{cases}
$$

In matrix form:

$$
\begin{pmatrix}
1 & 2 \\
1 & -1 \\
\end{pmatrix}
\begin{pmatrix}
a \\
b \\
\end{pmatrix}
= \begin{pmatrix}
5 \\
1 \\
\end{pmatrix}
$$

---

### 2. Solving for the Coefficients $a$ and $b$

#### Step 1: Eliminate $a$

Subtract the second equation from the first equation:

$$
(a + 2b) - (a - b) = 5 - 1
$$

$$
3b = 4 \implies b = \frac{4}{3}
$$

#### Step 2: Back-substitute to find $a$

From the second equation $a - b = 1$:

$$
a = 1 + b = 1 + \frac{4}{3} = \frac{3}{3} + \frac{4}{3} = \frac{7}{3}
$$

Therefore, $w$ **can** be written as a linear combination of $u$ and $v$, with the unique coefficients:

$$
a = \frac{7}{3}, \qquad b = \frac{4}{3}
$$

---

### 3. Reconstructing $w$ from $a$ and $b$

We substitute $a = \frac{7}{3}$ and $b = \frac{4}{3}$ back into the linear combination $au + bv$:

$$
\begin{aligned}
au + bv &= \frac{7}{3}(1, 1) + \frac{4}{3}(2, -1) \\
        &= \left( \frac{7}{3}, \; \frac{7}{3} \right) + \left( \frac{8}{3}, \; -\frac{4}{3} \right) \\
        &= \left( \frac{7 + 8}{3}, \; \frac{7 - 4}{3} \right) \\
        &= \left( \frac{15}{3}, \; \frac{3}{3} \right) \\
        &= (5, 1) \\
        &= w
\end{aligned}
$$

The reconstruction reproduces $w = (5, 1)$ identically.

---

### 4. Geometric Meaning of the Existence of the Coefficients

1. **Two Non-Parallel Directions Span the Plane $\mathbb{R}^2$:**
   The vectors $u = (1, 1)$ (slope $1$) and $v = (2, -1)$ (slope $-\frac{1}{2}$) point in two non-parallel directions in $\mathbb{R}^2$. Because they are not collinear, they are linearly independent and form a **basis** for $\mathbb{R}^2$. Consequently, *every* vector $w \in \mathbb{R}^2$ can be reached as a unique linear combination $au + bv$.

2. **Parallelogram Construction Along Oblique Axes:**
   Instead of moving $5$ units horizontally along $(1, 0)$ and $1$ unit vertically along $(0, 1)$, we decompose the journey from the origin $(0, 0)$ to $(5, 1)$ along the directions of $u$ and $v$:
   - First, travel $\frac{7}{3}$ units of $u$ from $(0, 0)$ to the point $\frac{7}{3}u = \left(\frac{7}{3}, \frac{7}{3}\right)$.
   - Next, from $\left(\frac{7}{3}, \frac{7}{3}\right)$, travel $\frac{4}{3}$ units of $v$, which adds the displacement $\frac{4}{3}v = \left(\frac{8}{3}, -\frac{4}{3}\right)$ and lands precisely on $w = (5, 1)$.
   - The vectors $\frac{7}{3}u$ and $\frac{4}{3}v$ form the adjacent sides of a parallelogram whose main diagonal is $w = (5, 1)$.

3. **Coordinates in the Basis $\{u, v\}$:**
   The pair $(a, b) = \left(\frac{7}{3}, \frac{4}{3}\right)$ represents the coordinates of $w$ relative to the basis $\{u, v\}$.

---

## Verification and Consistency Checks

### Check: Determinant of the Basis Matrix (Cramer's Rule)

For the matrix whose columns are $u$ and $v$:

$$
A =
\begin{pmatrix}
1 & 2 \\
1 & -1 \\
\end{pmatrix}
$$

Its determinant is:

$$
\det A = (1)(-1) - (2)(1) = -1 - 2 = -3 \neq 0
$$

Since $\det A = -3 \neq 0$, the matrix $A$ is invertible, so the system is guaranteed to have a unique solution for any $w \in \mathbb{R}^2$. Multiplying by $A^{-1}$:

$$
A^{-1} = -\frac{1}{3}
\begin{pmatrix}
-1 & -2 \\
-1 & 1 \\
\end{pmatrix}
$$

$$
\begin{pmatrix}
a \\
b \\
\end{pmatrix}
= -\frac{1}{3}
\begin{pmatrix}
-1 & -2 \\
-1 & 1 \\
\end{pmatrix}
\begin{pmatrix}
5 \\
1 \\
\end{pmatrix}
= -\frac{1}{3}
\begin{pmatrix}
-7 \\
-4 \\
\end{pmatrix}
= \begin{pmatrix}
\frac{7}{3} \\
\frac{4}{3} \\
\end{pmatrix}
$$

Both values match our elimination result.

---

## Why This Exercise Matters

- **Bridging Geometry and Linear Systems:** Asking whether a vector $w$ is a linear combination of $u$ and $v$ is algebraically identical to asking whether a system of linear equations is consistent.
- **Change of Basis Intuition:** Standard coordinates $(5, 1)$ simply mean $5(1, 0) + 1(0, 1)$. Replacing the standard axes with $\{u, v\}$ changes the coordinates of the same geometric vector to $\left(\frac{7}{3}, \frac{4}{3}\right)$.
