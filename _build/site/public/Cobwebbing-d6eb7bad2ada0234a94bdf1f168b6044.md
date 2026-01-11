# Cobwebbing and Population Growth Models

## A Graphical Procedure of Solution

Different methods for solving discrete functions:

- Iterate the function
- Find an analytic formula
- Graphical approach *(works for any function)*

Consider a general discrete model described by the **recursive/updating equation**

$$
N_{t+1} = f(N_t) \tag{1}
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

---

## Example 1: Exponential Growth

The most basic model of population growth assumes that population increases by a constant factor each time step. As an example, consider the equation below, which describes a population that is doubling every time step.

$$
N_{t+1} = 2N_t
$$

**1.** Sketch the graph of this updating function on the axes below, along with the graph of the diagonal line $N_{t+1} = N_{t}$.

![Exponential growth cobweb diagram](figures/cobweb-exponential.png)

**2.** Use the cobwebbing technique in the graph above to find successive values of $N_1$, $N_2$, ..., assuming that $N_0=0.05$.

**3.** Sketch the graph of $N_t$ versus $t$ on the axes below.

![Population versus time](figures/population-vs-time-exponential.png)

**4.** How would you describe the growth of $N_t$ as a function of $t$?

---

## Example 2: Logistic Growth

A more realistic model of population growth is a logistic model. In logistic growth, the *per capita reproduction rate* levels off as the population size increases.

The figure below shows the graph for the model

$$
N_{t+1} = 2N_t\left(1 - \frac{N_t}{2}\right)
$$

![Logistic growth cobweb diagram](figures/cobweb-logistic.png)

**1.** Use the cobwebbing technique in the graph above to find successive values of $N_1$, $N_2$, ..., assuming that $N_0=0.05$.

**2.** Sketch the graph of $N_t$ versus $t$ on the axes below.

![Population versus time for logistic](figures/population-vs-time-logistic.png)

**3.** How would you describe the growth of $N_t$ as a function of $t$?

---

## Example 3: General Updating Function

The figure below shows the graph for some updating function.

![General updating function](figures/cobweb-general.png)

**1.** Use the cobwebbing technique in the graph above to find successive values of $N_1$, $N_2$, ..., assuming that $N_0=0.5$.

**2.** Use the cobwebbing technique in the graph above to find successive values of $N_1$, $N_2$, ..., assuming that $N_0=0.7$.

**3.** Sketch the graph of $N_t$ versus $t$ on the axes below for each of the two initial values considered above.

![Population versus time comparison](figures/population-vs-time-comparison.png)

**4.** What are the equilibrium points for the system described by this model?