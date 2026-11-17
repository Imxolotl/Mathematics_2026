# Problem 9: Cross Product as a Perpendicular Direction

## Question

For $u=(1,2,0)$ and $v=(0,1,3)$ compute $u\times v$. Use dot products to check perpendicularity to both vectors, compute $v\times u$, and compare the results.

---

## Solution

### 1. Formula for the Cross Product in $\mathbb{R}^3$

For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, their cross product (vector product) is defined by the determinant expansion:

$$
u \times v = (u_2 v_3 - u_3 v_2, \; u_3 v_1 - u_1 v_3, \; u_1 v_2 - u_2 v_1)
$$

Equivalently, each component is a $2 \times 2$ minor determinant (with a minus sign on the middle component):

$$
(u \times v)_1 = \det
\begin{pmatrix}
u_2 & u_3 \\
v_2 & v_3 \\
\end{pmatrix},
\qquad
(u \times v)_2 = -\det
\begin{pmatrix}
u_1 & u_3 \\
v_1 & v_3 \\
\end{pmatrix},
\qquad
(u \times v)_3 = \det
\begin{pmatrix}
u_1 & u_2 \\
v_1 & v_2 \\
\end{pmatrix}
$$

---

### 2. Computation of $u \times v$

Given $u = (1, 2, 0)$ and $v = (0, 1, 3)$, we compute each component:

- **First component ($x$-coordinate):**

$$
u_2 v_3 - u_3 v_2 = (2)(3) - (0)(1) = 6 - 0 = 6
$$

- **Second component ($y$-coordinate):**

$$
u_3 v_1 - u_1 v_3 = (0)(0) - (1)(3) = 0 - 3 = -3
$$

- **Third component ($z$-coordinate):**

$$
u_1 v_2 - u_2 v_1 = (1)(1) - (2)(0) = 1 - 0 = 1
$$

Combining the three components:

$$
u \times v = (6, -3, 1)
$$

---

### 3. Checking Perpendicularity to Both $u$ and $v$

A vector is perpendicular to $u$ and $v$ if and only if its dot product with each of them is zero.

#### Check 1: Orthogonality to $u = (1, 2, 0)$

$$
\begin{aligned}
(u \times v) \cdot u &= (6, -3, 1) \cdot (1, 2, 0) \\
                     &= (6)(1) + (-3)(2) + (1)(0) \\
                     &= 6 - 6 + 0 \\
                     &= 0
\end{aligned}
$$

Since $(u \times v) \cdot u = 0$, we have $(u \times v) \perp u$.

#### Check 2: Orthogonality to $v = (0, 1, 3)$

$$
\begin{aligned}
(u \times v) \cdot v &= (6, -3, 1) \cdot (0, 1, 3) \\
                     &= (6)(0) + (-3)(1) + (1)(3) \\
                     &= 0 - 3 + 3 \\
                     &= 0
\end{aligned}
$$

Since $(u \times v) \cdot v = 0$, we have $(u \times v) \perp v$.

Thus, $u \times v = (6, -3, 1)$ is simultaneously perpendicular to both $u$ and $v$, meaning it is a **normal vector** to the plane spanned by $u$ and $v$.

---

### 4. Computation of $v \times u$

Now we reverse the order of the factors, taking $v = (0, 1, 3)$ first and $u = (1, 2, 0)$ second:

- **First component:**

$$
v_2 u_3 - v_3 u_2 = (1)(0) - (3)(2) = 0 - 6 = -6
$$

- **Second component:**

$$
v_3 u_1 - v_1 u_3 = (3)(1) - (0)(0) = 3 - 0 = 3
$$

- **Third component:**

$$
v_1 u_2 - v_2 u_1 = (0)(2) - (1)(1) = 0 - 1 = -1
$$

Combining the three components:

$$
v \times u = (-6, 3, -1)
$$

---

### 5. Comparison of $u \times v$ and $v \times u$

Comparing the two vectors:

$$
u \times v = (6, -3, 1), \qquad v \times u = (-6, 3, -1) = -(u \times v)
$$

1. **Anticommutativity:**
   The cross product is **anticommutative**: swapping the order of the arguments negates every component of the resulting vector ($v \times u = -(u \times v)$). Algebraically, this happens because swapping $u$ and $v$ interchanges two rows in the defining determinant, which multiplies the determinant by $-1$.

2. **What Remains the Same:**
   - **Perpendicularity (Line of Action):** Both $u \times v$ and $v \times u$ lie along the same line perpendicular to the plane spanned by $u$ and $v$.
   - **Length (Magnitude):** Both vectors have the exact same Euclidean length:

$$
\|u \times v\| = \|v \times u\| = \sqrt{6^2 + (-3)^2 + 1^2} = \sqrt{36 + 9 + 1} = \sqrt{46}
$$

3. **What Changes (Orientation / Right-Hand Rule):**
   The two vectors point in **opposite orientations** along the normal line. By the right-hand rule, curling the fingers of the right hand from $u$ toward $v$ points the thumb in the direction of $u \times v = (6, -3, 1)$, whereas curling from $v$ toward $u$ points the thumb in the opposite direction $v \times u = (-6, 3, -1)$.

---

## Verification and Consistency Checks

### Check: Lagrange's Identity ($\|u \times v\|^2 = \|u\|^2 \|v\|^2 - (u \cdot v)^2$)

We can independently verify the magnitude of $u \times v = (6, -3, 1)$ using only norms and the dot product:
- $\|u\|^2 = 1^2 + 2^2 + 0^2 = 5$
- $\|v\|^2 = 0^2 + 1^2 + 3^2 = 10$
- $u \cdot v = (1)(0) + (2)(1) + (0)(3) = 2$

By Lagrange's identity:

$$
\|u\|^2 \|v\|^2 - (u \cdot v)^2 = (5)(10) - 2^2 = 50 - 4 = 46
$$

Meanwhile, from our computed cross product $u \times v = (6, -3, 1)$:

$$
\|u \times v\|^2 = 6^2 + (-3)^2 + 1^2 = 36 + 9 + 1 = 46
$$

The two independent calculations match ($46 = 46$).

---

## Why This Exercise Matters

- **Constructing Normal Vectors:** In three-dimensional geometry, whenever you need a direction perpendicular to two known vectors (for example, to write the equation of a plane or compute surface normals in computer graphics), the cross product $u \times v$ constructs it directly.
- **Built-in Self-Check:** Checking $(u \times v) \cdot u = 0$ and $(u \times v) \cdot v = 0$ takes only a few seconds and immediately catches any sign or arithmetic error made while computing a cross product.
