# Modeling Biochemical Kinetics

## Introduction

In this section we will learn to recognize and formulate the governing equations of biochemical kinetics and learn some simple principles to analyze such equations.

## Two Molecular States

Let's consider a simple case where a **biological complex switches between two states**. One prototypical example is ion channels, which are pores in the membrane of a cell that are responsible for the electric conductance of membranes. The channel molecules typically shift between open and closed configurations.

%Add figure

The conventional description of a molecule shifting between two states, $A$ and $B$ (for example, open and closed), is the ***kinetic scheme***,

$$
\begin{equation*}
A \xrightleftharpoons[k_{-1}]{k_{1}} B.
\end{equation*}
$$

In this case $A$ and $B$ denote the **concentration** (number per unit volume) of the two molecular configurations, as well as their **states**.

To develop a mathematical equation we first need to make some assumptions:

- Transitions between states are random
- The probability that a transition occurs during some time interval does not depend on the history of events preceding the time in question
- If environmental conditions are fixed then the overall characteristics of the transitions that occur in some time interval do not depend on the time at which the observations are made

We can now derive an equation describing the change in concentration of $A$ and $B$ species over time. If we consider species $A$ then at a given time step $\Delta t$ the only possibility is that (i) the molecule remains in state $A$ or (ii) the molecule shifts to state $B$. We define $k_1 \Delta t$ to be the probability that (ii) occurs. We need to use $\Delta t$ here because $k_1$ is a rate, so that it has units of 1/time. Then, on average,

$$
\begin{equation*}
\begin{aligned}
\text{decrease in } A \text{ molecules} &= \text{total number of } A \text{ molecules} \times \text{fraction that become } B\\
&= A \cdot (k_1 \Delta t)\\
\\
\text{increase in } A \text{ molecules} &= \text{total number of } B \text{ molecules} \times \text{fraction of } B \text{ molecules that become } A\\
&= B \cdot (k_{-1} \Delta t).
\end{aligned}
\end{equation*}
$$

The expected change in the number of $A$ molecules during the time interval $t + \Delta t$ is

$$
\begin{equation*}
\begin{aligned}
A(t +\Delta t) - A(t) &= -A(t) \cdot (k_1 \Delta t) + B(t) \cdot (k_{-1} \Delta t)\\
\\
\frac{A(t +\Delta t) - A(t)}{\Delta t} &= -k_{1} \, A(t) + k_{-1} \, B(t)
\end{aligned}
\end{equation*}
$$

We can take the limit $\Delta t \to 0$ and use the definition of the derivative

$$
\begin{equation*}
\frac{dA}{dt} = \lim_{\Delta t\to 0} \frac{A(t +\Delta t) - A(t)}{\Delta t},
\end{equation*}
$$

which leads us to our differential equation

$$
\begin{equation*}
\frac{dA}{dt} = -k_{1} \, A + k_{-1} \, B.
\end{equation*}
$$

Similarly we can obtain for $B$

$$
\begin{equation*}
\frac{dB}{dt} = k_{1} \, A - k_{-1} \, B.
\end{equation*}
$$

The solution to these equations is

$$
\begin{equation*}
\begin{aligned}
A(t) &= A_{\infty} - (A_{\infty} -A_0) e^{-(k_1+ k_{-1}) t}\\
B(t) &= M-A(t),
\end{aligned}
\end{equation*}
$$

where

$$
\begin{equation*}
A_{\infty} = \frac{k_{-1} M}{k_1 + k_{-1}},
\end{equation*}
$$

$A_0$ is the initial concentration of $A$ and $M = A+B$[^conservation] is the total concentration of molecules, considered to be constant for all times.

:::{note}
This comes from the **conservation law**, and implies that in the given kinetic scheme molecules merely shift between two conformations, so that their total number is conserved (does not change).
:::

Let's look at some special cases:

- When $t=0$,

$$
\begin{equation*}
\begin{aligned}
A &= A_{\infty} - (A_{\infty} -A_0) e^{-(k_1 + k_{-1}) \cdot 0}\\
&= A_{\infty} - (A_{\infty} -A_0) e^{0}\\
&= A_{\infty} - (A_{\infty} -A_0) \cdot 1\\
&= A_{\infty} - (A_{\infty} -A_0) = A_{\infty} - A_{\infty} + A_0\\
&= A_0.
\end{aligned}
\end{equation*}
$$

This is why we called $A_0$ the initial concentration.

- $A_{\infty}$ gives the long-time behavior of $A$. To see this, assume $t \to \infty$

$$
\begin{equation*}
\begin{aligned}
\lim_{t\to \infty} e^{-t} &= 0,\\
\lim_{t\to \infty} e^{-2 t} &= \left(\lim_{t\to \infty} e^{-t} \right)^2 = (0)^2 = 0,
\end{aligned}
\end{equation*}
$$

so that

$$
\begin{equation*}
\begin{aligned}
\lim_{t\to \infty} A &= \lim_{t\to \infty} \left[A_{\infty} - (A_{\infty} -A_0) e^{-(k_1 + k_{-1}) t} \right]\\
&= A_{\infty} - (A_{\infty} -A_0)\lim_{t\to \infty} e^{-(k_1+ k_{-1})}\\
\\
&= A_{\infty} - (A_{\infty} -A_0) \cdot 0 = A_{\infty}.
\end{aligned}
\end{equation*}
$$

- **Steady-states** of $A$ and $B$ occur when concentrations are constant. At steady state:

