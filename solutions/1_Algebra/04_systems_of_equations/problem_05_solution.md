# Problem 5: Row Echelon Form and Number of Solutions

## Question

For the augmented matrix

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 3 \\
0 & 1 & 2 & \mid & 1 \\
0 & 0 & 0 & \mid & 0
\end{pmatrix}
$$

determine the number of solutions and write them in parametric form. Explain how you know how many variables may be chosen freely.

---

## Solution

### 1. Determining the Number of Solutions

Let the variables corresponding to columns 1, 2, and 3 be denoted by $x, y, z$ (or $x_1, x_2, x_3$).

1. **Check for Consistency:**
   The third row is:

$$
\begin{pmatrix}
0 & 0 & 0 & \mid & 0
\end{pmatrix}
$$

   This represents the equation $0x + 0y + 0z = 0$, which is trivially true for all values of $(x, y, z)$. There is no contradictory row of the form $(0 \; 0 \; 0 \mid c)$ with $c \neq 0$. Therefore, the system is **consistent**.

2. **Count the Pivots (Rank):**
   - In row 1, the leading entry (pivot) is at column 1 ($a_{11} = 1$).
   - In row 2, the leading entry (pivot) is at column 2 ($a_{22} = 1$).
   - Row 3 has no pivot.

   The rank of the coefficient matrix is $r = 2$, and the rank of the augmented matrix is also $r = 2$.

3. **Number of Solutions:**
   The total number of unknown variables is $n = 3$.
   Since the system is consistent and:

$$
r = 2 < 3 = n
$$

   the system has **infinitely many solutions**.

---

### 2. How Many Variables May Be Chosen Freely?

In any consistent linear system in row echelon form:

$$
\mathrm{Free\ Variables} = n - r = 3 - 2 = 1
$$

- **Basic (Pivot) Variables:** $x$ (column 1) and $y$ (column 2), because each corresponds to a pivot column. Their values are completely determined once the free variables are fixed.
- **Free Variable:** $z$ (column 3), because column 3 does not contain a pivot. It can be assigned any arbitrary real number.

---

### 3. Parametric Solution via Back-Substitution

Assign the free variable $z$ a parameter $t \in \mathbb{R}$:

$$
z = t
$$

#### Express $y$ in terms of $t$:

From row 2:

$$
y + 2z = 1 \implies y = 1 - 2z = 1 - 2t
$$

#### Express $x$ in terms of $t$:

From row 1:

$$
x + 2y - z = 3
$$

Substitute the expressions for $y$ and $z$:

$$
x + 2(1 - 2t) - t = 3
$$

$$
x + 2 - 4t - t = 3
$$

$$
x + 2 - 5t = 3 \implies x = 1 + 5t
$$

---

### 4. Vector Parametric Form

Collecting all variables into vector form:

$$
\begin{aligned}
\begin{pmatrix} x \\ y \\ z \end{pmatrix}
&=
\begin{pmatrix} 1+5t \\ 1-2t \\ t \end{pmatrix} \\[6pt]
&=
\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}
+t\begin{pmatrix} 5 \\ -2 \\ 1 \end{pmatrix},
\quad t\in\mathbb{R}
\end{aligned}
$$

The solution set forms a straight line in $\mathbb{R}^3$ passing through $(1, 1, 0)$ with direction vector $(5, -2, 1)^T$.

---

## Verification and Consistency Checks

### Check 1: Reduced Row Echelon Form (RREF)

We can also find the solution by carrying the matrix all the way to RREF using $R_1 \leftarrow R_1 - 2R_2$:

$$
R_1 - 2R_2 = (1 - 2(0), \; 2 - 2(1), \; -1 - 2(2) \mid 3 - 2(1)) = (1, 0, -5 \mid 1)
$$

The RREF is:

$$
\begin{pmatrix}
1 & 0 & -5 & \mid & 1 \\
0 & 1 & 2 & \mid & 1 \\
0 & 0 & 0 & \mid & 0
\end{pmatrix}
$$

From this form, the expressions for the basic variables in terms of the free variable $z$ can be read off instantly:

$$
x - 5z = 1 \implies x = 1 + 5z
$$

$$
y + 2z = 1 \implies y = 1 - 2z
$$

Setting $z = t$ reproduces $x = 1 + 5t$ and $y = 1 - 2t$ identically.

### Check 2: Testing Specific Parameter Values

1. **For $t = 0$:**
   The point is $(x, y, z) = (1, 1, 0)$.
   - Row 1: $1(1) + 2(1) - 1(0) = 1 + 2 = 3$ (matches).
   - Row 2: $0(1) + 1(1) + 2(0) = 1$ (matches).

2. **For $t = 1$:**
   The point is $(x, y, z) = (1 + 5, 1 - 2, 1) = (6, -1, 1)$.
   - Row 1: $1(6) + 2(-1) - 1(1) = 6 - 2 - 1 = 3$ (matches).
   - Row 2: $0(6) + 1(-1) + 2(1) = -1 + 2 = 1$ (matches).

Both sample points satisfy the original system, confirming the correctness of the solution.

---

## Why This Exercise Matters

1. **Reading Echelon Form Directly:** Once a matrix is in echelon form, the existence, uniqueness, or multiplicity of solutions can be determined by simple inspection of pivot positions.
2. **Dimension of the Solution Set:** The formula $\dim(V) = n - \mathrm{rank}(A)$ quantifies the degrees of freedom geometrically ($0$ for a unique point, $1$ for a line, $2$ for a plane).
3. **Decoupling Variables:** Identifying pivots clearly separates basic variables (which are solved for) from free variables (which parameterize the solution space).
