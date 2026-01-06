# Multiple Species Population Modelling - Introduction to Matrices
## The blue pill, or the red pill

---

## Definitions

**Definition:** A *vector* in $\mathbb{R}^n$ is a list of $n$ real numbers, usually written as a column.

**Definition:** An $m \times n$ *matrix* is a two-dimensional array of real numbers, with $m$ rows and $n$ columns. If a matrix has the same number of rows and columns, it is said to be a *square matrix*.

### Examples

**Vectors:**
$$\begin{bmatrix} 1 \\ -2 \\ 5 \end{bmatrix}, \quad \begin{bmatrix} 6.25 \\ \pi \\ e \\ 0 \end{bmatrix}, \quad \begin{bmatrix} 4 \\ -17 \end{bmatrix}$$

**Matrices:**
$$\begin{bmatrix} 7 & 8 & 17 \\ -3 & 4 & 93 \end{bmatrix}, \quad \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}, \quad \begin{bmatrix} -3 & 9 \\ 8 & -12 \\ 6.4 & 11 \end{bmatrix}$$

For our class we will primarily focus on square matrices, so the rest of the discussion will just use square matrices.

---

## Matrix Operations

Like regular numbers, there are operations that we can perform on matrices. Denote the following:

$$A = \begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{bmatrix}, \quad B = \begin{bmatrix} b_{11} & b_{12} \\ b_{21} & b_{22} \end{bmatrix}$$

### Matrix Addition

$$A + B = \begin{bmatrix} a_{11} + b_{11} & a_{12} + b_{12} \\ a_{21} + b_{21} & a_{22} + b_{22} \end{bmatrix}$$

**Rule:** Add corresponding entries

### Scalar Multiplication

$$4A = \begin{bmatrix} 4a_{11} & 4a_{12} \\ 4a_{21} & 4a_{22} \end{bmatrix}$$

**Rule:** Multiply each entry by the scalar

### Matrix Multiplication

Multiplication on the other hand is quite different. Though not hard once you get the hang of it, at first it may seem complicated.

$$AB = \begin{bmatrix}
a_{11} \cdot b_{11} + a_{12} \cdot b_{21} & a_{11} \cdot b_{12} + a_{12} \cdot b_{22} \\
a_{21} \cdot b_{11} + a_{22} \cdot b_{21} & a_{21} \cdot b_{12} + a_{22} \cdot b_{22}
\end{bmatrix}$$

$$BA = \begin{bmatrix}
b_{11} \cdot a_{11} + b_{12} \cdot a_{21} & b_{11} \cdot a_{12} + b_{12} \cdot a_{22} \\
b_{21} \cdot a_{11} + b_{22} \cdot a_{21} & b_{21} \cdot a_{12} + b_{22} \cdot a_{22}
\end{bmatrix}$$

**Rule:** Multiply each entry of *column* $i$ by its corresponding entry in *row* $j$ and then sum.

---

## Non-Commutativity of Matrix Multiplication

Note that matrix multiplication is not *commutative*. That is, $AB$ and $BA$ are not necessarily the same. This is more easily seen with a numerical example:

$$\begin{bmatrix} 2 & 5 \\ -1 & 9 \end{bmatrix} \begin{bmatrix} -3 & 6 \\ 2 & -4 \end{bmatrix} = \begin{bmatrix} 2 \cdot (-3) + 5 \cdot 2 & 2 \cdot 6 + 5 \cdot (-4) \\ (-1) \cdot (-3) + 9 \cdot 2 & (-1) \cdot 6 + 9 \cdot (-4) \end{bmatrix} = \begin{bmatrix} 4 & -8 \\ 21 & -42 \end{bmatrix}$$

$$\begin{bmatrix} -3 & 6 \\ 2 & -4 \end{bmatrix} \begin{bmatrix} 2 & 5 \\ -1 & 9 \end{bmatrix} = \begin{bmatrix} (-3) \cdot 2 + 6 \cdot (-1) & (-3) \cdot 5 + 6 \cdot 9 \\ 2 \cdot 2 + (-4) \cdot (-1) & 2 \cdot 5 + (-4) \cdot 9 \end{bmatrix} = \begin{bmatrix} -12 & 39 \\ 8 & -26 \end{bmatrix}$$

**Observation:** Notice that the two products are completely different!

---

## Using a Calculator (TI-83)

All of these calculations can be done on your calculator, which many of you will prefer. The following instructions are based on a TI-83 calculator.

1. Click "2nd" followed by "MATRIX". There should now be a list of letters [A], [B], etc.
2. Select the "EDIT" option followed by the matrix you wish to edit.
3. Set the size of the matrix. Remember the first number corresponds to the number of rows and the second is the number of columns.
4. Input each entry of the matrix. The default value for each one is zero.
5. Once you have done assigning all the matrices you need you can "QUIT" the "MATRIX" menu.
6. On the regular calculator screen you can call the matrices you have assigned by pressing "2nd" followed by "MATRIX" and then selecting the matrix you wish to call.

**Note:** If you want to assign a vector then you can just assign an $m \times 1$ matrix.

---

## Practice Problems

