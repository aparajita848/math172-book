# Fibonacci Rabbits

:::{important} 
:icon: false

**Instructions**:
- After you have completed your lab, by filling in the answers in the spaces provided, use your web-browser's print function (** Ctrl+P/Cmd+P), then ``Save as PDF" to print your Lab**. You may submit this PDF file to Blackboard.

_**Learning goals**_:

- Practice writing matrix equations for a hypothetical rabbit population growing under the given assumptions.
- Apply stability analysis using eigenvalues \& eigenvectors to study the long-term behavior of the population. 
- Connect the concepts of structured populations to an abstract application related to the familiar Fibonacci sequence & golden ratio.

_**Topics covered**_: Structured Populations, Eigenvector & Eigenvalues for stability analysis of structured populations.

:::

## Introduction

The Fibonacci Sequence is a mathematical phenomena that is defined as a sequence of numbers where the _**next number in the sequence is the sum of the two numbers preceding it**_ (for example, $ 0, 1, 1, 2, 3, 5, 8, 13, \dots $). The Fibonacci sequence can be observed appearing commonly in nature - in the arrangement of petals or sprouts for certain flowers or fruits and in the branching of trees; and can also be studied in the form of the _golden ratio_ {cite} `wikipedia_fibonacci`. Due to its ubiquitous appearance in nature, science, as well as other areas of study, attributed to both beauty & efficiency, it is a topic of much interest.

The sequence can be dated back to 200 B.C. Indian mathematics where they identified it in poetic patterns. However, the Fibonacci Sequence was officially discovered by Leonardo of Pisa (Fibonacci) in 1202. In Fibonacci’s book Liber Abaci, he shared his findings of the sequence in a structured population of rabbits. In this lab, you will develop and analyze a mathematical model that depicts a three-stage population of rabbits (baby, juvenile, and adult), a version of the original rabbit population growth problem proposed by Fibonacci in his book.

## Mathematical Model

Using the following _**assumptions**_, visualize the structured population using a table and a transition diagram for a hypothetical **3-stage model** for a rabbit population:

- Let $\Delta t = 1$ month
- The population model starts with a pair of baby rabbits, a male and a female.
- A baby rabbit will grow into a juvenile rabbit in a month.
- A juvenile rabbit will grow into an adult rabbit in a month.
- An adult characteristic is that the pair of rabbits will have already produced an offspring, who are also a pair of baby rabbits, male and female. And they will continue to do so, each month.
- The population is closed (no migration) and the mortality rate is 0 (no rabbits die, so the population is always increasing).

1. Fill in the tables below for each month, beginning with the first month, _the first row has been filled for you_.

| Time (months) | Total couples | Baby couples | Juvenile couples | Adult couples |
| :--- | :--- | :--- | :--- | :--- |
| 0 | <input type="number"> | <input type="number" size="5"> | <input type="number" > | <input type="number"> |
| 1 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |
| 2 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |
| 3 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |
| 4 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |
| 5 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |
| 6 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |
| 7 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |
| 8 | <input type="number"> | <input type="number"> | <input type="number"> | <input type="number"> |

```{raw} html
<table style="border-collapse:collapse; width:100%;">
  <thead>
    <tr>
      <th style="border:1px solid #333; padding:8px; text-align:left;">Month (n)</th>
      <th style="border:1px solid #333; padding:8px; text-align:left;">Newborn (N)</th>
      <th style="border:1px solid #333; padding:8px; text-align:left;">Juvenile (J)</th>
      <th style="border:1px solid #333; padding:8px; text-align:left;">Adult (A)</th>
      <th style="border:1px solid #333; padding:8px; text-align:left;">Total (T)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border:1px solid #333; padding:4px;">0</td>
      <td style="border:1px solid #333; padding:4px;"><input type="text" style="width:90%; border:none;" /></td>
      <td style="border:1px solid #333; padding:4px;"><input type="text" style="width:90%; border:none;" /></td>
      <td style="border:1px solid #333; padding:4px;"><input type="text" style="width:90%; border:none;" /></td>
      <td style="border:1px solid #333; padding:4px;"><input type="text" style="width:90%; border:none;" /></td>
    </tr>
    <!-- repeat this <tr> block for each row (month 1, 2, 3, ...) -->
  </tbody>
</table>
```


:::{list-table} Population table 1.
:header-rows: 1

* - Time (months) 
  - Total couples 
  - Baby couples 
  - Juvenile couples
  - Adult couples
* - 

 (a) 


