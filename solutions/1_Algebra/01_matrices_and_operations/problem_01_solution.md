# Problem 1: Matrix Size and Entries

## Question

Given matrices

$$
A =
\begin{pmatrix}
2 & -1 & 3 \\
0 & 4 & 5 \\
\end{pmatrix},
\qquad
B =
\begin{pmatrix}
1 & 0 \\
-2 & 3 \\
4 & 1 \\
\end{pmatrix}
$$

1. State the sizes of matrices $A$ and $B$.
2. Read off the entries $a_{12}$, $a_{23}$, $b_{21}$, and $b_{32}$.
3. Write the second row of $A$ and the first column of $B$ as vectors.

---

## Solution

### 1. Sizes of Matrices $A$ and $B$

A matrix size is written in the standard form $m \times n$, where:
- $m$ is the number of horizontal rows,
- $n$ is the number of vertical columns.

A convenient memory rule is **"rows first, columns second"** (RC, like "remote control").

**Matrix $A$:**
  - Counting rows horizontally:
    - Row 1: $(2, -1, 3)$
    - Row 2: $(0, 4, 5)$
    - Total number of rows: $m = 2$.
  - Counting columns vertically:
    - Column 1: entries $2$ and $0$ (from top to bottom)
    - Column 2: entries $-1$ and $4$
    - Column 3: entries $3$ and $5$
    - Total number of columns: $n = 3$.

  Therefore, the size of $A$ is $2 \times 3$.

- **Matrix $B$:**
  - Counting rows horizontally:
    - Row 1: $(1, 0)$
    - Row 2: $(-2, 3)$
    - Row 3: $(4, 1)$
    - Total number of rows: $m = 3$.
  - Counting columns vertically (from top to bottom):
    - Column 1: $(1, -2, 4)^\mathrm{T}$ (entries $1, -2, 4$)
    - Column 2: $(0, 3, 1)^\mathrm{T}$ (entries $0, 3, 1$)
    - Total number of columns: $n = 2$.

  Therefore, the size of $B$ is $3 \times 2$.

---

### 2. Reading Off Matrix Entries

In standard double-subscript notation $m_{ij}$:
- The first index $i$ indicates the **row** number.
- The second index $j$ indicates the **column** number.

Thus, $m_{ij}$ is the entry located at the intersection of row $i$ and column $j$.

- **Entry $a_{12}$:**
  - Matrix $A$, row 1, column 2.
  - In row 1 of $A$, $(2, -1, 3)$, the second element is $-1$.

$$
a_{12} = -1
$$

- **Entry $a_{23}$:**
  - Matrix $A$, row 2, column 3.
  - In row 2 of $A$, $(0, 4, 5)$, the third element is $5$.

$$
a_{23} = 5
$$

- **Entry $b_{21}$:**
  - Matrix $B$, row 2, column 1.
  - In row 2 of $B$, $(-2, 3)$, the first element is $-2$.

$$
b_{21} = -2
$$

- **Entry $b_{32}$:**
  - Matrix $B$, row 3, column 2.
  - In row 3 of $B$, $(4, 1)$, the second element is $1$.

$$
b_{32} = 1
$$

---

### 3. Row and Column Vectors

- **Second row of $A$:**
  - We take all entries in row 2 across all columns: $a_{21} = 0$, $a_{22} = 4$, $a_{23} = 5$.
  - Expressed as a row vector:

$$
r_2(A) =
\begin{pmatrix}
0 & 4 & 5 \\
\end{pmatrix}
$$

  In standard tuple notation, this is $(0, 4, 5) \in \mathbb{R}^3$.

- **First column of $B$:**
  - We take all entries in column 1 across all rows: $b_{11} = 1$, $b_{21} = -2$, $b_{31} = 4$.
  - Expressed as a column vector:

$$
c_1(B) =
\begin{pmatrix}
1 \\
-2 \\
4 \\
\end{pmatrix}
$$

  In transpose tuple notation, this can also be written as $(1, -2, 4)^\mathrm{T}$.

---

## Verification and Consistency Checks

1. **Total entry count:**
   - Matrix $A$ has size $2 \times 3$, so it must contain $2 \cdot 3 = 6$ entries. Listing them: $2, -1, 3, 0, 4, 5$ gives exactly 6 entries.
   - Matrix $B$ has size $3 \times 2$, so it must contain $3 \cdot 2 = 6$ entries. Listing them: $1, 0, -2, 3, 4, 1$ gives exactly 6 entries.

2. **Index validity:**
   - For $A \in \mathbb{R}^{2 \times 3}$, indices must satisfy $1 \le i \le 2$ and $1 \le j \le 3$. Both $a_{12}$ and $a_{23}$ fall within valid ranges.
   - For $B \in \mathbb{R}^{3 \times 2}$, indices must satisfy $1 \le i \le 3$ and $1 \le j \le 2$. Both $b_{21}$ and $b_{32}$ fall within valid ranges.

3. **Vector dimensions:**
   - A row vector extracted from a $2 \times 3$ matrix must have length equal to the number of columns ($3$), which matches $r_2(A) \in \mathbb{R}^3$.
   - A column vector extracted from a $3 \times 2$ matrix must have length equal to the number of rows ($3$), which matches $c_1(B) \in \mathbb{R}^3$.

---

## Why This Exercise Matters

Mastering matrix sizes and index notation is essential because all subsequent linear algebra operations rely on index rules:
- **Matrix addition** requires identical sizes ($m \times n$).
- **Matrix multiplication** $AB$ requires inner dimension agreement: $(m \times k) \cdot (k \times n) = (m \times n)$.
- **Dot products and matrix-vector multiplication** depend directly on taking rows of the first matrix against columns of the second matrix/vector.