Practice the matrix operations (either by hand or on your calculator) and calculate the following:

### Addition and Scalar Multiplication

**1.** $\begin{bmatrix} 3 & 6 \\ -1 & -3 \\ -5 & -1 \end{bmatrix} + \begin{bmatrix} 0 & -1 \\ 6 & 0 \\ 2 & 3 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 3 & 5 \\ 5 & -3 \\ -3 & 2 \end{bmatrix}$$
</details>

---

**2.** $\begin{bmatrix} -5 & 2 & -2 \\ 4 & -2 & 0 \end{bmatrix} - \begin{bmatrix} 6 & -5 & -6 \\ 1 & 3 & -3 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} -11 & 7 & 4 \\ 3 & -5 & 3 \end{bmatrix}$$
</details>

---

**3.** $-5 \begin{bmatrix} 5 & 6 & -4 \\ 4 & -2 & -1 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} -25 & -30 & 20 \\ -20 & 10 & 5 \end{bmatrix}$$
</details>

---

**4.** $5 \begin{bmatrix} -3 & 0 \\ 0 & 5 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} -15 & 0 \\ 0 & 25 \end{bmatrix}$$
</details>

---

**5.** $\begin{bmatrix} 4 & 2 \end{bmatrix} + \begin{bmatrix} -2 & -6 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 2 & -4 \end{bmatrix}$$
</details>

---

**6.** $7 \begin{bmatrix} 5 & 1 \\ 1 & -2 \\ 1 & 2 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 35 & 7 \\ 7 & -14 \\ 7 & 14 \end{bmatrix}$$
</details>

---

### Matrix Multiplication

**7.** $\begin{bmatrix} 0 & 2 \\ -2 & -5 \end{bmatrix} \begin{bmatrix} 6 & -6 \\ 3 & 0 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 6 & 0 \\ -27 & 12 \end{bmatrix}$$
</details>

---

**8.** $\begin{bmatrix} -5 & -5 \\ -1 & 2 \end{bmatrix} \begin{bmatrix} -2 & -3 \\ 3 & 5 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} -5 & -10 \\ 8 & 13 \end{bmatrix}$$
</details>

---

**9.** $\begin{bmatrix} -3 & 5 \\ -2 & 1 \end{bmatrix} \begin{bmatrix} 6 & -2 \\ 1 & -5 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} -13 & -19 \\ -11 & -1 \end{bmatrix}$$
</details>

---

**10.** $\begin{bmatrix} -1 & 2 & 1 \\ 8 & -3 & 5 \\ 11 & 2 & 6 \end{bmatrix} \begin{bmatrix} 3 & 2 & -1 \\ 5 & 3 & 2 \\ 6 & 1 & 4 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 13 & 5 & 9 \\ 39 & 12 & 6 \\ 79 & 34 & 17 \end{bmatrix}$$
</details>

---

**11.** $\begin{bmatrix} 2 & 6 & -5 \\ 1 & 3 & 4 \\ -7 & 2 & 10 \end{bmatrix} \begin{bmatrix} 1 & 0 & 11 \\ -5 & 2 & 4 \\ -9 & 7 & 8 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 17 & -23 & 6 \\ -50 & 34 & 55 \\ -107 & 74 & 11 \end{bmatrix}$$
</details>

---

**12.** $\begin{bmatrix} 5 & 3 & 2 \\ 6 & 4 & 1 \\ 7 & -9 & 12 \end{bmatrix} \begin{bmatrix} -2 & 5 & 4 \\ 5 & 6 & 13 \\ 3 & 2 & 1 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 11 & 47 & 61 \\ 11 & 56 & 77 \\ -23 & 5 & -77 \end{bmatrix}$$
</details>

---

**13.** $\begin{bmatrix} 6 & -12 \\ 5 & 11 \end{bmatrix} \begin{bmatrix} 2 & 8 \\ 3 & 1 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} -24 & 36 \\ 43 & 51 \end{bmatrix}$$
</details>

---

**14.** $\begin{bmatrix} 1 & -2 & 4 & 5 \\ 7 & -8 & -6 & 2 \\ 2 & 3 & -1 & -2 \\ -3 & 7 & -5 & 4 \end{bmatrix} \begin{bmatrix} -2 & 1 & -3 & 2 \\ 0 & -2 & -5 & -1 \\ 4 & -3 & -7 & 5 \\ 0 & 0 & 6 & 1 \end{bmatrix}$

<details>
<summary>Solution</summary>

$$= \begin{bmatrix} 14 & -7 & 9 & 29 \\ -38 & 41 & 73 & -6 \\ -8 & -1 & -26 & -6 \\ -14 & -2 & 33 & -34 \end{bmatrix}$$
</details>

---

## Key Takeaways

1. **Matrix Addition:** Add corresponding entries
2. **Scalar Multiplication:** Multiply every entry by the scalar
3. **Matrix Multiplication:** For entry $(i,j)$ in the product, take the dot product of row $i$ from the first matrix with column $j$ from the second matrix
4. **Non-commutativity:** In general, $AB \neq BA$
5. **Calculators are your friend:** For larger matrices, using a calculator is much more efficient!