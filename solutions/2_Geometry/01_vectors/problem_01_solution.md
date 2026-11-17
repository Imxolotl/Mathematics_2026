# Problem 1: Vector Operations and Their Meaning

## Question

For $u=(2,-1,3)$ and $v=(-1,4,2)$ compute

$$
u+v,\qquad u-v,\qquad 3u-2v.
$$

Then verify that $(u+v)-v=u$, and explain geometrically what adding two vectors means.

---

## Solution

### 1. Component-Wise Vector Operations

In $\mathbb{R}^3$, vector addition, subtraction, and scalar multiplication are performed coordinate by coordinate. For $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ and scalars $\alpha, \beta \in \mathbb{R}$:

$$
u + v = (u_1 + v_1, \; u_2 + v_2, \; u_3 + v_3)
$$

$$
u - v = (u_1 - v_1, \; u_2 - v_2, \; u_3 - v_3)
$$

$$
\alpha u + \beta v = (\alpha u_1 + \beta v_1, \; \alpha u_2 + \beta v_2, \; \alpha u_3 + \beta v_3)
$$

---

### 2. Computation of $u + v$

Substituting $u = (2, -1, 3)$ and $v = (-1, 4, 2)$:

$$
\begin{aligned}
u + v &= (2, -1, 3) + (-1, 4, 2) \\
      &= (2 + (-1), \; -1 + 4, \; 3 + 2) \\
      &= (1, 3, 5)
\end{aligned}
$$

Also written in column vector notation:

$$
u + v =
\begin{pmatrix}
2 \\
-1 \\
3 \\
\end{pmatrix}
+
\begin{pmatrix}
-1 \\
4 \\
2 \\
\end{pmatrix}
= \begin{pmatrix}
1 \\
3 \\
5 \\
\end{pmatrix}
$$

---

### 3. Computation of $u - v$

Subtracting the corresponding coordinates of $v$ from $u$:

$$
\begin{aligned}
u - v &= (2, -1, 3) - (-1, 4, 2) \\
      &= (2 - (-1), \; -1 - 4, \; 3 - 2) \\
      &= (2 + 1, \; -5, \; 1) \\
      &= (3, -5, 1)
\end{aligned}
$$

---

### 4. Computation of $3u - 2v$

First, we compute the scalar multiples $3u$ and $2v$ separately:

$$
3u = 3(2, -1, 3) = (3 \cdot 2, \; 3 \cdot (-1), \; 3 \cdot 3) = (6, -3, 9)
$$

$$
2v = 2(-1, 4, 2) = (2 \cdot (-1), \; 2 \cdot 4, \; 2 \cdot 2) = (-2, 8, 4)
$$

Next, we subtract $2v$ from $3u$:

$$
\begin{aligned}
3u - 2v &= (6, -3, 9) - (-2, 8, 4) \\
        &= (6 - (-2), \; -3 - 8, \; 9 - 4) \\
        &= (6 + 2, \; -11, \; 5) \\
        &= (8, -11, 5)
\end{aligned}
$$

---

### 5. Verification that $(u + v) - v = u$

Using the previously computed sum $u + v = (1, 3, 5)$ and $v = (-1, 4, 2)$:

$$
\begin{aligned}
(u + v) - v &= (1, 3, 5) - (-1, 4, 2) \\
            &= (1 - (-1), \; 3 - 4, \; 5 - 2) \\
            &= (2, -1, 3) \\
            &= u
\end{aligned}
$$

Algebraically, this follows from the associativity of vector addition and the additive inverse property:

$$
(u + v) - v = u + (v - v) = u + 0 = u
$$

---

### 6. Geometric Meaning of Vector Addition

Adding two vectors $u$ and $v$ in $\mathbb{R}^3$ has two equivalent geometric interpretations:

#### 1. Tip-to-Tail (Triangle) Rule — Successive Displacements
- Interpret a vector as a directed displacement in space.
- Starting at an initial point $P$, move along vector $u$ to reach an intermediate point $Q$.
- From point $Q$ (the head of $u$), place the tail of vector $v$ and move along $v$ to reach the final point $R$.
- The sum $u + v$ is the single net displacement vector pointing directly from the starting point $P$ to the final point $R$.
- Consequently, $(u + v) - v = u$ means that if you apply displacement $u$, then apply displacement $v$, and then reverse displacement $v$ (moving along $-v$), you return to the endpoint of $u$ alone.

#### 2. Parallelogram Rule — Combined Action from a Common Origin
- Place the tails of both $u$ and $v$ at the same origin $O$.
- When $u$ and $v$ are not collinear, they form two adjacent sides of a parallelogram in $\mathbb{R}^3$.
- The sum $u + v$ is the directed diagonal of this parallelogram starting at $O$, while the difference $u - v$ is the other diagonal pointing from the head of $v$ to the head of $u$.

---

## Verification and Consistency Checks

### Check 1: Identity $(u + v) + (u - v) = 2u$

Adding our computed results for $u + v = (1, 3, 5)$ and $u - v = (3, -5, 1)$:

$$
(u + v) + (u - v) = (1 + 3, \; 3 + (-5), \; 5 + 1) = (4, -2, 6) = 2(2, -1, 3) = 2u
$$

### Check 2: Decomposition of $3u - 2v$ as $u + 2(u - v)$

Notice that $3u - 2v = u + 2(u - v)$. Using $u = (2, -1, 3)$ and $u - v = (3, -5, 1)$:

$$
u + 2(u - v) = (2, -1, 3) + 2(3, -5, 1) = (2 + 6, \; -1 - 10, \; 3 + 2) = (8, -11, 5)
$$

This matches our direct calculation of $3u - 2v = (8, -11, 5)$.

---

## Why This Exercise Matters

- **Coordinate Independence:** Component-wise arithmetic reduces three-dimensional geometric displacements to three independent scalar calculations along the coordinate axes.
- **Reversibility of Vector Addition:** The identity $(u + v) - v = u$ demonstrates that vector subtraction is the exact inverse operation of vector addition.
- **Linear Combinations:** Expressions of the form $3u - 2v$ are linear combinations, which form the basis for spanning sets, lines, planes, and subspaces.
