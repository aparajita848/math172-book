# Probability
## What are the chances?!

---

## Introduction

### Defining Basic Terms in Probability

- **Probability experiments**: Chance process that leads to well-defined results called outcomes. For example, flipping a coin or rolling a die are called probability experiments.

- **Outcome**: Result of a single trial of a probability experiment.

- **Sample space**: The sample space of an experiment is a list of *all* possible outcomes. With a die for example, we have the sample space:
  $$S = \{1, 2, 3, 4, 5, 6\}$$

- **Elementary events**: The outcomes in the sample space. For example, 'rolling a 6' or 'first die rolling a 2, second rolling a 5' are elementary events. More complex events would be 'the sum of two die rolls is 8'. Such events occur if a number of different elementary events occur.

---

## Exercise: Listing Sample Spaces

List the sample space of the following probability experiments.

### 1. Tossing one coin

$$S = \{T, H\}$$

where $T$ represents tails and $H$ represents heads.

### 2. Answering a True/False question

$$S = \{T, F\}$$

where $T$ represents True and $F$ represents False.

### 3. Tossing two coins

$$S = \begin{Bmatrix}
(T,T) & (T,H) \\
(H,T) & (H,H)
\end{Bmatrix}$$

### 4. Rolling 2 dice

$$S = \begin{Bmatrix}
(1,1) & (1,2) & (1,3) & (1,4) & (1,5) & (1,6) \\
(2,1) & (2,2) & (2,3) & (2,4) & (2,5) & (2,6) \\
(3,1) & (3,2) & (3,3) & (3,4) & (3,5) & (3,6) \\
(4,1) & (4,2) & (4,3) & (4,4) & (4,5) & (4,6) \\
(5,1) & (5,2) & (5,3) & (5,4) & (5,5) & (5,6) \\
(6,1) & (6,2) & (6,3) & (6,4) & (6,5) & (6,6)
\end{Bmatrix}$$

> **Key Insight:** We can depict the sample space as a **list/matrix** of all possible outcomes.

---

## Using a Table to List Sample Space

Sometimes, when the number of possible outcomes in the sample space is long, we can use a table to organize the sample space.

### Exercise: Sum of Rolling Two Dice

List the sample space of the **sum of rolling two dice** using the table below:

|       |   | **Die 2** |   |   |   |   |   |
|-------|---|-----------|---|---|---|---|---|
|       |   | **1** | **2** | **3** | **4** | **5** | **6** |
| **Die 1** | **1** | 2 | 3 | 4 | 5 | 6 | 7 |
|       | **2** | 3 | 4 | 5 | 6 | 7 | 8 |
|       | **3** | 4 | 5 | 6 | 7 | 8 | 9 |
|       | **4** | 5 | 6 | 7 | 8 | 9 | 10 |
|       | **5** | 6 | 7 | 8 | 9 | 10 | 11 |
|       | **6** | 7 | 8 | 9 | 10 | 11 | 12 |

**Questions:**

1. **What are the total number of possible outcomes?** 
   - Answer: **36**

2. **How many outcomes give a sum of 7 or less?** 
   - Answer: **21** (counting the upper triangle with the diagonal as 7)

3. **How many outcomes give a sum of 5 or more?** 
   - Answer: **30**

---

## Using a Tree Diagram to List Sample Space

### Exercise: Sex of Three Children

List the sample space for the sex of three children of a family using a tree diagram.

```
                Child 1      Child 2      Child 3     Outcomes
                   |            |            |
Parents ---------> F ---------> F ---------> F -----> FFF
                   |            |            |
                   |            |----------> M -----> FFM
                   |            |
                   |----------> M ---------> F -----> FMF
                   |            |
                   |            |----------> M -----> FMM
                   |
                   |
                   |----------> M ---------> F -----> MFF
                   |            |
                   |            |----------> M -----> MFM
                   |            |
                   |----------> M ---------> F -----> MMF
                                |
                                |----------> M -----> MMM
```

**Sample space:** $S = \{MMM, MMF, MFM, MFF, FMM, FMF, FFM, FFF\}$

**Questions:**

1. **What are the total number of outcomes?** 
   - Answer: **8**

2. **How many outcomes have exactly 2 female children?** 
   - Answer: **3** (MFF, FMF, FFM), so probability is $\frac{3}{8}$

---

## Calculating Probability

**Example:** The probability of rolling a 6 on a single roll of a die is $\frac{1}{6}$

