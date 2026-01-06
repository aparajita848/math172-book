# Discrete Models
## One step at a time

**Warm-up: Penicillin clearance¹.** A 500 milligram penicillin pill is swallowed and immediately enters the intestine. Every five minute period after ingestion of the pill:

- (a) 10% of the penicillin in the intestine at the beginning of the period is absorbed into the plasma.
- (b) 1 mg of the penicillin in the intestine at the beginning of the period is absorbed into the plasma.

Let $I_t$ be the amount of penicillin in the intestine at the end of the $t^{th}$ five minute period after ingestion of the pill.

### Problem 1
Fill in the table below showing the population $I_t$ of penicillin $t^{th}$ five minute period later.

| mins | t | (a) $I_t$ | (b) $I_t$ |
|------|---|-----------|-----------|
| 0 | 0 | 500 | 500 |
| 5 | 1 | 450 | 499 |
| 10 | 2 | 405 | 498 |
| 15 | 3 | 364.5 | 497 |
| 20 | 4 | 328.05 | 496 |
| 25 | 5 | 295.25 | 495 |
| 30 | 6 | 265.72 | 494 |
| 35 | 7 | 239.15 | 493 |
| 40 | 8 | 215.23 | 492 |
| 45 | 9 | 193.71 | 491 |
| 50 | 10 | 174.34 | 490 |

### Problem 2
Complete the following equations:

**Initial Conditions:** $I_0 = 500$

**Penicillin change per time period** = Penicillin added - Penicillin removed

**(a)** $\Delta I = I_{t+1} - I_t = -0.1 I_t$

**(b)** $\Delta I = I_{t+1} - I_t = -1$

**Penicillin conc. at $t$:**

**(a)** $I_t = 500(0.9)^t$

**(b)** $I_t = 500 - 1 \cdot t$

### Problem 3
Calculate the amount of penicillin in the intestine after 50 five-minute periods for both scenarios.

**Penicillin conc. at $t=50$:**

**(a)** $I_{50} = 500(0.9)^{50} = 2.58$ mg

**(b)** $I_{50} = 500 - 1 \cdot (50) = 450$ mg

---

## Introduction to Discrete Models

For many organisms time isn't really a continuous variable. For example, birds may reproduce seasonally and not constantly throughout the year. Some plants and insects die after reproducing and the population after this event is made up of only the offspring. This population has what are called **non-overlapping generations** and is modelled with a **discrete difference equation** instead of the continuous differential equations we have already seen.

$$\Delta N = N_{t+1} - N_t$$

Suppose that a population increases (or decreases) by a constant rate each time period (day, month, year etc.). Call this rate $r$, the **discrete growth factor**. Then,

$$N_{t+1} = N_t + rN_t$$

Let's combine terms,

$$N_{t+1} = (1+r)N_t$$

We call $\lambda = 1 + r$ the **finite rate of increase** or **growth ratio**. Thus

$$N_{t+1} = \lambda N_t$$

The ratio of the population size during the next time period to the population size at the current time is precisely $\lambda$. After two time periods, the population size is

$$N_2 = \lambda N_1 = \lambda(\lambda N_0) = \lambda^2 N_0$$

This type of equation is called a **recursion equation**, or **updating equation**. The input for the next step is the output for the current step. Repeating this process we obtain

$$N_t = \lambda^t N_0$$

Compare this to our continuous model from before, $N_t = N_0 e^{rt}$, and it doesn't look drastically different. Indeed, $\lambda = e^r$ makes the models the same. The key difference here is that the **population changes at discrete time steps**, i.e. when $t$ is an integer.

---

## Example 1
Under the right conditions, some types of bacteria will divide every 20 minutes. That is, the population will double every 20 minutes. Starting with just one bacterium, how many will there be after an hour?

**Solution:**
First let's derive an equation to model the population of the bacteria. Since the population doubles every 20 minutes, $\lambda = 2$ and $t$ is the number of 20 minute intervals that have occurred. (It's worth mentioning that $\lambda = 1 + r = 2$ means $r = 1$. That is, the population increases by 100 percent.) And $N_0 = 1$ so,

$$N_t = \lambda^t N_0 = 2^t$$

One hour is $3 \times 20$ minute intervals, so $t = 3$, and so

$$N_3 = 2^3 = 8$$

If we had used our continuous model, we would have

$$\frac{dN}{dt} = N \Rightarrow N_t = e^t \Rightarrow N_3 = e^3 = 20.086$$

This is very different to the actual answer. This is because the continuous model is constantly reacting to changes in the population. The continuous model assumes that each infinitesimal amount of time that passes increases the population by some amount and so the number of cells being produced is constantly changing. When in reality you would have to wait 20 minutes before seeing any change in the population.

---

## Plotting Discrete Models

