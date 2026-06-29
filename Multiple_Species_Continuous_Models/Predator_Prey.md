# Predator-Prey Model
## Introduction

#### A dog eat dog world

Assume we have a closed ecosystem, so that there is no migration in or out of the system. Suppose that there are only two types of animals: the predator and the prey. Here the interdependence arises because one species serves as a food source for the other species.

## Modeling Prey Population Growth

We will use $Q$ to denote the **predator** population and the symbol $P$ to denote the **prey** population. The growth of the prey population will be some function, $f$, of the numbers of both preys and predators:

$$
\begin{equation*}
\dfrac{dP}{dt}=f(P,Q)
\end{equation*}
$$

Suppose that the predators are the only force limiting the growth of the prey population. In other words, if the predators are absent, the victim population increases exponentially:

$$
\begin{equation*}
\dfrac{dP}{dt}= rP
\end{equation*}
$$

where $r$ represents the _intrinsic growth rate_. This potential for increase of the prey population is offset by losses that occur when predators are present:

$$
\begin{equation*}
\dfrac{dP}{dt}={\colour rP-\alpha PQ}
\end{equation*}
$$

where $\alpha$ measures **capture efficiency**, _the effect of a predator on the per capita growth rate of the prey population_. 

:::{note}
This second term with $\alpha$ says that the losses to predation are proportional to the _product_ of predator and prey numbers. This is equivalent to a chemical reaction in which the reaction rates are proportional to the concentrations of molecules. If predators and preys move randomly through the environment, then their encounter rate is proportional to the product of their abundances.
:::

### $\alpha$ - capture efficiency

#### Exercise

_Discuss the following._
- What are the units of $\alpha$?

:::{tip} Solution
:icon: false
:class: dropdown

The units of $\alpha$ are $\dfrac{\mbox{prey}}{\mbox{time}\cdot \mbox{prey}\cdot \mbox{predator}}$

:::

- What could be the biological interpretation of a larger or smaller $\alpha$? Can you think of any real-life examples?

:::{tip} Solution
:icon: false
:class: dropdown

The larger $\alpha$ means that adding another predator will result in a higher decline of the growth rate of the prey population (there is a higher capture rate of prey per a single predator). 
    
Example: A baleen whale would have a large $\alpha$, because a single whale can consume millions of plankton. In contrast, a web-building spider might have a fairly low $\alpha$ if the addition of a single web does not greatly diminish the prey population, or increase the capture of prey.

:::

- Similarly, how could we interpret $\alpha P$?

:::{tip} Solution
:icon: false
:class: dropdown

This product is called **functional response** of the predator - the rate of prey capture by a predator as a function of the abundance of prey.

:::


## Modeling Predator Population Growth

The growth of the predator population will be some function, $g$ (to distinguish it from the function $f$ for the prey population), of the numbers of both preys and predators:

$$
\begin{equation*}
\dfrac{dQ}{dt}=g(P,Q)
\end{equation*}
$$

The predator we are modelling is an extreme specialist. It will feed only on the prey population and has no alternative source of prey. Consequently, if the prey population is absent, the predator population declines exponentially:

$$
\begin{equation*}
\dfrac{dQ}{dt}=-qQ}
\end{equation*}
$$

where $q$ represents the _intrinsic death rate_. Positive growth occurs only when the prey population is present:

$$
\begin{equation*}
\dfrac{dQ}{dt}=-qQ+\beta PQ
\end{equation*}
$$

where $\beta$ measures **conversion efficiency**, _the ability of predators to convert each new prey into additional per capita growth rate for the predator population_. 

:::{note}
This second term with $\alpha$ says that the losses to predation are proportional to the _product_ of predator and prey numbers. This is equivalent to a chemical reaction in which the reaction rates are proportional to the concentrations of molecules. If predators and preys move randomly through the environment, then their encounter rate is proportional to the product of their abundances. 
:::

