# Matrices
## Introduction

**Definition:** A **vector** in $\mathbb{R}^n$ is a list of $n$ real numbers, usually written as a column.

**Definition:** An $m\times n$ **matrix** is a two-dimensional array of real numbers, with $m$ rows and $n$ columns. If a matrix has the same number of rows and columns, it is said to be a **square matrix**.

For example, 

$$
\begin{equation*}
\begin{aligned}
\underset{\text{vectors}}{\underbrace{\begin{bmatrix}
1	\\
-2	\\
5	
\end{bmatrix},\hspace*{0.5cm}\begin{bmatrix}
6.25	\\
\pi	\\
e	\\
0
\end{bmatrix},\hspace*{0.5cm}\begin{bmatrix}
4	\\
-17		
\end{bmatrix}}},\hspace*{0.5cm}\underset{\text{matrices}}{\underbrace{\begin{bmatrix}
7	& 8	& 17	\\
-3	& 4	& 93
\end{bmatrix},\hspace*{0.5cm}
\begin{bmatrix}
1	& 2	& 3	\\
4	& 5	& 6	\\
7	& 8	& 9
\end{bmatrix},\hspace*{0.5cm}\begin{bmatrix}
-3	&	9	\\
8	&	-12	\\
6.4	&	11
\end{bmatrix}}}
\end{aligned}
\end{equation*}
$$

For our class we will primarily focus on square matrices, so the rest of the discussion will just use square matrices.

Like regular numbers, there are operations that we can perform on matrices. Denote the following

$$
\begin{equation*}
\begin{aligned}
A=\begin{bmatrix}
a_{11}	& a_{12}	\\ \\
a_{21}	& a_{22}	
\end{bmatrix},\hspace*{0.5cm}B=\begin{bmatrix}
b_{11}	& b_{12}	\\ \\
b_{21}	& b_{22}	
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

The first two operations work exactly how you might expect:

**Matrix Addition**

$$
\begin{equation*}
\begin{aligned}
A+B=\begin{bmatrix}
a_{11}+b_{11}	& a_{12}+b_{12}	\\ \\
a_{21}+b_{21}	& a_{22}+b_{22}
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

Add corresponding entries

**Scalar Multiplication**

$$
\begin{equation*}
\begin{aligned}
4A=\begin{bmatrix}
4a_{11}	& 4a_{12}\\ \\
4a_{21}	& 4a_{22}
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

Multiply each entry by the scalar.

**Matrix Multiplication**

Multiplication on the other hand is quite different. Though not hard once you get the hang of it, at first it may seem complicated.

$$
\begin{equation*}
\begin{aligned}
AB=\begin{bmatrix}
a_{11}\cdot b_{11}+a_{12}\cdot b_{21}	& a_{11}\cdot b_{12}+a_{12}\cdot b_{22}	\\ \\
a_{21}\cdot b_{11}+a_{22}\cdot b_{21}	& a_{21}\cdot b_{12}+a_{22}\cdot b_{22}
\end{bmatrix},\hspace*{0.5cm}BA=\begin{bmatrix}
b_{11}\cdot a_{11}+b_{12}\cdot a_{21}	& b_{11}\cdot a_{12}+b_{12}\cdot a_{22}	\\ \\
b_{21}\cdot a_{11}+b_{22}\cdot a_{21}	& b_{21}\cdot a_{12}+b_{22}\cdot a_{22}
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

Multiply each entry of **column** $i$ by its corresponding entry in **row** $j$ and then sum.

Note too that matrix multiplication is not **commutative**. That is $AB$ and $BA$ are not necessarily the same. This is more easily seen with a numerical example:

$$
\begin{equation*}
\begin{aligned}
\begin{bmatrix}
2	& 5	\\ \\
-1	& 9
\end{bmatrix}\begin{bmatrix}
-3	& 6	\\ \\
2	& -4
\end{bmatrix}=\begin{bmatrix}
2\cdot(-3)+5\cdot2	&	2\cdot6+5\cdot(-4)	\\ \\
(-1)\cdot(-3)+9\cdot2	&	(-1)\cdot6+9\cdot(-4)
\end{bmatrix}=\begin{bmatrix}
4	&	-8	\\ \\
21	&	-42
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
\begin{bmatrix}
-3	& 6	\\ \\
2	& -4
\end{bmatrix}\begin{bmatrix}
2	& 5	\\ \\
-1	& 9
 \end{bmatrix}=\begin{bmatrix}
