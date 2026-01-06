# Genetic Inheritance
## I got it from my mama

---

## Mendel's Experiments

In the mid nineteenth century Gregor Mendel studied genetic crosses between strains of the garden pea. He found that the plants' offspring retained traits of the parents. He followed seven visible characters of the pea, each represented by two contrasting traits.

| Character | Traits | Allele |
|-----------|--------|--------|
| Seed Shape | Round/Wrinkled | $R/r$ |
| Seed Colour | Yellow/Green | $Y/y$ |
| Pod Shape | Full/Constricted | $F/f$ |
| Pod Colour | Green/Yellow | $G/g$ |
| Flower Position | Axial/Terminal | $A/a$ |
| Flower Colour | Violet/White | $V/v$ |
| Stem Height | Tall/Dwarf | $T/t$ |

---

## Genotype vs Phenotype

An organism's **genotype** is its specific combination of alleles for a given gene. The **phenotype** is the physical manifestation of an organism's genotype. For example, for the pea flower's colour, the phenotype will be either violet or white. The genotype will be the combination of the dominant allele ($V$) and recessive allele ($v$).

### Example: Flower Colour

| Phenotype | Genotype | Description |
|-----------|----------|-------------|
| **Violet** | $VV$ | homozygous dominant |
| **Violet** | $Vv$ | heterozygous |
| **Violet** | $vV$ | heterozygous |
| **White** | $vv$ | homozygous recessive |

**Visual representation:**

```
Genotype:        VV           Vv           vv
              (homozygous) (heterozygous) (homozygous)
                   ↓            ↓            ↓
Phenotype:      Violet       Violet       White
```

**Key concepts:**
- **Dominant allele**: The allele that is expressed in the heterozygous condition (represented by capital letter)
- **Recessive allele**: The allele that is only expressed when homozygous (represented by lowercase letter)
- **Homozygous**: Two copies of the same allele ($VV$ or $vv$)
- **Heterozygous**: Two different alleles ($Vv$ or $vV$)

---

## Punnett Squares

**Punnett squares** allow geneticists to predict the possible genotypes and phenotypes of offspring. Each of the gametes is assigned a column or a row; the vertical columns represent those of the female parent and the horizontal rows represent those of the male parent. After filling in the information of each parent's genotypes we can predict the next generation's possible genotypes and phenotypes by looking at the combinations that follow.

---

## Example 1: Monohybrid Cross $Vv \times Vv$

In the monohybrid cross $Vv \times Vv$, the Punnett square is given by:

|     | $V$ (male) | $v$ (male) |
|-----|------------|------------|
| **$V$ (female)** | $VV$ | $Vv$ |
| **$v$ (female)** | $Vv$ | $vv$ |

### Results:
- **Genotype ratios:**
  - $VV$: 1 (homozygous dominant)
  - $Vv$: 2 (heterozygous)
  - $vv$: 1 (homozygous recessive)
  
- **Phenotype ratios:**
  - Violet: 3 ($VV$, $Vv$, $Vv$)
  - White: 1 ($vv$)
  - **Ratio: 3:1**

We see that there are three outcomes ($VV$, $Vv$ and $Vv$) that result in a violet flower, and just one ($vv$) that results in a white flower. There are two possible homozygous genotypes ($VV$ and $vv$) and one heterozygous ($Vv$).

---

## Example 2: More Monohybrid Crosses

Determine the Punnett squares for the crosses: $VV \times Vv$, $VV \times vv$ and $Vv \times vv$.

### Cross: $VV \times Vv$

|     | $V$ (male) | $v$ (male) |
|-----|------------|------------|
| **$V$ (female)** | $VV$ | $Vv$ |
| **$V$ (female)** | $VV$ | $Vv$ |

**Result:** All offspring have violet flowers (100% violet)

### Cross: $VV \times vv$

|     | $v$ (male) | $v$ (male) |
|-----|------------|------------|
| **$V$ (female)** | $Vv$ | $Vv$ |
| **$V$ (female)** | $Vv$ | $Vv$ |

**Result:** All offspring have violet flowers (100% violet, all heterozygous)

### Cross: $Vv \times vv$

|     | $v$ (male) | $v$ (male) |
|-----|------------|------------|
| **$V$ (female)** | $Vv$ | $Vv$ |
| **$v$ (female)** | $vv$ | $vv$ |

**Result:** 50% violet ($Vv$), 50% white ($vv$)

---

## Dihybrid Crosses

We can extend these Punnett squares to consider dihybrid crosses, that is, we can use Punnett squares to look at more than one character.

### Example: $VvTt \times vvTt$

Let's now look at the flower colour and stem height. The Punnett square of the cross $VvTt \times vvTt$ looks like:

|          | $vT$ (male) | $vt$ (male) | $vT$ (male) | $vt$ (male) |
|----------|-------------|-------------|-------------|-------------|
| **$VT$ (female)** | $VvTt$ | $Vvtt$ | $VvTt$ | $Vvtt$ |
| **$Vt$ (female)** | $VvTT$ | $VvTt$ | $VvTT$ | $VvTt$ |
| **$vT$ (female)** | $vvTt$ | $vvtt$ | $vvTt$ | $vvtt$ |
| **$vt$ (female)** | $vvTT$ | $vvTt$ | $vvTT$ | $vvTt$ |

