# Page 226

<img src="../../pictures/correction_yellow.svg" width="32px"/>
__Location:__ Chapter 24, solutions to Problems 6 and 7

## Problem 6

### It is (formula given in the solution)

... such that for every $n$ and $m$,
$A\overline{n}\,\overline{m}=(Z\,\overline{m})\overline{0}((\oplus)(A(\overline{n}(P\,\overline{m}))\overline{n}))$.
Again, such a bird $A$ can be ...

### It should become

... such that for every $n$ and $m$,
$A\overline{n}\,\overline{m}=Z\,\overline{m}\overline{0}(\oplus(A\overline{n}(P\,\overline{m}))\overline{n})$.
Again, such a bird $A$ can be ...

## Problem 7

### It is (two expressions to correct)

_Note_: the exponentiating bird is represented in the following with the symbol $\varepsilon$.

... for any positive number $m$,
$\varepsilon\,\overline{n}\,\overline{m}=\otimes(\varepsilon\,\overline{n}\,\overline{m})\overline{n}$.
Equivalently we want a bird $\varepsilon$ such that for all $n$ and $m$,
$\varepsilon\,\overline{n}\,\overline{m}=Z\,\overline{m}\overline{1}(\otimes(\varepsilon\,\overline{n}\,\overline{m})\overline{n})$.
Again, such a bird $\varepsilon$ can be ...

### It should become

... for any positive number $m$,
$\varepsilon\,\overline{n}\,\overline{m}=\otimes(\varepsilon\,\overline{n}(P\,\overline{m}))\overline{n}$.
Equivalently we want a bird $\varepsilon$ such that for all $n$ and $m$,
$\varepsilon\,\overline{n}\,\overline{m}=Z\,\overline{m}\overline{1}(\otimes(\varepsilon\,\overline{n}(P\,\overline{m}))\overline{n})$.
Again, such a bird $\varepsilon$ can be ...

## Short explanation

In the correction to Problem 6, besides a few redundant parentheses
that can go away just for ease of reading, the crucial point is the
term $A\overline{n}(P\,\overline{m})$: with the formula given in the
text, $A$ would be applied, incorrectly, to the two terms
$(\overline{n}(P\,\overline{m}))$ and $\overline{n}$, leaving
the sum bird to act on a single term. The correction restores the intended interplay
between $\oplus$ and $A$.

As for Problem 7, the expressions simply forgot to decrease $m$ by
one when "unfolding" one step in the recursive definition of the exponentiation.
