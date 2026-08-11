# Structured Populations

## Introduction

So far in our models, all individuals in a population were treated identically. Although our exponential model may work for ''simple" organisms such as single-celled bacteria or protozoa, in most populations, there are actually many subgroups whose vital behaviour can be quite different.  

Therefore, we extend our discrete models to a population divided into different subgroups whose reproduction and mortality rates depend on and influence each other.  For example, we could have an age-structured population, where reproduction only occurs after the individual has matured, while death rates are higher for either for newly-borns and/or for the oldest in the population who are more vulnerable to predators, parasite, and disease. Or, we could also have a stage-structured population, as for many insects which pass through the egg, larval, pupal, and adult stages and survival is influenced by which phase they are in. These are called _**structured populations**_. We will focus on linear models and develop a _**system of equations**_ (with a different growth equation for each subgroup), and use _**matrices**_ to solve them. 

## Example

**Stage-structured population.** Suppose we consider a hypothetical insect with three life stages: egg $(E)$, larva $(L)$ and adult $(A)$. Our insect is such that individuals progress from egg to larva and from larva to adult over one time step. Finally adults lay eggs and die in one more time step. Suppose we collect data and find that only $4\%$ of the eggs survive to become larvae, $39\%$ of the larvae make it to adulthood and the adults on average lay $73$ eggs each.

- First lets define our variables:

$$
\begin{equation*}
\begin{aligned}
E_t\hspace*{10pt}&:\hspace*{10pt}\text{Number of eggs at time }t\\
L_t\hspace*{10pt}&:\hspace*{10pt}\text{Number of larvae at time }t\\
A_t\hspace*{10pt}&:\hspace*{10pt}\text{Number of adults at time }t\\
\Delta t\hspace*{10pt}&:\hspace*{10pt}\text{Time step}
\end{aligned}
\end{equation*}
$$

- We can draw a **_transition diagram_** (the change in between one time step: $t_n$ and $t_{n+1}$) to help visualize the movement/change in our model:

```{mermaid}

flowchart LR
  A(($$E_t$$)) -->|0.04| B
  B(($$L_t$$)) -->|0.39| C
  C(($$A_t$$)) -->|73| A
```

```{image} ../images/structured_populations_fig1.png
:alt: Insect_cycle.
:width: 500px
:align: center
```


- Suppose that initially there are a 100 eggs, 10 larvae and 10 adults; use this find the number of individuals in each stage after one and two time-steps.:

$$
\begin{equation*}
\begin{aligned}
E_0=&100,& L_0=&10,& A_0=&10 \\
E_1=& 73*A_0 = 730,& L_1=&0.04*E_0 = 4,& A_1=& 0.39*L_0= 3.9\\
E_2=& 73*A_1 = 284.7,& L_1=&0.04*E_1 = 29.2,& A_1=& 0.39*L_1= 1.56\\
\end{aligned}
\end{equation*}
$$

- Write the difference equations and the recursive equations for each life stage:

$$
\begin{equation*}
\begin{aligned}
\Delta E &= 73A & E_{t+1}	&=	73A_t	\\
\Delta L &= 0.04E & L_{t+1}	&=	0.04E_t	\\
\Delta A &= 0.39L & A_{t+1}	&=	0.39L_t
\end{aligned}
\end{equation*}
$$ 

- Written as a **matrix equation** we have: (_**transition matrix** - we write the coefficients to each of the variables from the above recursive equations as the corresponding elements of the matrix._)

$$
\begin{equation*}
\begin{aligned}
\begin{bmatrix}
E_{t+1}	\\
L_{t+1}	\\
A_{t+1}
\end{bmatrix}=\begin{bmatrix}
%  E_t & L_t & A_t \\
 0	&	0	&	73	\\
 0.04	&	0	&	0	\\
 0	&	0.39	&	0
\end{bmatrix}\begin{bmatrix}
E_t	\\
L_t	\\
A_t
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

- Written this way we can easily find an explicit expression for our population model in terms of $t$. It is given by:

$$
\begin{equation*}
\begin{aligned}
\begin{bmatrix}
E_t	\\
L_t	\\
A_t
\end{bmatrix}=\begin{bmatrix}
0	&	0	&	73	\\
0.04	&	0	&	0	\\
0	&	0.39	&	0
\end{bmatrix}^t\begin{bmatrix}
E_0	\\
L_0	\\
A_0
\end{bmatrix}\Longrightarrow\boxed{\begin{bmatrix}
E_t	\\
L_t	\\
A_t
\end{bmatrix}=\begin{bmatrix}
0	&	0	&	73	\\
0.04	&	0	&	0	\\
0	&	0.39	&	0
\end{bmatrix}^t\begin{bmatrix}
100	\\
10	\\
10
\end{bmatrix}}
\end{aligned}
\end{equation*}
$$

We cam compare this to our discrete (exponential) model with just a single species $N_t = N_0\lambda^t$; then $N_t$ is synonymous with the vector $\begin{bmatrix}
 E_t	\\
L_t	\\
A_t   
\end{bmatrix}$, $\lambda$ is synonymous with the \textbf{transition matrix} and $N_0$ with the vector representing initial population $\begin{bmatrix}
 E_0	\\
L_0	\\
A_0   
\end{bmatrix}$.

---

**Structured population models** divide the population by groups (like the previous example) or developmental stages. For example

