---
title: My notes on STAT 330 -- Mathematical Statistics
author: Dillon Chan
colorlinks: urlcolor
geometry: margin=1in

---

## Preliminaries

Sample space

:   The set of all possible outcomes of an experiment, $S$.

$\sigma$-field

:   Let $S$ be a sample space with power set $\mathbb P(S)$. A collection of sets $\mathcal B \subseteq \mathbb P (S)$ is a $\sigma$-field / $\sigma$-algebra on $S$ if

    1. $\emptyset, S \in \mathcal B$

    2. $\mathcal B$ closed under complementation

    3. $\mathcal B$ closed under countable unions

Measurable space 

:   Let $S$ be a sample space and $\mathcal B$ be a $\sigma$-algebra. Then the pair $(S,\mathcal B)$ is a measurable space.

Measure

:   Let $X$ be a set and $\Sigma$ be a $\sigma$-algebra over $X$. A function

    $$\mu : X \to \mathbb R \cup \{+\infty\} \cup \{-\infty\}$$

    is called a measure if it satisfies:

    - Non-negativity: For all $E \in \Sigma$, $\mu(E) \geq 0$

    - Null empty set: $\mu(\emptyset) = 0$

    - Countable additivity: For all countable collections $\{E_i\}_{i=1}^\infty$ of pairwise disjoint sets[^pairwise_disjoint] in $\Sigma$, 
        $$\mu \left(\cup_{k=1}^\infty E_k \right) = \sum_{k=1}^\infty \mu(E_k) $$

    Definition from [wikipedia][wiki_measure]

Probability Measure

:   Let $S$ be a sample space for a random experiment. Let $\mathcal B = \{ A_1, A_2, \cdots \}$ be a $\sigma$-field on $S$. A probability measure is a function $\Pr: \mathcal B \to [0,1]$ that satisfies:

    - $\Pr(A) \geq 0$ for all $A \in \mathcal B$.
    - $\Pr(S) = 1$
    - If $A_1, A_2, \cdots \in \mathcal B$ are disjoint events then $\Pr(\cup_{i=1}^\infty A_i) = \sum_{i=1}^\infty \Pr(A_i)$. 

Measure space

:   A measure space is a [measurable space](#measurable-space) equipped with a [measure](#measure)


Probability space

:   A probability space is a [measureable space](#measurable-space) equipped with a [probability measure](#probability-measure).







[^pairwise_disjoint]: For any two elements in the set, them being disjoint is pairwise disjoint.

[wiki_measure]: <https://en.wikipedia.org/wiki/Measure_(mathematics)>




