# Simple Discrete Models
## Introduction

:::{tip} Warm-up
:class: dropdown
:open: true

:::

For many organisms time isn't really a continuous variable. For example, birds may reproduce seasonally and not constantly throughout the year. Some plants and insects die after reproducing and the population after this event is made up of only the offspring. This population has what are called **non-overlapping generations** and is modeled with a **discrete difference equation** instead of the continuous differential equations we have already seen.

$$
\begin{equation*}
\Delta N=N_{t+1}-N_t
\end{equation*}
$$

Suppose that a population increases (or decreases) by a constant rate each time period (day, month, year etc.). Call this rate $r$, the **discrete growth factor**. Then,

$$
\begin{equation*}
N_{t+1}=N_t+rN_t.
\end{equation*}
$$

Let's combine terms,

$$
\begin{equation*}
N_{t+1}=(1+r)N_t.
\end{equation*}
$$

We call $\lambda=1+r$ the **finite rate of increase** or **growth ratio**. Thus

$$
\begin{equation*}
N_{t+1}=\lambda N_t.
\end{equation*}
$$

The ratio of the population size during the next time period to the population size at the current time is precisely $\lambda$. After two time periods, the population size is

$$
\begin{equation*}
N_2=\lambda N_1=\lambda\left(\lambda N_0\right)=\lambda^2N_0.
\end{equation*}
$$

This type of equation is called a **recursion equation**, or **updating equation**. The input for the next step is the output for the current step. Repeating this process we obtain

$$
\begin{equation*}
N_t=\lambda^tN_0.
\end{equation*}
$$

Compare this to our continuous model from before, $N_t=N_0e^{rt}$, and it doesn't look drastically different. Indeed, $\lambda=e^r$ makes the models the same. The key difference here is that the **population changes at discrete time steps**, i.e. when $t$ is an integer. Let's look at an example.

### Example 1

Under the right conditions, some types of bacteria will divide every $20$ minutes. That is, the population will double every $20$ minutes. Starting with just one bacterium, how many will there be after an hour?

:::{tip} Solution
:icon: false
:class: dropdown

First let's derive an equation to model the population of the bacteria. Since the population doubles every $20$ minutes, $\lambda=2$ and $t$ is the number of $20$ minute intervals that have occurred. (Its worth mentioning that $\lambda=1+r=2$ means $r=1$. That is, the population increases by $100$ percent.) And $N_0=1$ so,

$$
\begin{equation*}
N_t=\lambda^t N_0=2^t.
\end{equation*}
$$

One hour is $3\times20$ minute intervals, so $t=3$, and so

$$
\begin{equation*}
N_3=2^3=8.
\end{equation*}
$$

:::

:::{note} 
If we had used our continuous model, we would have

$$
\begin{equation*}
\frac{dN}{dt}=N\Longrightarrow N_t=e^t\Longrightarrow N_3=e^3=20.086.
\end{equation*}
$$

This is very different to the actual answer. This is because the continuous model is constantly reacting to changes in the population. The continuous model assumes that each infinitesimal amount of time that passes increases the population by some amount and so the number of cells being produced is constantly changing. When in reality you would have to wait $20$ minutes before seeing any change in the population.
:::

When it comes to plotting this model, we can get some interesting graphs. If there are no deaths to a population and only an increase, then we obtain a graph that looks like a staircase with increasingly steeper steps. More interestingly, if reproduction happens discretely but deaths occur continuously throughout the year, for example sheep that give birth each spring, then we get a jagged graph with larger and larger ``teeth'' as time goes by.

#Add plots - A discrete model with no death and only reproduction (left) and a model with discrete reproduction and continuous death (right).

### Example 2

A population of $20$ killifish is introduced into a pond. These fish breed once a year. Assume the per capita growth rate of the fish is $0.31$ (fish/year)/fish.

(a) Give a formula for the number of fish after $t$ years.

:::{tip} Solution
:icon: false
:class: dropdown

The growth ratio is $\lambda=1+0.31=1.31$, thus

$$
\begin{equation*}
N_t=20\left(1.31\right)^t
\end{equation*}
$$

:::

(b) Give a formula for the number of fish after $t$ years.

:::{tip} Solution
:icon: false
:class: dropdown

The growth ratio is $\lambda=1+0.31=1.31$, thus

$$
\begin{equation*}
\begin{aligned}
20\left(1.31\right)^t=&2,000\\
1.31^t=&100\\
t\ln\left(1.31\right)=&\ln\left(100\right)\\
t=&\frac{\ln\left(100\right)}{\ln\left(1.31\right)}=17.05\text{ years}
\end{aligned}
\end{equation*}
$$

Since the fish breed once a year, the population will pass $2,000$ in year $18$.
:::

### Example 3

