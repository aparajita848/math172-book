# Probability

## Introduction

Defining some basic terms in Probability:
- **Probability experiments** - chance process that leads to well-defined results called
    outcomes. For example, flipping a coin or rolling a die are called probability experiments. 
- **Outcome** -  result of a single trial of a probability experiment. 
- **Sample space** - The **sample space** of an experiment is a list of **all** possible outcomes. With a die for example, we have the sample space

$$
\begin{equation*}
S=\{1,2,3,4,5,6\}.
\end{equation*}
$$

- **Elementary events** - the outcomes in the sample space. For example, 'rolling a $6$' or `first die rolling a $2$, second rolling a $5$' are elementary events. More complex events would be, `the sum of two die rolls is a $8$'. Such events occur if a number of different elementary events occur.

## Exercise 
List the sample space of the following probability experiments.

1. Tossing one coin.

:::{tip} Solution
:icon: false
:class: dropdown

$$ S = \{T,H\} $$ where $T$ represents tails and $H$ represents heads.
:::

2. Answering a True/False question.

:::{tip} Solution
:icon: false
:class: dropdown

$$ S = \{T,F\} $$ where $T$ represents True and $F$ represents False.
:::

3. Tossing two coins.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
        S =\begin{Bmatrix}
            (T,T) & (T,H) \\
            (H,T) & (H,H)
        \end{Bmatrix} 
    \end{aligned}
\end{equation*}
$$

:::

4. Rolling 2 dice.

:::{tip} Solution
:icon: false
:class: dropdown

$$ 
\begin{equation*}
\begin{aligned}
    S=\begin{Bmatrix}
    (1,1)	&	(1,2)	&	(1,3)	&	(1,4)	&	(1,5)	&	(1,6)	\\
    (2,1)	&	(2,2)	&	(2,3)	&	(2,4)	&	(2,5)	&	(2,6)	\\
    (3,1)	&	(3,2)	&	(3,3)	&	(3,4)	&	(3,5)	&	(3,6)	\\
    (4,1)	&	(4,2)	&	(4,3)	&	(4,4)	&	(4,5)	&	(4,6)	\\
    (5,1)	&	(5,2)	&	(5,3)	&	(5,4)	&	(5,5)	&	(5,6)	\\
    (6,1)	&	(6,2)	&	(6,3)	&	(6,4)	&	(6,5)	&	(6,6)	
    \end{Bmatrix},
    \end{aligned}
\end{equation*}
$$

_We can depict the sample space as a **list/matrix** of all possible outcomes._

:::

## _Using a Table to list Sample Space_

Sometimes, when the number of possible outcomes in the sample space is long, we can use a table to organize the sample space.

### Exercise 

List the sample space of the **sum of rolling two dice** by completing the table below:

%insert table

1. What are the total number of possible outcomes?

:::{tip} Solution
:icon: false
:class: dropdown

36

:::

2. How many outcomes give a sum of 7 or less?

:::{tip} Solution
:icon: false
:class: dropdown

21

counting the upper triangle with the diagonal as 7.

:::

3. How many outcomes give a sum of 5 or more?

:::{tip} Solution
:icon: false
:class: dropdown

30

:::

## _Using a Tree Diagram to list the Sample Space_

### Exercise

List the sample space for the sex of three children of a family by filling in the boxes in tree diagram.

% insert tree

1. What are the total number of possible outcomes?

:::{tip} Solution
:icon: false
:class: dropdown

8

:::

2. How many outcomes have exactly 2 female children?

:::{tip} Solution
:icon: false
:class: dropdown

$\dfrac{3}{8}$

:::

## Calculating Probability

**Example:** The probability of rolling a $6$ on a single roll of a die is $\dfrac{1}{6}$.

**Example:** The probability of rolling a $2$ on the first roll and a $5$ on the second is $\dfrac{1}{6}\cdot\dfrac{1}{6}=\dfrac{1}{36}$.

