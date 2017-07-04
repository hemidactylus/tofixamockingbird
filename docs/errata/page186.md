# Page 186

<img src="../../pictures/correction_blue.svg" width="32px"/>
__Location:__ Chapter 19, final Exercise

## Exercise (after the Appendix)

In terms of $B$, $C$, $S$, and $I$, find a combinator $A$
satisfying the condition $Axyz=xz(zy)$. The problem should be divided
into three parts: ...

## Solution

$$
    A = C(BBS)(CI)
$$

## Short explanation

As suggested by the text, and according to the
algorithm given in the Appendix, the solution proceeds
in three steps:

First, a distinguished $z$-eliminate $A_1$ of the expression
$X=xz(zy)$ must be found. By Rule 3a, this in turn requires to find:

- a distinguished $z$-eliminate of $xz$, which is $x$ (Rule 2);
- a distinguished $z$-eliminate of $zy$, which by Rule 3c is $CIy$.

Hence it is $A_1=Sx(CIy)$.

The second step consists of finding a distinguished $y$-eliminate $A_2$ of $A_1$:
by Rule 3b (and Rule 2), one has immediately

$$
    A_2 = B(Sx)(CI)\;.
$$

Finally, one needs a distinguished $x$-eliminate $A$ of $A_2$: again according to
Rule 3c, to find it one must have a distinguished $x$-eliminate of $B(Sx)$.
This latter term is $BBS$ (applying Rule 3b).

Application of Rule 3c then yields:

$$
    A = C(BBS)(CI)\;,
$$

as can be verified by feeding the equation $Axyz=xz(zy)$
to the [combinator-finder program](page178.md#actual-code)
(with the `BCSI` command-line option)
as well as by explicit computation:

$$
\begin{align} 
    Axyz =~& C(BBS)(CI)xyz=BBSx(CI)yz=B(Sx)(CI)yz=\\
         =~& Sx(CIy)z=xz(CIyz)=xz(Izy)=xz(zy)\;.
\end{align}
$$