**Example:** The probability of rolling a 2 on the first roll and a 5 on the second is $\frac{1}{6} \cdot \frac{1}{6} = \frac{1}{36}$

### Formula for Equally Likely Events

If all elementary events have the same probability, then the probability that an event $E$ occurs is given by:

$$\boxed{P(E) = \frac{\text{total number of elements in } E}{\text{total number of elements in } S}}$$

---

## Example: Sum of Dice

**Example:** Find the probability of getting a sum of 5 or less when rolling two dice.

$$E = \{(1,1), (1,2), (1,3), (1,4), (2,1), (2,2), (2,3), (3,1), (3,2), (4,1)\}$$

$$P(\text{sum is } \leq 5) = \frac{\text{total number of elements in } E}{\text{total number of elements in } S} = \frac{10}{36}$$

---

## Exercise: Dice Probabilities

Find the probabilities of the following events referring to the table of recorded outcomes of the sum of rolling two dice.

### 1. Probability of sum = 10

$$E = \{(4,6), (5,5), (6,4)\}$$

$$P(\text{sum is } 10) = \frac{3}{36} = \frac{1}{12}$$

### 2. Probability of sum ≥ 8

$$E = \{(2,6), (3,5), (3,6), (4,4), (4,5), (4,6), (5,3), (5,4), (5,5), (5,6), (6,2), (6,3), (6,4), (6,5), (6,6)\}$$

$$P(\text{sum is } \geq 8) = \frac{15}{36}$$

### 3. Probability of first roll = 3 AND second roll = even

$$E = \{(3,2), (3,4), (3,6)\}$$

$$P(3, \text{even number}) = \frac{3}{36} = \frac{1}{12}$$

**Alternative method:** Multiply individual probabilities: 
$$P(3, \text{even number}) = \frac{1}{6} \cdot \frac{3}{6} = \frac{1}{12}$$

### 4. Probability of first roll = 3 AND second roll = odd

$$E = \{(3,1), (3,3), (3,5)\}$$

$$P(3, \text{odd number}) = \frac{3}{36} = \frac{1}{12}$$

**Alternative method:** 
$$P(3, \text{odd number}) = \frac{1}{6} \cdot \frac{3}{6} = \frac{1}{12}$$

---

## Exercise: Three Children Probabilities

Find the probabilities of the following events referring to the tree diagram for the sex of 3 children in a family.

### 1. All 3 children are of the same sex

There are two cases: all male or all female.

$$E = \{MMM, FFF\}$$

$$P(\text{all children of same sex}) = \frac{2}{8} = \frac{1}{4} = 25\%$$

### 2. Exactly two male children

$$E = \{MMF, MFM, FMM\}$$

$$P(\text{2 male children}) = \frac{3}{8}$$

### 3. At least one child is female

$$E = \{MMF, MFM, MFF, FMM, FMF, FFM, FFF\}$$

$$P(\text{at least 1 female child}) = \frac{7}{8}$$

### 4. The youngest child (child 3) is female

$$E = \{MMF, MFF, FMF, FFF\}$$

$$P(\text{youngest child is female}) = \frac{4}{8} = \frac{1}{2} = 50\%$$

### 5. Youngest is female, GIVEN at least one is female

Here, the total sample cases decrease to seven as we only consider outcomes with at least one female child.

$$S = \{MMF, MFM, MFF, FMM, FMF, FFM, FFF\}$$
$$E = \{MMF, MFF, FMF, FFF\}$$

$$P(\text{youngest is female} \mid \text{at least one female}) = \frac{4}{7}$$

---

## Well That Escalated Quickly

Recall that if all elementary events have the same probability, then the **probability that an event $E$ occurs** is given by:

$$\boxed{P(E) = \frac{\text{total number of elements in } E}{\text{total number of elements in } S}}$$

In general, we wouldn't want to write out the sample space for all experiments. So far the number of elementary events has been small (although 36 could be considered tedious). If we were to write out the sample space for three rolls of a die, we would have 216 elementary events. Four would be 1296! Clearly any way around having to write all of these events would be welcomed.

### Multiplication Principle

**Principle 1:** Suppose an experiment consists of two actions. Action 1 has $m$ possible outcomes and action 2 has $n$ possible outcomes. Then the total number of possible outcomes is $m \cdot n$.

**Principle 2:** Suppose an experiment consists of $m$ actions. Each action has $n_i$ possible outcomes. Then the total number of outcomes for the experiment is $n_1 \cdot n_2 \cdots n_m$.

