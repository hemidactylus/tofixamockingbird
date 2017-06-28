# Pages 178, 185

<img src="/pictures/correction_blue.svg" width="32px"/>
__Location:__ Chapter 18, very last suggestion in the chapter; and Chapter 19, Appendix

## Suggestion:

After laying out, in Chapter 18, the unambiguous algorithm for
converting any expression $X$ (containing variables $x,y,\ldots$)
into a bird $A$ -- made of birds in $\{S,K,I\}$ --
such that for any $x,y,\ldots$ one has
$Axy\ldots=X$, the chapter ends with:

_This deterministic procedure can be easily programmed on a computer,
and those of you with home computers who like to work up software
should find it an entertaining and profitable exercise to
write a program to find combinators for any given expression._

The same suggestion can be imagined right at the end of the next chapter,
where a similar procedure is described for birds whose primitive
components are taken in the set $\{B,C,M,I\}$.

_Note_: it was not rather uncommon to possess a __home computer__ back in 1982.

## The program

The code given here performs the required task. In particular,
it asks for the combinator equation to solve, such as `Axyz=z(xx(Ky))`,
and returns the expression for $A$ in terms of the allowed primitive birds
(e.g. `A=(S(K(S(K(SI))))(S(K(S(KK)))(S(S(KS)(S(KK)(SII)))(KK))))`).

The code is given below.

## Short explanation

The code is composed of two parts: an input validator/parser and
the part that actually applies the algorithm (i.e. "the Secret").

- First the input
string is parsed and validated into a simple structure encoding
the hierarchy of the nested parenthesized expressions.
- Then, popping the free variables one by one, the $*$-eliminates are
iteratively constructed (here "$*$" stands for any free variable);
- each round of $*$-eliminate calculation, in turn, iteratively applies
the Principles illustrated earlier in the chapter.

## Actual code

The following runs with Python 3 (probably the only fussy parts are some `print` statement,
however) and should be run in a console: `python3 combinatorSolver.py`. It will interactively ask
for the expression to solve and output the corresponding solution.

HERE: merge with ch19 and rewrite the code so to recycle most of the machine!

```
#!/usr/bin/env python3

import sys

variables=list(map(chr,range(ord('a'),ord('z')+1)))
birds=list('SKI')

# parsing: from a string such as 'x(S(Ky))xz(yz)' to a parsed expression structure

DEBUG=False

ToDo=True

```
