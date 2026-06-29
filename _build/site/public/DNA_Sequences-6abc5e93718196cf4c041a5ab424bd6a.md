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

### Example

Suppose a $40$-base ancestral DNA sequence ($S_0$) is given by the top row in the table below and its descendent aligned sequence ($S_1$) is given by the bottom row. Markers have been placed after every string of length $5$ to help reading easier, this is by no means a standard way of studying DNA sequences.

$$
\begin{equation*}
 ACTTG | TCGGA | TGATC | AGCGG | TCCAT | GCACC | TGACA | ACGGT \\
 ACATG | TTGCT | TGACG | ACAGG | TCCAT | GCGCC | TGAGA | ACGGC
\end{equation*}
$$  


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

|   | A | G | C | T |
|---|---|---|---|---|
| A | 7 | 0 | 1 | 1 |
| G | 1 | 9 | 2 | 0 |
| C | 0 | 2 | 7 | 2 |
| T | 1 | 0 | 1 | 6 |
|   | 9 | 11| 11| 9 |

where, for example, the entry corresponding to $(C,G)$ is the frequency of a $C$ in the $S_0$ string becoming a $G$ in the $S_1$ string. The numbers at the bottom represent the frequencies of each $A$, $G$, $C$ and $T$ appearing in the string $S_0$.

We can estimate the conditional probabilities $P\left(S_1=i\mid S_0=j\right)$ by dividing each of the entries by the sum at the bottom of each column. For example, the number of sites at which a $C$ in $S_0$ becomes a $G$ in $S_1$ is $2$, and the number of times $C$ appears in $S_0$ is $11$. So the probability that a $C$ becomes a $G$ is $2/11$. Formally,

$$
\begin{equation*}
\begin{aligned}
P\left(S_1=G\mid S_0=C\right)=\frac{P\left(S_1=G\text{ and }S_0=C\right)}{P\left(S_0=C\right)}=\frac{2}{11}.
\end{aligned}
\end{equation*}
$$

Doing this for each entry yields:

|   | A | G | C | T |
|---|---|---|---|---|
| A | 0.778 | 0 | 0.091 | 0.111 |
| G | 0.111 | 0.818 | 0.182 | 0 |
| C | 0 | 0.182 | 0.636 | 0.222 |
| T | 0.111 | 0 | 0.091 | 0.667 |

We will construct a basic model of molecular evolution by making use of probability and matrix algebra. We define the vector $\mathbf{p}_0$ as the vector of probabilities that each of the bases $A$, $G$, $C$ and $T$ appear:

$$
\begin{equation*}
\begin{aligned}
=\frac{1}{\text{length of }S_0}\begin{bmatrix}
\#\text{ of }A\text{'s in }S_0\\
\#\text{ of }G\text{'s in }S_0\\
\#\text{ of }C\text{'s in }S_0\\
\#\text{ of }T\text{'s in }S_0\\
\end{bmatrix}
\mathbf{p}_0=\begin{bmatrix}
P_{A_0}\\ P_{G_0}\\ P_{C_0}\\ P_{T_0}
\end{bmatrix}
=\frac{1}{\text{length of }S_0}\begin{bmatrix}
\#\text{ of }A\text{'s in }S_0\\
\#\text{ of }G\text{'s in }S_0\\
\#\text{ of }C\text{'s in }S_0\\
\#\text{ of }T\text{'s in }S_0\\
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

where $P_{i_0}=P(S_0=i)$. We model the mutation process over one time step, assuming that only base substitutions can occur - no deletions, insertions or inversions are considered. We can store the $16$ conditional probabilities

$$
\begin{equation*}
\begin{aligned}
P\left(S_1=i\mid S_0=j\right),
\end{aligned}
\end{equation*}
$$

for $i,j=A,G,C,T$ in a $4\times4$ matrix as follows:

