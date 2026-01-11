# Infectious Disease Modeling
## SIRching for a cure

---

## Introduction

Within the field of epidemiology, mathematical modelling plays an important role in efforts that focus on predicting, assessing and controlling potential outbreaks by identifying the mechanisms by which diseases spread and developing tools to evaluate strategies to control an epidemic. Central to answering numerous questions that arise in the field is the study of the dynamics of disease transmission.

---

## The Basic SIR Model

We start with a simple model. Assume that the population of interest is **well-mixed**, which means that any individual is equally likely to come into contact with any other individual. We can divide the population into three classes:

- **$S$ = Susceptible**: those who are healthy but can be infected with the disease through contact with it
- **$I$ = Infected**: those who have the disease and are contagious
- **$R$ = Recovered or Removed**: those who have had the disease, are no longer infected and are immune from future infection

For now we will also assume that the system is **closed**, so the total population ($N$) remains constant:

$$S + I + R = N \quad \text{for all } t$$

---

## Dynamics of Infectious Disease

For an epidemic to occur, $I$ must increase. A large increase within a short amount of time represents a rapidly spreading outbreak, while a smaller increase signals a more gradual spread. Initially, we would expect the graph of $I$ to rise, as more and more of the population becomes infected. In time, though, if it is possible for individuals to recover, the number of infected individuals $I$ starts to decrease. At that point, the graph of $I$ turns down and the epidemic begins to subside.

**Note:** We have already **assumed that** the disease we are discussing is one from which **infected individuals recover**. Although, this is not true for all infectious diseases.

---

## Model Structure

In this **SIR model**, individuals of the population progress through the three classes in order: susceptibles remain disease-free or become infected; infected individuals pass through an infectious period until they recover from the disease; and a recovered individual is never at risk again (having developed permanent immunity against the disease).

Schematically, we can think of the model as:

```
[Susceptible] → [Infected] → [Recovered]
```

---

## Differential Equations: Susceptible Population

Disease spreads when a susceptible individual comes in contact with an infected individual and subsequently becomes infected. Therefore, the number of susceptibles decreases as susceptibles become ill. Then, the differential equation modeling the susceptible population can be given by:

$$\frac{dS}{dt} = -\alpha SI$$

where $\alpha$ is the **transmission coefficient**, which measures the likelihood that a contact between a susceptible and an infected will result in a new infection.

### Question for Consideration:
If $\alpha_1$ for one disease is smaller than $\alpha_2$ ($\alpha_1 < \alpha_2$) for another disease, what does this indicate about the difference between the diseases? If this is the only difference between the diseases, which will spread faster? Can you give an example?

---

## Differential Equations: Infected and Recovered Populations

The infected population $I$ grows by the addition of newly infected. At the same time, some infected individuals may recover or die, and so progress to the recovered/removed stage of the disease. The recovered/removed population increases in size by exactly the same amount that the infected class decreases. Therefore, our other two differential equations can be written as:

$$\frac{dI}{dt} = \alpha SI - \beta I$$

$$\frac{dR}{dt} = \beta I$$

where $\beta$ is the **removal rate**, measuring the fraction of the infected population that ceases to be infected, and thus moves into the recovered/removed population.

---

## Complete SIR System

The differential equations system altogether can be written as:

$$\begin{cases}
\dfrac{dS}{dt} = -\alpha SI \\\\
\dfrac{dI}{dt} = \alpha SI - \beta I \\\\
\dfrac{dR}{dt} = \beta I
\end{cases}$$

### Understanding the Parameters

The parameters $\alpha$ and $\beta$ are referred to as the **transmission** and **recovery coefficients**, respectively. Let's see where the $\alpha SI$ and $\beta I$ terms come from.

#### Derivation of $\alpha SI$ term:

Consider a single susceptible person, let's call him Rick. Now, Rick can catch the disease if he comes into contact with an infected person. It's unlikely Rick is popular enough to come into contact with everybody who is infected, so he will just come into contact with some proportion of them, say $p \cdot I$ of them, where $0 \leq p < 1$. Further, not every contact with a sick person will result in the spread of the disease, just another proportion of them, call this proportion $q$, where again $0 \leq q < 1$, and so the chances Rick will become infected is $q \cdot pI$.

