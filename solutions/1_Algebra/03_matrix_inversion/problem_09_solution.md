# Problem 9: Matrix Equation

## Question

Given

$$
A=
\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix},\qquad B=
\begin{pmatrix}
3 & 1 \\
2 & 4
\end{pmatrix}.
$$

Solve the equation $AX=B$ for $X$. Before calculating, decide on which side of the equation $A^{-1}$ must be used. Then check the result by computing $AX$.

---

## Solution

### 1. Deciding Which Side to Multiply by $A^{-1}$

We are given the matrix equation:

$$
AX = B
$$

Because matrix multiplication is non-commutative in general ($MN \neq NM$), the side on which we multiply by $A^{-1}$ is critical:

- If we multiply both sides on the **left** by $A^{-1}$:

$$
A^{-1}(AX) = A^{-1}B \implies (A^{-1}A)X = A^{-1}B \implies I X = A^{-1}B \implies X = A^{-1}B
$$

  This isolates $X$.

- If we multiplied both sides on the **right** by $A^{-1}$:

$$
(AX)A^{-1} = BA^{-1}
$$

  Because $X$ and $A^{-1}$ do not necessarily commute ($XA^{-1} \neq A^{-1}X$), the expression $AXA^{-1}$ does not cancel $A$ and does not isolate $X$.

**Decision:**
To cancel $A$ from the left side of $X$, we must multiply both sides on the **left** by $A^{-1}$:

$$
X = A^{-1}B
$$

---

### 2. Computing the Inverse Matrix $A^{-1}$

For matrix $A$:

$$
A =
\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix}
$$

The determinant is:

$$
\det A = (1)(1) - (2)(0) = 1
$$

Since $\det A = 1 \neq 0$, $A$ is invertible. Applying the $2 \times 2$ inverse formula:

$$
A^{-1} = \frac{1}{1}
\begin{pmatrix}
1 & -2 \\
0 & 1
\end{pmatrix}
= \begin{pmatrix}
1 & -2 \\
0 & 1
\end{pmatrix}
$$

Notice that $A$ is a unit shear matrix; its inverse is obtained simply by negating the shear parameter from $2$ to $-2$.

---

### 3. Computing the Solution Matrix $X = A^{-1}B$

Multiplying $A^{-1}$ on the left and $B$ on the right:

$$
X = A^{-1}B =
\begin{pmatrix}
1 & -2 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
3 & 1 \\
2 & 4
\end{pmatrix}
$$

Computing each entry by taking the dot product of rows of $A^{-1}$ with columns of $B$:
- Entry (1, 1): $(1)(3) + (-2)(2) = 3 - 4 = -1$
- Entry (1, 2): $(1)(1) + (-2)(4) = 1 - 8 = -7$
- Entry (2, 1): $(0)(3) + (1)(2) = 0 + 2 = 2$
- Entry (2, 2): $(0)(1) + (1)(4) = 0 + 4 = 4$

Combining the entries gives the solution matrix $X$:

$$
X =
\begin{pmatrix}
-1 & -7 \\
2 & 4
\end{pmatrix}
$$

---

### 4. Checking the Result by Computing $AX$

We verify the solution by computing $AX$ and checking whether it equals $B$:

$$
AX =
\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
-1 & -7 \\
2 & 4
\end{pmatrix}
$$

Evaluating each entry:
- Entry (1, 1): $(1)(-1) + (2)(2) = -1 + 4 = 3$
- Entry (1, 2): $(1)(-7) + (2)(4) = -7 + 8 = 1$
- Entry (2, 1): $(0)(-1) + (1)(2) = 0 + 2 = 2$
- Entry (2, 2): $(0)(-7) + (1)(4) = 0 + 4 = 4$

Combining the entries:

$$
AX =
\begin{pmatrix}
3 & 1 \\
2 & 4
\end{pmatrix}
= B
$$

The product matches matrix $B$ entry-by-entry, confirming that $X$ is the exact solution.

---

## Verification and Consistency Checks

### Check 1: Incorrect Order Calculation ($BA^{-1}$)

To see what happens if one multiplies on the wrong side, compute $BA^{-1}$:

$$
BA^{-1} =
\begin{pmatrix}
3 & 1 \\
2 & 4
\end{pmatrix}
\begin{pmatrix}
1 & -2 \\
0 & 1
\end{pmatrix}
$$

Evaluating entries:

$$
BA^{-1} =
\begin{pmatrix}
(3)(1) + (1)(0) & (3)(-2) + (1)(1) \\
(2)(1) + (4)(0) & (2)(-2) + (4)(1)
\end{pmatrix}
= \begin{pmatrix}
3 & -5 \\
2 & 0
\end{pmatrix}
$$

Now test $A(BA^{-1})$:

$$
A(BA^{-1}) =
\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
3 & -5 \\
2 & 0
\end{pmatrix}
= \begin{pmatrix}
3 + 4 & -5 + 0 \\
0 + 2 & 0 + 0
\end{pmatrix}
= \begin{pmatrix}
7 & -5 \\
2 & 0
\end{pmatrix}
\neq B
$$

This confirms that $BA^{-1}$ is not a solution to $AX = B$, highlighting the essential role of multiplication side.

### Check 2: Column-by-Column Vector Verification

Solving $AX = B$ is equivalent to solving two independent systems for the columns $x_1$ and $x_2$ of matrix $X$:

Evaluating column 1 ($x_1$):

$$
\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
-1 \\
2
\end{pmatrix}
= \begin{pmatrix}
-1 + 4 \\
2
\end{pmatrix}
= \begin{pmatrix}
3 \\
2
\end{pmatrix}
$$

Evaluating column 2 ($x_2$):

$$
\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
-7 \\
4
\end{pmatrix}
= \begin{pmatrix}
-7 + 8 \\
4
\end{pmatrix}
= \begin{pmatrix}
1 \\
4
\end{pmatrix}
$$

Both column equations produce the corresponding columns of $B$.

---

## Why This Exercise Matters

- **Non-Commutative Algebra Discipline:** Reinforces that division does not exist in matrix algebra; one must multiply by inverses while rigorously respecting left versus right positioning.
- **Equation Classification:** Distinguishes $AX = B$ (solution: $X = A^{-1}B$) from $XA = B$ (solution: $X = BA^{-1}$), establishing habits for more complex equations like $AXB = C \implies X = A^{-1}CB^{-1}$.
- **Multi-Vector Systems:** Illustrates that matrix equations are compact representations of multiple simultaneous vector systems sharing the same coefficient matrix.