$$
\begin{equation*}
\begin{aligned}
M=\begin{bmatrix}
P_{A_1\mid A_0}	&	P_{A_1\mid G_0}	&	P_{A_1\mid C_0}	&	P_{A_1\mid T_0}	\\
P_{G_1\mid A_0}	&	P_{G_1\mid G_0}	&	P_{G_1\mid C_0}	&	P_{G_1\mid T_0}	\\
P_{C_1\mid A_0}	&	P_{C_1\mid G_0}	&	P_{C_1\mid C_0}	&	P_{C_1\mid T_0}	\\
P_{T_1\mid A_0}	&	P_{T_1\mid G_0}	&	P_{T_1\mid C_0}	&	P_{T_1\mid T_0}	
\end{bmatrix},
\end{aligned}
\end{equation*}
$$

where we have used the abbreviations $P_{i_1\mid j_0}=P\left(S_1=i\mid S_0=j\right)$. These entries correspond precisely with the entries in the table of probabilities we found in the first example.

Before we calculate the product $M\mathbf{p}_0$, let us make the following observations: using equation (1), we see that

$$
\begin{equation*}
\begin{aligned}
P_{G_1\mid C_0}P_{C_0}=P\left(S_1=G\mid S_0=C\right)P\left(S_0=C\right)=P\left(S_1=G\textbf{ and }S_0=C\right).
\end{aligned}
\end{equation*}
$$

So in general,

$$
\begin{equation*}
\begin{aligned}
P_{i_1\mid j_0}P_{j_0}=P\left(S_1=i\textbf{ and }S_0=j\right),
\end{aligned}
\end{equation*}
$$

for $i,j=A,G,C,T$. Note further that,

$$
\begin{equation*}
\begin{aligned}
P\left(S_1=i\textbf{ and }S_0=A\right),\hspace*{0.2cm}P\left(S_1=i\textbf{ and }S_0=G\right),\hspace*{0.2cm}P\left(S_1=i\textbf{ and }S_0=C\right),\hspace*{0.2cm}P\left(S_1=i\textbf{ and }S_0=T\right)
\end{aligned}
\end{equation*}
$$

are all mutually exclusive events. So the sum of these four probabilities is the probability of the union of the four events. That is,

$$
\begin{equation*}
\begin{aligned}
P\left(S_1=i\textbf{ and }S_0=A\right)+P\left(S_1=i\textbf{ and }S_0=G\right)+P\left(S_1=i\textbf{ and }S_0=C\right)+P\left(S_1=i\textbf{ and }S_0=T\right)=P(S_1=i).
\end{aligned}
\end{equation*}
$$

With this in mind, calculating $M\mathbf{p}_0$, we obtain

$$
\begin{equation*}
\begin{aligned}
M\mathbf{p}_0	& =\begin{bmatrix}
P_{A_1\mid A_0}	&	P_{A_1\mid G_0}	&	P_{A_1\mid C_0}	&	P_{A_1\mid T_0}	\\
P_{G_1\mid A_0}	&	P_{G_1\mid G_0}	&	P_{G_1\mid C_0}	&	P_{G_1\mid T_0}	\\
P_{C_1\mid A_0}	&	P_{C_1\mid G_0}	&	P_{C_1\mid C_0}	&	P_{C_1\mid T_0}	\\
P_{T_1\mid A_0}	&	P_{T_1\mid G_0}	&	P_{T_1\mid C_0}	&	P_{T_1\mid T_0}	
\end{bmatrix}\begin{bmatrix}
P_{A_0}\\ P_{G_0}\\ P_{C_0}\\ P_{T_0}
\end{bmatrix}\\
				& =\begin{bmatrix}