One sees that this can naturally be extended to consider more than two characters, the table will obviously just get bigger.

---

## Probability and Genetics

Okay, so let's apply some probability to these Punnett squares. What we have done by creating the Punnett square is write out the complete sample space for the genotypes of the offspring. Given that the chance of inheriting a particular allele for each trait is 50%, each of the boxes in the square is equally likely to occur. Of course we do have duplicates, so we have a way of quickly reading off the probability of a particular genotype occurring.

### Example: Probability Questions for $VvTt \times vvTt$

Using the Punnett square above:

**1. What is the probability that the offspring has genotype $VvTt$?**

The type $VvTt$ appears 4 times in the Punnett square, so the probability of it occurring is $\frac{4}{16} = \boxed{\frac{1}{4}}$

**2. What is the probability that the offspring has genotype $vvTT$?**

The type $vvTT$ appears 2 times in the Punnett square, so the probability of it occurring is $\frac{2}{16} = \boxed{\frac{1}{8}}$

**3. What is the probability that the offspring has genotype $vvTt$ or $vvTT$?**

- The type $vvTt$ appears 4 times in the Punnett square, so the probability is $\frac{4}{16}$
- The type $vvTT$ appears 2 times in the Punnett square, so the probability is $\frac{2}{16}$
- The probability of either type $vvTt$ or $vvTT$ occurring is $\frac{4}{16} + \frac{2}{16} = \frac{6}{16} = \boxed{\frac{3}{8}}$

---

## Example: Round and Green Seeds

Find the probability that the offspring of the cross $RrYy \times RrYy$ has round and green seeds.

### Method 1: Using Punnett Square

|          | $RY$ | $Ry$ | $rY$ | $ry$ |
|----------|------|------|------|------|
| **$RY$** | $RRYY$ | $RRYy$ | $RrYY$ | $RrYy$ |
| **$Ry$** | $RRYy$ | $RRyy$ | $RrYy$ | $Rryy$ |
| **$rY$** | $RrYY$ | $RrYy$ | $rrYY$ | $rrYy$ |
| **$ry$** | $RrYy$ | $Rryy$ | $rrYy$ | $rryy$ |

Round seeds is the dominant gene and green seeds is recessive. Therefore we are looking for the occurrence of the genotypes $RRyy$ or $Rryy$:
- $RRyy$ occurs once
- $Rryy$ occurs twice

Therefore the probability is:

$$P(\text{round and green seeds}) = \boxed{\frac{3}{16}}$$

### Method 2: Using Probability Rules

We can do this without the Punnett square. Note that shape and colour are independent events and the allele inherited from the female and the allele inherited from the male are also independent. So:

$$\begin{align*}
P(\text{round and green seeds}) &= P(\text{round seeds}) \cdot P(\text{green seeds}) \\
&= P(RR \text{ or } Rr) \cdot P(yy) \\
&= [P(R_fR_m) + P(R_fr_m) + P(r_fR_m)] \cdot P(y_fy_m) \\
&= [P(R_f) \cdot P(R_m) + P(R_f) \cdot P(r_m) + P(r_f) \cdot P(R_m)] \cdot P(y_f) \cdot P(y_m) \\
&= \left[\frac{1}{2} \cdot \frac{1}{2} + \frac{1}{2} \cdot \frac{1}{2} + \frac{1}{2} \cdot \frac{1}{2}\right] \cdot \frac{1}{2} \cdot \frac{1}{2} \\
&= \left[\frac{1}{4} + \frac{1}{4} + \frac{1}{4}\right] \cdot \frac{1}{4} \\
&= \frac{3}{4} \cdot \frac{1}{4} \\
&= \boxed{\frac{3}{16}}
\end{align*}$$

**Key insight:** This shows that we can use probability rules to solve genetics problems without drawing out the entire Punnett square, especially useful for complex crosses!

---

## Genetic Terminology/Vocabulary

| Term | Definition |
|------|------------|
| **Alleles** | Alternative forms of traits |
| **Dihybrid cross** | Cross involving two characters |
| **Heredity** | Passing of traits from parent to offspring |
| **Heterozygous** | Two alleles of trait are different |
| **Homozygous** | Two alleles of trait are the same |
| **Genetics** | Study of heredity |
| **Genotype** | Pair of alleles present in an individual |
| **Monohybrid cross** | Cross involving a single character |
| **Phenotype** | Observable characteristic of an organism |
| **Trait** | Any characteristic that can be passed from parent to offspring |

---

## Summary

1. **Genotype** = genetic makeup (e.g., $VV$, $Vv$, $vv$)
2. **Phenotype** = physical appearance (e.g., violet or white)
3. **Dominant alleles** (capital letters) mask recessive alleles in heterozygotes
4. **Punnett squares** organize all possible offspring combinations
5. **Probability** can be calculated by:
   - Counting outcomes in Punnett square, OR
   - Using multiplication rule for independent events
6. Each allele has a **50% chance** of being inherited from each parent
7. **Independent assortment**: Different traits are inherited independently