$$
\begin{equation*}
\begin{aligned}
x^1_t\hspace*{10pt}&=\hspace*{10pt}\text{ number of individuals age }0\text{ through }15\text{ at time }t \\
x^2_t\hspace*{10pt}&=\hspace*{10pt}\text{ number of individuals age }16\text{ through }35\text{ at time }t \\
x^3_t\hspace*{10pt}&=\hspace*{10pt}\text{ number of individuals age }36\text{ through }65\text{ at time }t \\
x^4_t\hspace*{10pt}&=\hspace*{10pt}\text{ number of individuals age }66\text{ through }80\text{ at time }t \\
x^5_t\hspace*{10pt}&=\hspace*{10pt}\text{ number of individuals age }81\text{ or older at time }t 
\end{aligned}
\end{equation*}
$$

 In general we can represent these models in a simple matrix equation

$$
\begin{equation*}
\begin{aligned}
\mathbf{x}_{t+1}=P\mathbf{x}_t
\end{aligned}
\end{equation*}
$$

where 

$$
\begin{equation*}
\begin{aligned}
\mathbf{x}_t=\begin{bmatrix}
x_t^1 \\
x_t^2 \\
x_t^3 \\
\vdots \\
x_t^n
\end{bmatrix},\hspace*{2cm}P=\begin{bmatrix}
p_{11}	&	p_{12}	&	p_{13}	&	\cdots	&	p_{1n}	\\
p_{21}	&	p_{22}	&	p_{23}	&	\cdots	&	p_{2n}	\\
p_{31}	&	p_{32}	&	p_{33}	&	\cdots	&	p_{3n}	\\
\vdots	&	\vdots	&	\vdots	&	\ddots	&	\vdots	\\
p_{n1}	&	p_{n2}	&	p_{n3}	&	\cdots	&	p_{nn}	\\
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

where $n$ is the number of groups and $P$ is called the \textbf{transition matrix} because it captures the transition between time $t$ and $t+1$. The size of $P$ is $n\times n$ because $n$ is the total number of groups in the population. To construct $P$ we need to determine which groups transfer individuals from one to the other.


|   |$x^1_t$ | $x^2_t$ | $x^3_t$ |
|---|---|---|---| 
|$x^1_{t+1}$ | $p_{11}$ | $p_{12}$ | $p_{13}$ |
|$x^2_{t+1}$ | $p_{21}$ | $p_{22}$ | $p_{23}$ |
|$x^3_{t+1}$ | $p_{31}$	| $p_{32}$ | $p_{33}$ |

---
## Example

A population consists of three age classes: children $(C)$, mature individuals $(M)$ and elderly individuals $(E)$. After each time step, $50\%$ of children become mature individuals and $2\%$ die; $30\%$ of mature individuals become old and $5\%$ die; finally $40\%$ of old individuals die. Moreover, at each time step, each pair of mature individuals produce $3$ children.

- Given is the transition diagram modelling this situation.

_Make sure you understand the arrows in the diagram in relation to the information given in the word problem above. Note that unlike the developmental stages where each stage converts into the next within a time-step, in the above problem, a percentage of each class population will continue to survive into the next time-step._


```{mermaid}

flowchart LR
  A(($$C_t$$)) -->|0.5| B
  B(($$M_t$$)) -->|0.3| C
  B -->|1.5| A
  C(($$E_t$$)) -->|0.6| C
  B -->|0.65| B
  A -->|0.48| A
```

```{image} ../images/structured_populations_fig2.png
:alt: Population_cycle.
:width: 500px
:align: center
```


- Write the equations that model this population:

$$
\begin{equation*}
\begin{aligned}
C_{t+1}	&	=	0.48C_t+1.5M_t	\\
M_{t+1}	&	=	0.5C_t+0.65M_t	\\
E_{t+1}	&	=	0.3M_t+0.6E_t
\end{aligned}
\end{equation*}
$$

- Write the transition matrix for this model.

$$
\begin{equation*}
\begin{aligned}
P=\begin{bmatrix}
0.48	&	1.5	&	0	\\
0.5	&	0.65	&	0	\\
0	&	0.3	&	0.6
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

- Write a matrix equation modelling this situation as well as an explicit solution. Let $C_0$, $M_0$ and $E_0$ denote the initial populations of each group.

$$
\begin{equation*}
\begin{aligned}
\begin{bmatrix}
C_t	\\
M_t	\\
E_t
\end{bmatrix}=\begin{bmatrix}
0.48	&	1.5	&	0	\\
0.5	&	0.65	&	0	\\
0	&	0.3	&	0.6
\end{bmatrix}^t\begin{bmatrix}
C_0	\\
M_0	\\
E_0
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

- Suppose that $M_0=200$ and $C_0=E_0=0$. What is the total population after $4$ time steps have passed?

We plug-in $t=4$:

$$
\begin{equation*}
\begin{aligned}
\begin{bmatrix}
C_4	\\
M_4	\\
E_4
\end{bmatrix}=\begin{bmatrix}
0.48	&	1.5	&	0	\\
0.5	&	0.65	&	0	\\
0	&	0.3	&	0.6
\end{bmatrix}^4\begin{bmatrix}
0	\\
200	\\
0
\end{bmatrix}=\begin{bmatrix}
730	\\
466	\\
166
\end{bmatrix}\Longrightarrow 730+466+166=\boxed{1366}
\end{aligned}
\end{equation*}
$$


---


## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true


:::

:::{tip} Solution to Exercise 1
:icon: false
:class: dropdown


:::

:::{tip} Exercise 2
:class: dropdown
:open: true


:::

:::{tip} Solution to Exercise 2
:icon: false
:class: dropdown


:::
