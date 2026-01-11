# Differential Equations for Exponential Growth & Decay[^Source:{cite} (edited for the purpose of this course.)]

:::{tip} Warm-up
:class: dropdown
:open: true
Evaluate the following derivatives:

$$
\begin{align*}
\frac{d}{dx}[e^x] &= \\
\frac{d}{dx}[e^{kx}] &=
\end{align*}
$$

Suppose that $y=e^x$ rewrite the derivatives in terms of $y$.
:::
:::{tip} Solution
:class: dropdown
$$
\begin{align*}
\frac{d}{dx}[e^x] &= e^x\\
\frac{d}{dx}[e^{kx}] &= ke^x
\end{align*}
$$
Observe that the derivative of the function $e^x$ is itself, therefore, if $y=e^x$ then

$$
\frac{de^x}{dx}=e^x \implies \frac{dy}{dx}=y
$$ 
And similarly, if we let $y=e^{kx}$,
$$
\frac{de^{kx}}{dx}=ke^{kx} \implies \frac{dy}{dx}=ky
$$

The equation on the right (linking a function to its own derivative) is a new kind of equation called a **differential equation** (abbreviated DE). We say that $y=e^x$ is a function that "satisfies" the equation, and we call this a **solution to the differential equation**.
:::

**Definition**: A **differential equation** is a mathematical equation that relates one or more derivatives of some function to the function itself. Solving the differential equation is the process of identifying the function(s) that satisfies the given relationship.

:::{note}
The solution to an algebraic equation is a number, whereas the solution to a differential equation is a function.
:::

_Since we are interested in observing changing populations over time, we will henceforth use the independent variable $t$ for time and the dependent variable as $N$ for the population size._

$$
N(t) = \text{population size as a function of time } t.
$$

### _Observations_

- Consider the function $N(t)=e^t$. Show that this function satisfies the differential equation

$$
\frac{dN}{dt}=N
$$

:::{tip} Solution
:class: dropdown
Differentiating the function $N(t)=e^t$ gives

$$
\begin{align*}
\frac{dN}{dt} &= \frac{d}{dt}[e^t]=e^t\\
\frac{dN}{dt} &= N
\end{align*}
$$
:::

- The function $N(t)=e^{rt}$ (for $r$ constant) satisfies the differential equation

$$
\frac{dN}{dt}=rN \tag{1}
$$

:::{tip} Solution
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

## Solutions to a Differential Equation

### Definition: Solution to a Differential Equation

By a **solution to a differential equation**, we mean a function that satisfies that equation.

We often refer to "solution curves" - the graphs of the family of solutions of a differential equation, as shown, for example, in the panels of graphs above. So far, we found that "many" functions can be valid solutions of the differential equation (1), since we can choose the constant $C$ arbitrarily in the family of solutions $N(t) = Ce^{rt}$.

Hence, in order to distinguish one specific solution of interest, we need additional information. This additional information is called an **initial value, or initial condition**, and it specifies one point belonging to the solution curve of interest. A common way to set an initial value is to specify a fixed value of the function (say $N = N_0$) at time $t = 0$.

### Definition: Initial Value

An **initial value** for a differential equation is a specified, known value of the solution at some specific time point (usually at time $t = 0$).

---

### Example

Given the differential equation $\frac{dN}{dt}=rN$ and initial value $N(0)=N_0$, find the value of $C$ for the solution in equation $N(t)=Ce^{rt}$.

*Solution.* To solve:

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

### Unique Solution

The **(unique) solution** to the differential equation

$$
\frac{dN}{dt}=rN
$$

with the initial condition $N(0)=N_0$ is the **unique** function

$$
N(t)=N_0e^{rt}
$$

---

## Exercises

```{exercise}
:label: ex1_DiffEqns

Find the solution to the differential equation

$$
\frac{dN}{dt}=-0.5N
$$

that satisfies the initial condition $N(0)=3$. Describe the behaviour of the solution you have found *(sketch a graph)*.
```
```{solution} ex1_DiffEqns
:label: ex1_DiffEqns_sol
The differential equation (DE) indicates that $r=-0.5$, so solutions are exponential functions of the form $N(t)=N_0e^{rt}$ and $N_0=3$, so the solution is

$$
N(t)=3e^{-0.5t}
$$

*This is a decaying exponential function.*
```


```{exercise}
:label: ex2_DiffEqns

Find the solution to the following differential equation:

$$
\frac{dN}{dt}=rN, \quad N_0=400, \quad N_2=412.
$$
```

```{solution} ex2_DiffEqns
:label: ex2_DiffEqns_sol
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
```