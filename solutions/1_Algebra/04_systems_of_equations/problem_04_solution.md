# Problem 4: Infinitely Many Solutions

## Question

Solve

$$
\begin{cases}
x+y+z=2, \\
2x+2y+2z=4, \\
x-y+z=0.
\end{cases}
$$

Give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point really satisfies the system.

---

## Solution

### 1. Set Up the Augmented Matrix

We write the system as an augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
2 & 2 & 2 & \mid & 4 \\
1 & -1 & 1 & \mid & 0
\end{pmatrix}
$$

---

### 2. Forward Elimination

#### Step 1: Eliminate $x$ from rows 2 and 3

Using row 1 as the pivot row:

- $R_2 \leftarrow R_2 - 2R_1$:

$$
(2 - 2(1), \; 2 - 2(1), \; 2 - 2(1) \mid 4 - 2(2)) = (0, 0, 0 \mid 0)
$$

- $R_3 \leftarrow R_3 - R_1$:

$$
(1 - 1(1), \; -1 - 1(1), \; 1 - 1(1) \mid 0 - 1(2)) = (0, -2, 0 \mid -2)
$$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
0 & 0 & 0 & \mid & 0 \\
0 & -2 & 0 & \mid & -2
\end{pmatrix}
$$

#### Step 2: Reorder rows and scale

Move the zero row to the bottom ($R_2 \leftrightarrow R_3$):

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
0 & -2 & 0 & \mid & -2 \\
0 & 0 & 0 & \mid & 0
\end{pmatrix}
$$

Scale row 2 by dividing by $-2$ ($R_2 \leftarrow -\frac{1}{2}R_2$):

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
0 & 1 & 0 & \mid & 1 \\
0 & 0 & 0 & \mid & 0
\end{pmatrix}
$$

#### Step 3: Back-elimination to Reduced Row Echelon Form (RREF)

Eliminate the entry above the second pivot using $R_1 \leftarrow R_1 - R_2$:

$$
(1 - 0, \; 1 - 1, \; 1 - 0 \mid 2 - 1) = (1, 0, 1 \mid 1)
$$

The reduced row echelon form (RREF) is:

$$
\begin{pmatrix}
1 & 0 & 1 & \mid & 1 \\
0 & 1 & 0 & \mid & 1 \\
0 & 0 & 0 & \mid & 0
\end{pmatrix}
$$

---

### 3. Identification of Pivot and Free Variables

Looking at the leading entries (pivots):
- **Column 1 ($x$):** contains a pivot in row 1 $\implies x$ is a **basic (pivot) variable**.
- **Column 2 ($y$):** contains a pivot in row 2 $\implies y$ is a **basic (pivot) variable**.
- **Column 3 ($z$):** contains no pivot $\implies z$ is a **free variable**.

Because there is at least one free variable and no contradictory row $(0 \; 0 \; 0 \mid c)$ with $c \neq 0$, the system has **infinitely many solutions**.

---

### 4. Expressing the Solution in Parametric Form

Let the free variable $z$ be parameterized by a real scalar $t \in \mathbb{R}$:

$$
z = t
$$

From row 2:

$$
y = 1
$$

From row 1:

$$
x + z = 1 \implies x = 1 - z = 1 - t
$$

Writing the full solution in vector form:

$$
\begin{aligned}
\begin{pmatrix} x \\ y \\ z \end{pmatrix}
&=
\begin{pmatrix} 1-t \\ 1 \\ t \end{pmatrix} \\[6pt]
&=
\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}
+t\begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix},
\quad t\in\mathbb{R}
\end{aligned}
$$

Geometrically, this solution set represents a straight line in three-dimensional space $\mathbb{R}^3$ passing through the point $(1, 1, 0)$ with direction vector $(-1, 0, 1)^T$.

---

## Verification and Consistency Checks

### Check for Parameter Value $t = 0$

Setting $t = 0$ gives the specific point:

$$
(x, y, z) = (1 - 0, \; 1, \; 0) = (1, 1, 0)
$$

Substitute $(x, y, z) = (1, 1, 0)$ into the original equations:

1. **Equation 1:**

$$
x + y + z = 1 + 1 + 0 = 2 \quad \checkmark
$$

2. **Equation 2:**

$$
2x + 2y + 2z = 2(1) + 2(1) + 2(0) = 2 + 2 + 0 = 4 \quad \checkmark
$$

3. **Equation 3:**

$$
x - y + z = 1 - 1 + 0 = 0 \quad \checkmark
$$

All three original equations are satisfied.

### Check for Parameter Value $t = 2$

Setting $t = 2$ gives:

$$
(x, y, z) = (1 - 2, \; 1, \; 2) = (-1, 1, 2)
$$

1. **Equation 1:**

$$
(-1) + 1 + 2 = 2 \quad \checkmark
$$

2. **Equation 2:**

$$
2(-1) + 2(1) + 2(2) = -2 + 2 + 4 = 4 \quad \checkmark
$$

3. **Equation 3:**

$$
(-1) - 1 + 2 = 0 \quad \checkmark
$$

All three equations are satisfied again, confirming the validity of the general parametric solution.

---

## Why This Exercise Matters

1. **Redundant Equations:** The second equation $2x + 2y + 2z = 4$ was merely a multiple of the first equation (twice Equation 1), contributing no new information and turning into the row of zeros $(0 \; 0 \; 0 \mid 0)$.
2. **Degrees of Freedom:** The number of free variables equals the total number of unknowns minus the rank of the coefficient matrix: $n - \mathrm{rank}(A) = 3 - 2 = 1$. One degree of freedom corresponds to a 1-dimensional solution space (a line).
3. **Parametric Description:** When a system has infinitely many solutions, the solution cannot be written as a single point; rather, it is described systematically in terms of free parameters.
