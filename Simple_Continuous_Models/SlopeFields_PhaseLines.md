---
kernelspec:
  name: python3
  display_name: 'Python 3'
---

# Equilibria & Stability for Differential Equations

## Slope-Fields

We can interpret what a differential equation is saying in a geometric way using a **slope-field**, also called a _direction field_. Consider a general differential equation of the form $$\dfrac{dN}{dt}=f(N)$$ where $f(N)$ represents any arbitrary function of $N$. 

The solutions to such a differential equation are curves in the $(N,t)-$plane that describe how $N(t)$ changes over time. Each initial condition $N(0)=N_0$ is associated with one of these curves, so that together, these curves form a **_family of solutions_**.

#### Example 1

Consider the differential equation 

$$
\begin{equation*}
\frac{dN}{dt}=2N
\end{equation*}
$$

Compute some of the slopes for various values of $N$ and use this to sketch a slope field for this differential equation.

:::{tip} Solution
:icon: false
:class: dropdown

The above differential equation states that if a solution curve passes through a point $(t,N)$, then its **tangent line** at that point has a slope $2N$, (regardless of the value of $t$). _This example is simple enough that we can state the following: for
positive values of $N$, the slope is positive; for negative values of $N$, the slope is negative; and for $N=0$, the slope is zero._

| $N$ | $\frac{dN}{dt}$ | slope of tangent line (sign) | behavior of $N$ | direction of arrow |
| :---: | :---: | :---: | :---: | :---: |
| -2 | -4 | negative | decreasing | $\searrow$ |
| -1 | -2 | negative | decreasing | $\searrow$ |
| 0 | 0 | zero | constant | $\longrightarrow$ |
| 1 | 2 | positive | increasing | $\nearrow$ |
| 2 | 4 | positive | increasing | $\nearrow$ |

we combine the information from the table to generate the slope field and the corresponding solution curves. _Note that direction of the arrows (rather than their absolute magnitude) provides the most important qualitative tendency for the slope field sketch._


```{code-cell} python3
:key: value
#:tags: [remove-input]
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(0, 5, 0.5)
y = np.arange(-2, 2, 0.5)
X, Y = np.meshgrid(x, y)

U = np.ones(X.shape)
V = 2*Y

fig, ax = plt.subplots()
q = ax.quiver(X, Y, U, V)
ax.quiverkey(q, X=0.3, Y=1.1, U=10,
             label='Quiver key, length = 10', labelpos='E')

plt.show()
```

:::

#### Example 2

Sketch a slope field and solution curves for the problem of a cooling object (Newton's Law of cooling), given by the differential equation

$$
\begin{equation*}
\dfrac{dT}{dt}=f(T)=0.2(10-T)
\end{equation*}
$$

:::{tip} Solution
:icon: false
:class: dropdown

| $T$ | slope of tangent line (sign) | behavior of $T$ | direction of arrow |
| :---: | :---: | :---: | :---: | :---: |
| T<10 | negative | increasing | $\nearrow$ |
| T=10 | zero | constant | $\longrightarrow$|
| T>10 | positive | decreasing | $\searrow$ |


:::

## Phase-line Diagrams

---

## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true

Find the equilibrium points of the following equations algebraically.

1. $\dfrac{dN}{dt} = N^2-2N+1$
2. $\dfrac{dN}{dt} = \ln\left(\dfrac{N+2}{N^2}\right)$
3. $\dfrac{dN}{dt} = e^{2N}+6e^N+8$
:::

:::{tip} Solution to Exercise 1
:icon: false
:class: dropdown


:::

:::{tip} Exercise 2
:class: dropdown
:open: true
Find the equilibrium points for the following differential equations and determine whether they are stable or unstable.

1. $\dfrac{dN}{dt} = -0.4N+500$

%Add graphs
2. $\dfrac{dQ}{dt} = 0.4N-500$

%Add graphs

:::

:::{tip} Solution to Exercise 2
:icon: false
:class: dropdown


:::

:::{tip} Exercise 3
:class: dropdown
:open: true
Determine the equilibrium points and stability for $\dfrac{dN}{dt}=N^2-4$.

%Add graph

:::

:::{tip} Solution to Exercise 3
:icon: false
:class: dropdown


:::

:::{tip} Exercise 4
:class: dropdown
:open: true
Find the equilibrium points and determine stability for the following differential equations.

1. $\dfrac{dN}{dt} = 0.3N\left(1-\dfrac{N}{200}\right)$
2. $\dfrac{dQ}{dt} = (Q^3-8)(e^Q-1)$
3. $\dfrac{dN}{dt} = e^{2N}+6e^N+8$

:::

:::{tip} Solution to Exercise 4
:icon: false
:class: dropdown


:::

