# Problem 10: Columns of a Matrix Product

## Question

Given

$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \qquad
B = \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}.
$$

Denote the columns of $B$ by $b_1, b_2$.

1. Compute $Ab_1$ and $Ab_2$.
2. Compute the matrix $AB$.
3. Compare the results and explain why the columns of $AB$ are exactly the vectors $Ab_1$ and $Ab_2$.

---

## Key Concept — The Column Perspective of Matrix Multiplication

When multiplying two matrices $A$ and $B$, there are two main ways to view the calculation:

1. **The Entry View (dot products):**
   Each entry $(AB)_{ij}$ is the dot product of row $i$ of $A$ and column $j$ of $B$.

2. **The Column View (vector transformations):**
   Each column of $AB$ is the matrix $A$ multiplying the corresponding column of $B$:

$$
\text{column } j \text{ of } AB = A \cdot b_j
$$

This exercise demonstrates the column view directly.

---

## Setup: Sizes and Columns

- Matrix $A$ has size $2 \times 3$.
- Matrix $B$ has size $3 \times 2$.

The columns of $B$ are:

$$
b_1 = \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}, \qquad
b_2 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}
$$

We can write $B$ partitioned by its columns as:

$$
B = \begin{pmatrix} b_1 & b_2 \end{pmatrix}
$$

---

## Step 1 — Compute $Ab_1$ and $Ab_2$

### 1. Compute $Ab_1$

We multiply the $2 \times 3$ matrix $A$ by the $3 \times 1$ column vector $b_1$:

$$
Ab_1 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}
$$

Computing each entry:

- Row 1: $1 \cdot (1) + 2 \cdot (-1) + 0 \cdot (3) = 1 - 2 + 0 = -1$
- Row 2: $0 \cdot (1) + 1 \cdot (-1) + 1 \cdot (3) = 0 - 1 + 3 = 2$

$$
Ab_1 = \begin{pmatrix} -1 \\ 2 \end{pmatrix}
$$

*(We can also see this as a linear combination of the columns of $A$:)*

$$
1 \cdot \begin{pmatrix} 1 \\ 0 \end{pmatrix} + (-1) \cdot \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 3 \cdot \begin{pmatrix} 0 \\ 1 \end{pmatrix}
= \begin{pmatrix} 1 - 2 + 0 \\ 0 - 1 + 3 \end{pmatrix}
= \begin{pmatrix} -1 \\ 2 \end{pmatrix}
$$

---

### 2. Compute $Ab_2$

We multiply the $2 \times 3$ matrix $A$ by the $3 \times 1$ column vector $b_2$:

$$
Ab_2 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}
$$

Computing each entry:

- Row 1: $1 \cdot (2) + 2 \cdot (0) + 0 \cdot (1) = 2 + 0 + 0 = 2$
- Row 2: $0 \cdot (2) + 1 \cdot (0) + 1 \cdot (1) = 0 + 0 + 1 = 1$

$$
Ab_2 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}
$$

*(As a linear combination of the columns of $A$:)*

$$
2 \cdot \begin{pmatrix} 1 \\ 0 \end{pmatrix} + 0 \cdot \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 1 \cdot \begin{pmatrix} 0 \\ 1 \end{pmatrix}
= \begin{pmatrix} 2 + 0 + 0 \\ 0 + 0 + 1 \end{pmatrix}
= \begin{pmatrix} 2 \\ 1 \end{pmatrix}
$$

---

## Step 2 — Compute the Matrix Product $AB$

Matrix $A$ is $2 \times 3$ and matrix $B$ is $3 \times 2$. The inner dimensions match ($3 = 3$), so $AB$ is a $2 \times 2$ matrix:

$$
AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}
$$

Computing each entry using row-by-column multiplication:

### Entry (1, 1): row 1 of $A$ · column 1 of $B$

$$
1 \cdot 1 + 2 \cdot (-1) + 0 \cdot 3 = 1 - 2 + 0 = -1
$$

### Entry (1, 2): row 1 of $A$ · column 2 of $B$

$$
1 \cdot 2 + 2 \cdot 0 + 0 \cdot 1 = 2 + 0 + 0 = 2
$$

### Entry (2, 1): row 2 of $A$ · column 1 of $B$

$$
0 \cdot 1 + 1 \cdot (-1) + 1 \cdot 3 = 0 - 1 + 3 = 2
$$

### Entry (2, 2): row 2 of $A$ · column 2 of $B$

$$
0 \cdot 2 + 1 \cdot 0 + 1 \cdot 1 = 0 + 0 + 1 = 1
$$

### Result for $AB$

$$
AB = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}
$$

---

## Step 3 — Comparison and Explanation

### Comparison