If all elementary events have the same probability, then the probability that an event $E$ occurs is given by:

$$
\begin{equation*}
\begin{aligned}
\boxed{P(E)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}}
\end{aligned}
\end{equation*}
$$

### Example 

Find the probability of getting a sum of 5 or less when rolling two dice. (Use the dice
table from the previous page).

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
E=\left\{(1,1),(1,2),(1,3),(1,4),(2,1),(2,2),(2,3),(3,1),(3,2),(4,1)\right\}
\end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
P\left(\text{sum is }\leq 5\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{10}{36}
\end{aligned}
\end{equation*}
$$

:::

### Exercise 

Find the probabilities of the following events referring to the table of recorded outcomes of the sum of rolling two dice.

1. What is the probability of getting a sum of exactly 10 when rolling two dice? 

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    E=\left\{(4,6),(5,5),(6,4)\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
    \begin{aligned}
    P\left(\text{sum is }10\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{3}{36} = \dfrac{1}{12}
    \end{aligned}
\end{equation*}
$$


:::

2. Find the probability of getting a sum of 8 or more when rolling two dice.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
    \begin{aligned}
    E=\left\{(1,1),(1,2),(1,3),(1,4),(2,1),(2,2),(2,3),(3,1),(3,2),(4,1)\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
    \begin{aligned}
    P\left(\text{sum is }\geq 8\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{10}{36}
    \end{aligned}
\end{equation*}
$$

:::

3. What is the probability of getting a 3 on the first roll and an even number on the second roll?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    E=\left\{(3,2),(3,4),(3,6)\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
    \begin{aligned}
    P\left(3,\text{even number}\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{3}{36} = \dfrac{1}{12}
    \end{aligned}
\end{equation*}
$$

 Alternatively, you can also multiply the individual probabilities: $P\left(3,\text{even number}\right)=\dfrac{1}{6}\cdot\dfrac{3}{6} =\dfrac{1}{12}$.

:::

4. What is the probability of getting a 3 on the first roll and an odd number on the second roll?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    E=\left\{(3,1),(3,3),(3,5)\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
    \begin{aligned}
    P\left(3,\text{odd number}\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{3}{36} = \dfrac{1}{12}
    \end{aligned}
\end[equation*}
$$

Alternatively, you can also multiply the individual probabilities: $P\left(3,\text{odd number}\right)=\dfrac{1}{6}\cdot\dfrac{3}{6} =\dfrac{1}{12}$.

:::

### Exercise

Find the probabilities of the following events referring to the tree diagram of recorded outcomes for the sex of 3 children in a family.

1. Find the probability that all 3 children are of the same sex? 

:::{tip} Solution
:icon: false
:class: dropdown

There are two cases, all male or all female, so;

$$
\begin{equation*}
\begin{aligned}
    E=\left\{MMM,FFF\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
    P\left(\text{all children of same sex}\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{2}{8} = \dfrac{1}{4} \text{ or } 25\%
    \end{aligned}
\end{equation*}
$$


:::

2. Find the probability of exactly two male children in a 3 children family?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    E=\left\{MMF,MFM,FMM\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
    P\left(\text{2 male children}\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{3}{8} 
    \end{aligned}
\end{equation*}
$$

:::

3. What is the probability that at least one child is female?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    E=\left\{MMF,MFM,MFF,FMM,FMF,FFM,FFF\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
    P\left(\text{at least 1 female child}\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{7}{8} 
    \end{aligned}
\end{equation*}
$$

:::

4. What is the probability that the youngest child (child 3) is female?

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    E=\left\{MMF,MFF,FMF,FFF\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
    P\left(\text{youngest child is female}\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{4}{8} = \dfrac{1}{2} \text{ or } 50\% 
    \end{aligned}
\end[equation*}
$$

:::

5. What is the probability that the youngest child is a female, given that at least one child is female?

:::{tip} Solution
:icon: false
:class: dropdown

Here, the total sample cases would decrease to seven as we only consider the outcomes with at least one female child.

$$
\begin{equation*}
\begin{aligned}
    S=&\left\{MMF,MFM,MFF,FMM,FMF,FFM,FFF\right\}\\
    E=&\left\{MMF,MFF,FMF,FFF\right\}
    \end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
   P\left(\text{youngest child is a female, if at least one child is female}\right)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}=\frac{4}{7} 
    \end{aligned}
\end[equation*}
$$

:::

### Well that escalated quickly

Recall that if all elementary events have the same probability, then the **probability that an event $E$ occurs** is given by:

$$
\begin{equation*}
\begin{aligned}
\boxed{P(E)=\frac{\text{total number of elements in }E}{\text{total number of elements in }S}}
\end{aligned}
\end{equation*}
$$

In general, we wouldn't want to write out the sample space for all experiments. So far the number of elementary events has been small (although $36$ could be considered tedious). If we were to write out the sample space for three rolls of a die, we would have $216$ elementary events. Four would be $1296$! Clearly any way around having to write all of these events would be welcomed. First we start with the following observations:

Suppose an experiment consists of two actions. Action $1$ has $m$ possible outcomes and action $2$ has $n$ possible outcomes. Then the total number of possible outcomes is $m\cdot n$.

Suppose an experiment consists of $m$ actions. Each actions has $n_i$ possible outcomes. Then the total number of outcomes for the experiment is $n_1\cdot n_2\cdots n_m$.

### Example

Suppose an experiment has two actions. The first action has outcomes $\{A,B,C,D\}$ and the second has outcomes $\{1,2,3\}$.

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    S=\begin{Bmatrix}
    (A,1)	&	(A,2)	&	(A,3) \\	
    (B,1)	&	(B,2)	&	(B,3) \\
    (C,1)	&	(C,2)	&	(C,3) \\
    (D,1)	&	(D,2)	&	(D,3) 	
    \end{Bmatrix},
    \end{aligned}
\end{equation*}
$$

:::

- The probability of $A$ occurring is:

:::{tip} Solution
:icon: false
:class: dropdown

$P(A)=\dfrac{3}{12}=\dfrac{1}{4}$

:::

- The probability of $2$ occurring is:

:::{tip} Solution
:icon: false
:class: dropdown

$P(2)=\dfrac{4}{12}= \dfrac{1}{3}$

:::

- The probability of $(A,2)$ occurring is:

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
    P((A,2))=&\dfrac{1}{12}\; \text{from the sample space}\\
=&\dfrac{1}{4}\times\dfrac{1}{3}=\dfrac{1}{12}.
\end{aligned}
\end{equation*}
$$

:::

### Example 

Suppose a family has four children. Find the probability that there are exactly two males and two females.

:::{tip} Solution
:icon: false
:class: dropdown

here are $2$ possible outcomes for each child, so there are a total of $2^4=16$ outcomes. Of those, $6$ of them have $2$ males and $2$ females:

$$
\begin{equation*}
\begin{aligned}
\left\{(M,M,F,F),(M,F,M,F),(M,F,F,M),(F,M,F,M),(F,M,M,F),(F,F,M,M)\right\}
\end{aligned}
\end{equation*}
$$

so the probability of exactly two males and two females is $\dfrac{6}{16}=\boxed{\dfrac{3}{8}}$.

:::

## The feeling's mutual

Suppose we have two events, $E$ and $F$, whose probabilities we know. We are interested in the probability that $E$ **or** $F$ occurs in a single instance. Thus new event, which is denoted by $E\cup F$, is the set of outcomes that appear in either $E$ or $F$, or both. We call this set the **union** of $E$ and $F$.

Consider the roll of a single die; suppose that $E$ is the event that a six is rolled and $F$ is the event that a number smaller than 4 is rolled. _(You can imagine such a situation when playing a game of Monopoly for example.)_ Then,

$$
\begin{equation*}
\begin{aligned}
E=\{6\},\hspace*{1cm}F=\{1,2,3\},\hspace*{1cm}E\cup F=\{1,2,3,6\}.
\end{aligned}
\end{equation*}
$$

So the probability of $E$ or $F$ occurring is $\dfrac{4}{6}=\dfrac{2}{3}$. Notice that in this case, $P(E)=\dfrac{1}{6}$ and $P(F)=\dfrac{3}{6}$ and so $P(E\cup F)=P(E)+P(F)$. This is not always the case however.

Let $E$, as before, be the event that a six is rolled. This time let $G$ be the event that a number 4 or greater is rolled, then

$$
\begin{equation*}
\begin{aligned}
E=\{6\},\hspace*{1cm}G=\{4,5,6\},\hspace*{1cm}E\cup G=\{4,5,6\}.
\end{aligned}
\end{equation*}
$$

This time $P(E\cup G)\neq P(E)+P(G)$. The difference this time is that the events $E$ and $G$ shared an outcome. If we had tried to add the probabilities for our answer this time, then we would have counted the event `rolls a six' twice. In general, the formula for the probability of $E$ **or** $F$ occurring is given by

$$
\begin{equation*}
\begin{aligned}
\boxed{P\left(E\cup F\right)=P\left(E\right)+P\left(F\right)-P\left(E\cap F\right)}
\end{aligned}
\end{equation*}
$$

where $P\left(E\cap F\right)$ is the probability that $E$ **and** $F$ occur. The set $E\cap F$ is called the **intersection** of $E$ and $F$.

To find the probability that the event $P(E\cap F)$ occurs, we need to determine whether the events $E$ and $F$ are **independent** and/or **mutually exclusive**.

- Two events, $E$ and $F$, are **independent** if knowledge of one event doesn't change the probability of the other. If $E$ and $F$ are independent events, then

$$
\begin{equation*}
\begin{aligned}
P(E\cap F)=P(E)\cdot P(F).
\end{aligned}
\end{equation*}
$$

_Events that are not independent are called **dependent**._

:::{note}
Imagine rolling a die and flipping a coin. Then the event that `the roll is even' and `the flip is heads' are independent events - the outcome of the die roll does not affect the outcome of the coin flip.
:::

- Two events are **mutually exclusive** if it is impossible for them to occur simultaneously.

$$
\begin{equation*}
\begin{aligned}
P(E\cap F)=0.
\end{aligned}
\end{equation*}
$$

### Example 

Consider the **sum of rolling two dice** and the following three events:

<center>

$E=$ 'the sum is 7 or less', $F=$ 'the sum is 5 or more', $G=$ 'the sum is exactly 10'.

</center>

Find the Probability of the following:

- The events $E$ or $F$ occur.

:::{tip} Solution
:icon: false
:class: dropdown

$E$ and $F$ are **not** mutually exclusive or independent.

$$
\begin{equation*}
P(E\cup F) = P(E)+P(F)-P(E\cap F)=\dfrac{21}{36}+\dfrac{30}{36}-\dfrac{15}{36}=\dfrac{36}{36} = 1
\end{equation*}
$$

_If you see the possible outcomes, $\geq 5\; or \leq 7$ encompass all the outcomes._

:::

- The events $E$ or $G$ occur.

:::{tip} Solution
:icon: false
:class: dropdown

$E$ and $G$ are mutually exclusive and independent.

$$
\begin{equation*}
P(E\cup G) = P(E)+P(G)-P(E\cap G)=\dfrac{21}{36}+\dfrac{3}{36}-0=\dfrac{24}{36} = \dfrac{2}{3}
\end{equation*}
$$

:::

- The events $F$ or $G$ occur.

:::{tip} Solution
:icon: false
:class: dropdown

$F$ and $G$ are **not** mutually exclusive or independent.

$$
\begin{equation*}
P(F\cup G) = P(F)+P(G)-P(F\cap G)=\dfrac{30}{36}+\dfrac{3}{36}-\dfrac{3}{36}=\dfrac{30}{36}
\end{equation*}
$$

:::

## Terms & Conditions Apply

**Conditional probability** is a measure of the probability of an event, given that another event has occurred. If $E$ and $F$ are two events, then the conditional probability of $F$ given $E$ has occurred is defined by:

$$
\begin{equation*}
\begin{aligned}
\boxed{P\left(F\mid E\right)=\frac{P\left(E\cap F\right)}{P\left(E\right)}}
\end{aligned}
\end{equation*}
$$

### Example

Medical tests for diseases are sometimes characterised by their **sensitivity** and **specificity**. The sensitivity of the test is the probability that a diseased person will show a positive test result (a correct positive). The specificity of a test is the probability that a healthy person will show a negative result (a correct negative). Both sensitivity and specificity are conditional probabilities.

$$
\begin{equation*}
\begin{aligned}
\text{Sensitivity}=&P\left(\text{positive}\mid\text{diseased}\right)\\
\text{Specificity}=&P\left(\text{negative}\mid\text{healthy}\right)
\end{aligned}
\end{equation*}
$$

A study investigated the use of X-ray readings to diagnose tuberculosis. Diagnosis of $1,820$ individuals produced the data in the table below. Compute both the sensitivity and specificity for this method of diagnosis.

```{table} Table showing the study results of x-ray readings for patients with tuberculosis and the control group.


| | Persons without TB | Persons with TB |
| --- | --- | --- |
| Negative X-ray | 1,739 | 8 |
| Positive X-ray | 51 | 22 |
```

:::{tip} Solution
:icon: false
:class: dropdown

Sensitivity: $F = \{\text{Positive X-ray}\}\quad\&\quad E = \{\text{Persons with TB}\}$.

$$
\begin{equation*}
\begin{aligned}
P\left(\text{Positive}\mid\text{TB}\right)=\frac{P\left(\text{Positive}\cap\text{TB}\right)}{P\left(\text{TB}\right)}=\frac{22}{8+22}=\frac{22}{30}=0.733
\end{aligned}
\end{equation*}
$$

Specificity: $F = \{\text{Negative X-ray}\}\quad\&\quad E = \{\text{Persons without TB}\}$.

$$
\begin{equation*}
\begin{aligned}
P\left(\text{Negative}\mid\text{No TB}\right)=\frac{P\left(\text{Negative}\cap\text{No TB}\right)}{P\left(\text{No TB}\right)}=\frac{1,739}{1,739+51}=\frac{1,739}{1,790}=0.972
\end{aligned}
\end{equation*}
$$

:::

### Example

Flipping a coin two times will have $4$ outcomes, assuming that it is equally likely to get Heads or Tails.

 (a) The possible outcomes are:

:::{tip} Solution
:icon: false
:class: dropdown

$$
\begin{equation*}
\begin{aligned}
S=\left\{\left(T,T\right),\left(T,H\right),\left(H,T\right),\left(H,H\right)\right\}
\end{aligned}
\end{equation*}
$$

:::

 (b) The probability of each outcome is:

:::{tip} Solution
:icon: false
:class: dropdown

$\dfrac{1}{4}$

:::

 (c) The probability that at least one coin-flip gives Heads is:

:::{tip} Solution
:icon: false
:class: dropdown

$\dfrac{3}{4}$

:::

 (d) The probability that the second coin-flip is Heads is:

:::{tip} Solution
:icon: false
:class: dropdown

$\dfrac{1}{2}$

:::

 (e) The conditional probability that the second coin-flip is Heads, given that at least one coin-flip is Heads is:

:::{tip} Solution
:icon: false
:class: dropdown

$\dfrac{2}{3}$

:::

 (f) The conditional probability that at least one coin-flip is Heads, given that the second coin-flip is Heads is:

:::{tip} Solution
:icon: false
:class: dropdown

$\dfrac{1}{1}$

:::

---

## Exercises

:::{tip} Exercise 1
:class: dropdown
:open: true


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
