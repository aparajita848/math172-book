# Logistic (Limited) Growth

---

## Density-dependent Growth

In the Malthusian model, we encountered the differential equation:

$$\frac{dN}{dt} = rN$$

where $N(t)$ is the population size at time $t$ and $r$ is the constant representing per capita growth rate. We showed that this differential equation has exponential solutions. It means that two behaviours are generically obtained: explosive growth if $r > 0$ or extinction if $r < 0$.

The case of $r > 0$ is unrealistic in the long-run, since real populations cannot keep growing indefinitely in an explosive, exponential way. Eventually running out of space or resources, the population growth dwindles, and the population attains some static level rather than expanding forever. This motivates a revision of our previous model to depict **density-dependent growth**.

Intuitively, the higher the population, the more resources are being used. So, as resources deplete, the birth rate should slow down. If it doesn't, the resources run dry and everybody dies. We start with the familiar exponential model

$$\frac{dN}{dt} = (b' - d')N$$

but instead of $b'$ and $d'$ being constant, we will modify them to be density dependent and reflect ***crowding***.

---

## Modeling Crowding Effects

### Density-Dependent Birth Rate

As a population becomes more crowded, we expect the per capita birth rate to decrease, since there are fewer resources per organism available. So let's start with the simplest decreasing function - a straight line with negative slope.

$$b' = b - aN$$

where $b$ and $a$ are constants. Notice how if the population is small then $b' \approx b$, so then we are essentially in the ideal conditions of unlimited resources. Then as $N$ grows larger we move away from that. So, $b$ is the same as it was in the exponential model - it is the instantaneous per capita birth rate when resources are unlimited. The constant $a$ measures the strength of the density dependence. If $a$ is large, then the birth rate drops sharply as the population grows. If there is no dependence on population - i.e. $a = 0$ - then we obtain the exponential model as before. So we are generalizing our model.

### Density-Dependent Death Rate

The same idea can be applied to death rates - as the population grows, death rates should increase. So,

$$d' = d + cN$$

for constants $d$ and $c$, where $d$ is as in the exponential model and $c$ is the strength of the density dependence.

---

## Deriving the Logistic Equation

Combining the above equations then, we have

$$\frac{dN}{dt} = ((b - aN) - (d + cN))N = ((b - d) - (a + c)N)N$$

If we multiply this equation by $1 = (b-d)/(b-d)$, then we have

$$\frac{dN}{dt} = (b - d)\left(1 - \frac{(a+c)}{(b-d)}N\right)N$$

As with the exponential model, let $r = b - d$ and define

$$K = \frac{(b - d)}{(a + c)}$$

called the **carrying capacity**. Then our model becomes

$$\boxed{\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)}$$

This is the **logistic growth equation**. It is the simplest model that describes population growth in an environment with limited resources.

---

## Understanding the Logistic Model

Notice that it looks a lot like the exponential model we have already seen, but with an extra term tacked onto it. This term, $(1 - N/K)$ represents the **unused portion of the carrying capacity**. It is the percentage of resources that are available.

### Example Interpretation:
- Suppose $K = 100$ and $N = 7$
- Then the unused portion of the carrying capacity is $(1 - (7/100)) = 0.93$
- So the population is resource rich and growing at 93% of the growth rate of an exponentially increasing population
- Similarly, if $N$ was close to $K$ the population would grow at a much slower rate

### What if $N > K$?
If the population exceeds the carrying capacity, the term in parentheses becomes negative and so the growth rate will be negative. So instead of growing, the population will decline and will grow again once $N < K$.

### Growth Conditions:
- **Exponential model**: Population stops growing if either $r$ or $N$ were zero
- **Logistic model**: Population also stops changing if $N = K$
- Other values of $N$ will mean that the population will always tend towards $K$

---

## Graphical Interpretation: Birth and Death Rates

*(Diagram would show density-dependent birth and death rates intersecting at $N = K$)*

The density dependent birth and death rates are plotted. Their point of intersection is where $N = K$, which you can show with some simple algebra:
- **When $N < K$** (left of intersection): births outnumber deaths → population increases
- **When $N > K$** (right of intersection): deaths outnumber births → population decreases

The point where $N = K$ forms a **stable equilibrium**. It means as long as the starting population is non-zero, the population size will always tend towards $K$.

---

## Explicit Solution

With the exponential growth model, we were able to write an explicit expression for the population size at any given time $t$. Although the derivation is more complicated, we can do the same with the logistic model:

$$N_t = \frac{K}{1 + \left(\frac{K - N_0}{N_0}\right)e^{-rt}}$$

Graphically, the logistic growth curve looks like an **S-shaped curve**. The tendency towards the carrying capacity is seen as a horizontal asymptote.

*(Diagram would show S-shaped curves with different initial populations, all approaching $K = 100$)*

