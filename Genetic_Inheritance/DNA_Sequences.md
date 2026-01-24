# DNA Sequences
## Introduction

Genetic information is encoded by DNA molecules, which are passed from parent to offspring. For this transfer, the DNA must be copied. During the copying process, sections of the molecule may be altered in various ways. Before getting into this, let's briefly look at the basic structure of DNA.

The DNA molecule forms a double helix, a ladder-like structure. At each of the points where the ladder's upright poles are joined by a rung, one of four possible molecular subunits appears. These subunits, called **nucleotides** - adenine, guanine, cytosine and thymine - are denoted by the letters $A$, $G$, $C$ and $T$. Because of chemical similarity, adenine and guanine are called **purines**, while cytosine and thymine are called **pyrimidines**.

Each base has a complementary base with which it can form the rung of the ladder through a hydrogen bond. We always find either $A$ paired with $T$ or $G$ paired with $C$. Thus, knowing one side of the ladder structure is enough to deduce the other. For example, if along one pole of the ladder we have a sequence of bases

$$
\begin{equation*}
\begin{aligned}
AGCGCGTATTAG
\end{aligned}
\end{equation*}
$$

then the other would have the complementary sequence

$$
\begin{equation*}
\begin{aligned}
TCGCGCATAATC.
\end{aligned}
\end{equation*}
$$

Finally, the DNA molecule has a directional sense so that we can make a distinction between a sequence like $ATCGAT$ and the inverted sequence $TAGCTA$. The upshot of all this structure is that we will be able to think of $DNA$ sequences mathematically simply as sequences composed of the four letters $A$, $T$, $C$ and $G$.

## Example

Suppose a $40$-base ancestral DNA sequence ($S_0$) is given by the top row in the table below and its descendent aligned sequence ($S_1$) is given by the bottom row. Markers have been placed after every string of length $5$ to help reading easier, this is by no means a standard way of studying DNA sequences.

-----------------------------------------------
-----------------------------------------------
ACTTG|TCGGA|TGATC|AGCGG|TCCAT|GCACC|TGACA|ACGGT
ACATG|TTGCT|TGACG|ACAGG|TCCAT|GCGCC|TGAGA|ACGGC 
-----------------------------------------------
-----------------------------------------------

Thinking of each site as a trial of the same probabilistic process, we can estimate $16$ conditional probabilities describing the likelihood of observing different types of base substitutions when comparing the sequences of ancestor and descendent:

$$
\begin{equation*}
\begin{aligned}
P\left(S_1=i\mid S_0=j\right),
\end{aligned}
\end{equation*}
$$

where $i,j=A,G,C,T$.
One way to do this is to arrange the data into a table:

 |A|G|C|T
---|---|---|---|---
A|7|0|1|1
G|1|9|2|0
C|0|2|7|2
T|1|0|1|6
----------
 |9|11|11|9

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
