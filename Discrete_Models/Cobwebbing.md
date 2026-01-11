# Cobwebbing and Population Growth Models

## Introduction

Different methods for solving discrete functions:

- Iterate the function
- Find an analytic formula
- Graphical approach *(works for any function)*

Consider a general discrete model described by the **recursive/updating equation**

$$
N_{t+1} = f(N_t) 
$$

where $f$ is an arbitrary function of $N_t$.

We can elicit a considerable amount of information about the population growth behavior by simple graphical means. The dynamic evolution of the solution $N_t$ in equation (1) can be obtained graphically as follows:

1. On the graph of $N_{t+1}$ vs. $N_t$, we plot both $N_{t+1}=f(N_t)$ and $N_{t+1}=N_t$.
2. The equilibrium points (or steady states) are intersections of the curve $N_{t+1}=f(N_t)$ and the straight line $N_{t+1}=N_t$.
3. Suppose we start at an arbitrary $N_0$.
4. Then $N_1$ is given by simply moving along the $N_{t+1}$ axis until we intersect with the curve $N_{t+1}=f(N_t)$, which gives $N_1=f(N_0)$.
5. The line $N_{t+1}=N_t$ is now used to start again with $N_1$ in the place of $N_0$.
6. We then get $N_2$ by proceeding as before and then $N_3, N_4$ and so on.
7. The arrows show the path sequence. *This path is simply a series of reflections in the line $N_{t+1}=N_t$*
