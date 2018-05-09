# Questions

## When is probability space sigma algebra not just sample space

Let $S = \{1,2,3,4\}$ with $B \subseteq S$ a $\sigma$-algebra, say $B = \{ \null, \{1,2,3,4\}, \{1,2\}, \{3,4\} \}$. 

It was shown that $B$ is indeed a sigma algebra.

Definition of a probability set function

$$ Pr: B \to [0,1] $$

Satisfies:

- $Pr(A \subseteq B) \geq 0$
- $Pr(S) = 1$
- $B$ is a sigma algebra
- $Pr(\cup A_i) = \sum Pr(A_i)$

However, can the probability space $(S, B, Pr)$ really exist (in a 'practical' sense)? For example, if $S$ truly was a sample space, then $Pr(3)$ shouldn't be completely nonzero, otherwise it would not be in the sample space.

This is assuming that the experiment realizes one event only. Otherwise, if it was possible for the experiment to yield two events, say $\{3,4\}$ then $\{3,4\} \in S$, which its not.

Moreover, $B$ doesn't even contain $\{3\}$, so is it fair to say that this probability space models an experiment where $\{3\}$ is an outcome? After all, if $Pr: B \to [0,1]$ then $Pr(3)$ is not even defined.
