# Single Species Population Modelling - The Malthusian Model

*Notes- Joe Foster, 2020*

## How Many?

A population is a group of organisms, all of the same species, that live together. A population can increase, by reproduction, and decrease, by death. We will start by looking at simple models that can be used to predict population size. Later on in the class we will create more sophisticated models as we consider more and more different factors that can influence population size.

Let $N$ denote the **size of the population** of whatever organism we consider. Our independent variable is **time**, $t$ - we want to know the size of a population at a given time. We will use the subscript $t$ to denote the population at a given time:

$$
N_t = \text{population size at time } t.
$$

$N_0$ will denote the population at time $t=0$, and we will refer to this as the **initial population**.

There are many reasons for a population to change, which we can categorise into four categories:

$$
\begin{aligned}
B &= \text{Births}, & D &= \text{Deaths}, \\
I &= \text{Immigration}, & E &= \text{Emigration}.
\end{aligned}
$$

Births and deaths depend on the current size of the population, but immigration and emigration depend on the movement of organisms in the population. What this means is that to study births and deaths, we just look at the population we care about. For immigration and emigration we must look at more than just the target population.

We can incorporate these factors into a mathematical expression for population growth:

$$
N_{t+1} = N_t + B - D + I - E \tag{1}
$$

where the variables $B$, $D$, $I$ and $E$ represent the number of births, deaths, immigrants entering the population and emigrants leaving the population, respectively, between times $t$ and $t+1$. We are interested in ***how the population changes over time***. We denote this change by $\Delta N = N_{t+1} - N_t$, and so by our expression, we have

$$
\Delta N = B - D + I - E. \tag{2}
$$

For now, we will make the assumption that the population is **closed**; that is, there is no immigration or emigration affecting our population. While not necessarily true in nature, to get us started this assumption will be beneficial. So, until further notice,

$$
\Delta N = B - D. \tag{3}
$$

Our next assumption that we will impose on our populations is that they grow **continuously**. That is, the time step we are using is infinitely small. This allows us to describe population growth with a smooth curve and we can model the **population growth rate**, $\frac{dN}{dt}$, with a **continuous differential equation**,

$$
\frac{dN}{dt} = B - D. \tag{4}
$$

Since we have a continuous differential equation, $B$ and $D$ now represent the **birth rate** and **death rate**, respectively. As we mentioned earlier, births and deaths depend on the current size of the population. For example, the more rabbits there are, the more births of baby bunnies will occur. If each member of the population produces the same number of offspring during the time interval, then the birth rate will be **directly proportional** to the current population. We can make a similar assumption for the death rate. Let $b$ and $d$ denote the **instantaneous birth rate** and **instantaneous death rate**, then,

$$
B = bN, \quad D = dN.
$$

Plugging this into (4) and rearranging gives

$$
\frac{dN}{dt} = (b-d)N. \tag{5}
$$

Let $r = b - d$. Then $r$ is called the **instantaneous rate of increase** or **intrinsic rate of increase**. It is also referred to as the **Malthusian parameter**, named after Thomas Robert Malthus (1766-1834). This gives us the **Malthusian growth model**

$$
\frac{dN}{dt} = rN. \tag{6}
$$

This is a simple model of **exponential population growth**. It is interpreted as follows: the population growth rate, $\frac{dN}{dt}$, is proportional to $N$ and that populations only increase if $r > 0$ (this happens when the instantaneous birth rate $b$ exceeds the instantaneous death rate $d$). The larger the population, the faster its rate of increase.

Our model is currently written as a differential equation. It tells us the population growth rate, but not the population size. To get an explicit expression for $N$, we need to *solve* the differential equation. There are lots of tools out there that deal with solving differential equations, but would you believe it, we have stumbled upon perhaps the easiest differential equation out there. Our model says that the derivative of $N$ is $r$ times $N$. Your first guess is most likely correct, and with a little integration you can verify this. So, the model for predicting population size is given by

$$
N_t = N_0 e^{rt}, \tag{7}
$$

where we recall that $N_0$ is the initial population size.