In a different pond, $50$ of the killifish are released. The population is counted five years later and there are $213$ of the fish. What is the per capita growth rate of the population?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
50\lambda^5=213\Longrightarrow\lambda^5=\frac{213}{50}\Longrightarrow\lambda=\sqrt[5]{\frac{213}{50}}=1.336
\end{equation*}
$$

so,

$$
\begin{equation*}
r=\lambda-1=1.336-1=0.336\text{ (fish/year)/fish}
\end{equation*}
$$

:::

To summarize, discrete models are appropriate for situations where reproduction happens after specific time-intervals; the new offspring are all added in a single burst. For example, seasonally reproducing organisms such as Mayflies or turtles, or experiments where observations happen at regular time-intervals. _(Note that they are a **type** of models, separate from the continuous models which were represented using differential equations. It does not include just one population growth model, but several models where time is not represented continuously.)_

  - **_time is discrete_** $\longrightarrow$ $t$ is an integer, counting the number of distinct time-intervals $\Delta t$. _($t$ can also be seen as an index, representing the count through the observations.)_
  - **_Population size as a sequence_** $\longrightarrow$ $N_t$ is the measurement after $t$ time-intervals or observations. $N_0$ is the initial value and $N_t$ would be the measurement after $t$ observations.


**Discrete-difference equation:** $\boxed{\Delta N = N_{t+1}-N_t}$ _(can also be written as $\frac{\Delta N}{\Delta t}$, where $\Delta t = 1$ or after each unit time interval, where the unit time is dependent on the problem.)_ \\

**Recursive equation:** $\boxed{N_{t+1}=N_t+\Delta N}$ _(relates the population at the next time-step ($t+1$) to the current time step ($t$).)_

**Solution/explicit-formula:** $\boxed{N_t}$ _(function of $t$, and $N_0$, formulated after finding the pattern followed by the recursive equation.)_

:::{important} Summary:
:icon: false
:class: dropdown

- **Linear Discrete Model**:

$$
\begin{equation*}
    \begin{aligned}
        \text{discrete difference equation:}\quad &\Delta N = c,\quad \textit{ some constant}.\\
        \text{ recursive equation:}\quad &N_{t+1} = N_t + c\\
        \text{general formula/explicit solution:}\quad &N_t = N_0 + ct
    \end{aligned}
\end{equation*}
$$

- **Exponential Discrete Model**:

$$
\begin{equation*}
    \begin{aligned}
        \text{ discrete difference equation:}\quad &\Delta N = rN_t,\quad  r\; \text{is the growth/decay rate.}\\
        \text{recursive equation:}\quad &N_{t+1} = N_t (1+r) = N_t\cdot \lambda \\
        \text{ general formula/explicit solution:}\quad &N_t = N_0\lambda^t
    \end{aligned}
\end{equation*}
$$

  - **_growth_** when $r>0 \implies \lambda > 1$
  - **_decay_** when $r<0 \implies0<\lambda <1$

:::

:::{important} Derivations of formulae:
:icon: false
:class: dropdown

\begin{enumerate}
- For a discrete model, with a **constant** $\Delta N=c$ (the discrete difference is some constant $C$), then the recursive equation is given by

$$
\begin{equation*}
    \begin{aligned}
        N_{t+1} =& N_t + c,\quad \text{given the initial value, $N_0$, we can find:}\\
        N_1 =& N_0 + c\\
        N_2 = N_1 + c =& N_0 +c+c = N_0 + 2c\\
        N_3 = N_2 + c =& N_0 + 2c + c = N_0 + 3c \\
        N_4 = N_3 + c =& N_0 + 3c + c = N_0 + 4c \\
        .\\
        .\\
        .\\
        N_t =& N_0 + ct
    \end{aligned}
\end{equation*}
$$

Therefore, in such a case, the explicit solution is a **linear** equation : 

$$
\begin{equation*}
N_t = N_0+\Delta N\cdot t
\end{equation*}
$$

_You can think of such a population growing linearly, the difference between the population at consecutive time-steps is the slope $\Delta N = N_{t+1}-N_t$ ._

- For a discrete model, with a $\Delta N$ **proportional to the population size** or a **percent increase/decrease**, then, the discrete difference equation is given by:

$$
\begin{equation*}
\Delta N = rN_t
\end{equation*}
$$

where $r$ is the growth/decay rate. The recursive equation is given by

$$
  \begin{equation*}
  \begin{aligned}
        N_{t+1} =& N_t + \Delta N\\
        =& N_t +rN_t\\
        =& N_t(1+r)\\
        =& N_t \;\lambda,\quad \text{given the initial value, $N_0$, we can find:}\\
        N_1 =& N_0 \;\lambda \\
        N_2 =& N_1\lambda = N_0 \cdot \lambda\cdot \lambda = N_0 \lambda^2\\
        N_3 =& N_2\lambda = N_0 \cdot \lambda^2\cdot \lambda = N_0 \lambda^3 \\
        N_4 =& N_3\lambda = N_0 \cdot \lambda^3\cdot \lambda = N_0 \lambda^4 \\
        .\\
        .\\
        .\\
        N_t =& N_0 \lambda^t
  \end{aligned} 
  \end{equation*}
