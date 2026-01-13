# Infectious Disease Modeling

## Introduction

Within the field of epidemiology, mathematical modeling plays an important role in efforts that focus on predicting, assessing and controlling potential outbreaks by identifying the mechanisms by which diseases spread and developing tools to evaluate strategies to control an epidemic. Central to answering numerous questions that arise in the field is the study of the dynamics of disease transmission.

We start with a simple model. Assume that the population of interest is **well-mixed**, which means that any individual is equally likely to come into contact with any other individual. We can divide the population into three classes: 

- $S=$ susceptible - those who are healthy but can be infected with the disease through contact with it,
- $I=$ infected - those who have the disease and are contagious,
- $R=$ recovered or removed - those who have had the disease, are no longer infected and are immune from future infection.

For now we will also assume that the system is **closed**, so the total population ($N$) remains constant. 

$$
\begin{equation*}
 S+I+R=N\quad \quad \mbox{for all} \; t
\end{equation*}
$$

## Dynamics of Infectious Disease

For an epidemic to occur, $I$ must increase. A large increase within a short amount of time represents a rapidly spreading outbreak, while a smaller increase signals a more gradual spread. Initially, we would expect the graph of $I$, to rise, as more and more of the population becomes infected. In time, though, if it is possible for individuals to recover, the number of infected individuals $I$, starts to decrease. At that point, the graph $I$ turns down and the epidemic begins to subside.

:::{note}
However, that we have already **assumed that** the disease we are discussing is one from which **infected recover**. Although, this is not true for all infectious diseases.
:::

In this **$SIR$ model**, individuals of the population progress through the three classes in order: susceptibles remain disease-free or become infected; infected individuals pass through an infectious period until they recover from the disease; and a recovered individual is never at risk again (having developed permanent immunity against the disease). Schematically, we can think of the model as:


\boxed{Susceptibles}$\Longrightarrow$\boxed{Infected}$\Longrightarrow$\boxed{Recovered}

Disease spreads when a susceptible individual comes in contact with an infected individual and subsequently becomes infected. Therefore, the number of susceptibles decreases as susceptibles become ill. Then, the differential equation modeling the suscpetible population can be given by:

$$
\begin{equation*}
\dfrac{dS}{dt}= -\alpha SI
\end{equation*}
$$

where $\alpha$ is the **transmission coefficient**, which measures the likelihood that a contact between a susceptible and an infected will result in a new infection.

:::{attention} ? Question
:icon: false
If $\alpha_1$ for one disease is smaller than $\alpha_2$ $(\alpha_1<\alpha_2)$ for another disease, what does this indicate about the difference between the diseases? If this is the only difference between the diseases, which will spread faster? Can you give an example?
::

The infected population $I$, grows by the addition of newly infected. At the same time, some infected individuals may recover or die, and so progress to the recovered/removed stage of the disease. The recovered/removed population increases in size, by exactly the same amount that the infected class decreases. Therefore, our other two differential equations can be written as:

$$
\begin{equation*}
\begin{aligned}
    \dfrac{dI}{dt}=& {\colour \alpha SI - \beta I }\\
    \\
    \dfrac{dR}{dt} =& {\colour \beta I}
\end{aligned}
\end{equation*}
$$

where $\beta$ is the **removal rate**, measuring the fraction of the infected population that ceases to be infected, and thus moves into the recovered/removed population.

The differential equations system altogether can be written as:

$$
\begin{equation*}
\begin{aligned}
\begin{cases}
\dfrac{dS}{dt}={\colour -\alpha SI}\\
\\\\
\dfrac{dI}{dt}={\colour \alpha SI-\beta I}\\
\\\\
\dfrac{dR}{dt}={\colour \beta I}
\end{cases}
\hspace*{1cm}\begin{cases}
\dfrac{dS}{dt}=-aSI+rR\\
\\
\dfrac{dI}{dt}=aSI-bI\\
\\
\dfrac{dR}{dt}=bI-rR
\end{cases}\hspace*{1cm}\begin{cases}
\dfrac{dS}{dt}=cN-aSI-cS\\
\\
\dfrac{dI}{dt}=aSI-bI-cI\\
\\
\dfrac{dR}{dt}=bI-cR
\end{cases}\hspace*{1cm}\begin{cases}
\dfrac{dS}{dt}=(c-v)N-aSI-cS\\
\\
\dfrac{dI}{dt}=aSI-bI-cI\\
\\
\dfrac{dR}{dt}=bI-cR+vN
\end{cases}
\end{aligned}
\end{equation*}
$$

