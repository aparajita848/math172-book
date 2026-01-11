# Differential Equations for Exponential Growth & Decay

:::{tip} Warm-up
:class: dropdown
:open: true
Evaluate the following derivative:

$$
\begin{equation*}
\frac{d}{dx}[e^x] = 
\end{equation*}
$$

Suppose that $y=e^x$, rewrite the derivative in terms of $y$.
:::

::::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\frac{d}{dx}[e^x] = e^x
\end{equation*}
$$

Observe that the derivative of the function $e^x$ is itself, therefore, if $y=e^x$ then

:::{math}
:enumerated: false
\frac{de^x}{dx}=e^x 
:::
:::{math}
:label: diff_eq_exp
\implies \frac{dy}{dx}=y
:::

The equation [](#diff_eq_exp) (linking a function to its own derivative) are a new kind of equations called a **differential equation** (abbreviated DE). We say that $y=e^x$ is a function that "satisfies" equation [](#diff_eq_exp), and we call this a **solution to the differential equation** [](#diff_eq_exp). 

::::

## Introduction

**Definition**: A **differential equation** is a mathematical equation that relates one or more derivatives of some function to the function itself. Solving the differential equation is the process of identifying the function(s) that satisfies the given relationship.

:::{note}
The solution to an algebraic equation is a number, whereas the solution to a differential equation is a function.
:::

Since we are interested in observing changing populations over time, we will henceforth use the independent variable $t$ for time and the dependent variable as $N$ for the population size.

$$
\begin{equation*}
N(t) = \text{population size as a function of time } t.
\end{equation*}
$$

**_Observations_**

1. Consider the function $N(t)=e^t$. Show that this function satisfies the differential equation

$$
\begin{equation*}
\frac{dN}{dt}=N
\end{equation*}
$$

:::{tip} Solution
:icon: false
:class: dropdown
Differentiating the function $N(t)=e^t$ gives

$$
\begin{equation*}
\begin{aligned}
\frac{dN}{dt} &= \frac{d}{dt}[e^t]=e^t\\
\frac{dN}{dt} &= N
\end{aligned}
\end{equation*}
$$
:::

2. Show that the function $N(t)=e^{rt}$ (for $r$ constant) satisfies the differential equation

:::{math}
:label: diff_eq_exp_r
\frac{dN}{dt}=rN 
:::

:::{tip} Solution
:icon: false
:class: dropdown
We can verify by differentiating $N(t)=e^{rt}$, using the chain rule. Setting $u=rt$, and $N(t) = e^u$, we have

$$
\begin{equation*}
\begin{aligned}
\frac{dN}{dt} &= \frac{dN}{du}\cdot \frac{du}{dt}=e^u\cdot r = re^u = rN\\
\implies \frac{dN}{dt} &= rN
\end{aligned}
\end{equation*}
$$

:::

:::{note}
_It is interesting to ask: Is this the only function that satisfies the differential equation [](#diff_eq_exp_r)? Are there other possible solutions? What about a function such as $N(t) = 2e^{rt}$ or $N(t) = 400e^{rt}$?_

For any constant $C$, the function $N(t) = Ce^{rt}$ is a solution to the DE [](#diff_eq_exp_r). _(verify by differentiating)_
:::

:::{important} **General Solution**
:icon: false

Solutions to the differential equation

$$
\begin{equation*}
\frac{dN}{dt}=rN
\end{equation*}
$$

are the functions

$$
\begin{equation*}
N(t)=Ce^{rt}
\end{equation*}
$$

for $C$ an arbitrary constant.

- If $r > 0$, then we have **exponential growth**.
- If $r < 0$, then we have **exponential decay**.

Since $e^{rt}$ is always positive, the constant $C$ determines the sign of the function as a whole - whether its graph lies above or below the $t$ axis.
:::

% Add simulation here.
---

## Solutions to a Differential Equation

**Definition**: By a **solution to a differential equation**, we mean a function that satisfies that equation.

We often refer to "solution curves" - the graphs of the family of solutions of a differential equation, as shown, for example, in the panels of graphs above. So far, we found that "many" functions can be valid solutions of the differential equation (1), since we can choose the constant $C$ arbitrarily in the family of solutions $N(t) = Ce^{rt}$.

Hence, in order to distinguish one specific solution of interest, we need additional information. This additional information is called an **initial value, or initial condition**, and it specifies one point belonging to the solution curve of interest. A common way to set an initial value is to specify a fixed value of the function (say $N = N_0$) at time $t = 0$.

**Definition**: An **initial value** for a differential equation is a specified, known value of the solution at some specific time point (usually at time $t = 0$).


#### Example

Given the differential equation $\frac{dN}{dt}=rN$ and initial value $N(0)=N_0$, find the value of $C$ for the solution in equation $N(t)=Ce^{rt}$.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
N(t)=Ce^{rt}, \text{ so } N(0) = Ce^{r\cdot 0} =Ce^0 = C\cdot 1 = C
\end{equation*}
$$

Using the initial condition, $N(0)=N_0$, so

$$
\begin{equation*}
C=N_0
\end{equation*}
$$

Therefore we have shown that

$$
\begin{equation*}
N(t)=N_0e^{rt}, \text{ where } N_0 \text{ is the initial value.}
\end{equation*}
$$
:::

:::{important} **Unique Solution**
:icon: false

The **(unique) solution** to the differential equation

$$
\begin{equation*}
\frac{dN}{dt}=rN
\end{equation*}
$$

with the initial condition $N(0)=N_0$ is the function

$$
\begin{equation*}
N(t)=N_0e^{rt}
\end{equation*}
$$

:::

---

## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true

Find the solution to the differential equation

$$
\begin{equation*}
\frac{dN}{dt}=-0.5N
\end{equation*}
$$

that satisfies the initial condition $N(0)=3$. Describe the behaviour of the solution you have found *(sketch a graph)*.
:::
:::{tip} Solution to Exercise 1
:icon: false
:class: dropdown
The differential equation (DE) indicates that $r=-0.5$, so solutions are exponential functions of the form $N(t)=N_0e^{rt}$ and $N_0=3$, so the solution is

$$
\begin{equation*}
N(t)=3e^{-0.5t}
\end{equation*}
$$

*This is a decaying exponential function.*
:::


:::{tip} Exercise 2
:class: dropdown
:open: true

Find the solution to the following differential equation:

$$
\begin{equation*}
\frac{dN}{dt}=rN, \quad N_0=400, \quad N_2=412.
\end{equation*}
$$
:::

:::{tip} Solution to Exercise 2
:icon: false
:class: dropdown
 If we do what we have done before in previous problems, then we obtain the solution

$$
\begin{equation*}
N_t=400e^{rt}.
\end{equation*}
$$

But how do we solve for $r$? Well, notice that we have two conditions. We have used $N_0=400$ already, so the key to solving for $r$ must lie in the other condition, $N_2=412$. Observe,

$$
\begin{equation*}
\begin{aligned}
N_2 &= 400e^{r\cdot2}=412\\
\implies e^{r\cdot2} &= \frac{412}{400}\\
\implies 2r &= \ln\left(\frac{412}{400}\right)\\
\implies r &= \frac{1}{2}\ln\left(\frac{412}{400}\right)=0.0148.
\end{aligned}
\end{equation*}
$$

Thus the final solution is

$$
\begin{equation*}
N=400e^{0.0148t}
\end{equation*}
$$
:::