If we assume that there is nothing special about Rick and that everybody has the same chance of being infected, then per day we would expect $qpI \cdot S$ susceptible people will become infected. Let $\alpha = qp$ and we have $\alpha SI$ people added to the infected population and $\alpha SI$ people lost from the susceptible population.

#### Derivation of $\beta I$ term:

Now let's suppose that the lifespan of the disease is, typically, $k$ days. Then after having the disease for $k$ days, Rick will get better. Now, without thinking too hard about this, there is a $1/k$ chance that today is the day that Rick will get better. Again, assuming that Rick is not special, we would expect that $I/k$ of the infected people will become healthy today. Letting $\beta = 1/k$ we have $\beta I$ people added to the recovered population and $\beta I$ people lost from the infected population.

**Therefore, $\dfrac{1}{\beta}$ measures the lifespan of the disease, or how long the disease lasts (on average) for an infected person.**

---

## Conservation of Population

We can verify that the assumption that the population remains constant is upheld. Since we have split the total population, $N$, into three disjoint categories, we have $N = S + I + R$. So,

$$\frac{dN}{dt} = \frac{dS}{dt} + \frac{dI}{dt} + \frac{dR}{dt} = 0$$

Thus $N$ does not change.

**Note:** One can see that this system has similarities with the predator-prey systems we have already seen. Indeed we could progress with this system the same way we did with the predator-prey, and ask similar questions. But as one might assume, the presence of a third equation does complicate matters.

### Typical SIR Dynamics

*(Graphs would show S decreasing from high to low, I rising then falling in a bell curve, and R increasing from low to high)*

The typical behavior shows:
- **S (blue)**: Decreases over time as people become infected
- **I (red)**: Rises to a peak then decreases as people recover
- **R (green)**: Increases over time as people recover

---

## Disease Spread & Outbreak

An **epidemic** is the local outbreak of disease (a disease is called a *pandemic* when it spreads to a global level as in the case of COVID-19).

### Basic Reproduction Number ($R_0$)

The **basic reproduction rate ($R_0$)** is a crucial parameter for dealing with an epidemic and keeping it under control. It is the average number of secondary infections produced by one primary infection in a wholly susceptible population ($R = 0$) (i.e., the number of individuals a single infectious individual will infect throughout the duration of their infection), given by the formula:

$$R_0 = \frac{\alpha}{\beta}$$

**Interpretation:**
- If $R_0 > 1$: The transmission rate of the infection is higher than the recovery rate, so an **epidemic is bound to occur**
- If $R_0 < 1$: The recovery rate is higher than the transmission rate ($\beta > \alpha$), so the number of recovered individuals should eventually surpass the number of infected, and the **disease will eventually die out**
- If $R_0 = 1$: The transmission rate is equal to the recovery rate ($\alpha = \beta$), and the disease will neither spread nor decline

We compare the initial susceptible population $S_0$ with the $R_0$ value to assess the disease outbreak.

---

## Herd Immunity

Mass vaccination is the cheapest and most effective means of disease control. Although it is generally safe, no medicine is completely risk free as it may carry unprecedented and harmful side-effects. Vaccination not only provides protection for the individual, but also for the community at large, since it keeps the effective reproduction rate below the level which would allow an epidemic to start. This is called **herd immunity**.

### Herd Immunity Threshold (HIT)

The **herd immunity threshold (HIT)** is given by the formula:

$$\textbf{HIT} = 1 - \left(\frac{1}{R_0}\right)$$

The HIT can also be defined as the level at which the transmission of infectious diseases becomes unsustainable as one infected person generates less than one secondary case on average in a population. Often, the HIT can predict total infections achieved at the end of transmission without vaccination. If vaccination is used to control the spread of infectious diseases, the HIT indicates the share of a population that needs to be vaccinated.

---

## Practice Problems

### Problem 1: Pig Farm Virus

A commercial hog farm has 1,000 pigs that are kept together. At some point a virus starts in the population of pigs. Assume that the following SIR model gives a description of the progress of the virus.

$$\begin{cases}
\dfrac{dS}{dt} = -0.001SI \\\\
\dfrac{dI}{dt} = 0.001SI - 0.2I \\\\
\dfrac{dR}{dt} = 0.2I
\end{cases}$$

**(a) For initial conditions $S(0) = 990$, $I(0) = 10$ and $R(0) = 0$, approximate $S(t)$, $I(t)$ and $R(t)$ for $t = 1, 2, 3$:**