---

## Example: Two-Action Experiment

Suppose an experiment has two actions. The first action has outcomes $\{A, B, C, D\}$ and the second has outcomes $\{1, 2, 3\}$.

The sample space would look like:

$$S = \begin{Bmatrix}
(A,1) & (A,2) & (A,3) \\
(B,1) & (B,2) & (B,3) \\
(C,1) & (C,2) & (C,3) \\
(D,1) & (D,2) & (D,3)
\end{Bmatrix}$$

- The probability of $A$ occurring is $P(A) = \frac{3}{12} = \frac{1}{4}$
- The probability of $2$ occurring is $P(2) = \frac{4}{12} = \frac{1}{3}$
- The probability of $(A,2)$ occurring is:
  $$P((A,2)) = \frac{1}{12} = \frac{1}{4} \times \frac{1}{3} = \frac{1}{12}$$

---

## Example: Four Children

Suppose a family has four children. Find the probability that there are exactly two males and two females.

There are 2 possible outcomes for each child, so there are a total of $2^4 = 16$ outcomes. Of those, 6 of them have 2 males and 2 females:

$$\{(M,M,F,F), (M,F,M,F), (M,F,F,M), (F,M,F,M), (F,M,M,F), (F,F,M,M)\}$$

So the probability of exactly two males and two females is $\frac{6}{16} = \boxed{\frac{3}{8}}$.

---

## The Feeling's Mutual: Union and Intersection

Suppose we have two events, $E$ and $F$, whose probabilities we know. We are interested in the probability that $E$ **or** $F$ occurs in a single instance. This new event, which is denoted by $E \cup F$, is the set of outcomes that appear in either $E$ or $F$, or both. We call this set the **union** of $E$ and $F$.

### Example: Single Die Roll

Consider the roll of a single die; suppose that $E$ is the event that a six is rolled and $F$ is the event that a number smaller than 4 is rolled. Then,

$$E = \{6\}, \quad F = \{1,2,3\}, \quad E \cup F = \{1,2,3,6\}$$

So the probability of $E$ or $F$ occurring is $\frac{4}{6} = \frac{2}{3}$.

Notice that in this case, $P(E) = \frac{1}{6}$ and $P(F) = \frac{3}{6}$ and so $P(E \cup F) = P(E) + P(F)$. This is not always the case however.

### When Events Overlap

Let $E$, as before, be the event that a six is rolled. This time let $G$ be the event that a number 4 or greater is rolled, then

$$E = \{6\}, \quad G = \{4,5,6\}, \quad E \cup G = \{4,5,6\}$$

This time $P(E \cup G) \neq P(E) + P(G)$. The difference is that events $E$ and $G$ shared an outcome. If we had tried to add the probabilities for our answer this time, then we would have counted the event 'rolls a six' twice.

### General Formula for Union

In general, the formula for the probability of $E$ *or* $F$ occurring is given by:

$$\boxed{P(E \cup F) = P(E) + P(F) - P(E \cap F)}$$

where $P(E \cap F)$ is the probability that $E$ **and** $F$ occur. The set $E \cap F$ is called the **intersection** of $E$ and $F$.

---

## Independent and Mutually Exclusive Events

To find the probability that the event $P(E \cap F)$ occurs, we need to determine whether the events $E$ and $F$ are *independent* and/or *mutually exclusive*.

### Independent Events

Two events, $E$ and $F$, are **independent** if knowledge of one event doesn't change the probability of the other. If $E$ and $F$ are independent events, then:

$$P(E \cap F) = P(E) \cdot P(F)$$

*Events that are not independent are called **dependent**.*

### Mutually Exclusive Events

Two events are **mutually exclusive** if it is impossible for them to occur simultaneously.

$$P(E \cap F) = 0$$

---

## Example: Sum of Two Dice

Consider the **sum of rolling two dice** and the following three events:

- $E =$ 'the sum is 7 or less'
- $F =$ 'the sum is 5 or more'
- $G =$ 'the sum is exactly 10'

**Probabilities:**
$$P(E) = \frac{21}{36}, \quad P(F) = \frac{30}{36}, \quad P(G) = \frac{3}{36}$$
$$P(E \cap F) = \frac{15}{36}, \quad P(F \cap G) = \frac{3}{36}, \quad P(E \cap G) = 0$$

### Find: Events $E$ or $F$ occur

