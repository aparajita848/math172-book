# (EXTRA) Predator-Prey Model Variation
## Incorporating a Prey Carrying Capacity

> **Note:** *Not part of your syllabus, just to give you an example of how we could tweak our simplistic Predator-Prey model to add other dynamics.*

---

## Introduction

The unique prediction of the Predator-Prey model is **cycles** of predator and prey populations. However, these cycles are very sensitive to the restrictive assumptions and nullclines of the model. Here, we incorporate a more realistic assumption about predators and prey that bend the nullclines and produce other dynamics.

The general form of our **Predator-Prey Model** looks like:

$$\begin{cases}
\dfrac{dP}{dt} = F_1(P) - G_1(P,Q) \\\\
\dfrac{dQ}{dt} = F_2(Q) + G_2(P,Q)
\end{cases}$$

where the functions $F_1$ and $F_2$ represent the population growth of $P$ and $Q$, respectively, if there were no interactions between the two species. The functions $G_1$ and $G_2$ represent the effect of predation on the two species.

---

## Model with Prey Carrying Capacity

For the discussion here we will look at a model where the prey population grows logistically in the absence of a predator and the prey is the sole food source for the predators. By adding a carrying capacity to the prey population, we can model a more realistic situation where we can expect that as the prey population becomes more crowded, it will start to be limited by other resources (that have nothing to do with predators).

We begin by obtaining the equation for the prey population, denoted by $P$. We assume that in the absence of predators the population follows a logistic growth model:

$$\frac{dP}{dt} = rP\left(1 - \frac{P}{K}\right)$$

Now if we assume that the decrease in the number of prey is proportional to the number of predators, denoted by $Q$, we obtain:

$$\frac{dP}{dt} = rP\left(1 - \frac{P}{K}\right) - sQP$$

where $s$ is a positive constant.

For the predator, we assume that its sole food source is the prey, so without it the population decreases exponentially. The population increase due to predation will again be assumed to be proportional to the population of prey. This yields:

$$\frac{dQ}{dt} = -uQ + vQP$$

where $u$ and $v$ are positive constants.

### Complete Model

To clarify, the predator-prey model we have formulated here is

$$\begin{cases}
\dfrac{dP}{dt} = rP\left(1 - \dfrac{P}{K}\right) - sQP \\\\
\dfrac{dQ}{dt} = -uQ + vQP
\end{cases}$$

where $r, K, s, u,$ and $v$ are all positive constants, where $u < 1$.

---

## Equilibria and Stability

Recall that our previous encounters with determining equilibria involved us finding roots of the derivative in our model. For the predator-prey model this is still the same, the only difference is that now we require that **both derivatives need to be zero** at the same time. That is: The equilibrium points of the predator-prey model occur when

$$\frac{dP}{dt} = \frac{dQ}{dt} = 0$$

Solving one derivative equal to zero is straightforward. Solving two simultaneously can be tricky. To facilitate this, here we introduce **nullclines**, which are lines where one of the derivatives is equal to zero.

---

## Finding the Nullclines

### P-Nullclines

The nullclines for $dP/dt = 0$ are found as:

$$\frac{dP}{dt} = rP\left(1 - \frac{P}{K}\right) - sQP = P\left[r\left(1 - \frac{P}{K}\right) - sQ\right] = 0$$

so the two solutions are

$$P = 0 \quad \text{or} \quad Q = \frac{r}{s}\left(1 - \frac{P}{K}\right) \tag{1}$$

### Q-Nullclines

The nullclines for $dQ/dt = 0$ are found as:

$$\frac{dQ}{dt} = -uQ + vQP = Q[-u + vP] = 0$$

so the two solutions are

$$Q = 0 \quad \text{or} \quad P = \frac{u}{v} \tag{2}$$

---

## Visualizing Nullclines

### P-Nullclines Graph

The P-nullclines consist of:
- A vertical line: $P = 0$ (the Q-axis)
- A decreasing linear line: $Q = \frac{r}{s}\left(1 - \frac{P}{K}\right)$ from point $(0, \frac{r}{s})$ to point $(K, 0)$

### Q-Nullclines Graph