We now make some observations. The parameters $\alpha$ and $\beta$ are referred to as the **transmission** and **recovery coefficients**, respectively. Let's see where the $\alpha SI$ and $\beta I$ terms comes from.

Consider a single susceptible person, let's call him Rick. Now, Rick can catch the disease if he comes into contact with an infected person. It's unlikely Rick is popular enough to come into contact with everybody who is infected, so he will just come into contact with some proportion of them, say $p\cdot I$ of them, where $0\leq p<1$. Further, not every contact with a sick person will result in the spread of the disease, just another proportion of them, call this proportion $q$, where again $0\leq q<1$, and so the chances Rick will become infected is $q\cdot pI$. If we assume that there is nothing special about Rick and that everybody has the same chance of being infected, then per day we would expect $qpI\cdot S$ susceptible people will become infected. Let $\alpha=qp$ and we have $aSI$ people added to the infected population and $\alpha SI$ people lost from the susceptible population.

Now lets suppose that the lifespan of the disease is, typically, $k$ days. Then after having the disease for $k$ days, Rick will get better. Now, without thinking too hard about this, there a $1/k$ chance that today is the day that Rick will get better. Again, assuming that Rick is not special, we would expect that $I/k$ of the infected people will become healthy today. Letting $b=1/k$ we have $bI$ people added to the recovered population and $bI$ people lost from the infected population. **_Therefore, $\dfrac{1}{\beta}$ measures the lifespan of the disease, or how long the disease lasts (on average) for an infected person._**

We can verify that the assumption the population remains constant is upheld, since we have split the total population, $N$, into three disjoint categories, we have $N=S+I+R$. So,

$$
\begin{equation*}
\begin{aligned}
\frac{dN}{dt}={\colour \frac{dS}{dt}+\frac{dI}{dt}+\frac{dR}{dt}=0}.
\end{aligned}
\end{equation*}
$$

Thus $N$ does not change.

One can see that this system has similarities with the predator-prey systems we have already seen. Indeed we could progress with this system the same way we did with the predator-prey, and ask similar questions. But as one might assume, the presence of a third equation does complicate matters.

Below are the graphs of what $S$, $I$ and $R$ look like.

%Add graph

## Disease Spread \& Outbreak

An **epidemic** is the local outbreak of disease (a disease is called a _pandemic_ when it spreads to a global level as in the case of COVID-19). The **basic reproduction rate ($R_0$)** is a crucial parameter for dealing with an epidemic and keeping it under control. It is the average number of secondary infections produced by one primary infection in a wholly susceptible population ($R=0$) (i.e. the number of individuals a single infectious individual will infect throughout the duration of their infection), given by the formula:

$$
\begin{equation*}
R_0=\dfrac{\alpha}{\beta}
\end{equation*}

If $R_0>1$, it means that the transmission rate of the infection is higher than the recovery rate, so an epidemic is bound to occur. If $R_0<1$, the recovery rate is higher than the transmission rate ($\beta>\alpha$), so the number of recovered individuals should eventually surpass the number of infected, and the disease will eventually die out. _If $R_0=1$ then the transmission rate is equal to the recovery rate ($\alpha=\beta)$, and the disease will neither spread nor decline._ So we compare the initial susceptible population $S_0$ with the $R_0$ value to assess the disease outbreak.

## Herd Immunity

Mass vaccination is the cheapest and most effective means of disease control. Although it is generally safe, no medicine is completely risk free as it may carry unprecedented and harmful side-effects. Vaccination not only provides protection for the individual, but also for the community at large, since it keeps the effective reproduction rate below the level which would allow an epidemic to start. This is called the **herd-immunity**.

The **herd immunity threshold (HIT)** is given by the formula:

$$
\begin{equation*}
**HIT** = 1-\left(\dfrac{1}{R_0}\right)
\end{equation*}
$$

The HIT can also be defined as the level that the transmission of infectious diseases becomes unsustainable as one infected person generates less than one secondary case on average in a population. Often, the HIT can predict total infections achieved at the end of transmission without vaccination. If vaccination is used to control the spread of infectious diseases, the HIT indicates the share of a population that needs to be vaccinated.


---

## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true

A commercial hog farm has 1,000 pigs that are kept together. At some point a virus starts in the population of pigs. Assume that the following SIR model gives a description of the progress of the virus

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