$$

explicit solution is an **exponential** equation : 

$$
\begin{equation*}
N_t = N_0\lambda^ t,\quad \lambda = 1 + r
\end{equation*}
$$

where $r$ is the growth/decay rate (written as a decimal). 
    
_Here the difference between the population at consecutive time-steps is not constant, but their ratios is $\dfrac{N_{t+1}}{N_t}=\lambda$, the population increases by a multiple $\lambda$ each time._

:::
___

## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true

Suppose a human population is growing at 1\% per year and initially has 1,000,000 individuals. Let $P_t$ denote the populations size $t$ years after the initial population of $P_0=1,000,000$ individuals. What will the population be in 50 years?
:::

:::{tip} Solution to Exercise 1
:icon: false
:class: dropdown

**Discrete Difference Equation:** $\Delta P=rP_t=0.01P_t$

**Recursive Equation:** $P_{t+1}=P_t+\Delta P=\lambda P_t = (1.01)P_t$

**Explicit Formula:** $P_t = P_0\lambda^t = 1,000,000 (1.01)^t $

In 50 years $\implies t=50$:

$$
\begin{equation*}
P_{50}=1,000,000(1.01)^{50} \approx 1,644,631 \;\text{individuals}
\end{equation*}
$$

The population will have approximately 1,644,631 individuals after 50 years according to this model.

:::


:::{tip} Exercise 2
:class: dropdown
:open: true

If a restaurant purchases 500 lbs of rice and uses approximately 20 lbs each day for their dishes, how long will this purchase of rice last? 
:::

:::{tip} Solution to Exercise 2
:icon: false
:class: dropdown

**Discrete Difference Equation:** $\Delta R=-20$

**Recursive Equation:** $R_{t+1}=R_t+\Delta R = R_t - 20$

**Explicit Formula:** $R_t = 500-20t $

To find out how long the rice would last, we can set $R_t=0$ and solve for $t$:

$$
\begin{equation*}
\begin{aligned}
    R_t=500-20t=&0\\
    500=&20t\\
    t=&\dfrac{500}{20}=25\;\text{days}
\end{aligned}
\end{equation*}
$$

The restaurant would take 25 days to use up the 500 lbs of rice purchased.

:::

:::{tip} Exercise 3
:class: dropdown
:open: true

I start with 2 chocolate bars. Every day, I eat 10\% of the chocolate that I started the day with. Write down a dynamical system describing the chocolate I have left after each day and determine how much chocolate I have left after two weeks.

:::

:::{tip} Solution to Exercise 3
:icon: false
:class: dropdown

**Discrete Difference Equation:** $\Delta C=rC_t=-0.1C_t$

**Recursive Equation:** $C_{t+1}=\lambda C_t = (0.9)C_t$

**Explicit Formula:** $C_t = C_0\lambda^t = 2 (0.9)^t $

After 2 weeks $\implies t=14$ days _(assuming that $t$ is in days and $C$ is in bars of chocolate)_:

$$
\begin{equation*}
C_{14} = 2 (0.9)^{14} \approx 0.458 \;\text{chocolate bars}
\end{equation*}
$$

There will be 0.458 or 45.8\% of a chocolate bar left after two weeks.

:::

:::{tip} Exercise 4
:class: dropdown
:open: true

The polymerase chain reaction is a means of making multiple copies of a DNA segment from only a minute amount of original DNA. The procedure consists of a sequence of multiple cycles. During the course of one cycle, each DNA segment present is duplicated. Introduce notation and write a discrete dynamical system with initial condition from which the amount of DNA present at the end of each cycle can be computed. Suppose you begin with 1 picogram = 0.000000000001 g of DNA. How many grams of DNA would be present after 30 cycles.
 
:::

:::{tip} Solution to Exercise 4
:icon: false
:class: dropdown

**Discrete Difference Equation:** $\Delta D=rD_t=D_t$

**Recursive Equation:** $D_{t+1}=\lambda D_t = 2D_t$

**Explicit Formula:** $D_t = D_0\lambda^t = 0.000000000001\cdot 2^t = 10^{-13}\cdot 2^t$

After 30 cycles $\implies t=30$ _(assuming that $t$ represents number of cycles and $D$ is in grams of DNA.)_:

$$
\begin{equation*}
D_{30} = 0.000000000001\cdot 2^{30} \approx 0.001074 \;\text{grams}
\end{equation*}
$$

There will be approximately 0.001074 grams of DNA present after 30 cycles.

:::


