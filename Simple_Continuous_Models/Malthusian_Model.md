# The Malthusian (Unlimited) Growth Model
% ## Single-species Population Model


## Introduction

A population is a group of organisms, all of the same species, that live together. A population can increase, by reproduction, and decrease, by death. We will start by looking at simple models that can be used to predict population size. Later on in the class we will create more sophisticated models as we consider more and more different factors that can influence population size.

:::{note} Notation
Let $N$ denote the **size of the population** of whatever organism we consider. Our independent variable is **time**, $t$ - we want to know the size of a population at a given time. We will use the subscript $t$ to denote the population at a given time:

$$
\begin{equation*}
N_t = \text{population size at time } t.
\end{equation*}
$$

$N_0$ will denote the population at time $t=0$, and we will refer to this as the **initial population**.

:::

Making the assumption that the population is **closed**; that is, there is no immigration or emigration; the population changes with time only due to births and mortality. Consider the changes that take place in the population size between time $t$ and $t+h$,
where $\Delta t = h$ is a small time increment. Then

$$
\begin{equation*}
\begin{align*}
    \Delta N = N(t+h)-N(t) =& [\text{Change in $N$}]\\
    =& [\text{Number of births}] - [\text{Number of deaths}]
\end{aligned}
\end{equation*}
$$ 

This equation is sometimes called a **balance equation** as it helps us keep track of people entering and leaving the population. We use it to derive a differential equation linking the derivative of $N$ to the value of $N$ at the given time.

Notice that dividing each term by the time interval $h$, we obtain:

$$
\begin{equation*}
\begin{aligned}
\dfrac{N(t+h)-N(t)}{h}=\left[\dfrac{\text{Number of births}}{h}\right] - \left[\dfrac{\text{Number of deaths}}{h}\right]
\end{aligned}
\end{equation*}
$$

Our next assumption that we will impose on our populations is that they grow **continuously**. That is, the time step we are using is infinitely small. This allows us to describe population growth with a smooth curve and we can model the **population growth rate**, ${dN}/{dt}$, with a **continuous differential equation**. Therefore, if we shrink the time interval, $h\to 0$ (limit as $h$ goes to 0), the term on the left-hand-side is the derivative $\dfrac{dN}{dt}$, so

:::{math}
:label: rate_birth_death
\dfrac{dN}{dt}=\left[\text{Number of births per unit time}\right] - \left[\text{Number of deaths per unit time}\right]
:::

For simplicity, we finally assume that all individuals are identical and that the number of births per unit time is :::directly proportional::: to the population size. For example, the more rabbits there are, the more births of baby bunnies will occur. If each member of the population produces the same number of offspring during the time interval, then the birth rate will be directly proportional to the current population. Denote by $b$ the constant of proportionality. Similarly, we assume that the number of deaths per unit time is also directly proportional to population size with $d$ the constant of proportionality.

\begin{equation*}
\begin{aligned}
    b =& \text{per capita birth rate} = \dfrac{\text{number of births per unit time}}{\text{population size}}\\
    d =& \text{per capita death rate} = \dfrac{\text{number of deaths per unit time}}{\text{population size}}
\end{aligned}
\end{equation*}

Consequently, we have
\begin{equation*}
\begin{aligned}
    \text{Number of births per unit time} =& bN\\
    \text{Number of deaths per unit time} =& dN
\end{aligned}
\end{equation*}

