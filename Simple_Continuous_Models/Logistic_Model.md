# Logistic (Limited) Growth Model


## Introduction

In the Malthusian model, we encountered the differential equation:

$$
\begin{equation*}
\dfrac{dN}{dt}=rN,
\end{equation*}
$$

where $N(t)$ is the population size at time $t$ and $r$ is the constant representing per capita growth rate. We showed that this differential equation has exponential solutions. It means that two behaviours are generically obtained: explosive growth if $r > 0$ or extinction if $r < 0$.

The case of $r > 0$ is unrealistic in the long-run, since real populations cannot keep growing indefinitely in an explosive, exponential way. Eventually running out of space or resources, the population growth dwindles, and the population attains some static level rather than expanding forever. This motivates a revision of our previous model to depict **density-dependent growth**.

Intuitively, the higher the population, the more resources are being used. So, as resources deplete, the birth rate should slow down. If it doesn't, the resources run dry and everybody dies. We start with the familiar exponential model

$$
\begin{equation*}
\frac{dN}{dt}=(b'-d')N,
\end{equation*}
$$

but instead of $b'$ and $d'$ being constant, we will modify them to be density dependent and reflect **_crowding_**.

As a population becomes more crowded, we expect the per capita birth rate to decrease, since there are fewer resources per organism available. So let's start with the simplest decreasing function - a straight line with negative slope.

$$
\begin{equation*}
b'=b-aN
\end{equation*}
$$

where $b$ and $a$ are constants. Notice how if the population is small then $b'\approx b$, so then we are essentially in the ideal conditions of unlimited resources. Then as $N$ grows larger we move away from that. So, $b$ is the same as it was in the exponential model - it is the instantaneous per capita birth rate when resources are unlimited. The constant $a$ measures the strength of the density dependence. If $a$ is large, then the birth rate drops sharply as the population grows. If there is no dependence on population - i.e. $a=0$ - then we obtain the exponential model as before. So we are generalizing our model. The same idea can be applied to death rates - as the population grows, death rates should increase. So,

$$
\begin{equation*}
d'=d+cN
\end{equation*}
$$

for constants $d$ and $c$, where $d$ is as in the exponential model and $c$ is the strength of the density dependence. Combining the above equations then, we have

$$
\begin{equation*}
\frac{dN}{dt}=\left((b-aN)-(d+cN)\right)N=\left((b-d)-(a+c)N\right)N.
\end{equation*}
$$

If we multiply this equation by $1=(b-d)/(b-d)$, then we have

$$
\begin{equation*}
\frac{dN}{dt}=(b-d)\left(1-\frac{(a+c)}{(b-d)}N\right)N.
\end{equation*}
$$

As with the exponential model, let $r=b-d$ and define 

$$
\begin{equation*}
K=\frac{(b-d)}{(a+c)},
\end{equation*}
$$

called the **carrying capacity**. Then our model becomes

$$
\begin{equation*}
\frac{dN}{dt}=rN\left(1-\frac{N}{K}\right).
\end{equation*}
$$

This is the **logistic growth equation**. It is the simplest model that describes population growth in an environment with limited resources. Notice that it looks a lot like the exponential model we have already seen, but with an extra term tacked onto it. This term, $(1-N/K)$ represents the **unused portion of the carrying capacity**. It is the percentage of resources that are available. For example, suppose $K=100$ and $N=7$. Then the unused portion of the carrying capacity is $(1-(7/100))=0.93$. So the population is resource rich and growing at $93\%$ of the growth rate of an exponentially increasing population. Similarly, if $N$ was close to $K$ the population would grow at a much slower rate.

What happens if the population exceeds the carrying capacity? Well, the term in parentheses becomes negative and so the growth rate will be negative. So instead of growing, the population will decline and will grow again once $N<K$. With the exponential model, the population would stop growing if either $r$ or $N$ were zero. In the logistic model population will also stop changing if $N=K$. Other values of $N$ will mean that the population will always tend towards $K$. Graphically we can see this below. The density dependent birth and death rates are plotted. There point of intersection is where $N=K$, which you can show with some simple algebra. Whenever the population size is less than $K$, i.e. to the left of the intersection point, births outnumber deaths and the population will increase. If the population is greater than $K$, i.e. to the right of the intersection point, deaths outnumber the births and the population will decrease.

