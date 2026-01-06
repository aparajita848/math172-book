# Structured Populations
## *Multiple Species Population Model*

---

## Introduction

So far in our models, all individuals in a population were treated identically. Although our exponential model may work for "simple" organisms such as single-celled bacteria or protozoa, in most populations, there are actually many subgroups whose vital behaviour can be quite different.

Therefore, we extend our discrete models to a population divided into different subgroups whose reproduction and mortality rates depend on and influence each other. For example, we could have an age-structured population, where reproduction only occurs after the individual has matured, while death rates are higher either for newly-borns and/or for the oldest in the population who are more vulnerable to predators, parasites, and disease. Or, we could also have a stage-structured population, as for many insects which pass through the egg, larval, pupal, and adult stages and survival is influenced by which phase they are in. These are called ***structured populations***. We will focus on linear models and develop a **system of equations** (with a different growth equation for each subgroup), and use **matrices** to solve them.

---

## Example: Stage-Structured Population

Suppose we consider a hypothetical insect with three life stages: egg $(E)$, larva $(L)$ and adult $(A)$. Our insect is such that individuals progress from egg to larva and from larva to adult over one time step. Finally adults lay eggs and die in one more time step. Suppose we collect data and find that only 4% of the eggs survive to become larvae, 39% of the larvae make it to adulthood and the adults on average lay 73 eggs each.

### Step 1: Define Variables

$$\begin{align*}
E_t &: \text{Number of eggs at time } t \\
L_t &: \text{Number of larvae at time } t \\
A_t &: \text{Number of adults at time } t \\
\Delta t &: \text{Time step}
\end{align*}$$

### Step 2: Transition Diagram

We can draw a **transition diagram** (the change in between one time step: $t_n$ and $t_{n+1}$) to help visualize the movement/change in our model:

```
    0.04        0.39
E_t -----> L_t -----> A_t
 ^                      |
 |         73           |
 +----------------------+
```

**Interpretation:**
- 4% of eggs (0.04) survive to become larvae
- 39% of larvae (0.39) survive to become adults
- Each adult produces 73 eggs

### Step 3: Calculate Initial Time Steps

Suppose that initially there are 100 eggs, 10 larvae and 10 adults; use this to find the number of individuals in each stage after one and two time-steps:

**Initial conditions:**
$$E_0 = 100, \quad L_0 = 10, \quad A_0 = 10$$

**After 1 time step:**
$$\begin{align*}
E_1 &= 73 \times A_0 = 730 \\
L_1 &= 0.04 \times E_0 = 4 \\
A_1 &= 0.39 \times L_0 = 3.9
\end{align*}$$

**After 2 time steps:**
$$\begin{align*}
E_2 &= 73 \times A_1 = 284.7 \\
L_2 &= 0.04 \times E_1 = 29.2 \\
A_2 &= 0.39 \times L_1 = 1.56
\end{align*}$$

### Step 4: Difference and Recursive Equations

Write the difference equations and the recursive equations for each life stage:

$$\begin{align*}
\Delta E &= 73A & E_{t+1} &= 73A_t \\
\Delta L &= 0.04E & L_{t+1} &= 0.04E_t \\
\Delta A &= 0.39L & A_{t+1} &= 0.39L_t
\end{align*}$$

### Step 5: Matrix Equation

Written as a **matrix equation** we have: (**transition matrix** - we write the coefficients to each of the variables from the above recursive equations as the corresponding elements of the matrix.)

$$\begin{bmatrix}
E_{t+1} \\
L_{t+1} \\
A_{t+1}
\end{bmatrix} = \begin{bmatrix}
0 & 0 & 73 \\
0.04 & 0 & 0 \\
0 & 0.39 & 0
\end{bmatrix} \begin{bmatrix}
E_t \\
L_t \\
A_t
\end{bmatrix}$$

### Step 6: Explicit Solution

Written this way we can easily find an explicit expression for our population model in terms of $t$. It is given by:

$$\begin{bmatrix}
E_t \\
L_t \\
A_t
\end{bmatrix} = \begin{bmatrix}
0 & 0 & 73 \\
0.04 & 0 & 0 \\
0 & 0.39 & 0
\end{bmatrix}^t \begin{bmatrix}
E_0 \\
L_0 \\
A_0
\end{bmatrix} \Longrightarrow \boxed{\begin{bmatrix}
E_t \\
L_t \\
A_t
\end{bmatrix} = \begin{bmatrix}
0 & 0 & 73 \\
0.04 & 0 & 0 \\
0 & 0.39 & 0
\end{bmatrix}^t \begin{bmatrix}
100 \\
10 \\
10
\end{bmatrix}}$$

**Comparison to single species model:**

We can compare this to our discrete (exponential) model with just a single species $N_t = N_0\lambda^t$; then $N_t$ is synonymous with the vector $\begin{bmatrix} E_t \\ L_t \\ A_t \end{bmatrix}$, $\lambda$ is synonymous with the **transition matrix** and $N_0$ with the vector representing initial population $\begin{bmatrix} E_0 \\ L_0 \\ A_0 \end{bmatrix}$.

---

## General Form of Structured Population Models

**Structured population models** divide the population by groups (like the previous example) or developmental stages. For example:

$$\begin{align*}
x^1_t &= \text{number of individuals age 0 through 15 at time } t \\
x^2_t &= \text{number of individuals age 16 through 35 at time } t \\
x^3_t &= \text{number of individuals age 36 through 65 at time } t \\
x^4_t &= \text{number of individuals age 66 through 80 at time } t \\
x^5_t &= \text{number of individuals age 81 or older at time } t
\end{align*}$$

