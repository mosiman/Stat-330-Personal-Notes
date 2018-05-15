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

Theorem: Boole's Inequality

:   If $A_1, A_2, \cdots$ is a sequence of events, then $\Pr\left( \cup_{i=1}^\infty A_i \right) \leq \sum_{i=1}^\infty \Pr(A_i)$. 

    *Proof*: In the case where each $A_i$ are independent, the result follows by the definition of a probability measure. Suppose any $A_i, A_j$ are not independent. Then we have that $\Pr(A_i \cup A_j) = \Pr(A_i) + \Pr(A_j) - \Pr(A_i \cap A_j)$ which is certainly less than the case where they are independent. The proof follows by induction.

Theorem: Bonferroni's Inequality

:   If $A_1, \cdots, A_k$ are events, then $\Pr\left(\cap_{i=1}^k A_i\right) \geq 1 - \sum_{i=1}^k \Pr(A_i^C)$. 

    *Proof*: Recall [De Morgan's Laws][DML], which states that $(A \cup B)^C = A^C \cap B^C$, and also that $(A \cap B)^C = A^C \cup B^C$. Then
    $$
    \begin{aligned}
        \Pr\left(\cap_{i=1}^k A_i\right) & = \Pr\left(\cap_{i=1}^k (A_i^C)^C \right)\\
        & = \Pr\left(\cup_{i=1}^k A_i^C \right)\\
        & \leq \sum_{i=1}^k \Pr(A_i^C) & \text{Boole's inequality}\\
        & = 1 - \sum_{i=1}^k \Pr(A_i)
    \end{aligned}
    $$
    The result has been proven.

Theorem: Continuity property

:   If $A_1 \subset A_2 \subset \cdots$ is a sequence where $A = \cup_{i=1}^\infty A_i$ then $\lim_{n \to \infty} \Pr(\cup_{i=1}^n A_i) = \Pr(A)$. 

    *Proof*: We note that for any $A_i, A_{i+1}$ we have that $\Pr(A_i \cap A_{i+1}) = \Pr(A_{i+1})$. Consider some finite $n$. Then we have that $\Pr(\cap_{i=1}^n A_i) = A_n$. Assuming that $\lim_{n\to \infty} A_n = A$, then $\lim_{n \to \infty} \Pr(\cup_{i=1}^n A_i) = \lim_{n \to \infty} A_n = A$. 

Random Variable

:   Consider a [probability space](#probability-space) $(S, \mathcal B, \Pr)$. The function $X: S \to \mathbb R$ is called a *Random Variable* if $\Pr(X \leq x) = \Pr(\{\omega \in S \, | \, X(\omega) \leq x\})$ is valid for all $x \in \mathbb R$. 

Cumulative Distribution Function

:   The *cumulative distribution function* (CDF) of a [random variable](#random-variable) $X$ is defined to be
    $$ F(x) = \Pr(X \leq x)$$
    for all $x \in \mathbb R$. 

    Furthermore, it has the following properties:

    - $F$ is non-decreasing (since if $A_i \subset A_{i+1}$ then $\Pr(A_i) \leq \Pr(A_{i+1})$). 
    - $\lim_{x \to - \infty} F(x) = 0$ and $\lim_{x \to \infty} F(x) = 1$. 
    - $F$ is right-continuous, by convention. I.e., $\lim_{x \to a^+} F(x) = F(a)$. 
    - $\Pr(a < X \leq b) = \Pr(X \leq b) - \Pr(X \leq a) = F(b) - F(a)$, where $a < b$. (This is 'the area between two points'). 
    - $\Pr(X = b) = F(b) = \lim{a \to b^-}F(a)$ (the magnitude of the 'jump' at $X = b$. Note for continuous CDFs, this is 0. 
        
Support

:   Let $f(x)$ be the probability function of a random variable $X$. The *support* of $X$ is $A = \{x | f(x) > 0\}$. 






[^pairwise_disjoint]: For any two elements in the set, them being disjoint is pairwise disjoint.

[wiki_measure]: <https://en.wikipedia.org/wiki/Measure_(mathematics)>

[DML]: <https://en.wikipedia.org/wiki/Algebra_of_sets#Some_additional_laws_for_complements>