%Add graph

The density dependent birth and death rates intersect when the population size is equal to the carrying capacity.

The point where $N=K$ forms a **stable equilibrium**. It means as long as the starting population is non-zero, the population size will always tend towards $K$.

With the exponential growth model, we were able to write an explicit expression for the population size at any given time $t$. Although the derivation is more complicated, we can do the same with the logistic model:

$$
\begin{equation*}
N_t=\frac{K}{1+\left(K-N_0)/N_0\right)e^{-rt}}.
\end{equation*}
$$

Graphically, the logistic growth curve looks like an $S$-shaped curve. The tendency towards the carrying capacity is seen as a vertical asymptote.

%Add graph

Logistic growth curves with carrying capacity $K=100$, intrinsic growth rate $r=0.3$ and varying initial populations. 

### Example 1
Suppose a species of fish in a lake is modeled by a logistic population model
with intrinsic growth rate of $r = 0.3$ _(or 30\%)_ per year and carrying capacity of $K = 10000$. 

(a) Write the differential equation describing the logistic population model for this
 problem. 

:::{tip} Solution
:icon: false

$$
\begin{equation*}
\dfrac{dN}{dt}=0.3N\left(1-\dfrac{N}{10000}\right)
\end{equation*}
$$

:::

(b) Determine the equilibrium solutions for this model.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    \dfrac{dN}{dt}=0.3N\left(1-\dfrac{N}{10000}\right)=&0\\
    0.3N=& 0 & \left(1-\dfrac{N}{10000}\right)=&0\\
    N=& 0 & 1=&\dfrac{N}{10000}\\
    & & N=& 10000
\end{aligned}
\end{equation*}
$$

For the logistic equation, the equilibrium points lie at $N=0$ and the carrying capacity $N=K=10000$.

:::

(c) If 2500 fish are initially introduced into the lake,
(i) Solve and find the analytic explicit solution $N(t)$ that models the number of fish in the lake after $t$ years. 

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
N_t=\frac{10000}{1+\left(\frac{10000-2500}{2500}\right)e^{-0.3t}}=\dfrac{10000}{1+3e^{-0.3t}}
\end{equation*}
$$

:::

(ii) Use it to estimate the number of fish in the lake after 5 years.
:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
N_5=\dfrac{10000}{1+3e^{-0.3(5)}}= 5990\;\text{fish}
\end{equation*}
$$

:::

