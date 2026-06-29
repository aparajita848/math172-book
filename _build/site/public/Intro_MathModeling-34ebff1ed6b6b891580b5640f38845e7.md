# Introduction to Mathematical Modeling 

% quotation:
> All models are wrong, but some of them are useful.
> 
> -- George Box

> Everything should be made as simple as possible, but no simpler.
> 
> -- Albert Einstein


A model can be regarded as a caricature of a real system by capturing the key elements, and neglecting the details ({cite}`Segel2013`).  In particular, we can use mathematical models to study complex interactions in nature through a simplified and structured lens. They also generate testable predictions and by trying to either verify or refute these predictions, we can further investigate the underlying mechanism of the system that we are attempting to study. 


**Definition:** A mathematical model is a representation of the essential aspects of a new or existing system, which presents knowledge of that system in a usable form. Models are not replicas of reality, they are simplified representations of it.

:::{important} Important Model Components
:icon: false

- **Variables** - a symbol that represents a measurement that can change during the course of an experiment. 
  - independent _(usually time $t$)_
  - dependent _(usually population size, $N(t)$)_
- **Parameters** - a symbol that represents a measurement that does not change during the course of an experiment.
  - does not depend on the independent variable
  - can be varied/changed under experimental conditions
- **Constants**
  - fixed, e.g. Avogadro constant, gravitational constant
- **Species** - animal, plant, microbe or material whose dynamics we are trying to study and is often taken to be the dependent variable.

- **Dynamics** - pattern of changes over time. 

- **Equation/System** 
  - describes the dynamics of the model
  - represented using either differential or difference equations.
- **Solution (Explicit)**
  - It is the solution to the differential or difference equation or system.

:::

### Types of Models


```{image} images/types_of_models.png
:alt: Types of models.
:width: 500px
:align: center
```

Fundamentally, mathematical models can be categorized in three main ways. First, models are either discrete or continuous based on how the data is measured. Second, they can be deterministic or stochastic depending on predictability; whether the same inputs always produce the same outputs, or whether randomness causes different outputs each time. Third, models are classified as static or dynamic based on whether they describe a system at a single point in time or show how the system evolves over time. 

In our course, we will focus on deterministic dynamical models, but study both cases; when time is measured discretely vs. continuously. Discrete-time dynamical systems describe a sequence of measurements made at equally spaced intervals. These dynamical systems are described mathematically by a rule that gives the value at one time as a function of the value at the previous time. Continuous-time dynamical systems, usually called **differential equations**, describe measurements that are collected over an entire time interval. A differential equation consists of a rule that gives the **instantaneous rate of change** of a set of measurements ({cite}`Adler2013`).


### How to Construct a Model

```{image} images/create_math_model.png
:alt: Types of models.
:width: 500px
:align: center
```
  1. Formulate the question

To construct a model, we first identify the real-world problem that we wish to investigate and formulate it as a clear question or hypothesis. We can then establish the **assumptions** that will simplify the problem into a workable model - these assumptions define what factors we'll include, what we'll ignore, and what restrictions or conditions apply.
	
%The hardest step is to provide a formal set of equations. The single most important aid to this endeavor is what can be called **bookkeeping**. This is the process of keeping track of some quantity that remains invariant

 2. Determine the basic ingredients

After identifying our _independ,ent_ and _dependent_ variables, we further determine the **parameters**, **constants** and **initial conditions** that characterize the system. Finally, we need to choose the type of equations that would best describe the relationships between them. Since we focus on deterministic dynamic models, our choice is usually between discrete (difference) equations or differential equations, based on how we measure _time_ in our model

 3. Construct the Mathematical Framework

We translate our assumptions and ingredients into formal mathematical equations. The single most important aid in this step is **bookkeeping**—the process of tracking quantities that remain conserved or invariant in the system (such as total population, mass, energy, or probability). These conservation principles often guide us toward the correct form of our equations.

 4. Solve and Simulate the model

Since our model captures the dynamics of a system through rate equations (differential or difference equations), we need to solve these equations to observe how the system changes over time. While simpler models may have known analytical (explicit) solutions, more complex models require numerical methods and computer simulation to generate results.

 5. Analyze the Results

We analyze our simulation results both qualitatively and quantitatively. Qualitative analysis includes studying the model's behavior, equilibrium points, and stability. Quantitative analysis involves extracting specific numerical predictions and comparing trends. Various analytical techniques—such as stability analysis, phase plane analysis, and sensitivity analysis—help us understand the model's behavior under different conditions.

 6. Validate and Refine

We relate our results back to the original question and compare predictions with observed data or real-world behavior. This process is iterative: if your results fail to match reality or answer the original question satisfactorily, you must reconsider your assumptions, adjust parameters, or refine the mathematical framework. The cycle continues until the model adequately represents the system of interest.


### Successes & Failures of Mathematical Modeling

Mathematical modeling is typically the result of a trade-off between **accuracy** and **simplicity** since large, complex models may be more accurate in theory, but in practice they are hard to simulate and require many parameters that may not be available or identifiable.

The modeling process is considered successful when the obtained model possesses the following characteristics:
- **Accurate:** the model should attempt to accurately describe current existing observations.

- **Predictive:** the model should allow to appropriately predict the behavior of the system in situations not already observed.

- **Reusable:** the model can be adapted and applied to other similar cases or systems, demonstrating generality beyond a single specific scenario.
 
- **Parsimonious:** the model should be as simple as possible. That is, given competing and equally good models, the simplest is preferred (Occam's Razor).

%Definitions Related to Modeling Philosophy {cite}`Botsford2019`
%Generality—strictly speaking, the quality of a statement applying to all cases.

%Realism—having the same structural form as a real object.

%Precision—the quality of a statistical estimate having a narrow distribution of error about apoint, but not necessarily about the true value.

%Accuracy—the quality of a statistical estimate having a narrow distribution of error aboutthe true value.

%Holism—including all of the relevant factors

%Strategic models—models devised to answer very general questions about populationbehavior, with little attention to accurately portraying a specific situation.

%Tactical models—models devised to answer specific questions about real situations for the purpose of making projections on which management will be based

The two dangers inherent in the use of mathematical models are **over-complexity** and **confusing the model with reality**. When a model is too complex, it may contain variables we can never measure or mathematical solutions too intricate to interpret meaningfully or prove to be computationally, too expensive. When models become laden with excessive detail, the principal features are obscured. The most useful models are often the simplest ones that still capture the essential dynamics. The second danger is that we forget that the models are abstract representations of nature. However logical or elegant a model appears, nature is not obligated to follow its rules. Models are tools for understanding, not perfect replicas.({cite}`Gotelli1998`)

By carefully examining a model's assumptions and limitations, we can identify where it departs from reality and make informed decisions about when and how to apply it. The key is to use models appropriately while recognizing their inherent limitations.