Look at the matrix $AB$ alongside the vectors $Ab_1$ and $Ab_2$:

$$
AB = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}
$$

- Column 1 of $AB$ is:

$$
\begin{pmatrix} -1 \\ 2 \end{pmatrix} = Ab_1
$$

- Column 2 of $AB$ is:

$$
\begin{pmatrix} 2 \\ 1 \end{pmatrix} = Ab_2
$$

Therefore:

$$
AB = \begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix}
$$

The columns of $AB$ are exactly the vectors $Ab_1$ and $Ab_2$. ✅

---

### Why Does This Always Hold?

Let $A$ be an $m \times n$ matrix, and let $B$ be an $n \times p$ matrix with columns $b_1, b_2, \dots, b_p$:

$$
B = \begin{pmatrix} b_1 & b_2 & \dots & b_p \end{pmatrix}
$$

1. By definition of matrix multiplication, the entry in row $i$, column $j$ of $AB$ is:

$$
(AB)_{ij} = \sum_{k=1}^n a_{ik} b_{kj}
$$

2. On the other hand, the $j$-th column of $B$ is the vector:

$$
b_j = \begin{pmatrix} b_{1j} \\ b_{2j} \\ \vdots \\ b_{nj} \end{pmatrix}
$$

3. When we multiply the matrix $A$ by the vector $b_j$, the $i$-th entry of the resulting vector $A b_j$ is:

$$
(A b_j)_i = \sum_{k=1}^n a_{ik} b_{kj}
$$

4. Because $(AB)_{ij} = (A b_j)_i$ for every row $i$, the entire $j$-th column of $AB$ is equal to $A b_j$:

$$
AB = A \begin{pmatrix} b_1 & b_2 & \dots & b_p \end{pmatrix} = \begin{pmatrix} Ab_1 & Ab_2 & \dots & Ab_p \end{pmatrix}
$$

This equality is an identity that holds for all matrices of compatible sizes.

---

## Conceptual Meaning: Parallel Transformation

This result shows the true nature of matrix multiplication:

- The matrix $A$ represents a linear transformation $T_A(v) = Av$.
- Multiplying $A$ by a single vector $b_1$ transforms that one vector into $Ab_1$.
- Multiplying $A$ by the matrix $B$ transforms all vectors $b_1, b_2, \dots, b_p$ **simultaneously in parallel**:

$$
A \cdot \begin{pmatrix} b_1 & b_2 & \dots & b_p \end{pmatrix}
= \begin{pmatrix} T_A(b_1) & T_A(b_2) & \dots & T_A(b_p) \end{pmatrix}
$$

---

## Verification and Consistency Checks

### Transpose Check

Using the rule $(AB)^T = B^T A^T$:

$$
B^T = \begin{pmatrix} 1 & -1 & 3 \\ 2 & 0 & 1 \end{pmatrix}, \qquad
A^T = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ 0 & 1 \end{pmatrix}
$$

Multiplying $B^T A^T$:

- Entry (1, 1): $1 \cdot 1 + (-1) \cdot 2 + 3 \cdot 0 = 1 - 2 + 0 = -1$
- Entry (1, 2): $1 \cdot 0 + (-1) \cdot 1 + 3 \cdot 1 = 0 - 1 + 3 = 2$
- Entry (2, 1): $2 \cdot 1 + 0 \cdot 2 + 1 \cdot 0 = 2 + 0 + 0 = 2$
- Entry (2, 2): $2 \cdot 0 + 0 \cdot 1 + 1 \cdot 1 = 0 + 0 + 1 = 1$

$$
B^T A^T = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}
$$

Transposing our earlier result for $AB$:

$$
(AB)^T = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}^T = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}
$$

Comparing the two matrices:

$$
(AB)^T = B^T A^T
$$

The identity holds. ✅

---

## Why This Exercise Matters

- **Matrix multiplication is bundled matrix-vector multiplication:** Instead of memorizing matrix multiplication as an abstract row-by-column formula, we see that it is simply multiple matrix-vector products arranged as columns.
- **Foundation for column space and rank:** Every column of $AB$ is a linear combination of the columns of $A$. This immediately implies:

$$
\text{col}(AB) \subseteq \text{col}(A) \implies \text{rank}(AB) \le \text{rank}(A)
$$

- **Batch processing in machine learning:** In modern deep learning frameworks (PyTorch, TensorFlow), a batch of data vectors $x_1, x_2, \dots, x_k$ is stacked as columns in a matrix $X$. Applying layer weights $W$ produces:

$$
WX = \begin{pmatrix} Wx_1 & Wx_2 & \dots & Wx_k \end{pmatrix}
$$

evaluating the entire batch in a single hardware-accelerated matrix multiplication.
