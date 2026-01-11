# Introduction to Mathematical Modeling 

% quotation:
> All models are wrong, but some of them are useful.
> 
> -- George Box

> Everything should be made as simple as possible, but no simpler.
> 
> -- Albert Einstein


The increasing use of mathematics in biology is inevitable as biology becomes more quantitative. The complexity of the biological sciences makes interdisciplinary involvement essential. For the biologist, mathematical modeling offers another research tool commensurate with a new powerful laboratory technique but _only_ if used appropriately and its limitations recognized.{cite}`Murray2002`. In particular, we can use mathematical models to study complex interactions in nature through a simplified and structured lens. Further, models also generate testable predictions. By trying to verify or refute these predictions, we will make much faster progress in understanding nature. The models highlight the distinction between the _patterns_ we see in nature and the different _mechanisms_ that might cause those patterns {cite}`Gotelli1998`. 

A model can be regarded as a caricature of a real system {cite}`Segel2013` by capturing the key elements, while the detail is neglected. Concentration on the essential is a central feature of a good model {cite}`Segel2013`. Models that describe changing systems do so by formulating a set of differential equations. Analysis of various sorts can then determine what the model predicts (in terms of a solution to the set of equations). 


**Definition:** A mathematical model is a representation of the essential aspects of a new or existing system, which presents knowledge of that system in usable form. Models are not replicas of reality, they are simplified representations of it.

Mathematical modeling is typically the result of a trade-off between accuracy and simplicity since large, complex models may be more accurate in theory, but in practice they are hard to simulate and require many parameters that may not be available or identifiable.

### Types of Models


```{image} images/types_of_models
:alt: Types of models.
:width: 500px
:align: center
```


### Model Components

- **Variables**
  - independent
  - dependent
- **Parameters**
  - not dependent on independent variables
  - can be varied/changed under experimental conditions
- **Constants**
  - fixed, e.g., Avogadro constant, gravitational constant
- **Types of Equations**
  - algebraic equation or polynomial equation is an equation in which both sides are polynomials. These are further classified by degree: linear, quadratic, cubic, etc. 
  - A parametric equation is an equation for which the solutions are sought as functions of some other variables
  - A differential equation is a functional equation involving derivatives of the unknown functions.  ODE, PDE.
  - A stochastic equations includes a random term or variable, they can be algebraic or differential (SDEs).

### How to Construct a Model

```{image} images/create_math_model.png
:alt: Types of models.
:width: 500px
:align: center
```
1. Formulation of a mathematical model

The first step is to ask what are the essential ingredients in the simplest possible embodiment of the phenomenon under investigation? Having listed the major actors in the drama, the "unknowns" or **dependent variables**, one must next indicate how these actors are related to one another. The modeling process requires a choice of **independent variables**. In this course, the main independent variable is considered to be **_time_**. The next step is the choice of formalism. Should the phenomenon be regarded as probabilistic or deterministic? If the latter, should one use differential equations, because quantities change continuously in time? Or are difference equations appropriate? These are natural when there are discrete changes.
	
The hardest step is to provide a formal set of equations. The single most important aid to this endeavor is what can be called **bookkeeping**. This is the process of keeping track of some quantity that remains invariant
2. Solving the model equations
3. Drawing qualitative conclusions

Manipulation of model equations yields two types of results, quantitative and qualitative. The value of quantitative results is clear, but qualitative conclusions might be even more useful. One 
4. Choosing parameters

It may be possible to draw qualitative conclusions from a model without using any a priori information concerning the magnitudes of the parameters involved. When models begin to be moderately complex, however, it is helpful to know rough orders f magnitude estimates for the various parameters. Such estimates can often be obtained from literature or from general intuition. 
5. Robustness
6. Analysis of results



### Dangers/Successes & failures of mathematical modeling

The modeling process is considered successful when the obtained model possesses the following characteristics:
- **Accurate:** the model should attempt to accurately describe current existing observations.
- **Predictive:** the model should allow to appropriately predict the behavior of the system in situations not already observed.
- **Reusable:** the model can be reused in another, similar case.
- **Parsimonious:** the model should be as simple as possible. That is, given competing and equally good models, the simplest is preferred.

In what sense is mathematics successful in aiding in biological understanding? As far as the biologist is concerned, 

It could be argued that every model is a lie, because detail is neglected or major features distorted to bring out the most essential aspects. However just because a model is wrong, is not sufficient reason to reject it, and just because a model is more or less right, is not sufficient reason to accept it. A "wrong" model may be so laden with detail that the principal features are completely obscured. As Picasso said of good art, a good model is "a lie that helps us see the truth"

However, the use of esoteric mathematics arrogantly applied to biological problems by mathematicians who know little about the real biology, together with unsubstantiated claims as to how important such theories are, do little to promote the interdisciplinary involvement which is so essential. {cite}`Murray2002`
There are two dangers inherent in the use of mathematical models in ecology. The first danger is that we build models that are too complex. When this happens, the models may contain many variable that we can never measure in nature, and the mathematical solutions may be too complex.  Consequently, the most useful ecological models are often the simplest ones. The second danger is that we forget that the models are abstract representations of nature. However logical a model might appear, nothing says that nature must follow its rules. By carefully focusing on the assumptions of the model, we may be able to pinpoint the places where it departs from reality {cite}`Gotelli1998`.