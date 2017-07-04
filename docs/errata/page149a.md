# Page 149

<img src="../../pictures/correction_red.svg" width="32px"/>
__Location:__ Chapter 14, bonus exercise 1, proposition (d)

## It is

(d) If $Px(Pyz)$ sings on all days, so does $P(Pxy)(Pyz)$.

## It should __disappear__

_[no sentence (d) to prove at all]_

## Short explanation

From the first three of Byrd's laws, proposition (d) __does not__ follow.
(The [rest of the exercise](page149b.md) proceeds without problems, though.)

In the terms of Problem 1 of the Chapter, the particular arrangement

$$
    x \notin S~~,~~~y \in S~~,~~~z \notin S
$$

acts as a counterexample, making it impossible to
derive the fact that $P(Pxy)(Pyz) \in S$ from $Px(Pyz)\in S$
using the first three laws of Problem 1 alone.

In terms of the usual Aristotelian logic
(i.e. under the isomorphism presented in "Discussion" on page 145),
the following truth table
makes the counterexample explicit:

| $x$ | $y$ | $z$ |$y\to z$|$z\to y$|$(x\to y)\to(y\to z)$|$x\to(y\to z)$|$[x\to(y\to z)]\to[(x\to y)\to(y\to z)]$|
|-----|-----|-----|--------|--------|---------------------|--------------|----------------------------------------|
|  T  |  T  |  T  |   T    |   T    |          T          |       T      |              T                         |
|  T  |  T  |  F  |   F    |   T    |          F          |       F      |              T                         |
|  T  |  F  |  T  |   T    |   F    |          T          |       T      |              T                         |
|  T  |  F  |  F  |   T    |   F    |          T          |       T      |              T                         |
|  F  |  T  |  T  |   T    |   T    |          T          |       T      |              T                         |
|__F__|__T__|__F__| __F__  | __T__  |        __F__        |     __T__    |            __F__                       |
|  F  |  F  |  T  |   T    |   T    |          T          |       T      |              T                         |
|  F  |  F  |  F  |   T    |   T    |          T          |       T      |              T                         |
