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
\dfrac{dP}{dt}= rP-\alpha PQ
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
\dfrac{dQ}{dt}=-qQ
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

---
### Example

Suppose we have an ecosystem of rabbits $(P)$ and foxes $(Q)$ with the following assumptions:
- In the absence of foxes, rabbits grow exponentially with intrinsic growth rate $r=0.84$.
- The decrease in rabbits due to predation is proportional to the number of predators, with coefficient $\alpha=0.04$.
- The rabbits are the sole food source for the foxes, without them the population decreases exponentially with rate $q=0.88$.
- Predation causes an increase in the foxes population proportional to the number of rabbits $(P)$ with coefficient $\beta=0.02$.

1. Write down the differential equation that models the growth of the rabbits in this situation.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\dfrac{dP}{dt}=0.84P-0.04QP
\end{equation*}
$$

:::

2. Write down the differential equation that models the growth of the foxes in this situation.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\dfrac{dQ}{dt}=-0.88Q+0.02QP
\end{equation*}
$$

:::

3. Use the simulation below to observe how the populations behave in time; (you may begin with a hundred rabbits and 15 foxes initially):

---

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

The graphs below represent plots of the solutions in $(1)$, on the left, and $(2)$, on the right.


The coloured lines indicate when the given derivative is zero. We can then choose a point on the plane and from its position relative to these lines we can determine in which direction the population is moving.

For example, for the $P$-nullclines, if we choose a point that lies inside the triangle, then we have $Q<\dfrac{r}{\alpha}$, so then $\dfrac{dP}{dt}>0$ and so the population of $P$ is increasing. Above the line, $\dfrac{dP}{dt}<0$ and so the population decreases. For the $Q$-nullclines, if we choose a point to the left of the line $P=\dfrac{q}{\beta}$, then $P<\dfrac{q}{\beta}$ and so $\dfrac{dQ}{dt}<0$ and the population of $Q$ decreases. To the right, $\dfrac{dQ}{dt}>0$ and so the population of $Q$ increases. We indicate these below:



Overlaying one plot on top of the other, we obtain the following:


In the upper right-hand corner region, both predator and prey are abundant. Because we are above the $Q-$nullcline, prey are abundant enough for the predator to increase. However, we are to the right of the vertical prey-nullcline, consequently, there are too many predators, and the prey population declines. 


The predator and prey nullclines divide the graph into plane into four regions. The equilibrium points are therefore the points of intersection of the $P$-nullclines with the $Q$-nullclines, depicted above there appears to be $2$. As with single species, we can determine the stability of each of the equilibrium points by looking at the direction of the arrows with respect to the points. Taking a point anywhere on the quadrant we move in the direction the arrows tell us. The vector of net movement points can be used to trace the approximate shape around the equilibrium point.The result, in the cases of a stable equilibrium, is an approximate ellipse cycling counterclockwise.

For example, in the diagram below, we start with a point in the `lower left quadrant'. The arrows above tell us that we should move down and to the right. Once we cross into the `lower right quadrant', the direction to move in changes to up and to the right. Continuing this manner we see that the result is a spiral path, similar to the one below.

How does the ellipse translate into growth curves for the predator and prey populations? Both populations cycle periodically, increasing and decreasing smoothly from minimum to maximum. The ellipse indicates that the peak of the predator population occurs when the prey population is at its mid-point and vice-versa.

---

### Example 2

---

## Variations of the Simplistic Predator-Prey Model

Assume we have a closed ecosystem, so that there is no migration in or out of the system. Suppose that there are only two types of animals: the predator and the prey. Here the interdependence arises because one species serves as a food source for the other species.

The general form of our **Predator-Prey Model** looks like:

$$
\begin{equation*}
\begin{aligned}
\dfrac{dP}{dt}=&F_1(P)-G_1(P,Q)	\\\\
\dfrac{dQ}{dt}=&F_2(Q)+G_2(P,Q)
\end{aligned}
\end{equation*}
$$

where the functions $F_1$ and $F_2$ represent the the population growth of $P$ and $Q$, respectively, if there were no interactions between the two species. The functions $G_1$ and $G_2$ represent the affect of predation on the the two species.

For the discussion here we will look at a model where the prey population grows logistically with the absence of a predator and the prey is the sole food source for the predators. You will find examples in the homework problems of other possible predator-prey models where what we talk about here can be applied, with the obvious adjustments coming from algebraic manipulations.