$$
\begin{equation*}
\begin{cases}
\dfrac{dA}{dt} = -k_1A+k_{-1}B=0\\ 
\dfrac{dB}{dt} = k_1A-k_{-1}B=0
\end{cases}
\implies k_1A=k_{-1}B
\end{equation*}
$$

The rate of conversion of $A$ to $B$ should exactly balance the rate of conversion of $B$ to $A$.

For all the examples below, let's assume $M=100$.

### Example 1

If $k_1 = 0.1$, $k_{-1} = 0.5$, and

**(a)** $A_0 = 90$

**(b)** $A_0 = 5$

- In which case will you have more $A$ after a long time (long-time behavior)?

:::{tip} Solution
:icon: false
:class: dropdown

  Note that in the formula for $A_{\infty}$, the long term behaviour of $A$ depends on the rates of conversion and the total concentration $M$. Since they are the same for both cases, both will have the same concentration of $A$ in the long-term.
:::

- What is the limiting value of $A$?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
  A_{\infty} = \frac{k_{-1}M}{k_1+k_{-1}} = \frac{0.5 \cdot (100)}{0.1+0.5} = \frac{50}{0.6} = 83.33
\end{equation*}
$$

:::

- Is $A$ growing or decaying in (a)? in (b)?

:::{tip} Solution
:icon: false
  Comparing the initial values to $A_{\infty}$, we see that $A$ is decaying in (a) while it is growing in (b).
:::

### Example 2

For $k_1 = 0.25$ and $A_0 = 10$, the two figures below show the concentration of $A$ and $B$ as functions of time. One of the figures corresponds to $k_{-1}<k_1$ and the other to $k_{-1}>k_1$.

**(a)** Which one is $k_{-1}<k_1$? Which is $k_{-1}>k_1$?

:::{tip} Solution
:icon: false
:class: dropdown

:::

**(b)** Knowing that $A_{\infty} = 200/3$, can you determine the value of $k_{-1}$?

:::{tip} Solution
:icon: false
:class: dropdown

:::

%Add figures

---

## The Law of Mass Action

In the last section we considered kinetic reactions where we only have one reactant and one product. In this section we will consider reactions where two molecules have to collide in order to form some product. To formulate the relevant equations we make use of the **Law of Mass Action:**

***In a reaction involving the interaction of two types of molecules, the rate of reaction is proportional to the concentrations of the two reactants.***

For example,

%Add figure

In this reaction

$$
\begin{equation*}
A + A \xrightleftharpoons[k_{-1}]{k_{1}} C,
\end{equation*}
$$

the rate of the forward reaction would be $k_1 [A] \cdot [A]$, where the square braces denote concentrations. So that if we want to write the *differential equations* describing the change in reactants and products we have

$$
\begin{equation*}
\begin{aligned}
\frac{dA}{dt} &= -\text{forward} + \text{backward}\\
&= -n k_1 A^2 + m k_{-1} C,
\end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
\frac{dC}{dt} &= \text{forward} - \text{backward}\\
&= i k_1 A^2 - j k_{-1} C.
\end{aligned}
\end{equation*}
$$

Here $n$, $m$, $i$ and $j$ are constants found through mass balance.

In our case we know that you lose two $A$ molecules in order to form one $C$ molecule so that $n=2$. Similarly, every time a $C$ molecule breaks it gives two $A$ molecules, so $m=2$. Since only one $C$ is formed at each forward reaction and only one $C$ is gained at each backward reaction, $i=j=1$. Then our differential equations become:

$$
\begin{equation*}
\begin{aligned}
\frac{dA}{dt} &= -2 k_1 A^2 + 2 k_{-1} C,\\
\\
\frac{dC}{dt} &= k_1 A^2 - k_{-1} C.
\end{aligned}
\end{equation*}
$$

Another way of looking at this is noting that $A + 2C$ is always the same, independent of time. This means that the total amount of single molecules at a given time is conserved.

Let's look at other reactions and their differential equations.

### Two-molecule Dimerization

Two types of molecules, $A$ and $B$, combine to form a complex $C$

%Add figure

$$
\begin{equation*}
A + B \xrightleftharpoons[k_{-1}]{k_{1}} C
\end{equation*}
$$

Which gives the differential equations

$$
\begin{equation*}
\begin{aligned}
\frac{dA}{dt} &= -k_1 A\,B + k_{-1} C,\\
\\
\frac{dB}{dt} &= -k_1 A\,B + k_{-1} C,\\
\\
\frac{dC}{dt} &= k_1 A\,B - k_{-1} C.
\end{aligned}
\end{equation*}
$$

### Enzyme Kinetics

An enzyme molecule, $E$, binds to a substrate molecule, $S$, to form a complex $C$; this reaction is reversible. The complex then breaks into a product, $P$, and the original enzyme, which can then catalyze a new reaction. (The second step is assumed to be very fast, since the enzyme catalyzes the reaction.)

%Add figure

$$
\begin{equation*}
E + S \xrightleftharpoons[k_{-1}]{k_{1}} C \xrightarrow{k_{2}} E+P
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
\frac{dE}{dt} &= -k_1 E\,S + k_{-1} C + k_2 C,\\
\\
\frac{dS}{dt} &= -k_1 E\,S + k_{-1} C,
\end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
\frac{dC}{dt} &= k_1 E\,S - k_{-1} C - k_2 C,\\
\\
\frac{dP}{dt} &= k_{2} C.
\end{aligned}
\end{equation*}
$$

---

## Exercises

