# Problem 7: Identity Matrix, Zero Matrix, and Powers

## Question

For

$$
A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

compute

$$
AI, \qquad IA, \qquad A + 0, \qquad A^2, \qquad A^3.
$$

Explain the roles of the matrices $I$ and $0$, and describe the pattern you observe in successive powers of $A$.

---

## Key Definitions — What Are $I$ and $0$?

For a $2 \times 2$ matrix, the standard identity and zero matrices are:

### The Identity Matrix $I$

$$
I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
$$

In matrix algebra, $I$ is the **multiplicative identity**. It acts like the number $1$ in ordinary multiplication: multiplying any compatible matrix by $I$ leaves the matrix unchanged.

### The Zero Matrix $0$

$$
0 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}
$$

In matrix algebra, $0$ is the **additive identity**. It acts like the number $0$ in ordinary addition: adding $0$ to any matrix of the same size leaves the matrix unchanged.

---

## Step 1 — Compute $AI$ and $IA$

### Computing $AI$

We multiply $A$ on the right by $I$:

$$
AI = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
$$

#### Entry (1, 1): row 1 of $A$ · column 1 of $I$

$$
2 \cdot 1 + 1 \cdot 0 = 2 + 0 = 2
$$

#### Entry (1, 2): row 1 of $A$ · column 2 of $I$

$$
2 \cdot 0 + 1 \cdot 1 = 0 + 1 = 1
$$

#### Entry (2, 1): row 2 of $A$ · column 1 of $I$

$$
0 \cdot 1 + 2 \cdot 0 = 0 + 0 = 0
$$

#### Entry (2, 2): row 2 of $A$ · column 2 of $I$

$$
0 \cdot 0 + 2 \cdot 1 = 0 + 2 = 2
$$

#### Result for $AI$

$$
AI = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
$$

---

### Computing $IA$

We multiply $A$ on the left by $I$:

$$
IA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

#### Entry (1, 1): row 1 of $I$ · column 1 of $A$

$$
1 \cdot 2 + 0 \cdot 0 = 2 + 0 = 2
$$

#### Entry (1, 2): row 1 of $I$ · column 2 of $A$

$$
1 \cdot 1 + 0 \cdot 2 = 1 + 0 = 1
$$

#### Entry (2, 1): row 2 of $I$ · column 1 of $A$

$$
0 \cdot 2 + 1 \cdot 0 = 0 + 0 = 0
$$

#### Entry (2, 2): row 2 of $I$ · column 2 of $A$

$$
0 \cdot 1 + 1 \cdot 2 = 0 + 2 = 2
$$

#### Result for $IA$

$$
IA = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
$$

Multiplying by $I$ from either side preserves $A$:

$$
AI = IA = A
$$

---

## Step 2 — Compute $A + 0$

Matrix addition is performed entry-by-entry:

$$
A + 0 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} + \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}
$$

Evaluating each entry:

$$
A + 0 = \begin{pmatrix} 2 + 0 & 1 + 0 \\ 0 + 0 & 2 + 0 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A
$$

Adding the zero matrix preserves $A$:

$$
A + 0 = 0 + A = A
$$

---

## Step 3 — Compute $A^2$

The square of a matrix is the matrix multiplied by itself: $A^2 = A \cdot A$.

$$
A^2 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

### Entry (1, 1): row 1 of $A$ · column 1 of $A$

$$
2 \cdot 2 + 1 \cdot 0 = 4 + 0 = 4
$$

### Entry (1, 2): row 1 of $A$ · column 2 of $A$

$$
2 \cdot 1 + 1 \cdot 2 = 2 + 2 = 4
$$

### Entry (2, 1): row 2 of $A$ · column 1 of $A$

$$
0 \cdot 2 + 2 \cdot 0 = 0 + 0 = 0
$$

### Entry (2, 2): row 2 of $A$ · column 2 of $A$

$$
0 \cdot 1 + 2 \cdot 2 = 0 + 4 = 4
$$

### Result for $A^2$

$$
A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}
$$

---

## Step 4 — Compute $A^3$

By definition of matrix powers, $A^3 = A^2 \cdot A$:

$$
A^3 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}
$$

### Entry (1, 1): row 1 of $A^2$ · column 1 of $A$

$$
4 \cdot 2 + 4 \cdot 0 = 8 + 0 = 8
$$

### Entry (1, 2): row 1 of $A^2$ · column 2 of $A$

$$
4 \cdot 1 + 4 \cdot 2 = 4 + 8 = 12
$$

### Entry (2, 1): row 2 of $A^2$ · column 1 of $A$

$$
0 \cdot 2 + 4 \cdot 0 = 0 + 0 = 0
$$

### Entry (2, 2): row 2 of $A^2$ · column 2 of $A$

