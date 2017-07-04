# Page 226

<img src="../../pictures/correction_green.svg" width="32px"/>
__Location:__ Chapter 24, solution to Problem 7

## The issue

_Note_: the exponentiating bird is represented in the following with the symbol $\varepsilon$.

The exponentiating bird is said to be able to evaluate
the expression $n^m$ for _any_ two natural numbers $n$ and $m$.

Still, what is its behaviour when $n=m=0$? Using the definition of $\varepsilon$
and applying the rules, one finds that

$$
    \varepsilon\,\overline{0}\,\overline{0} = \overline{1}\;,
$$

i.e. $0^0=1$, against the mathematical fact that the result is undefined.

## Possible workarounds

Dealing separately with the case $m=n=0$ in the expression simply requires
to stack another zero-tester $Z$ in front of the given formula for $\varepsilon$.
Still, what should the bird return in that case? An option would perhaps be that
of introducing a special _number bird_ standing for "undefined", thus enlarging the set
over which the arithmetic birds operate much in the same way as `nan` and `inf`
are treated by the arithmetic units within most CPUs.