| $t$ | $S$ | $I$ | $R$ | $dS/dt$ | $dI/dt$ | $dR/dt$ |
|-----|-----|-----|-----|---------|---------|---------|
| 0 | 990 | 10 | 0 | -10 | 8 | 2 |
| 1 | 980 | 18 | 2 | -18 | 14 | 4 |
| 2 | 962 | 32 | 6 | -31 | 24 | 6 |
| 3 | 931 | 56 | 12 | | | |

**(b) What is the transmission coefficient ($\alpha$) of this virus?**

$$\boxed{\alpha = 0.001}$$

**(c) Approximately how many days is each pig infected for?**

$$\frac{1}{\beta} = \frac{1}{0.2} = \boxed{5 \text{ days}}$$

**(d) What is the basic reproductive rate ($R_0$) for this viral infection? Would this viral infection cause an epidemic among the pig population?**

$$R_0 = \frac{\alpha}{\beta} = \frac{0.001}{0.2} = 0.005$$

Since $R_0 = 0.005 < 1$, the disease will not cause an epidemic, but will eventually die out.

---

### Problem 2: Avian Flu in Chickens

Consider the following SIR model for the spread of a mild form of avian flu in a chicken farm with 100 chickens:

$$\begin{cases}
\dfrac{dS}{dt} = -0.25SI \\\\
\dfrac{dI}{dt} = 0.25SI - 0.1I \\\\
\dfrac{dR}{dt} = 0.1I
\end{cases}$$

**(a) What is the transmission coefficient of this model?**

$$\boxed{\alpha = 0.25}$$

**(b) Approximately how many days is each chicken infected for?**

$$\frac{1}{\beta} = \frac{1}{0.1} = \boxed{10 \text{ days}}$$

**(c) For initial conditions $S(0) = 80$, $I(0) = 15$ and $R(0) = 5$, approximate $S(t)$, $I(t)$ and $R(t)$ for $t = 1, 2, 3$:**

| $t$ | $S$ | $I$ | $R$ | $dS/dt$ | $dI/dt$ | $dR/dt$ |
|-----|------|------|------|---------|---------|---------|
| 0 | 80 | 15 | 5 | -3 | 1.5 | 1.5 |
| 1 | 77 | 16.5 | 6.5 | -3.2 | 1.5 | 1.7 |
| 2 | 73.8 | 18 | 8.2 | -3.3 | 1.5 | 1.8 |
| 3 | 70.5 | 19.5 | 10 | | | |

**(d) What is the basic reproductive rate ($R_0$) for this viral infection? Would this viral infection cause an epidemic among the chicken population?**

$$R_0 = \frac{\alpha}{\beta} = \frac{0.25}{0.1} = 2.5$$

Since $R_0 = 2.5 > 1$, the disease will spread into an epidemic.

**(e) What is the herd immunity threshold for this population to control the spread of the viral infection on this farm?**

$$\textbf{HIT} = 1 - \left(\frac{1}{R_0}\right) = 1 - \left(\frac{1}{2.5}\right) = 0.6 \text{ or } 60\%$$

In this farm with 100 chickens, **60 will need to be vaccinated or immune** to achieve herd immunity and control the spread.

---

## Summary of Key Concepts

1. **SIR Model Structure**: $S \rightarrow I \rightarrow R$ (one-way progression)

2. **Key Parameters**:
   - $\alpha$ = transmission coefficient (rate of disease spread)
   - $\beta$ = removal/recovery rate
   - $1/\beta$ = average duration of infection

3. **Basic Reproduction Number**:
   $$R_0 = \frac{\alpha}{\beta}$$
   - $R_0 > 1$: Epidemic occurs
   - $R_0 < 1$: Disease dies out
   - $R_0 = 1$: Endemic (neither grows nor dies)

4. **Herd Immunity Threshold**:
   $$\text{HIT} = 1 - \frac{1}{R_0}$$
   - Proportion of population that needs immunity to stop epidemic

5. **Conservation**: $S + I + R = N$ (constant total population)

6. **System of Equations**:
   $$\begin{cases}
   \dfrac{dS}{dt} = -\alpha SI \\
   \dfrac{dI}{dt} = \alpha SI - \beta I \\
   \dfrac{dR}{dt} = \beta I
   \end{cases}$$