**Key features:**
- All curves approach the carrying capacity $K$
- If $N_0 < K$: population increases in S-shape
- If $N_0 > K$: population decreases to $K$
- Growth is fastest at $N = K/2$ (inflection point)

---

## Example: Fish Population

Suppose a species of fish in a lake is modeled by a logistic population model with intrinsic growth rate of $r = 0.3$ (or 30%) per year and carrying capacity of $K = 10000$.

### (a) Write the differential equation

$$\frac{dN}{dt} = 0.3N\left(1 - \frac{N}{10000}\right)$$

### (b) Determine the equilibrium solutions

$$\frac{dN}{dt} = 0.3N\left(1 - \frac{N}{10000}\right) = 0$$

This gives us:
- $0.3N = 0 \Rightarrow N = 0$
- $1 - \frac{N}{10000} = 0 \Rightarrow N = 10000$

**For the logistic equation, the equilibrium points lie at $N = 0$ and the carrying capacity $N = K = 10000$.**

### (c) If 2500 fish are initially introduced into the lake

**(i) Solve and find the analytic explicit solution $N(t)$:**

$$N_t = \frac{10000}{1 + \left(\frac{10000 - 2500}{2500}\right)e^{-0.3t}} = \frac{10000}{1 + 3e^{-0.3t}}$$

**(ii) Estimate the number of fish after 5 years:**

$$N_5 = \frac{10000}{1 + 3e^{-0.3(5)}} = 5990 \text{ fish}$$

**(iii) Graph $N(t)$:**

*(Diagram would show S-shaped curve starting at $N_0 = 2500$, approaching horizontal asymptote at $K = 10000$)*

**Key features of graph:**
- Initial population: $N_0 = 2500$
- Carrying capacity: $K = 10000$ (horizontal asymptote)
- S-shaped curve
- Fastest growth at $N = 5000$

**(iv) Time to reach 8000 fish:**

Using a graphing calculator, it takes about **8.3 years** for there to be 8000 fish in the lake.

---

## Steady-state & Equilibrium Points

When we study a population model we are most likely interested in **long-term behaviour**. Often, after enough time has passed, the model settles into a pattern. With respect to the previous discussion, the carrying capacity is the population that the model wants to tend towards. If it were to reach this value, then the population would remain the same. One can see this by plugging $N = K$ into our model:

$$\frac{dN}{dt}\bigg|_{N=K} = rN\left(1 - \frac{N}{K}\right)\bigg|_{N=K} = rK\left(1 - \frac{K}{K}\right) = 0$$

When the derivative is zero, there is no change. Since we assume that our change is entirely dependent on the current population size, as soon as the population remains the same for one time period, it will remain the same from that point onwards.

This value $N = K$ is called an **equilibrium point**. For the logistic growth model there are two equilibrium points, $N = 0$ and $N = K$. If the population were to reach either of these values then they would never change. Since our differential equations give the derivative of our model, to find equilibrium points we simply set our equation to zero and solve.

---

## Stability Analysis

*(Diagram would show parabolic curve of $dN/dt$ vs $N$, with arrows indicating direction of population change)*

**Key features:**
- Maximum growth rate occurs at $N = K/2$ (where $dN/dt = rK/4$)
- Equilibrium points at $N = 0$ and $N = K$
- Arrows show direction of population movement

### Classifying Equilibrium Points

We can classify the equilibrium points further. Notice the arrows in the plot:
- When $dN/dt > 0$: population $N$ is **increasing** (moves right)
- When $dN/dt < 0$: population $N$ is **decreasing** (moves left)

**At $N = 0$ (unstable equilibrium):**
- When population is *close* to zero, the population is increasing away from the equilibrium point
- We call this point an **unstable** or **repelling** equilibrium point
- The population is repelled - it wants to move away

**At $N = K$ (stable equilibrium):**
- When $N$ is *close* to $K$, the population size is moving towards $K$
  - If below: increases
  - If above: decreases
- We call this type of equilibrium point **stable** or **attracting**
- The population is attracted - it moves towards this point

**Summary:** For the logistic model, there are always 2 equilibrium points:
- An **unstable** one at $N = 0$
- A **stable** one at $N = K$

---

## Allee Effect

### All's well that ends well

We have already talked about how population grows in terms of the logistic model and how the carrying capacity works - it governs the behaviour of populations with high densities. But we have not yet considered how a small population might affect growth.

Our initial assumptions say that the growth rate of a population will decrease at higher densities and increase at lower densities due to competition for limited resources - food and land for example. But if you had a population consisting of, say, a single tiger, then it does not matter how much food or land that tiger has, the population will die out because it has nothing to breed with.

**The Allee effect**, named after Walter Clyde Allee, is the principle that individuals within a population require the presence of other individuals in order to survive and reproduce successfully. Thus when the population size is too small, it will not be able to maintain a positive growth rate.