P_{A_1\mid A_0}P_{A_0}	+	P_{A_1\mid G_0}P_{G_0}	+	P_{A_1\mid C_0}P_{C_0}	+	P_{A_1\mid T_0}P_{T_0}	\\
P_{G_1\mid A_0}P_{A_0}	+	P_{G_1\mid G_0}P_{G_0}	+	P_{G_1\mid C_0}P_{C_0}	+	P_{G_1\mid T_0}P_{T_0}	\\
P_{C_1\mid A_0}P_{A_0}	+	P_{C_1\mid G_0}P_{G_0}	+	P_{C_1\mid C_0}P_{C_0}	+	P_{C_1\mid T_0}P_{T_0}	\\
P_{T_1\mid A_0}P_{A_0}	+	P_{T_1\mid G_0}P_{G_0}	+	P_{T_1\mid C_0}P_{C_0}	+	P_{T_1\mid T_0}P_{T_0}	
\end{bmatrix}\\
				& =\begin{bmatrix}
P_{A_1}\\ P_{G_1}\\ P_{C_1}\\ P_{T_1}
\end{bmatrix}\\
				&=\mathbf{p}_1
\end{aligned}
\end{equation*}

The matrix $M$ we constructed above is an example of a \textbf{Markov matrix}. Formally, it is a matrix whose entries are all $\geq 0$ and whose columns sum to $1$.
These matrices aren't new, we used them in our discussion about structured populations, particularly in the examples about trees, grasses, dunes etc.. 
We also have the following facts about Markov matrices:

- A Markov matrix always has $\lambda=1$ as its largest (dominant) eigenvalue,
- All eigenvalues of a Markov matrix satisfy $|\lambda|=1$,
- There is precisely one eigenvector (up to scalar multiplication) corresponding to the eigenvalue $\lambda=1$.

### Example 1

Back to our example. We have:

$$
\begin{equation*}
\begin{aligned}
\mathbf{p}_0=\frac{1}{40}\begin{bmatrix}
9	\\ 11	\\ 11	\\ 9
\end{bmatrix}=\begin{bmatrix}
0.225	\\ 0.275	\\ 0.275	\\ 0.225
\end{bmatrix},\hspace*{1cm}M=\begin{bmatrix}
0.778	& 0		& 0.091	& 0.111	\\
0.111	& 0.818	& 0.182	& 0		\\
0		& 0.182	& 0.636	& 0.222	\\
0.111	& 0		& 0.091	& 0.667
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

and so,

$$
\begin{equation*}
\begin{aligned}
\mathbf{p}_1=M\mathbf{p}_0=\begin{bmatrix}
0.778	& 0		& 0.091	& 0.111	\\
0.111	& 0.818	& 0.182	& 0		\\
0		& 0.182	& 0.636	& 0.222	\\
0.111	& 0		& 0.091	& 0.667
\end{bmatrix}\begin{bmatrix}
0.225	\\  0.275	\\  0.275	\\  0.225
\end{bmatrix}=\begin{bmatrix}
0.22505	\\  0.29975	\\  0.2749	\\  0.200075
\end{bmatrix}\begin{bmatrix}
0.225	\\	0.3	\\	0.275	\\	0.2
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

Which agrees with the actual value,

$$
\begin{equation*}
\begin{aligned}
\mathbf{p}_1=\frac{1}{40}\begin{bmatrix}
7+0+1+1	\\	1+9+2+0	\\	0+2+7+2	\\	1+0+1+6
\end{bmatrix}=\frac{1}{40}\begin{bmatrix}
9	\\	12	\\	11	\\	8
\end{bmatrix}=\begin{bmatrix}
0.225	\\	0.3	\\	0.275	\\	0.2
\end{bmatrix}.\\
\end{aligned}
\end{equation*}
$$

Of course, this is expected. We explicitly constructed the matrix $M$ so that it would give us exactly $\mathbf{p}_1$. What is more interesting perhaps is asking questions such as the following: What proportion of sites will have a base $A$ in the ancestral sequence and a $T$ in the descendent sequence after $100$ time steps? That is, what is $P\left(S_{100}=T\textbf{ and }S_0=A\right)$?