(iii) Graph $N(t)$, (_doesn't have to be exact, just the general shape, but make sure to label the main parts such as $K$)_.

%Add graph

(iv) Use a graphing calculator to estimate the time it will take for there to be 8000 fish in the lake.

:::{tip} Solution
:icon: false
:class: dropdown
It takes about 8.3 years for there to be 8000 fish in the lake.
:::

## Steady-state & Equilibrium points

When we study a population model we are most likely interested in **long-term behaviour**. Often, after enough time has passed, the model settles into a pattern. With respect to the previous discussion, the carrying capacity is the population that the model wants to tend towards. If it were to reach this value, then the population would remain the same. One can see this by plugging $N=K$ into our model

$$
\begin{equation*}
\frac{dN}{dt}\Big|_{N=K}=rN\left(1-\frac{N}{K}\right)\Big|_{N=K}=rK\left(1-\frac{K}{K}\right)=0.
\end{equation*}
$$

When the derivative is zero, there is no change. Since we assume that our change is entirely dependent on the current population size, as soon as the population remains the same for one time period, it will remain the same from that point onwards.

This value $N=K$ is called an **equilibrium point**. For the logistic growth model there are two equilibrium points, $N=0$ and $N=K$. If the population were to reach either of these values then they would never change. Since our differential equations give the derivative of our model, to find equilibrium points we simply set our equation to zero and solve. 

%Add graph

We can classify the equilibrium points further. Notice the arrows drawn on the plot above. When the derivative $dN/dt$ is positive, the population $N$ is increasing, i.e. moves to the right. Similarly when the derivative is negative the population moves to the left. These are what the arrows are indicating. When the population is **close** to zero, the population is increasing away from the equilibrium point $N=0$. So, we call this point an **unstable** equilibrium point. When $N$ is **close** to $K$, the population size is moving towards $K$ - if its below it increases, if its above it decreases. So we call this type of equilibrium point **stable**. Alternatively we could describe these points as **repelling** of **attracting**, respectively. The population is repelled by unstable equilibrium points - it wants to move away - and is attracted to stable equilibrium points - it moves towards them.

For the case of the logistic model, there are always $2$ equilibrium points - an unstable one at $N=0$ and a stable one at $N=K$.

## Allee Effect

We have already talked about how populations grow in terms of the logistic model and how the carrying capacity works -- it governs the behaviour of populations with high densities. But we have not yet considered how a small population might affect growth

Our initial assumptions say that the growth rate of a population will decrease at higher densities and increase at lower densities due to competition for limited resources -- food and land for example. But if you had a population consisting of, say, a single tiger, then it does not matter how much food or land that tiger has, the population will die out because it has nothing to breed with. **The Allee effect**, named after Walter Clyde Allee, is the principle that individuals within a population require the presence of other individuals in order to survive and reproduce successfully. Thus when the population size is too small, it will not be able to maintain a positive growth rate. **The logistic equation with Allee effect** has the form

$$
\begin{equation*}
\frac{dN}{dt}=rN\left(1-\frac{N}{K}\right)\left(\frac{N}{A}-1\right),
\end{equation*}
$$

where, as before, $r$ is the intrinsic growth rate, $K$ is the carrying capacity and the new variable, $A$, is the minimal size of the population required to survive -- called the **_Allee threshold_**.

We will assume that $A<K$, since we want $A$ to represent the **minimum** size the population needs and $K$ should be the **maximum** size it can sustain. We will see that the long term outcome of a population modeled by this equation depends on whether the initial value is above or below the value of $A$.

### Example 2
Write a possible differential equation for a population whose growth is modeled by a logistic equation with Allee effect if the intrinsic growth rate is $15\%$ the carrying capacity is $800$ individuals and at least $100$ individuals are required in order for the population to survive.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
{\frac{dN}{dt}=0.15N\left(1-\frac{N}{800}\right)\left(\frac{N}{100}-1\right)}
\end{equation*}
$$

:::

As with the logistic model, if $N>K$ then $dN/dt<0$ and the population is decreasing. If $A<N<K$, then $dN/dt>0$ and the population is increasing. The new behaviour of this model is when $N<A$, which given that $A<K$ we can see that $dN/dt<0$ and so the population decreases.

%Add graph

With the addition of this new term, the model picks up another equilibrium point at $N=A$, bringing the total to three -- the points $N=0$ and $N=K$ survive from the previous logistic model. Noticeably, the point $N=0$ now becomes a stable equilibrium point, since any population level below $A$ will result in distinction. The point $N=A$ is unstable, with the population either growing to its maximum capacity or dying out and the points $N=K$ remains a stable equilibrium point. 

The point about the DE is that it is more like a metaphor for a class of population models with density-dependent regulatory mechanisms--a kind of compensating effect of overcrowding--and must not be taken literally as the equation governing the population dynamics. The main point about the logistic form is that it is a particularly convenient form to take when seeking qualitative dynamic behavior in populations in which $N=0$ is an unstable steady state and $N(t)$ tend to a finite positive stable steady state.

%Add graph

### Example 1 contd.

(d) _For the example above_, suppose it is observed that there needs to be a minimum of 1000 fish in the lake for the fish population to survive.

(i) Modify the logistic model in (a) to incorporate the critical population threshold.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\dfrac{dN}{dt}=0.3N\left(1-\dfrac{N}{10000}\right)\left(\dfrac{N}{1000}-1\right)
\end{equation*}
$$

:::

(ii) What are the equilibrium solutions for this new model?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    \dfrac{dN}{dt}=0.3N\left(1-\dfrac{N}{10000}\right)\left(\dfrac{N}{1000}-1\right)=&0\\
    0.3N=& 0 & 1-\dfrac{N}{10000}=&0 & \dfrac{N}{1000}-1=&0  \\
    N=& 0 & 1=&\dfrac{N}{10000} & \dfrac{N}{1000}=&1\\
    & & N=& 10000 & N=& 1000
\end{aligned}
\end{equation*}
$$

For the logistic equation with Allee threshold, the equilibrium points lie at $N=0$ and the carrying capacity $N=K=10000$, and the Allee threshold $N=A=1000$.
:::
---

## Exercises