![Trajectories of exponential growth](figures/malthusian-growth.png)

*Trajectories of exponential growth of populations with varying instantaneous growth rates, $r$.*

Let's finally do some examples.

---

### Example 1

Suppose a population of zooplankton is growing over time so that the intrinsic rate of increase is 0.007 per day. Assume that plankton reproduce continuously. The initial population is $N_0 = 3$ grams.

**a)** Write the differential equation that models this situation.

<span style="color: brown;">*Solution.*</span>

$$
\frac{dN}{dt} = 0.007N
$$

**b)** Write an explicit formula for the population size of zooplankton in this situation.

<span style="color: brown;">*Solution.*</span>

$$
N = 3e^{0.007t}
$$

**c)** How long does it take for the population to reach 3.3 grams?

<span style="color: brown;">*Solution.*</span>

$$
\begin{aligned}
3.3 &= 3e^{0.007t}\\
\frac{3.3}{3} &= e^{0.007t}\\
\ln\left(\frac{3.3}{3}\right) &= 0.007t\\
t &= \frac{1}{0.007}\ln\left(\frac{3.3}{3}\right) = 13.616 \text{ days}
\end{aligned}
$$

---

### Example 2

Papua New Guinea currently has a population of 8.510 million people. The net growth rate is currently 172,753 people per year. Compute the intrinsic growth rate $r$ and write a continuous differential equation modelling the population. Give an explicit formula for the population size and use it to predict the population a decade from now.

<span style="color: brown;">*Solution.*</span>

$$
\begin{aligned}
\frac{dN}{dt} &= rN\\
r &= \frac{dN/dt}{N} = \frac{172,753}{8,510,000} = 0.0203
\end{aligned}
$$

Therefore, the differential equation is:

$$
\frac{dN}{dt} = 0.0203N
$$

The explicit formula is:

$$
N_t = 8.510e^{0.0203t}
$$

The population after 10 years:

$$
N_{10} = 8.510e^{0.0203 \cdot 10} = 10.425 \text{ million people}
$$

---

## Every _____ I'm Doubling

One property of an exponential model is that, despite its net growth depending on the current population size, the **doubling time** of the population is constant no matter the current size. That is, the time it takes for a population to grow from $100$ to $200$ is the same amount of time that it would take to grow from $800$ to $1600$ - the population will always double after a fixed time period. Solving for the doubling time is relatively simple. We want to find a time $t_D$ so that

$$
N_{t_D} = 2N_0. \tag{8}
$$

Substituting this into equation (7) yields

$$
2N_0 = N_0 e^{rt_D}. \tag{9}
$$

Solving for $t_D$ is simple now and we obtain

$$
t_D = \frac{\ln(2)}{r}. \tag{10}
$$

---

### Example 3

A population of insects has an intrinsic growth rate of $12\%$ per year.

**a)** Write the differential equation that models this situation.

<span style="color: brown;">*Solution.*</span>

$$
\frac{dN}{dt} = 0.12N
$$

**b)** Write an explicit formula for the population size of the insects in this situation.

<span style="color: brown;">*Solution.*</span>

$$
N = N_0 e^{0.12t}
$$

**c)** How long does it take for the population to double?

<span style="color: brown;">*Solution.*</span> Using the formula, we have

$$
t_D = \frac{\ln(2)}{0.12} = 5.776 \text{ years}
$$

---

## Symbol Reference

| Symbol | Meaning |
|--------|---------|
| $b$ | Instantaneous birth rate |
| $B$ | Number of births |
| $d$ | Instantaneous death rate |
| $D$ | Number of deaths |
| $\Delta N$ | Change in population size between time $t$ and $t+1$ |
| $\frac{dN}{dt}$ | Population growth rate |
| $e$ | Euler's number |
| $E$ | Number of emigrants leaving the population |
| $I$ | Number of immigrants entering the population |
| $N$ | Population size |
| $N_0$ | Initial population |
| $N_t$ | Population size at time $t$ |
| $r$ | Instantaneous rate of increase |
| $t$ | Time |
| $t_D$ | Doubling time |