We begin by obtaining the equation for the prey population, denoted by $P$. We assume that in the absence of predators the population follows a logistic growth model:

$$
\begin{equation*}
\frac{dP}{dt}=rP\left(1-\frac{P}{K}\right).
\end{equation*}
$$

Now if we assume that the decrease on the number of preys is proportional to the number of predators, denoted by $Q$, we obtain:

$$
\begin{equation*}
\frac{dP}{dt}=rP\left(1-\frac{P}{K}\right)-sQP,
\end{equation*}
$$

where $s$ is a positive constant. For the predator, we assume that its sole food source is the prey, so without it the population decreases exponentially. The population increase due to predation will again be assumed to be proportional to the population of prey. This yields:

$$
\begin{equation*}
\frac{dQ}{dt}=-uQ+vQP
\end{equation*}
$$

where $u$ and $v$ are positive constants.

To clarify, the predator-prey model we have formulated here is

$$
\begin{equation*}
\begin{aligned}
\dfrac{dP}{dt}=&rP\left(1-\dfrac{P}{K}\right)-sQP \\\\
\dfrac{dQ}{dt}=&-uQ+vQP
\end{aligned}
\end{equation*}
$$

where $r, K, s, u,$ and $v$ are all positive constants, where $u<1$.

### Equilibria and Stability

Recall that our previous encounters with determining equilibria involved us finding roots of the derivative in our model. For the predator-prey model this is still the same, the only difference is that now we require that **both derivatives need to be zero** at the same time. That is: The equilibrium points of the predator-prey model occur when

$$
\begin{equation*}
\frac{dP}{dt}=\frac{dQ}{dt}=0.\\
\end{equation*}
$$

Solving one derivative equal to zero is straightforward. Solving two simultaneously can be tricky. To facilitate this, here we introduce **nullclines**, which are lines where one of the derivatives is equal to zero.

The nullclines for $dP/dt=0$ are found as:

$$
\begin{equation*}
\frac{dP}{dt}=rP\left(1-\frac{P}{K}\right)-sQP=P\left[r\left(1-\frac{P}{K}\right)-sQ\right]=0,
\end{equation*}
$$

so the two solutions are

$$
\begin{equation*}
P=0\hspace*{0.5cm}\text{or}\hspace*{0.5cm}Q=\frac{r}{s}\left(1-\frac{P}{K}\right).
\end{equation*}
$$

The nullclines for $dQ/dt=0$ are found as:

$$
\begin{equation*}
\frac{dQ}{dt}=-uQ+vQP=Q\left[-u+vP\right]=0,
\end{equation*}
$$

so the two solutions are

$$
\begin{equation*}
Q=0\hspace*{0.5cm}\text{or}\hspace*{0.5cm}P=\frac{u}{v}.
\end{equation*}
$$

The graphs below represent plots of the solutions in $(1)$, on the left, and $(2)$, on the right.




The coloured lines indicate when the given derivative is zero. We can then choose a point on the plane and from its position relative to these lines we can determine in which direction the population is moving.

For example, for the $P$-nullclines, if we choose a point that lies inside the triangle, then we have $Q<r\left(1-P/K\right)/s$, so then $dP/dt>0$ and so the population of $P$ is increasing. Above the line $dP/dt<0$ and so the population decreases. For the $Q$-nullclines, if we choose a point to the left of the line $P=u/v$, then $P<u/v$ and so $dQ/dt<0$ and the population of $Q$ decreases. To the right, $dQ/dt>0$ and so the population of $Q$ increases. We indicate these below:

Overlaying one plot on top of the other, we obtain the following:

The equilibrium points are therefore the points of intersection of the $P$-nullclines with the $Q$-nullclines, depicted above there appears to be $3$. As with single species, we can determine the stability of each of the equilibrium points by looking at the direction of the arrows with respect to the points. Taking a point anywhere on the quadrant we move in the direction the arrows tell us. The result, in the cases of a stable equilibrium, is a path that spirals into a stable equilibrium point. For example, in the diagram below, we start with a point in the `lower left quadrant'. The arrows above tell us that we should move down and to the right. Once we cross into the `lower right quadrant', the direction to move in changes to up and to the right. Continuing this manner we see that the result is a spiral path, similar to the one below. 

### Stability with Jacobian

Another way to study the stability is to use the **Jacobian matrix** corresponding to the model, which we introduce now.


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