$E$ and $F$ are *not* mutually exclusive or independent.

$$P(E \cup F) = P(E) + P(F) - P(E \cap F) = \frac{21}{36} + \frac{30}{36} - \frac{15}{36} = \frac{36}{36} = 1$$

*If you see the possible outcomes, $\geq 5$ or $\leq 7$ encompass all the outcomes.*

### Find: Events $E$ or $G$ occur

$E$ and $G$ are mutually exclusive (but not independent).

$$P(E \cup G) = P(E) + P(G) - P(E \cap G) = \frac{21}{36} + \frac{3}{36} - 0 = \frac{24}{36} = \frac{2}{3}$$

### Find: Events $F$ or $G$ occur

$F$ and $G$ are *not* mutually exclusive (but are dependent).

$$P(F \cup G) = P(F) + P(G) - P(F \cap G) = \frac{30}{36} + \frac{3}{36} - \frac{3}{36} = \frac{30}{36}$$

---

## Terms and Conditions Apply: Conditional Probability

**Conditional probability** is a measure of the probability of an event, given that another event has occurred. If $E$ and $F$ are two events, then the conditional probability of $F$ given $E$ has occurred is defined by:

$$\boxed{P(F \mid E) = \frac{P(E \cap F)}{P(E)}}$$

---

## Example: Medical Test Sensitivity and Specificity

Medical tests for diseases are sometimes characterized by their **sensitivity** and **specificity**:
- **Sensitivity** = probability that a diseased person will show a positive test result (correct positive)
- **Specificity** = probability that a healthy person will show a negative result (correct negative)

Both sensitivity and specificity are conditional probabilities:

$$\text{Sensitivity} = P(\text{positive} \mid \text{diseased})$$
$$\text{Specificity} = P(\text{negative} \mid \text{healthy})$$

### X-ray Diagnosis of Tuberculosis

A study investigated the use of X-ray readings to diagnose tuberculosis. Diagnosis of 1,820 individuals produced the data in the table below. Compute both the sensitivity and specificity for this method of diagnosis.

|                | Persons without TB | Persons with TB |
|----------------|-------------------|-----------------|
| **Negative X-ray** | 1,739 | 8 |
| **Positive X-ray** | 51 | 22 |

**Sensitivity:** $F = \{\text{Positive X-ray}\}$ and $E = \{\text{Persons with TB}\}$

$$P(\text{Positive} \mid \text{TB}) = \frac{P(\text{Positive} \cap \text{TB})}{P(\text{TB})} = \frac{22}{8+22} = \frac{22}{30} = 0.733$$

**Specificity:** $F = \{\text{Negative X-ray}\}$ and $E = \{\text{Persons without TB}\}$

$$P(\text{Negative} \mid \text{No TB}) = \frac{P(\text{Negative} \cap \text{No TB})}{P(\text{No TB})} = \frac{1,739}{1,739+51} = \frac{1,739}{1,790} = 0.972$$

---

## Example: Flipping a Coin Twice

Flipping a coin two times will have 4 outcomes, assuming that it is equally likely to get Heads or Tails.

**(a) The possible outcomes are:**

$$S = \{(T,T), (T,H), (H,T), (H,H)\}$$

**(b) The probability of each outcome is:** $\frac{1}{4}$

**(c) The probability that at least one coin-flip gives Heads is:** $\frac{3}{4}$

**(d) The probability that the second coin-flip is Heads is:** $\frac{1}{2}$

**(e) The conditional probability that the second coin-flip is Heads, given that at least one coin-flip is Heads is:** $\frac{2}{3}$

**(f) The conditional probability that at least one coin-flip is Heads, given that the second coin-flip is Heads is:** $1$

---

## Summary of Key Concepts

1. **Basic Probability Formula:**
   $$P(E) = \frac{\text{number of favorable outcomes}}{\text{total number of outcomes}}$$

2. **Multiplication Principle:** For $k$ independent actions with $n_1, n_2, \ldots, n_k$ outcomes each, total outcomes = $n_1 \times n_2 \times \cdots \times n_k$

3. **Union (OR):**
   $$P(E \cup F) = P(E) + P(F) - P(E \cap F)$$

4. **Intersection (AND):**
   - If independent: $P(E \cap F) = P(E) \cdot P(F)$
   - If mutually exclusive: $P(E \cap F) = 0$

5. **Conditional Probability:**
   $$P(F \mid E) = \frac{P(E \cap F)}{P(E)}$$