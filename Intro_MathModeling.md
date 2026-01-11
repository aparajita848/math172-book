# Introduction to Mathematical Modeling 

% quotation:
> All models are wrong, but some of them are useful.
> 
> -- George Box

> Everything should be made as simple as possible, but no simpler.
> 
> -- Albert Einstein


A model can be regarded as a caricature of a real system by capturing the key elements, and neglecting the detail ({cite}`Segel2013`).  In particular, we can use mathematical models to study complex interactions in nature through a simplified and structured lens. They also generate testable predictions and by trying to either verify or refute these predictions, we can further investigate the underlying mechanism of the system that we are attempting to study. 


**Definition:** A mathematical model is a representation of the essential aspects of a new or existing system, which presents knowledge of that system in a usable form. Models are not replicas of reality, they are simplified representations of it.

:::{important} Important Model Components
:icon: false

- **Variables** - a symbol that represents a measurement that can change during the course of an experiment. 
  - independent
  - dependent
- **Parameters** - a symbol that represents a measurement that does not change during the course of an experiment.
  - not dependent on independent variables
  - can be varied/changed under experimental conditions
- **Species** - animal, plant, microbe or material whose dynamics we are trying to study and is often taken to be the dependent variable.

- **Dynamics** - pattern of changes over time. 

- **Equation/System** 
  - describes the dynamics of the model
  - represented using either differential or difference equations.
- **Solution**
  - It is the solution to the differential or difference equation or system.

:::


### How to Construct a Model

```{image} images/create_math_model.png
:alt: Types of models.
:width: 500px
:align: center
```
  1. Formulate the question

To construct a model, we first need to begin with the 
	
%The hardest step is to provide a formal set of equations. The single most important aid to this endeavor is what can be called **bookkeeping**. This is the process of keeping track of some quantity that remains invariant

2. Determine the basic ingredients

After identifying our _independent_ and _dependent_ variables; for example, if we are studying the , we can choose the kind of equations 
3. Drawing qualitative conclusions

Manipulation of model equations yields two types of results, quantitative and qualitative. The value of quantitative results is clear, but qualitative conclusions might be even more useful. One 
4. Choosing parameters

It may be possible to draw qualitative conclusions from a model without using any a priori information concerning the magnitudes of the parameters involved. When models begin to be moderately complex, however, it is helpful to know rough orders f magnitude estimates for the various parameters. Such estimates can often be obtained from literature or from general intuition. 
5. Robustness
6. Analysis of results
7. Checks and balances
8. Relate the results back to the question

### Types of Models


```{image} images/types_of_models.png
:alt: Types of models.
:width: 500px
:align: center
```

In general, mathematical models ca

In our course, we will focus on deterministic dynamical models, but study both cases; when time is measured discretely vs. continuously. Discrete-time dynamical systems describe a sequence of measurements made at equally spaced intervals. These dynamical systems are described mathematically by a rule that gives the value at one time as a function of the value at the previous time. Continuous-time dynamical systems, usually called **differential equations**, describe measurements that are collected over an entire time interval. A differential equation consists of a rule that gives the **instantaneous rate of change** of a set of measurements ({cite}`Adler2013`).


### Successes & failures of mathematical modeling

Mathematical modeling is typically the result of a trade-off between accuracy and simplicity since large, complex models may be more accurate in theory, but in practice they are hard to simulate and require many parameters that may not be available or identifiable.

The complexity of the biological sciences makes interdisciplinary involvement essential... for the biologist, mathematical modeling offers another research tool commensurate with a new powerful laboratory technique but _only_ if used appropriately and its limitations recognized.{cite}`Murray2002`.

The modeling process is considered successful when the obtained model possesses the following characteristics:
- **Accurate:** the model should attempt to accurately describe current existing observations.
- **Predictive:** the model should allow to appropriately predict the behavior of the system in situations not already observed.
- **Reusable:** the model can be reused in another, similar case.
- **Parsimonious:** the model should be as simple as possible. That is, given competing and equally good models, the simplest is preferred.

%Definitions Related to Modeling Philosophy {cite}`Botsford2019`
%Generality—strictly speaking, the quality of a statement applying to all cases.

%Realism—having the same structural form as a real object.

%Precision—the quality of a statistical estimate having a narrow distribution of error about apoint, but not necessarily about the true value.

%Accuracy—the quality of a statistical estimate having a narrow distribution of error aboutthe true value.

%Holism—including all of the relevant factors

%Strategic models—models devised to answer very general questions about populationbehavior, with little attention to accurately portraying a specific situation.

%Tactical models—models devised to answer specific questions about real situations for the purpose of making projections on which management will be based

%In what sense is mathematics successful in aiding in biological understanding? As far as the biologist is concerned, 

%It could be argued that every model is a lie, because detail is neglected or major features distorted to bring out the most essential aspects. However just because a model is wrong, is not sufficient reason to reject it, and just because a model is more or less right, is not sufficient reason to accept it. A "wrong" model may be so laden with detail that the principal features are completely obscured. As Picasso said of good art, a good model is "a lie that helps us see the truth"

%However, the use of esoteric mathematics arrogantly applied to biological problems by mathematicians who know little about the real biology, together with unsubstantiated claims as to how important such theories are, do little to promote the interdisciplinary involvement which is so essential. {cite}`Murray2002`
There are two dangers inherent in the use of mathematical models in ecology. The first danger is that we build models that are too complex. When this happens, the models may contain many variable that we can never measure in nature, and the mathematical solutions may be too complex.  Consequently, the most useful ecological models are often the simplest ones. The second danger is that we forget that the models are abstract representations of nature. However logical a model might appear, nothing says that nature must follow its rules. By carefully focusing on the assumptions of the model, we may be able to pinpoint the places where it departs from reality {cite}`Gotelli1998`.