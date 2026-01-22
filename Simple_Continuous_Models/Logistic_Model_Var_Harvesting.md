# Logistic with Harvesting

```{image} images/overfishing.jpg
:alt: Types of models.
:width: 500px
:align: center
```

Harvesting is the process of removing renewable resources for the purposes of food, clothing, shelter or for commercial use. For example, harvesting of food crops, marine fishery or even hunting. We will study different kinds of harvesting on a species growing logistically, such that the effect of harvesting is introduced as a separate function to the already existing logistic growth model. Ideally, we would aim for the _**maximum sustainable yield**_ with the minimum effort.

## Constant Harvesting

By constant harvesting, we mean removing a **fixed** number of the species from the population, per unit time. Then, the population size $N(t)$ of the species can satisfy the logistic model: 

$$
\begin{equation*}
\dfrac{dN}{dt}=rN\left(1-\dfrac{N}{K}\right)-h
\end{equation*}
$$

provided that the species are **harvested** at a **constant rate** $h>0$. 

## Sustainable Harvesting

The **maximum sustainable yield** is the critical harvesting rate which is determined by the formula $\dfrac{rK}{4}$ (which also happens to be the peak growth rate for the logistic function). When the harvesting rate is below this point, it means that harvesting is done sustainably allowing the population to renew itself and continue to grow _provided that the initial population is higher than the critical threshold_.  

## Over-harvesting & Restocking

But if instead, the harvesting rate is above the maximum sustainable yield, then the species is being harvested at a rate higher than they are able to replenish themselves, causing the population to decline and eventually die out. In such a case, restocking may be considered to prevent the species from dying out.

_We can study the dynamics of the population for different harvesting rates and observe the following phenomenon by plotting both the $N\; vs.\; t$ graph, the change in population over time, as well as the phase-line diagram._


### Example 

A population of fish in a lake are increasing with intrinsic growth $r=1$ and have a carrying capacity of 100 thousand fish. Suppose each year, 16 thousand fish are harvested.

1. Write a differential equation modeling this situation.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\dfrac{dN}{dt}=N\left(1-\dfrac{N}{100}\right)-16
\end{equation*}
$$

:::

2. Calculate the **maximum sustainable yield** for the fish population.

:::{tip} Solution
:icon: false
:class: dropdown

The maximum sustainable yield is given by:

$$
\begin{equation*}
\dfrac{rK}{4} = \dfrac{1\cdot 100}{4}=25\;\;\text{thousand fish per year}
\end{equation*}
$$

:::

3. If there are initially 30 thousand fish in the lake, will harvesting at this rate be sustainable? Explain why.

:::{tip} Solution
:icon: false
:class: dropdown

The harvest rate is less than the maximum sustainable yield, so now we need to check whether the initial population is larger than the lower equilibrium point for the population to continue thriving while harvesting.
    
The equilibrium points for the following differential equations are:

$$
\begin{equation*}
\begin{aligned}
        \dfrac{dN}{dt}=N\left(1-\dfrac{N}{100}\right)-16 =& 0\\
        N - \dfrac{N^2}{100}-16 =& 0 \\
        100N -N^2 -1600 =& 0 \\
        N^2 -100N +1600 =& 0 \\
        (N-80)(N-20) =& 0 \\
\text{equilibrium points: }\; N=80, N=&20 \quad \text{thousand fish}
    \end{aligned}
\end{equation*}
$$

Since the initial population $N_0 = 30 $ thousand fish is greater than the lower equilibrium point $N=20$, the current harvesting rate is sustainable as the population will continue to grow logistically until it reaches the maximum capacity of 80 thousand fish.

:::

## Variable Harvesting

$$
\begin{equation*}
\dfrac{dN}{dt}=rN\left(1-\dfrac{N}{K}\right)-hN
\end{equation*}
$$

This variation of the logistic model results by **harvesting** at a non-constant rate _**proportional to the present population size $N$**_. _The effect is to decrease the instantaneous growth rate $r$ by the constant amount $h$ in the standard logistic model._

```{image} images/varH_sus.png
:alt: Types of models.
:width: 450px
:align: left
```
```{image} images/varH_unsus.png
:alt: Types of models.
:width: 450px
:align: right
```

In this scenario, to maintain a sustainable practice of harvesting, the harvesting rate should be less than the intrinsic growth rate, $h<r$. 

## Restocking

The equation 

$$
\begin{equation*}
\dfrac{dN}{dt}=rN\left(1-\dfrac{N}{K}\right)-h\sin(\omega t)
\end{equation*}
$$

models a logistic population that is **periodically harvested and restocked** with maximal rate $h>0$. The period is $T=\dfrac{2\pi}{\omega}$. The equation might model extinction for stocks less than some threshold population, and otherwise a stable population that oscillates about an ideal carrying capacity $K$ with period $T$.

---

Although simple in nature, these models can provide important information for the ecological preservation of species while also yielding economic gain. By determining the maximum sustainable yield of a species, the government will be able to regulate harvesting or hunting activities and prevent the possibility of extinction.



---


## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true

A species of fish in a lake is modeled by a logistic population model with instrinsic growth rate of 20\% per year and a carrying capacity of $K=10000$. Suppose 320 fish are harvested each year from the lake.

1. Write the differential equation for the following situation incorporating the harvesting of fish.

2. What are the equilibrium points of this model? What do they represent?

3. To make a higher profit, the fishermen decide to harvest 600 fish instead, per year from the lake. Would this be sustainable in the long run?  _(is the harvesting rate within or higher than than the maximum sustainable yield?)_

:::

:::{tip} Solution to Exercise 1
:icon: false
:class: dropdown

1. 

$$
\begin{equation*}
\dfrac{dN}{dt}=0.2N\left(1-\dfrac{N}{10000}\right)-320
\end{equation*}
$$

2. The equilibrium points of this differential equation are:

$$
\begin{equation*}
\begin{aligned}
        \dfrac{dN}{dt}=0.2N\left(1-\dfrac{N}{10000}\right)-320 =& 0\\
        0.2N - \dfrac{0.2\cdot N^2}{10000} - 320 =& 0\\
        0.2N - \dfrac{N^2}{50000} - 320 =& 0\\
        10000N - N^2 - 16000000 =& 0 \\
        N^2 - 1000N +16000000 =& 0\\
        (N-8000)(N-2000) =& 0 \\
        N = 8000,\; N=2000
    \end{aligned}
\end{equation*}
$$

_you can also use your graphing calculator to find the $x-$intercepts of the $\frac{dN}{dt}$ function._

The upper equilibrium point ($N=8000$) represent the upper/maximum threshold for the population while the lower equilibrium point ($N=2000$) represents the critical threshold below which the population will eventually die out.

3. The **maximum sustainable yield** is given by $\dfrac{rK}{4}=\dfrac{0.2\cdot 10000}{4} = 500$
    
    since harvesting 600 fish per year from the lake would be greater than the maximum sustainable yield, no matter the initial fish population, they will eventually die out at this rate; therefore, it is not sustainable.
:::