Having calculated the matrix $M$, we can answer this question quite quickly.


### Example 

We continue with our example. We have

$$
\begin{equation*}
\begin{aligned}
\mathbf{p}_0=\begin{bmatrix}
0.225	\\ 0.275	\\ 0.275	\\ 0.225
\end{bmatrix}=\begin{bmatrix}
P_{A_0}	\\ P_{G_0}	\\ P_{C_0}	\\ P_{T_0}
\end{bmatrix},\hspace*{1cm}M=\begin{bmatrix}
0.778	& 0		& 0.091	& 0.111	\\
0.111	& 0.818	& 0.182	& 0		\\
0		& 0.182	& 0.636	& 0.222	\\
0.111	& 0		& 0.091	& 0.667
\end{bmatrix}=\begin{bmatrix}
P_{A_1\mid A_0}	&	P_{A_1\mid G_0}	&	P_{A_1\mid C_0}	&	P_{A_1\mid T_0}	\\
P_{G_1\mid A_0}	&	P_{G_1\mid G_0}	&	P_{G_1\mid C_0}	&	P_{G_1\mid T_0}	\\
P_{C_1\mid A_0}	&	P_{C_1\mid G_0}	&	P_{C_1\mid C_0}	&	P_{C_1\mid T_0}	\\
P_{T_1\mid A_0}	&	P_{T_1\mid G_0}	&	P_{T_1\mid C_0}	&	P_{T_1\mid T_0}	
\end{bmatrix}\\
\end{aligned}
\end{equation*}
$$

First, lets answer the question: What proportion of sites will have a base $A$ in the ancestral sequence and a $T$ in the descendent sequence after $1$ time step? That is, what is $P\left(S_{1}=T\textbf{ and }S_0=A\right)$? Note that we have the following,

$$
\begin{equation*}
\begin{aligned}
P\left(S_{1}=T\textbf{ and }S_0=A\right)=P\left(S_{1}=T\mid S_0=A\right)P\left(S_0=A\right)=P_{T_1\mid A_0}P_{A_0}\\
\end{aligned}
\end{equation*}
$$

So the probability that we are interested in is merely the product of the $(4,1)-$entry in $M$ and the first entry in $\mathbf{p}_0$. So,

$$
\begin{equation*}
\begin{aligned}
P\left(S_{1}=T\textbf{ and }S_0=A\right)=0.111\times0.225=0.024975\\
\end{aligned}
\end{equation*}
$$

Extending this to the original question - What proportion of sites will have a base $A$ in the ancestral sequence and a $T$ in the descendent sequence in $100$ time steps? That is, what is $P\left(S_{100}=T\textbf{ and }S_0=A\right)$? - the answer is the product of the $(4,1)-$entry in $M^{100}$ and the first entry in $\mathbf{p}_0$. So,

$$
\begin{equation*}
\begin{aligned}
M^{100}=\begin{bmatrix}
0.185	&	0.185	&	0.185	&	0.185	\\
0.395	&	0.395	&	0.395	&	0.395	\\
0.282	&	0.282	&	0.282	&	0.282	\\
0.139	&	0.139	&	0.139	&	0.139
\end{bmatrix},\hspace*{1cm}
P\left(S_{100}=T\textbf{ and }S_0=A\right)=0.139\times0.225=0.031275\\
\end{aligned}
\end{equation*}
$$

So, roughly $3\%$ of sites will begin with a base $A$ and mutate into a base $T$ after $100$ time steps.

Let's do this all again with another example.

### Example

Suppose a $40$-base ancestral DNA sequence ($S_0$) is given by the top row in the table below and its descendent aligned sequence ($S_1$) is given by the bottom row. 


