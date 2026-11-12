# Problem 10: Inverse of a Diagonal Matrix

## Question

Given

$$
D=
\begin{pmatrix}
2 & 0 & 0 \\
0 & -3 & 0 \\
0 & 0 & 5
\end{pmatrix},\qquad E=
\begin{pmatrix}
2 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 5
\end{pmatrix}.
$$

Without using Gauss–Jordan elimination, decide which matrix is invertible. For the invertible matrix, give the inverse and check the result by multiplication.

---

## Solution

### 1. Invertibility Criterion for Diagonal Matrices

A diagonal matrix

$$
M =
\begin{pmatrix}
d_1 & 0 & \cdots & 0 \\
0 & d_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & d_n
\end{pmatrix}
$$

has determinant equal to the product of its main diagonal entries:

$$
\det M = \prod_{i=1}^n d_i = d_1 \cdot d_2 \cdots d_n
$$

A matrix is invertible if and only if its determinant is non-zero:

$$
\det M \neq 0 \iff \prod_{i=1}^n d_i \neq 0
$$

This condition is satisfied if and only if $d_i \neq 0$ for all $i \in \{1, 2, \dots, n\}$.

Therefore, a diagonal matrix is **invertible if and only if all of its diagonal entries are non-zero**.
If even a single diagonal entry is zero, the determinant is zero and the matrix is singular (not invertible).

---

### 2. Deciding Invertibility for $D$ and $E$

#### Analysis of Matrix $D$

The diagonal entries of $D$ are:

$$
d_{11} = 2, \qquad d_{22} = -3, \qquad d_{33} = 5
$$

- None of the diagonal entries is zero: $2 \neq 0$, $-3 \neq 0$, and $5 \neq 0$.
- The determinant of $D$ is:

$$
\det D = (2)(-3)(5) = -30 \neq 0
$$

Therefore, matrix $D$ is **invertible**.

#### Analysis of Matrix $E$

The diagonal entries of $E$ are:

$$
e_{11} = 2, \qquad e_{22} = 0, \qquad e_{33} = 5
$$

- The second diagonal entry is zero: $e_{22} = 0$.
- Consequently, the entire second row of $E$ consists of zeros: $r_2 = (0, 0, 0)$.
- The determinant of $E$ is:

$$
\det E = (2)(0)(5) = 0
$$

Since $\det E = 0$ (and $E$ contains an entirely zero row, meaning $\mathrm{rank}(E) \le 2 < 3$), matrix $E$ is **not invertible** (singular).

---

### 3. Finding the Inverse of Matrix $D$

For any diagonal matrix with non-zero diagonal entries, its inverse is also diagonal, and each diagonal entry is simply the reciprocal of the corresponding entry of $D$:

$$
(D^{-1})_{ii} = \frac{1}{d_{ii}}
$$

Taking the reciprocal of each diagonal entry:
- First diagonal entry: $\frac{1}{2}$
- Second diagonal entry: $\frac{1}{-3} = -\frac{1}{3}$
- Third diagonal entry: $\frac{1}{5}$

Therefore, the inverse matrix is:

$$
D^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 & 0 \\
0 & -\frac{1}{3} & 0 \\
0 & 0 & \frac{1}{5}
\end{pmatrix}
$$

---

### 4. Check by Multiplication

We verify the inverse by calculating the product $D D^{-1}$:

$$
D D^{-1} =
\begin{pmatrix}
2 & 0 & 0 \\
0 & -3 & 0 \\
0 & 0 & 5
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & 0 & 0 \\
0 & -\frac{1}{3} & 0 \\
0 & 0 & \frac{1}{5}
\end{pmatrix}
$$

Because both matrices are diagonal, multiplying them corresponds to multiplying their corresponding diagonal entries component-wise, while all off-diagonal entries remain zero:
- Entry (1, 1): $(2)\left(\frac{1}{2}\right) = 1$
- Entry (2, 2): $(-3)\left(-\frac{1}{3}\right) = 1$
- Entry (3, 3): $(5)\left(\frac{1}{5}\right) = 1$
- All off-diagonal entries: $0$

Combining the entries gives:

$$
D D^{-1} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
= I_3
$$

Similarly, checking left multiplication:

$$
D^{-1} D =
\begin{pmatrix}
\frac{1}{2} & 0 & 0 \\
0 & -\frac{1}{3} & 0 \\
0 & 0 & \frac{1}{5}
\end{pmatrix}
\begin{pmatrix}
2 & 0 & 0 \\
0 & -3 & 0 \\
0 & 0 & 5
\end{pmatrix}
= \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
= I_3
$$

The calculation confirms that $D^{-1}$ is the exact inverse of $D$.

---

## Verification and Consistency Checks

### Check 1: Non-Trivial Kernel for $E$

Since $E$ has a zero in row 2, consider the standard basis vector $e_2$:

$$
e_2 =
\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}
$$

Evaluating $E e_2$:

$$
E e_2 =
\begin{pmatrix}
2 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 5
\end{pmatrix}
\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}
= \begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$

Since $e_2 \neq 0$ is in the null space, $\ker E \neq \{0\}$, proving independently that $E$ is not injective and cannot have an inverse.

### Check 2: Determinant of the Inverse for $D$

Using the determinant property $\det(D^{-1}) = \frac{1}{\det D}$:

$$
\det(D^{-1}) = \left(\frac{1}{2}\right)\left(-\frac{1}{3}\right)\left(\frac{1}{5}\right) = -\frac{1}{30}
$$

Since $\det D = -30$, we have:

$$
\det(D^{-1}) = \frac{1}{-30} = \frac{1}{\det D}
$$

The reciprocal relationship holds exactly.

---

## Why This Exercise Matters

- **Exploiting Matrix Structure:** Teaches students to recognize special matrix structures (such as diagonal, triangular, and orthogonal forms) to compute determinants and inverses by inspection in $\mathcal{O}(n)$ time rather than running expensive $\mathcal{O}(n^3)$ elimination routines.
- **Spectral Decomposition (Eigendecomposition):** In the diagonalization $A = P D P^{-1}$, the inverse of $A$ is computed as $A^{-1} = P D^{-1} P^{-1}$. Computing $D^{-1}$ by taking diagonal reciprocals is the central operational step in matrix inversion via eigendecomposition.
- **Rank and Zero Rows:** Reinforces that a zero row immediately flags rank deficiency, eliminating the need for further computation.