(-3)\cdot2+6\cdot(-1)	&	(-3)\cdot5+6\cdot9	\\ \\
2\cdot2+(-4)\cdot(-1)	&	2\cdot5+(-4)\cdot9
\end{bmatrix}=\begin{bmatrix}
-12	&	39	\\ \\
8	&	-26
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

:::{tip}

All of these calculations can be done on your calculator, which many of you will prefer. The following instructions are based on a TI-83 calculator.
 - Click ``2nd'' followed by ``MATRIX''. There should now be a list of letters [A], [B], etc..
 - Select the ``EDIT'' option followed by the matrix you wish to edit.
 - Set the size of the matrix. Remember the first number corresponds to the number of rows and the second is the number of columns.
 - Input each entry of the matrix. The default value for each one is zero.
 - Once you have done assigning all the matrices you need you can ``QUIT'' the ``MATRIX'' menu.
 - On the regular calculator screen you can call the matrices you have assigned by pressing ``2nd`` followed by ``MATRIX'' and then selecting the matrix you wish to call.
 - Note: If you want to assign a vector then you can just assign an $m\times1$ matrix.

:::

---

## Exercises

Practice the matrix operations (either by hand or on your calculator) and calculate the following:

:::{tip} Exercise 1
:class: dropdown
:open: true

$$
\begin{equation*}
 \begin{bmatrix}
3	& 6	\\
-1	& -3	\\
-5	& -1
\end{bmatrix}+\begin{bmatrix}
0	& -1	\\
6	& 0	\\
2	& 3
\end{bmatrix}
\end{equation*}
$$

:::

:::{tip} Solution to Exercise 1
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{bmatrix}
3	&	5	\\
5	&	-3	\\
-3	&	2
\end{bmatrix}
\end{equation*}
$$

:::

:::{tip} Exercise 2
:class: dropdown
:open: true

$$
\begin{equation*}
\begin{bmatrix}
-5	& 2	& -2	\\
4	& -2	& 0
\end{bmatrix}-\begin{bmatrix}
6	& -5	& -6	\\
1	& 3	& -3
\end{bmatrix}
\end{equation*}
$$

:::

:::{tip} Solution to Exercise 2
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{bmatrix}
-11	&	7	&	4	\\
3	&	-5	&	3
\end{bmatrix}
\end{equation*}
$$


:::

:::{tip} Exercise 3
:class: dropdown
:open: true

$$
\begin{equation*}
-5\begin{bmatrix}
5	& 6	& -4	\\
4	& -2	& -1
\end{bmatrix}
\end{equation*}
$$

:::

:::{tip} Solution to Exercise 3
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{bmatrix}
-25	&	-30	&	20	\\
-20	&	10	&	5
\end{bmatrix}
\end{equation*}
$$


:::

:::{tip} Exercise 4
:class: dropdown
:open: true

$$
\begin{equation*}
\begin{bmatrix}
0	&	2	\\
-2	&	-5	
\end{bmatrix}\begin{bmatrix}
6	&	-6	\\
3	&	0
\end{bmatrix}
\end{equation*}
$$

:::

:::{tip} Solution to Exercise 4
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{bmatrix}
6	&	0	\\
-27	&	12
\end{bmatrix}
\end{equation*}
$$


:::

:::{tip} Exercise 5
:class: dropdown
:open: true

$$
\begin{equation*}
\begin{bmatrix}
1	&	-2	&	4	&	5	\\
7	&	-8	&	-6	&	2	\\
2	&	3	&	-1	&	-2	\\
-3	&	7	&	-5	&	4
\end{bmatrix}\begin{bmatrix}
-2	&	1	&	-3	&	2	\\
0	&	-2	&	-5	&	-1	\\
4	&	-3	&	-7	&	5	\\
0	&	0	&	6	&	1	
\end{bmatrix}
\end{equation*}
$$

:::

:::{tip} Solution to Exercise 5
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{bmatrix}
14	&	-7	&	9	&	29	\\
-38	&	41	&	73	&	-6	\\
-8	&	-1	&	-26	&	-6	\\
-14	&	-2	&	33	&	-34
\end{bmatrix}
\end{equation*}
$$


:::