### The Logistic Equation with Allee Effect

$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)\left(\frac{N}{A} - 1\right)$$

where:
- $r$ = intrinsic growth rate
- $K$ = carrying capacity
- $A$ = **Allee threshold** (minimal size of population required to survive)

We assume that $A < K$, since we want $A$ to represent the *minimum* size the population needs and $K$ should be the *maximum* size it can sustain. The long term outcome of a population modeled by this equation depends on whether the initial value is above or below the value of $A$.

---

## Example: Allee Effect

**Example 1:** Write a possible differential equation for a population whose growth is modeled by a logistic equation with Allee effect if the intrinsic growth rate is 15%, the carrying capacity is 800 individuals and at least 100 individuals are required in order for the population to survive.

$$\frac{dN}{dt} = 0.15N\left(1 - \frac{N}{800}\right)\left(\frac{N}{100} - 1\right)$$

### Behavior Analysis:
- If $N > K$: then $dN/dt < 0$ → population is **decreasing**
- If $A < N < K$: then $dN/dt > 0$ → population is **increasing**
- If $N < A$: then $dN/dt < 0$ → population is **decreasing** (NEW!)

*(Diagram would show three S-curves: one starting above K declining to K, one starting between A and K rising to K, and one starting below A declining to 0)*

**Key features:**
- Carrying capacity $K$ (upper dashed line)
- Critical threshold $A$ (lower dashed line)
- Three different outcomes based on $N_0$

---

## Equilibrium Analysis with Allee Effect

With the addition of this new term, the model picks up another equilibrium point at $N = A$, bringing the total to **three equilibrium points**:

1. **$N = 0$** - **STABLE** (now!)
   - Any population level below $A$ will result in extinction
   - Population is attracted to this point from below $A$

2. **$N = A$** - **UNSTABLE**
   - Critical threshold
   - Population either grows to maximum capacity or dies out
   - Acts as a tipping point

3. **$N = K$** - **STABLE**
   - Carrying capacity
   - Population is attracted to this point from above $A$

*(Diagram would show cubic curve of $dN/dt$ vs $N$ with three equilibrium points marked with arrows showing stability)*

**Stability summary:**
- Arrows pointing away from $N = A$: **unstable**
- Arrows pointing toward $N = 0$: **stable**
- Arrows pointing toward $N = K$: **stable**

---

## Example Continued: Allee Threshold

### (d) Suppose there needs to be a minimum of 1000 fish for survival

**(i) Modify the logistic model to incorporate the critical population threshold:**

$$\frac{dN}{dt} = 0.3N\left(1 - \frac{N}{10000}\right)\left(\frac{N}{1000} - 1\right)$$

**(ii) What are the equilibrium solutions for this new model?**

$$\frac{dN}{dt} = 0.3N\left(1 - \frac{N}{10000}\right)\left(\frac{N}{1000} - 1\right) = 0$$

This gives us three equilibrium points:

1. $0.3N = 0 \Rightarrow N = 0$
2. $1 - \frac{N}{10000} = 0 \Rightarrow N = 10000$
3. $\frac{N}{1000} - 1 = 0 \Rightarrow N = 1000$

**For the logistic equation with Allee threshold, the equilibrium points lie at:**
- $N = 0$ (stable)
- $N = A = 1000$ (unstable, Allee threshold)
- $N = K = 10000$ (stable, carrying capacity)

---

## Notation Summary

| Symbol | Meaning |
|--------|---------|
| $A$ | Allee threshold |
| $b$ | Instantaneous birth rate |
| $d$ | Instantaneous death rate |
| $\Delta N$ | Change in population size between time $t$ and $t+1$ |
| $\frac{dN}{dt}$ | Population growth rate |
| $e$ | Euler's number |
| $K$ | Carrying capacity |
| $N$ | Population size |
| $N_0$ | Initial population |
| $N_t$ | Population size at time $t$ |
| $r$ | Instantaneous rate of increase |
| $t$ | Time |
| $t_D$ | Doubling time |
| $t_H$ | Half-life |

---

## Key Takeaways

1. **Logistic growth** models populations with limited resources: $\frac{dN}{dt} = rN(1 - N/K)$
2. **Carrying capacity** $K$ is the maximum sustainable population
3. The term $(1 - N/K)$ represents the unused portion of carrying capacity
4. **Two equilibrium points**: $N = 0$ (unstable) and $N = K$ (stable)
5. Growth is fastest at $N = K/2$ (inflection point of S-curve)
6. **Allee effect** adds a minimum viable population threshold $A$
7. With Allee effect, **three equilibrium points**: $N = 0$ (stable), $N = A$ (unstable), $N = K$ (stable)
8. Initial population determines long-term fate when Allee effect is present