In general we can represent these models in a simple matrix equation

$$\mathbf{x}_{t+1} = P\mathbf{x}_t$$

where

$$\mathbf{x}_t = \begin{bmatrix}
x_t^1 \\
x_t^2 \\
x_t^3 \\
\vdots \\
x_t^n
\end{bmatrix}, \quad P = \begin{bmatrix}
p_{11} & p_{12} & p_{13} & \cdots & p_{1n} \\
p_{21} & p_{22} & p_{23} & \cdots & p_{2n} \\
p_{31} & p_{32} & p_{33} & \cdots & p_{3n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
p_{n1} & p_{n2} & p_{n3} & \cdots & p_{nn}
\end{bmatrix}$$

where $n$ is the number of groups and $P$ is called the **transition matrix** because it captures the transition between time $t$ and $t+1$. The size of $P$ is $n \times n$ because $n$ is the total number of groups in the population. To construct $P$ we need to determine which groups transfer individuals from one to the other.

### Interpreting the Transition Matrix

|             | Moving from $x^1_t$ | Moving from $x^2_t$ | Moving from $x^3_t$ |
|-------------|---------------------|---------------------|---------------------|
| **Moving into $x^1_{t+1}$** | $p_{11}$ | $p_{12}$ | $p_{13}$ |
| **Moving into $x^2_{t+1}$** | $p_{21}$ | $p_{22}$ | $p_{23}$ |
| **Moving into $x^3_{t+1}$** | $p_{31}$ | $p_{32}$ | $p_{33}$ |

**Reading the matrix:** Entry $p_{ij}$ represents the proportion (or rate) of individuals moving **from group $j$** at time $t$ **into group $i$** at time $t+1$.

---

## Example: Age-Structured Population

A population consists of three age classes: children $(C)$, mature individuals $(M)$ and elderly individuals $(E)$. After each time step, 50% of children become mature individuals and 2% die; 30% of mature individuals become old and 5% die; finally 40% of old individuals die. Moreover, at each time step, each pair of mature individuals produce 3 children.

### Transition Diagram

```
       0.48         0.65         0.6
    C ←---→ C    M ←---→ M    E ←---→ E
    ↓             ↓             
    | 0.5         | 0.3         
    ↓             ↓             
    M             E
    
    C ←---1.5--- M
```

**Key transitions:**
- Children to Children: 0.48 (48% survive and remain children)
- Children to Mature: 0.5 (50% mature)
- Mature to Mature: 0.65 (65% survive and remain mature)
- Mature to Elderly: 0.3 (30% age to elderly)
- Mature to Children: 1.5 (each pair produces 3 children = 1.5 per individual)
- Elderly to Elderly: 0.6 (60% survive)

*Make sure you understand the arrows in the diagram in relation to the information given in the word problem above. Note that unlike the developmental stages where each stage converts into the next within a time-step, in the above problem, a percentage of each class population will continue to survive into the next time-step.*

### Step 1: Write the Equations

Write the equations that model this population:

$$\begin{align*}
C_{t+1} &= 0.48C_t + 1.5M_t \\
M_{t+1} &= 0.5C_t + 0.65M_t \\
E_{t+1} &= 0.3M_t + 0.6E_t
\end{align*}$$

### Step 2: Transition Matrix

Write the transition matrix for this model:

$$P = \begin{bmatrix}
0.48 & 1.5 & 0 \\
0.5 & 0.65 & 0 \\
0 & 0.3 & 0.6
\end{bmatrix}$$

### Step 3: Matrix Equation and Explicit Solution

Write a matrix equation modelling this situation as well as an explicit solution. Let $C_0$, $M_0$ and $E_0$ denote the initial populations of each group.

$$\begin{bmatrix}
C_t \\
M_t \\
E_t
\end{bmatrix} = \begin{bmatrix}
0.48 & 1.5 & 0 \\
0.5 & 0.65 & 0 \\
0 & 0.3 & 0.6
\end{bmatrix}^t \begin{bmatrix}
C_0 \\
M_0 \\
E_0
\end{bmatrix}$$

### Step 4: Calculate Future Population

Suppose that $M_0 = 200$ and $C_0 = E_0 = 0$. What is the total population after 4 time steps have passed?

We plug in $t = 4$:

$$\begin{bmatrix}
C_4 \\
M_4 \\
E_4
\end{bmatrix} = \begin{bmatrix}
0.48 & 1.5 & 0 \\
0.5 & 0.65 & 0 \\
0 & 0.3 & 0.6
\end{bmatrix}^4 \begin{bmatrix}
0 \\
200 \\
0
\end{bmatrix} = \begin{bmatrix}
730 \\
466 \\
166
\end{bmatrix}$$

Therefore, the total population is:

$$730 + 466 + 166 = \boxed{1366}$$

---

## Key Concepts Summary

1. **Structured populations** divide individuals into distinct groups based on age, stage, size, or other characteristics
2. **Transition matrices** capture how individuals move between groups over one time step
3. The general form is $\mathbf{x}_{t+1} = P\mathbf{x}_t$, where:
   - $\mathbf{x}_t$ is a vector of population sizes for each group at time $t$
   - $P$ is the transition matrix with entries $p_{ij}$ representing movement from group $j$ to group $i$
4. The explicit solution is $\mathbf{x}_t = P^t\mathbf{x}_0$
5. Matrix entry $p_{ij}$ represents: **from column $j$ → into row $i$**
6. Each column of $P$ typically sums to ≤ 1 (accounting for deaths and transitions)
7. Reproduction terms can make column sums exceed 1 (population growth)