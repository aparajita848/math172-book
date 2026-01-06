# Eigenvectors and Eigenvalues
## Long-term Analysis of Structured Populations

## Warm-up

Consider the matrix $A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$ and the vectors $\mathbf{v}_1 = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$ and $\mathbf{v}_2 = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$.

**a.** Compute $A\mathbf{v}_1$ and $A\mathbf{v}_2$.

**Solution:**
$$A\mathbf{v}_1 = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix} \begin{bmatrix} 1 \\ 1 \end{bmatrix} = \boxed{\begin{bmatrix} 3 \\ 3 \end{bmatrix}}$$

$$A\mathbf{v}_2 = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix} \begin{bmatrix} -1 \\ 1 \end{bmatrix} = \boxed{\begin{bmatrix} -1 \\ 1 \end{bmatrix}}$$

**b.** Compute $A^2\mathbf{v}_1$ and $A^2\mathbf{v}_2$.

**Solution:**
$$A^2\mathbf{v}_1 = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}^2 \begin{bmatrix} 1 \\ 1 \end{bmatrix} = \boxed{\begin{bmatrix} 9 \\ 9 \end{bmatrix}}$$

$$A^2\mathbf{v}_2 = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}^2 \begin{bmatrix} -1 \\ 1 \end{bmatrix} = \boxed{\begin{bmatrix} -1 \\ 1 \end{bmatrix}}$$

**c.** What do you notice about your answers in (a) and (b)?

**Solution:**
$$A\mathbf{v}_1 = 3\mathbf{v}_1, \quad A\mathbf{v}_2 = \mathbf{v}_2, \quad A^2\mathbf{v}_1 = 9\mathbf{v}_1 = 3^2\mathbf{v}_1, \quad A^2\mathbf{v}_2 = \mathbf{v}_2$$

Multiplication by $A$ on $\mathbf{v}_1$ is the same as multiplying $\mathbf{v}_1$ by 3, multiplication by $A$ on $\mathbf{v}_2$ is the same as multiplying $\mathbf{v}_2$ by 1.

---

## Definition

**Definition:** Let $A$ be an $n \times n$ matrix. An **eigenvector** of $A$ is a vector $\mathbf{v}$ such that

$$A\mathbf{v} = \lambda\mathbf{v}$$

where $\lambda$ is some scalar (constant number) called an **eigenvalue** of $A$.

---

## Geometric Interpretation

Great, but like, what *is* an eigenvector? Geometrically, an eigenvector, corresponding to a real non-zero eigenvalue, points in a direction that is stretched by the transformation and the eigenvalue is the factor by which it is stretched. If the eigenvalue is negative, the direction is reversed.

### Example: Geometric Visualization

Consider the matrix $A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$. It has two eigenvectors $\mathbf{v}_1 = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$ and $\mathbf{v}_2 = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$, with eigenvalues 3 and 1 respectively. So, geometrically speaking, multiplying a vector $\mathbf{w}$ by $A$ will have the effect of stretching $\mathbf{w}$ in the direction of $\mathbf{v}_1$ by a scale factor of 3 and in the direction of $\mathbf{v}_2$ by a scale factor of 1.

*(Visualizations would show vectors $\mathbf{w}_1 = \begin{bmatrix} 2 \\ 1 \end{bmatrix}$ and $\mathbf{w}_2 = \begin{bmatrix} 1 \\ 3 \end{bmatrix}$ being transformed by $A$, with the red dashed line $y=x$ showing the direction of the dominant eigenvector $\mathbf{v}_1$.)*

Above we see the effect of multiplying the vectors $\mathbf{w}_1 = \begin{bmatrix} 2 \\ 1 \end{bmatrix}$ and $\mathbf{w}_2 = \begin{bmatrix} 1 \\ 3 \end{bmatrix}$ by $A$. The first eigenvector $\mathbf{v}_1$ has the highest eigenvalue of 3. We call $\mathbf{v}_1$ a **dominant eigenvector** for the **dominant eigenvalue** 3. More specifically, the dominant eigenvalue is the one with the highest **absolute value**. The red dashes indicate the line $y = x$ which is the line that $\mathbf{v}_1$ lies on. Notice how the vectors $\mathbf{w}_1$ and $\mathbf{w}_2$ are stretched towards this line - the dominant eigenvector pulls vectors towards it.

---

## Dominant Eigenvalue and Long-term Behavior

The dominant eigenvalue describes the main component of the model's behaviour. In our single species linear models the dominant eigenvalue was the *intrinsic growth factor*. It was the single most important number in describing the population over time. To take this comparison further, if we have initial conditions $\mathbf{x}_0 = \mathbf{w}_1$, then given that

$$\mathbf{x}_0 = \frac{3}{2} \cdot \mathbf{v}_1 - \frac{1}{2} \cdot \mathbf{v}_2$$

Our model $\mathbf{x}_t = A^t\mathbf{x}_0$ can be written as

$$\mathbf{x}_t = \frac{3}{2} \cdot 3^t \cdot \mathbf{v}_1 - \frac{1}{2} \cdot 1^t \cdot \mathbf{v}_2$$

As $t$ gets larger and larger, the $\mathbf{v}_2$ makes less and less of an impact. So then we see that $\mathbf{x}_t$ approaches a multiple of $\mathbf{v}_1$.

*Remember when you said we wouldn't go too much into the math and focus on using the theory? Yes, I do. Sorry.*

---

## Structured Population Models

Consider a structured population of the form

$$\mathbf{x}_t = P^t\mathbf{x}_0$$

