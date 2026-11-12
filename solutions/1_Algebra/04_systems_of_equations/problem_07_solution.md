# Problem 7: Choosing a Method Deliberately

## Question

Do not solve all of the following systems completely. For each situation, choose the method that best uses its structure and justify your choice:

1. one system with a triangular coefficient matrix

$$
\begin{cases}
2x-y=3, \\
4y=8;
\end{cases}
$$

2. three systems $Ax=b_i$ with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. one $3\times3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

For case 1, carry out the chosen method completely. For cases 2 and 3, describe the plan and indicate which part of the computation would be reusable or unnecessary. Do not judge a method by its name alone — refer to the number of right-hand sides and the structure of the matrix.

---

## Solution

### Case 1: Triangular Coefficient Matrix

$$
\begin{cases}
2x-y=3, \\
4y=8
\end{cases}
$$

#### Chosen Method: Direct Back-Substitution
- **Justification:** The coefficient matrix is already upper triangular:

$$
A =
\begin{pmatrix}
2 & -1 \\
0 & 4 \\
\end{pmatrix}
$$

  The forward elimination stage of Gaussian elimination has already been completed by the structure of the equations. Inverting the matrix or running elimination steps would perform needless extra operations. Back-substitution finds the solution immediately from the bottom up.

#### Complete Execution:

1. **Solve for $y$ from the bottom equation:**

$$
4y = 8 \implies y = \frac{8}{4} = 2
$$

2. **Substitute $y = 2$ into the top equation and solve for $x$:**

$$
2x - 2 = 3 \implies 2x = 5 \implies x = \frac{5}{2}
$$

The unique solution is:

$$
\begin{pmatrix}
x \\
y \\
\end{pmatrix}
= \begin{pmatrix}
\frac{5}{2} \\
2 \\
\end{pmatrix}
$$

#### Verification:
- First equation: $2\left(\frac{5}{2}\right) - 2 = 5 - 2 = 3 \quad \checkmark$
- Second equation: $4(2) = 8 \quad \checkmark$

---

### Case 2: Three Systems $Ax = b_i$ with Known Inverse $A^{-1}$

#### Chosen Method: Matrix-Vector Multiplication ($x_i = A^{-1} b_i$)
- **Justification:** Finding an inverse matrix is normally computationally expensive. However, here $A^{-1}$ is **already known**. Since $Ax = b \iff x = A^{-1}b$ for an invertible matrix, computing each solution requires only a single matrix-vector multiplication:

$$
x_1 = A^{-1} b_1, \qquad x_2 = A^{-1} b_2, \qquad x_3 = A^{-1} b_3
$$

- **Computational Plan:**
  1. Multiply matrix $A^{-1}$ by column vector $b_1$ to obtain $x_1$.
  2. Multiply matrix $A^{-1}$ by column vector $b_2$ to obtain $x_2$.
  3. Multiply matrix $A^{-1}$ by column vector $b_3$ to obtain $x_3$.

- **What is Reusable:**
  The precomputed inverse matrix $A^{-1}$ is used directly for all three systems. Its entries are computed once (or provided upfront) and never recalculated.

- **What is Unnecessary:**
  Running Gaussian elimination three separate times on $[A \mid b_1]$, $[A \mid b_2]$, and $[A \mid b_3]$ is completely unnecessary. Doing so would repeat the exact same row operations on $A$ three separate times.

---

### Case 3: One $3 \times 3$ System with Unknown Inverse and a Single Target Vector

#### Chosen Method: Gaussian Elimination with Back-Substitution
- **Justification:** We only need to solve for one specific right-hand side vector $b$.
  - Inverting a $3 \times 3$ matrix from scratch requires solving for 3 separate unit basis columns (row reducing $[A \mid I_3]$ of size $3 \times 6$), which requires approximately $\frac{8}{3}n^3$ arithmetic operations.
  - In contrast, performing Gaussian elimination on the single augmented matrix $[A \mid b]$ of size $3 \times 4$ requires only $\frac{2}{3}n^3$ operations — roughly **three times less computational work**.

- **Computational Plan:**
  1. Form the $3 \times 4$ augmented matrix $[A \mid b]$.
  2. Apply row operations to reduce $[A \mid b]$ to upper triangular (row echelon) form.
  3. Perform backward substitution from row 3 to row 1 to obtain the single solution vector $x$.

- **What is Reusable / Unnecessary:**
  - **Unnecessary:** Computing the full inverse matrix $A^{-1}$ is unnecessary overhead because we have no further systems sharing the matrix $A$.
  - **Efficiency:** Gaussian elimination directly targets the specific vector $b$ in a single pass without spending effort on unused columns.

---

## Comparison Summary

| Situation | Matrix Structure / Context | Optimal Method | Why Chosen |
| :--- | :--- | :--- | :--- |
| **Case 1** | Upper triangular coefficient matrix | Back-substitution | Forward elimination is already done; solve bottom-up directly. |
| **Case 2** | Multiple vectors $b_i$, $A^{-1}$ already known | Matrix-vector product $x_i = A^{-1} b_i$ | Reuses known $A^{-1}$ in three fast matrix-vector multiplications. |
| **Case 3** | Single vector $b$, $A^{-1}$ not known | Gaussian elimination on $[A \mid b]$ | Inverting $A$ requires $\approx 3\times$ more operations than solving for a single $b$. |

---

## Why This Exercise Matters

1. **Algorithmic Efficiency:** In linear algebra, mathematical equivalence ($x = A^{-1}b$ vs. elimination) does not mean computational equivalence. Choosing the method suited to the problem structure saves substantial time and prevents errors.
2. **Cost of Inversion:** Matrix inversion is rarely the most efficient path for solving a single linear system; it is primarily advantageous when the same matrix is applied to many different right-hand sides.
3. **Exploiting Structure:** Triangular systems, diagonal matrices, and previously decomposed matrices should always be solved with specialized, minimal steps.