### $\beta$ - conversion efficiency

#### Exercise

_Discuss similarly, the characteristics of $\beta$._
- What are the units of $\beta$?

:::{tip} Solution
:icon: false
:class: dropdown

The units of $\beta$ are $\dfrac{\mbox{predator}}{\mbox{time}\cdot \mbox{predator}\cdot \mbox{prey}}$

:::

- What could be the biological interpretation of a larger or smaller $\beta$? Can you think of any real-life examples?

:::{tip} Solution
:icon: false
:class: dropdown

We expect $\beta$ to be high when a single prey is particularly valuable, such as a moose that is captured by a pack of wolves. In contrast, $\beta$ will be low when a single prey does not contribute much to the growth of the predator population; for example a single seed consumed by a granivorous bird.
:::

- Similarly, how could we interpret $\beta P$?

:::{tip} Solution
:icon: false
:class: dropdown

This product $\beta P$ is called the **numerical response** of the predator population - the growth rate of the predator population as a function of prey abundance.

:::


The general form of our **Predator-Prey Model or System** looks like:

$$
\begin{equation*}
\begin{aligned}
    \dfrac{dP}{dt}=& rP- \alpha PQ \\ \\
    \dfrac{dQ}{dt}=& -qQ+ \beta PQ
\end{aligned}
\end{equation*}
$$

where $r, q, \alpha$ and $\beta$ are all positive constants, along with the **model assumptions**:

- growth of the prey population is limited only by predation.

- The predator can persist only if the prey population is present (in the absence of prey, the predator population will starve to extinction).

## Equilibria & Stability

Recall that our previous encounters with determining equilibria involved us finding roots of the derivative in our model. For the predator-prey model this is still the same, the only difference is that now we require that **both derivatives need to be zero** at the same time. That is: The equilibrium points of the predator-prey model occur when

$$
\begin{equation*}
\frac{dP}{dt}=\frac{dQ}{dt}=0
\end{equation*}
$$

Solving one derivative equal to zero is straightforward. Solving two simultaneously can be tricky. To facilitate this, here we introduce **nullclines**, which are lines where one of the derivatives is equal to zero.

The **nullclines** for $\dfrac{dP}{dt}=0$ are found as:

$$
\begin{equation*}
\frac{dP}{dt}=rP-\alpha PQ=P\left(r-\alpha Q\right)=0,
\end{equation*}
$$

so the two solutions are

$$
\begin{equation*}
P=0\hspace*{0.5cm}\text{or}\hspace*{0.5cm}Q=\dfrac{r}{\alpha}.
\end{equation*}
$$

Although we solved for the prey equilibrium, one of the solutions is in terms of $Q$, the predator population! The important result is that a specific number of predators ($Q=\dfrac{r}{\alpha}$) will maintain the prey population at zero growth. This predator level is determined by the ratio of the growth rate of the prey ($r$) to the capture efficiency of the predators ($\alpha$). The faster the growth rate of the prey population, the more predators are needed to keep the prey population in check. Conversely, the higher the capture efficiency, the fewer predators needed for control.

The **nullclines** for $\dfrac{dQ}{dt}=0$ are found as:

$$
\begin{equation*}
\frac{dQ}{dt}=-qQ+\beta PQ=Q\left(-q+\beta P\right)=0,
\end{equation*}
$$

so the two solutions are

$$
\begin{equation*}
Q=0\hspace*{0.5cm}\text{or}\hspace*{0.5cm}P=\frac{q}{\beta}.
\end{equation*}
$$

Thus, the predator population is controlled by a fixed number of prey ($P=\dfrac{q}{\beta}$). The greater the death rate of the predators ($q$), the more prey needed to keep the predator population from declining. Conversely, the greater the conversion efficiency of predators ($\beta$), the fewer prey needed to maintain the predators at equilibrium.

### Graphical Solutions to the Predator-Prey Model


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