We refer to constants such as $b,d$ as **parameters**. In general, for a given population, these would have specific numerical values that could be found through experiment, by collecting data, or by making simple assumptions.  Taking the assumptions and the form of the balance equation [](#rate_birth_death) together we have:

$$
\begin{equation*}
\dfrac{dN}{dt}=bN-dN=(b-d)N
\end{equation*}
$$

This gives us the **Malthusian growth model** named after Thomas Robert Malthus (1766-1834).

Recall that this is a differential equation: it links the derivative of $N(t)$ to the function $N(t)$. By solving the equation (i.e. identifying its solution), we are be
able to make a projection about how fast a population is growing.

Define the constant $r = b -d$. Then $r$ is the **intrinsic** or **instantaneous growth rate**, of the population, so

:::{math}
:label: rate_birth_death_2
\dfrac{dN}{dt}=rN,\quad \text{ for } r=d-b
:::

Suppose we also know that at time $t = 0$, the population size is $N_0$. Then:

:::{math}
:label: rate_birth_death_sol
N(t)=N_0e^{rt}=N_0e^{(b-d)t}
:::

- Since $N(t)$ represents a population size, it has to be non-negative to have
biological relevance. This is true so long as $N_0 > 0$.
- The initial condition $N(0) = N_0$, allows us to specify the (otherwise
arbitrary) constant multiplying the exponential function.
- The population **grows** provided $r > 0$ which happens when $b > d > 0$ i.e.
**when birth rate exceeds mortality rate**.
- If $r < 0$, or equivalently, $b < d$ then more people die on average than are
born, so that the population shrinks and (eventually) go extinct.

%Add simulation
---

## Doubling-Time & Half-life

One property of an exponential model is that, despite its net growth depending on the current population size, the **doubling time** of the population is constant no matter the current size. That is, the time it takes for a population to grow from $100$ to $200$ is the same amount of time that it would take to grow from $800$ to $1600$ - the population will always double after a fixed time period. For a growing population ($r>0$), solving for the doubling time is relatively simple. We want to find a time $t_D$ so that 
$$
\begin{equation*}
N_{t_D}=2N_0.
\end{equation*}
$$

Substituting this into equation [](#rate_birth_death_sol) yields
$$
\begin{equation*}
2N_0=N_0e^{rt_D}.
\end{equation*}

Solving for $t_D$ is simple now and we obtain the **doubling-time**:
$$
\begin{equation*}
t_D=\frac{\ln(2)}{r}.
\end{equation*}
$$

Similarly, for a **decaying population with negative growth rate** ($r<0$):
$$
\begin{equation*}
N_{t_H}=\dfrac{N_0}{2}.
\end{equation*}
$$

Substituting this into equation [](#rate_birth_death_sol) yields
$$
\begin{equation*}
\begin{aligned}
\dfrac{N_0}{2}=&N_0e^{rt_H}.\\
\dfrac{1}{2}=&e^{rt_H}.\\
\ln\left(\dfrac{1}{2}\right)=&rt_H.
\end{aligned}
\end{equation*}
$$

The **half-life** is given by:
$$
\begin{equation*}
t_H = \frac{\ln(1/2)}{r}=& \dfrac{- \ln(2)}{r},\quad r<0.
\end{equation*}
$$


---

## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true

Suppose a population of zooplankton is growing over time so that the intrinsic rate of increase is 0.007 per day. Assume that plankton reproduce continuously. The initial population is $N_0=3$ grams.

(a) Write the differential equation that models this situation.
(b) Write an explicit formula for the population size of zooplankton in this situation.
(c) How long does it take for the population to reach 3.3 grams?

:::
:::{tip} Solution to Exercise 1
:icon: false
:class: dropdown
(a) $\frac{dN}{dt}=0.007N$

(b) $N=3e^{0.007t}$

(c)
$$
\begin{equation*}
\begin{aligned}
3.3=&3e^{0.007t} \\
\frac{3.3}{3}=&e^{0.007t} \\
\ln\left(\frac{3.3}{3}\right)=&0.007t \\
t=&\frac{1}{0.007}\ln\left(\frac{3.3}{3}\right) = 13.616\text{ days}
\end{aligned}
\end{equation*}
:::


:::{tip} Exercise 2
:class: dropdown
:open: true

A population of insects has an intrinsic growth rate of $12\%$ per year. Suppose that initially there are 100 insects.

(a) Write the differential equation that models this situation.
(b) Write an explicit formula for the population size of the insects in this situation. 
(c) How long does it take for the population to double? 

:::

:::{tip} Solution to Exercise 2
:icon: false
:class: dropdown
(a) $\dfrac{dN}{dt}=0.12N$

(b) $N_t=100e^{0.12t}$

(c) 
$$
\begin{equation*}
\begin{aligned}
N_t=100e^{0.12t} =& 200 \\
e^{0.12t} =& \dfrac{200}{100} \\
\ln(e^{0.12t}) =& \ln(2) \\
0.12t =& \ln(2) \\
t=&\frac{\ln(2)}{0.12}=5.776\text{ years}
\end{aligned}
\end{equation*}
$$
:::