The Q-nullclines consist of:
- A horizontal line: $Q = 0$ (the P-axis)
- A vertical line: $P = \frac{u}{v}$

---

## Determining Direction of Population Change

The colored lines indicate when the given derivative is zero. We can then choose a point on the plane and from its position relative to these lines we can determine in which direction the population is moving.

### For P-Nullclines:
- **Inside the triangle** (below the line $Q = \frac{r}{s}(1 - P/K)$): We have $Q < \frac{r}{s}(1 - P/K)$, so $\frac{dP}{dt} > 0$ → $P$ is **increasing** (arrows point right)
- **Above the line**: $\frac{dP}{dt} < 0$ → $P$ is **decreasing** (arrows point left)

### For Q-Nullclines:
- **Left of the line** $P = \frac{u}{v}$: We have $P < \frac{u}{v}$, so $\frac{dQ}{dt} < 0$ → $Q$ is **decreasing** (arrows point down)
- **Right of the line**: $\frac{dQ}{dt} > 0$ → $Q$ is **increasing** (arrows point up)

---

## Phase Plane Analysis

When we overlay both sets of nullclines on the same plot, we can determine the direction of motion in each region by combining the horizontal movement (from P-nullclines) and vertical movement (from Q-nullclines).

### The Four Quadrants:

The phase plane is divided into four regions by the nullclines:

1. **Lower Left** (below P-nullcline, left of Q-nullcline):
   - $P$ increasing (→), $Q$ decreasing (↓)
   - Net direction: Southeast

2. **Upper Left** (above P-nullcline, left of Q-nullcline):
   - $P$ decreasing (←), $Q$ decreasing (↓)
   - Net direction: Southwest

3. **Upper Right** (above P-nullcline, right of Q-nullcline):
   - $P$ decreasing (←), $Q$ increasing (↑)
   - Net direction: Northwest

4. **Lower Right** (below P-nullcline, right of Q-nullcline):
   - $P$ increasing (→), $Q$ increasing (↑)
   - Net direction: Northeast

---

## Equilibrium Points

The equilibrium points are the points of intersection of the P-nullclines with the Q-nullclines. There are **three equilibrium points**:

1. **(0, 0)**: The origin (both populations extinct)
2. **(K, 0)**: Only prey present, at carrying capacity
3. **$\left(\frac{u}{v}, \frac{r}{s}\left(1 - \frac{u}{vK}\right)\right)$**: Coexistence equilibrium

---

## Stability Analysis

As with single species models, we can determine the stability of each equilibrium point by looking at the direction of the arrows with respect to the points.

### Spiral Behavior

Taking a point anywhere on the quadrant, we move in the direction the arrows tell us. The result, in the case of a stable equilibrium, is a path that **spirals into a stable equilibrium point**.

**Example trajectory:** Starting with a point in the 'lower left quadrant':
1. The arrows tell us to move down and to the right
2. Once we cross into the 'lower right quadrant', the direction changes to up and to the right
3. Continuing in this manner, we see that the result is a spiral path that converges to the interior equilibrium point

This spiral pattern is characteristic of predator-prey models with a prey carrying capacity, where the system exhibits **damped oscillations** that eventually stabilize at the coexistence equilibrium.

---

## Key Features of This Model

1. **Three equilibrium points**: extinction, prey-only, and coexistence
2. **Stable coexistence**: Unlike the classic Lotka-Volterra model (which has neutral stability), this model can have a stable interior equilibrium
3. **Damped oscillations**: Populations spiral toward equilibrium rather than cycling indefinitely
4. **More realistic**: The prey carrying capacity represents resource limitation independent of predation

---

## Summary

The addition of a carrying capacity to the prey population creates a more realistic predator-prey model that:
- Allows for stable coexistence of both species
- Produces damped oscillations rather than perpetual cycles
- Reflects the fact that prey populations face resource limitations beyond just predation
- Results in a system where populations converge to a stable equilibrium over time

The key difference from the basic Lotka-Volterra model is that the prey nullcline is now **curved** (linear, actually, but not vertical/horizontal), which fundamentally changes the dynamics and allows for asymptotic stability at the interior equilibrium point.