When it comes to plotting this model, we can get some interesting graphs. If there are no deaths to a population and only an increase, then we obtain a graph that looks like a staircase with increasingly steeper steps. More interestingly, if reproduction happens discretely but deaths occur continuously throughout the year, for example sheep that give birth each spring, then we get a jagged graph with larger and larger "teeth" as time goes by.

*(Graphs would show: A discrete model with no death and only reproduction (left) and a model with discrete reproduction and continuous death (right).)*

---

## Example 2
A population of 20 killifish is introduced into a pond. These fish breed once a year. Assume the per capita growth rate of the fish is 0.31 (fish/year)/fish.

**a) Give a formula for the number of fish after $t$ years.**

The growth ratio is $\lambda = 1 + 0.31 = 1.31$, thus

$$N_t = 20(1.31)^t$$

**b) How long will it take for there until there are 2,000 fish in the pond?**

$$20(1.31)^t = 2000 \Rightarrow 1.31^t = 100 \Rightarrow t\ln(1.31) = \ln(100) \Rightarrow t = \frac{\ln(100)}{\ln(1.31)} = 17.05 \text{ years}$$

Since the fish breed once a year, the population will pass 2,000 in year 18.

---

## Example 3
In a different pond, 50 of the killifish are released. The population is counted five years later and there are 213 of the fish. What is the per capita growth rate of the population?

**Solution:**

$$50\lambda^5 = 213 \Rightarrow \lambda^5 = \frac{213}{50} \Rightarrow \lambda = \sqrt[5]{\frac{213}{50}} = 1.336$$

so,

$$r = \lambda - 1 = 1.336 - 1 = 0.336 \text{ (fish/year)/fish}$$

---

## Summary

To summarize, discrete models are appropriate for situations where reproduction happens after specific time-intervals; the new offspring are all added in a single burst. For example, seasonally reproducing organisms such as Mayflies or turtles, or experiments where observations happen at regular time-intervals. *(Note that they are a **type** of models, separate from the continuous models which were represented using differential equations. It does not include just one population growth model, but several models where time is not represented continuously.)*

- **time is discrete** → $t$ is an integer, counting the number of distinct time-intervals $\Delta t$. *($t$ can also be seen as an index, representing the count through the observations.)*
- **Population size as a sequence** → $N_t$ is the measurement after $t$ time-intervals or observations. $N_0$ is the initial value and $N_t$ would be the measurement after $t$ observations.

**Discrete-difference equation:** $\boxed{\Delta N = N_{t+1} - N_t}$ *(can also be written as $\frac{\Delta N}{\Delta t}$, where $\Delta t = 1$ or after each unit time interval, where the unit time is dependent on the problem.)*

**Recursive equation:** $\boxed{N_{t+1} = N_t + \Delta N}$ *(relates the population at the next time-step ($t+1$) to the current time step ($t$).)*

**Solution/explicit-formula:** $\boxed{N_t}$ *(function of $t$, and $N_0$, formulated after finding the pattern followed by the recursive equation.)*

### Model Types:

**Linear Discrete Model:**
- Discrete difference equation: $\Delta N = c$, some constant.
- Recursive equation: $N_{t+1} = N_t + c$
- General formula/explicit solution: $N_t = N_0 + ct$

**Exponential Discrete Model:**
- Discrete difference equation: $\Delta N = rN_t$, $r$ is the growth/decay rate.
- Recursive equation: $N_{t+1} = N_t(1+r) = N_t \cdot \lambda$
- General formula/explicit solution: $N_t = N_0\lambda^t$
  - **growth** when $r > 0 \Rightarrow \lambda > 1$
  - **decay** when $r < 0 \Rightarrow 0 < \lambda < 1$

---

## Derivations of Formulae

**1. For a discrete model with a constant $\Delta N = c$**

The recursive equation is given by

$$N_{t+1} = N_t + c$$

Given the initial value, $N_0$, we can find:

$$N_1 = N_0 + c$$
$$N_2 = N_1 + c = N_0 + c + c = N_0 + 2c$$
$$N_3 = N_2 + c = N_0 + 2c + c = N_0 + 3c$$
$$N_4 = N_3 + c = N_0 + 3c + c = N_0 + 4c$$
$$\vdots$$
$$N_t = N_0 + ct$$

Therefore, in such a case, the explicit solution is a **linear** equation:

$$N_t = N_0 + \Delta N \cdot t$$

*You can think of such a population growing linearly, the difference between the population at consecutive time-steps is the slope $\Delta N = N_{t+1} - N_t$.*

**2. For a discrete model with $\Delta N$ proportional to the population size**

The discrete difference equation is given by:

$$\Delta N = rN_t$$

where $r$ is the growth/decay rate. The recursive equation is given by

$$N_{t+1} = N_t + \Delta N = N_t + rN_t = N_t(1+r) = N_t \lambda$$

Given the initial value, $N_0$, we can find:

$$N_1 = N_0 \lambda$$
$$N_2 = N_1\lambda = N_0 \cdot \lambda \cdot \lambda = N_0 \lambda^2$$
$$N_3 = N_2\lambda = N_0 \cdot \lambda^2 \cdot \lambda = N_0 \lambda^3$$
$$N_4 = N_3\lambda = N_0 \cdot \lambda^3 \cdot \lambda = N_0 \lambda^4$$
$$\vdots$$
$$N_t = N_0 \lambda^t$$

The explicit solution is an **exponential** equation:

$$N_t = N_0\lambda^t, \quad \lambda = 1 + r$$

where $r$ is the growth/decay rate (written as a decimal).

*Here the difference between the population at consecutive time-steps is not constant, but their ratio is $\frac{N_{t+1}}{N_t} = \lambda$, the population increases by a multiple $\lambda$ each time.*

---

## Practice Problems²

**1.** Suppose a human population is growing at 1% per year and initially has 1,000,000 individuals. Let $P_t$ denote the population size $t$ years after the initial population of $P_0 = 1,000,000$ individuals. What will the population be in 50 years?

**Solution:**
- **Discrete Difference Equation:** $\Delta P = rP_t = 0.01P_t$
- **Recursive Equation:** $P_{t+1} = P_t + \Delta P = \lambda P_t = (1.01)P_t$
- **Explicit Formula:** $P_t = P_0\lambda^t = 1,000,000(1.01)^t$

In 50 years $\Rightarrow t = 50$:

$$P_{50} = 1,000,000(1.01)^{50} \approx 1,644,631 \text{ individuals}$$

The population will have approximately 1,644,631 individuals after 50 years according to this model.

---

**2.** If a restaurant purchases 500 lbs of rice and uses approximately 20 lbs each day for their dishes, how long will this purchase of rice last?

**Solution:**
- **Discrete Difference Equation:** $\Delta R = -20$
- **Recursive Equation:** $R_{t+1} = R_t + \Delta R = R_t - 20$
- **Explicit Formula:** $R_t = 500 - 20t$

To find out how long the rice would last, we can set $R_t = 0$ and solve for $t$:

$$R_t = 500 - 20t = 0$$
$$500 = 20t$$
$$t = \frac{500}{20} = 25 \text{ days}$$

The restaurant would take 25 days to use up the 500 lbs of rice purchased.

---

**3.** I start with 2 chocolate bars. Every day, I eat 10% of the chocolate that I started the day with. Write down a dynamical system describing the chocolate I have left after each day and determine how much chocolate I have left after two weeks.

**Solution:**
- **Discrete Difference Equation:** $\Delta C = rC_t = -0.1C_t$
- **Recursive Equation:** $C_{t+1} = \lambda C_t = (0.9)C_t$
- **Explicit Formula:** $C_t = C_0\lambda^t = 2(0.9)^t$

After 2 weeks $\Rightarrow t = 14$ days *(assuming that $t$ is in days and $C$ is in bars of chocolate)*:

$$C_{14} = 2(0.9)^{14} \approx 0.458 \text{ chocolate bars}$$

There will be 0.458 or 45.8% of a chocolate bar left after two weeks.

---

**4.** The polymerase chain reaction is a means of making multiple copies of a DNA segment from only a minute amount of original DNA. The procedure consists of a sequence of multiple cycles. During the course of one cycle, each DNA segment present is duplicated. Introduce notation and write a discrete dynamical system with initial condition from which the amount of DNA present at the end of each cycle can be computed. Suppose you begin with 1 picogram = 0.000000000001 g of DNA. How many grams of DNA would be present after 30 cycles.

**Solution:**
- **Discrete Difference Equation:** $\Delta D = rD_t = D_t$
- **Recursive Equation:** $D_{t+1} = \lambda D_t = 2D_t$
- **Explicit Formula:** $D_t = D_0\lambda^t = 0.000000000001 \cdot 2^t = 10^{-12} \cdot 2^t$

After 30 cycles $\Rightarrow t = 30$ *(assuming that $t$ represents number of cycles and $D$ is in grams of DNA.)*:

$$D_{30} = 0.000000000001 \cdot 2^{30} \approx 0.001074 \text{ grams}$$

There will be approximately 0.001074 grams of DNA present after 30 cycles.

---

## Notation Summary

| Symbol | Meaning |
|--------|---------|
| $b$ | Instantaneous birth rate |
| $d$ | Instantaneous death rate |
| $\Delta N$ | Change in population size between time $t$ and $t+1$ |
| $\frac{dN}{dt}$ | Population growth rate |
| $e$ | Euler's number |
| $\lambda$ | Finite rate of increase *(growth factor)* |
| $N$ | Population size |
| $N_0$ | Initial population |
| $N_t$ | Population size at time $t$ |
| $r$ | Instantaneous rate of increase/discrete growth rate |
| $t$ | Time |
| $t_D$ | Doubling time |

---

**References:**
1. Penicillin clearance problem
2. https://mathinsight.org/exponential_growth_decay_discrete_exercises