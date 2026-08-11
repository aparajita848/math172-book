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
  A($E_t$) --> B
  B($L_t$) --> C
  C($A_t$) --> A
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
