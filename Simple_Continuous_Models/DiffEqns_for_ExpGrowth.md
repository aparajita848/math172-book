# Differential Equations for Exponential Growth & Decay[^Source:{cite} (edited for the purpose of this course.)]

:::{tip} Warm-up
:class: dropdown
:open: true
Evaluate the following derivatives:

```{math}
:nonumber:
\begin{align}
\frac{d}{dx}[e^x] &= \\
\frac{d}{dx}[e^{kx}] &=
\end{align}
```

Suppose that $y_1=e^x$ and $y_2=e^{kx}$, rewrite the derivatives in terms of $y_1$ and $y_2$.
:::

::::{tip} Solution
:icon: false
:class: dropdown

:::{math}
:enumerated: false
\begin{align}
\frac{d}{dx}[e^x] &= e^x \\
\frac{d}{dx}[e^{kx}] &= ke^{kx}
\end{align}
:::

Observe that the derivative of the function $e^x$ is itself, therefore, if $y_1=e^x$ then

:::{math}
:enumerated: false
\frac{de^x}{dx}=e^x 
:::
:::{math}
:label: diff_eq_exp1
\implies \frac{dy_1}{dx}=y_1
:::
And similarly, if we let $y_2=e^{kx}$,
:::{math}
:enumerated: false
\frac{de^{kx}}{dx}=ke^{kx} 
:::
:::{math}
:label: diff_eq_exp2
\implies \frac{dy_2}{dx}=ky_2
:::

The equations on the right in [](#diff_eq_exp1) and [](#diff_eq_exp2) (linking a function to its own derivative) are a new kind of equations called a **differential equation** (abbreviated DE). We say that $y_1=e^x$ is a function that "satisfies" equation [](#diff_eq_exp1), and we call this a **solution to the differential equation**. 

And similarly, $y_2=e^{kx}$ is a solution to the differential equation [](#diff_eq_exp2).
::::
---


**Definition**: A **differential equation** is a mathematical equation that relates one or more derivatives of some function to the function itself. Solving the differential equation is the process of identifying the function(s) that satisfies the given relationship.

:::{note}
The solution to an algebraic equation is a number, whereas the solution to a differential equation is a function.
:::

Since we are interested in observing changing populations over time, we will henceforth use the independent variable $t$ for time and the dependent variable as $N$ for the population size.

$$
N(t) = \text{population size as a function of time } t.
$$

### _Observations_

1. Consider the function $N(t)=e^t$. Show that this function satisfies the differential equation

$$
\frac{dN}{dt}=N
$$

:::{tip} Solution
:icon: false
:class: dropdown
Differentiating the function $N(t)=e^t$ gives

$$
\begin{aligned*}
\frac{dN}{dt} &= \frac{d}{dt}[e^t]=e^t\\
\frac{dN}{dt} &= N
\end{aligned*}
$$
:::

2. The function $N(t)=e^{rt}$ (for $r$ constant) satisfies the differential equation

$$
\frac{dN}{dt}=rN \tag{1}
$$

:::{tip} Solution
:icon: false
:class: dropdown
We can verify by differentiating $N(t)=e^{rt}$, using the chain rule. Setting $u=rt$, and $N(t) = e^u$, we have

$$
\begin{align*}
\frac{dN}{dt} &= \frac{dN}{du}\cdot \frac{du}{dt}=e^u\cdot r = re^u = rN\\
\implies \frac{dN}{dt} &= rN
\end{align*}
$$

_It is interesting to ask: Is this the only function that satisfies the differential equation (1)? Are there other possible solutions? What about a function such as $N(t) = 2e^{rt}$ or $N(t) = 400e^{rt}$?_

:::{note}
For any constant $C$, the function $N(t) = Ce^{rt}$ is a solution to the DE (1). _(verify by differentiating)_
:::

:::{important} **General Solution**
:icon: false

Solutions to the differential equation

$$
\frac{dN}{dt}=rN
$$

are the functions

$$
N(t)=Ce^{rt}
$$

for $C$ an arbitrary constant.

- If $r > 0$, then we have **exponential growth**.
- If $r < 0$, then we have **exponential decay**.

Since $e^{rt}$ is always positive, the constant $C$ determines the sign of the function as a whole - whether its graph lies above or below the $t$ axis.
:::

![Exponential growth and decay curves](figures/exponential-curves.png)

*Left panel: $r>0$ (growth), Right panel: $r<0$ (decay)*

---

**Definition**: By a **solution to a differential equation**, we mean a function that satisfies that equation.

We often refer to "solution curves" - the graphs of the family of solutions of a differential equation, as shown, for example, in the panels of graphs above. So far, we found that "many" functions can be valid solutions of the differential equation (1), since we can choose the constant $C$ arbitrarily in the family of solutions $N(t) = Ce^{rt}$.

Hence, in order to distinguish one specific solution of interest, we need additional information. This additional information is called an **initial value, or initial condition**, and it specifies one point belonging to the solution curve of interest. A common way to set an initial value is to specify a fixed value of the function (say $N = N_0$) at time $t = 0$.

**Definition**: An **initial value** for a differential equation is a specified, known value of the solution at some specific time point (usually at time $t = 0$).

---

### Example

Given the differential equation $\frac{dN}{dt}=rN$ and initial value $N(0)=N_0$, find the value of $C$ for the solution in equation $N(t)=Ce^{rt}$.

To solve:

$$
N(t)=Ce^{rt}, \text{ so } N(0) = Ce^{r\cdot 0} =Ce^0 = C\cdot 1 = C
$$

Using the initial condition, $N(0)=N_0$, so

$$
C=N_0
$$

Therefore we have shown that

$$
N(t)=N_0e^{rt}, \text{ where } N_0 \text{ is the initial value.}
$$

---

:::{important} **Unique Solution**
:icon: false

The **(unique) solution** to the differential equation

$$
\frac{dN}{dt}=rN
$$

with the initial condition $N(0)=N_0$ is the **unique** function

$$
N(t)=N_0e^{rt}
$$

:::

---

## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true

Find the solution to the differential equation

$$
\frac{dN}{dt}=-0.5N
$$

that satisfies the initial condition $N(0)=3$. Describe the behaviour of the solution you have found *(sketch a graph)*.
:::
:::{tip} Solution to Exercise 1
:class: dropdown
The differential equation (DE) indicates that $r=-0.5$, so solutions are exponential functions of the form $N(t)=N_0e^{rt}$ and $N_0=3$, so the solution is

$$
N(t)=3e^{-0.5t}
$$

*This is a decaying exponential function.*
:::


:::{tip} Exercise 2
:class: dropdown
:open: true

Find the solution to the following differential equation:

$$
\frac{dN}{dt}=rN, \quad N_0=400, \quad N_2=412.
$$
:::

:::{tip} Solution to Exercise 2
:class: dropdown
 If we do what we have done before in previous problems, then we obtain the solution

$$
N_t=400e^{rt}.
$$

But how do we solve for $r$? Well, notice that we have two conditions. We have used $N_0=400$ already, so the key to solving for $r$ must lie in the other condition, $N_2=412$. Observe,

$$
\begin{aligned}
N_2 &= 400e^{r\cdot2}=412\\
\implies e^{r\cdot2} &= \frac{412}{400}\\
\implies 2r &= \ln\left(\frac{412}{400}\right)\\
\implies r &= \frac{1}{2}\ln\left(\frac{412}{400}\right)=0.0148.
\end{aligned}
$$

Thus the final solution is

$$
N=400e^{0.0148t}.
$$
:::