$$
0 \cdot 1 + 4 \cdot 2 = 0 + 8 = 8
$$

### Result for $A^3$

$$
A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}
$$

---

## Step 5 — Explaining the Roles of $I$ and $0$

In matrix algebra, $I$ and $0$ serve as fundamental **neutral elements**:

- **Role of $I$ (Multiplicative Identity):**
  For any square matrix $A$, $AI = IA = A$. It preserves the matrix under multiplication, exactly like $1$ in real numbers ($a \cdot 1 = 1 \cdot a = a$).

- **Role of $0$ (Additive Identity):**
  For any matrix $A$, $A + 0 = 0 + A = A$. It preserves the matrix under addition, exactly like $0$ in real numbers ($a + 0 = 0 + a = a$).

- **Multiplication by $0$ (Annihilator):**
  Just like multiplying a number by zero gives zero, multiplying any matrix by the zero matrix yields the zero matrix: $A \cdot 0 = 0 \cdot A = 0$.

---

## Step 6 — Pattern in Successive Powers of $A$

Let us place the computed powers side by side:

$$
A^1 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}, \qquad
A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}, \qquad
A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}
$$

Let us analyze each position in the matrix:

1. **Bottom-left entry $(2, 1)$:**
   Always stays $0$. The matrix remains upper-triangular for all powers.

2. **Diagonal entries $(1, 1)$ and $(2, 2)$:**
   - $n = 1$: $2 = 2^1$
   - $n = 2$: $4 = 2^2$
   - $n = 3$: $8 = 2^3$
   
   For power $n$, the diagonal entries are $2^n$.

3. **Top-right entry $(1, 2)$:**
   - $n = 1$: $1 = 1 \cdot 2^0$
   - $n = 2$: $4 = 2 \cdot 2^1$
   - $n = 3$: $12 = 3 \cdot 2^2$

   For power $n$, the top-right entry is $n \cdot 2^{n-1}$.

### General Formula

For any positive integer $n \ge 1$:

$$
A^n = \begin{pmatrix} 2^n & n \cdot 2^{n-1} \\ 0 & 2^n \end{pmatrix}
$$

---

## Deeper Insight: Algebraic Reason for the Pattern

We can split $A$ into two parts:

$$
A = 2I + N
$$

where:

$$
2I = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}, \qquad
N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$

Notice that $N$ is **nilpotent of order 2**:

$$
N^2 = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = 0
$$

Since $2I$ commutes with any matrix, $(2I)N = N(2I)$. We can therefore expand $(2I + N)^n$ using the **Binomial Theorem**:

$$
A^n = (2I + N)^n = (2I)^n + n(2I)^{n-1}N + \binom{n}{2}(2I)^{n-2}N^2 + \dots
$$

Since $N^2 = 0$, every term with $N^k$ for $k \ge 2$ is zero! Only the first two terms remain:

$$
A^n = 2^n I + n \cdot 2^{n-1} N
$$

Writing this in matrix form:

$$
A^n = 2^n \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + n \cdot 2^{n-1} \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2^n & n \cdot 2^{n-1} \\ 0 & 2^n \end{pmatrix}
$$

This explains why the formula holds for every positive integer $n$.

---

## Verification and Consistency Checks

### Checking $n = 4$

Using the formula for $n = 4$:

$$
A^4 = \begin{pmatrix} 2^4 & 4 \cdot 2^3 \\ 0 & 2^4 \end{pmatrix} = \begin{pmatrix} 16 & 32 \\ 0 & 16 \end{pmatrix}
$$

Direct computation via $A^2 \cdot A^2$:

$$
A^2 \cdot A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} = \begin{pmatrix} 16 + 0 & 16 + 16 \\ 0 + 0 & 0 + 16 \end{pmatrix} = \begin{pmatrix} 16 & 32 \\ 0 & 16 \end{pmatrix}
$$

Both results match. ✅

### Checking Determinants

Using the property $\det(A^n) = (\det A)^n$:

- $\det(A) = 2 \cdot 2 - 1 \cdot 0 = 4$
- $\det(A^2) = 4 \cdot 4 - 4 \cdot 0 = 16 = 4^2$ ✅
- $\det(A^3) = 8 \cdot 8 - 12 \cdot 0 = 64 = 4^3$ ✅

---

## Why This Exercise Matters

- **Neutral elements organize matrix algebra:** Seeing $I$ and $0$ explicitly establishes the baseline rules for matrix arithmetic.
- **Matrix powers are not entrywise powers:** Raising a matrix to a power does not simply raise each individual entry to that power (the top-right entry becomes $n \cdot 2^{n-1}$, not $1^n = 1$).
- **Introduction to Jordan blocks:** The matrix $A$ is a prototypical $2 \times 2$ Jordan block. The formula derived here is the exact tool used in linear differential equations and matrix exponential computations.