%$A$ $G$ $C$ $T$ $T$ & 
%$C$ $C$ $G$ $A$ $T$ & 
%$C$ $C$ $G$ $C$ $T$ & 
%$A$ $T$ $A$ $A$ $T$ & 
%$C$ $G$ $T$ $T$ $A$ & 
%$G$ $T$ $T$ $G$ $T$ & 
%$T$ $A$ $C$ $A$ $C$ & 
%$C$ $T$ $C$ $T$ $G$ \\&&&&&&&\\

%$A$ $G$ $G$ $T$ $T$ & 
%$C$ $T$ $G$ $T$ $A$ & 
%$C$ $C$ $G$ $T$ $A$ & 
%$A$ $A$ $C$ $A$ $T$ & 
%$C$ $G$ $T$ $T$ $A$ & 
%$G$ $T$ $C$ $G$ $T$ & 
%$T$ $A$ $C$ $A$ $C$ & 
%$C$ $T$ $C$ $T$ $A$ 


- First let's record the number of changes in a table

%Add table

- Our vector $\mathbf{p}_0$ and transition matrix $M$ are given by

$$
\begin{equation*}
\begin{aligned}
\mathbf{p}_0=\frac{1}{40}\begin{bmatrix}
8	\\	7	\\	11	\\	14
\end{bmatrix}=\begin{bmatrix}
0.200	\\	0.175	\\	0.275	\\	0.350
\end{bmatrix}\hspace*{1cm}M=\begin{bmatrix}
\frac{6}{8}	&	\frac{1}{7}	&	\frac{0}{11}	&	\frac{3}{14}	\\\\
\frac{0}{8}	&	\frac{6}{7}	&	\frac{1}{11}	&	\frac{0}{14}	\\\\
\frac{1}{8}	&	\frac{0}{7}	&	\frac{8}{11}	&	\frac{1}{14}	\\\\
\frac{1}{8}	&	\frac{0}{7}	&	\frac{2}{11}	&	\frac{10}{14}
\end{bmatrix}
=\begin{bmatrix}
0.750	&	0.143	&	0		&	0.214	\\
0		&	0.857	&	0.091	&	0		\\
0.125	&	0		&	0.727	&	0.071	\\
0.125	&	0		&	0.182	&	0.714
\end{bmatrix}
\end{aligned}
\end{equation*}
$$

- The proportion of sites that will have a base $T$ that mutates into a base $A$ after $1$ time step is

$$
\begin{equation*}
\begin{aligned}
P\left(S_1=A\textbf{ and }S_0=T\right)=P\left(S_1=A\mid S_0=T\right)P\left(S_0=A\right)=0.214\times0.350=\boxed{0.0749}
\end{aligned}
\end{equation*}
$$

:::{note}
 Note for this question we can heck our answer since this probability should match the $(T,A)$ entry in the frequency table divided by the total number of sites. In this case it is $\dfrac{3}{40}=0.075$
:::

- The proportion of sites that will have a base $T$ that mutates into a base $A$ after $50$ time steps is

$$
\begin{equation*}
\begin{aligned}
M^{50}=\begin{bmatrix}
0.333	&	0.333	&	0.333	&	0.333	\\
0.146	&	0.146	&	0.146	&	0.146	\\
0.229	&	0.229	&	0.229	&	0.229	\\
0.292	&	0.292	&	0.292	&	0.292
\end{bmatrix},
\end{aligned}
\end{equation*}
$$

$$
\begin{equation*}
\begin{aligned}
P\left(S_{50}=A\textbf{ and }S_0=T\right)=P\left(S_{50}=A\mid S_0=T\right)P\left(S_0=A\right)=0.333\times0.350=\boxed{0.11655}
\end{aligned}
\end{equation*}
$$

- The (**conditional**) probability that a base $C$ will have mutated into a base $T$ after $50$ time steps is

$$
\begin{equation*}
\begin{aligned}
\boxed{0.292}
\end{aligned}
\end{equation*}
$$

:::{note} 
Note the difference in wording here. Before we were asking the **proportion** of **all** sites. Here we considering a single site which are told/assuming has base $C$.
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