where the entries of $\mathbf{x}_t$ give the size of each class in the population and $P$ is the transition matrix with dominant eigenvector $\mathbf{v}$ and eigenvalue $\lambda$, then the total population grows approximately at the rate $\lambda^t$ and the relative size of the classes to the population tend towards $\mathbf{v}$. The dominant eigenvector is hence often referred to as the **stable age distribution** or **stable stage distribution** because it gives us the proportions of the population that should appear in each age or stage class, once we account for the growth trend.

---

## Example: Dunes, Grasses, Shrubs, and Trees

An area of land is covered by dunes $(D)$, grasses $(G)$, shrubs $(S)$ and trees $(T)$. In this model, time is measured in decades. We have the following transition diagram:

**Transition Diagram:**
```
       0.2
    D ←---→ D
    ↓ 0.8   ↑ 0.1
    ↓       ↑
    G ←---→ G
      0.5   
    ↓ 0.4   ↑ 0.1
    ↓       ↑
    S ←---→ S
      0.7   
    ↓ 0.2   ↑ 0.05
    ↓       ↑
    T ←---→ T
      0.95
```

**Key transitions:**
- Dunes → Dunes: 0.2, Dunes → Grasses: 0.8
- Grasses → Dunes: 0.1, Grasses → Grasses: 0.5, Grasses → Shrubs: 0.4
- Shrubs → Dunes: 0.1, Shrubs → Shrubs: 0.7, Shrubs → Trees: 0.2
- Trees → Dunes: 0.05, Trees → Trees: 0.95

### Solution

**The transition matrix for this model is given by:**

$$P = \begin{bmatrix}
0.2 & 0.1 & 0.1 & 0.05 \\
0.8 & 0.5 & 0 & 0 \\
0 & 0.4 & 0.7 & 0 \\
0 & 0 & 0.2 & 0.95
\end{bmatrix}$$

**The matrix $P$ has dominant eigenvector:**

$$\mathbf{v} \approx \begin{bmatrix}
0.0753768844 \\
0.1206030151 \\
0.1608040201 \\
0.6432160805
\end{bmatrix}$$

**The equation modelling this population is given by:**

$$\mathbf{x}_t = P^t\mathbf{x}_0$$

**Choose some initial conditions $\mathbf{x}_0$. Calculate $\mathbf{x}_1$, $\mathbf{x}_5$, $\mathbf{x}_{10}$ and $\mathbf{x}_{100}$:**

$$\mathbf{x}_0 = \begin{bmatrix} 0.25 \\ 0.25 \\ 0.25 \\ 0.25 \end{bmatrix}, \quad
\mathbf{x}_1 = \begin{bmatrix} 0.1125 \\ 0.325 \\ 0.275 \\ 0.2875 \end{bmatrix}, \quad
\mathbf{x}_5 = \begin{bmatrix} 0.0879138281 \\ 0.16066375 \\ 0.2877575 \\ 0.4636649219 \end{bmatrix}$$

$$\mathbf{x}_{10} = \begin{bmatrix} 0.0796880889 \\ 0.1321259187 \\ 0.2055510208 \\ 0.5826349716 \end{bmatrix}, \quad
\mathbf{x}_{100} = \begin{bmatrix} 0.0753768844 \\ 0.1206030151 \\ 0.1608040202 \\ 0.6432160803 \end{bmatrix}$$

**Observation:** Notice that $\mathbf{x}_{100}$ is essentially equal to the dominant eigenvector $\mathbf{v}$, demonstrating that the population has reached its stable stage distribution where:
- Approximately 7.5% will be dunes
- Approximately 12.1% will be grasses
- Approximately 16.1% will be shrubs
- Approximately 64.3% will be trees

---

## Example: Checking for Stable Stage Distribution

Consider a structured population consisting of 4 classes. The dominant eigenvalue for this model is $\lambda = 1.171$ with an eigenvector of

$$\mathbf{v} = \begin{bmatrix} 3356 \\ 1156 \\ 476 \\ 496 \end{bmatrix}$$

We find that

$$\mathbf{x}_{21} = \begin{bmatrix} 1776 \\ 612 \\ 252 \\ 263 \end{bmatrix}$$

**Question:** Has the population reached its stable stage distribution at $t = 21$?

### Solution

In the previous example, the eigenvector given had entries that added up to 1:

$$0.0753768844 + 0.1206030151 + 0.1608040201 + 0.6432160805 = 1$$

So each entry was precisely the percentage of the population that each class will eventually be. In this example, the entries of $\mathbf{v}$ add up to 5484:

$$3356 + 1156 + 476 + 496 = 5484$$

so to see the percentages, we should divide $\mathbf{v}$ by 5484,

$$\frac{1}{5484}\mathbf{v} = \begin{bmatrix}
3356/5484 \\
1156/5484 \\
476/5484 \\
496/5484
\end{bmatrix} = \begin{bmatrix}
0.612 \\
0.211 \\
0.087 \\
0.090
\end{bmatrix}$$

Doing the same with $\mathbf{x}_{21}$, we have:

$$\frac{1}{2903}\mathbf{x}_{21} = \begin{bmatrix}
1776/2903 \\
612/2903 \\
252/2903 \\
263/2903
\end{bmatrix} = \begin{bmatrix}
0.612 \\
0.211 \\
0.087 \\
0.091
\end{bmatrix}$$

which is basically the same. So we can say **yes**, the population has reached its stable stage distribution.

---

## Key Takeaways

1. **Eigenvectors** represent directions that are only scaled (not rotated) by a matrix transformation
2. **Eigenvalues** represent the scaling factor in the eigenvector direction
3. The **dominant eigenvector** (corresponding to the largest absolute eigenvalue) determines the long-term behavior of structured populations
4. The **stable stage distribution** is given by the dominant eigenvector (normalized so entries sum to 1)
5. To check if a population has reached stability, normalize both the current state and the eigenvector and compare the proportions