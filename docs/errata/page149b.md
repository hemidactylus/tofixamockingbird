# Page 149

<img src="../../pictures/correction_blue.svg" width="32px"/>
__Location:__ Chapter 14, bonus exercises 1, 2 and 3

_Note_: part (d) of Exercise 1 cannot in fact be proven and has to be [removed
from the exercise](page149a.md).

## Exercise solutions

_Note_: in the following, the fact that bird $x$ sings is symbolised by
$x\in S$, with $S$ the set of all singing birds.

### Exercise 1

Assuming the first three laws of Professor Byrd, one can proceed as follows:

(a) Either $x\in S$, in which case by Law 1 $Pxx\in S$, or
$x \notin S$, so that by Law 2 $Pxx \in S$.

(b) Assume $Py(Pyx) \in S$: them either $y\in S$, in which case
by Law 3 $Pyx\in S$, or $y \notin S$, so that by Law 2
$Pyx\in S$.

(c) Starting from the facts that $Pxy\in S$ and $Pyz \in S$,
two cases are possible: (i) $x\in S$, so that
by Law 3 $y \in S$, which together with the second assumption leads
by Law 3 to $z \in S$ and then by Law 1 to
$Pxz\in S$; or (ii) $x\notin S$, which immediately by Law 2 implies
that, again, $Pxz \in S$.

(e) Given that $Px(Pyz)\in S$, either (a) $x \in S$ or (b) $x \notin S$.
In the first case, by Law 3 one has
$Pyz\in S$: now, either (a1) $y\in S$, in which case by Law 3 again it is
$z \in S$, hence by Law 1 $Pxz\in S$
and subsequently $Py(Pxz)\in S$, or (a2) $y \notin S$, whereby immediately
$Py(Pxz)\in S$. In case (b) above, instead, from $x \notin S$ one deduces
$Pxz \in S$ by Law 2, hence directly through Law 1 the conclusion
$Py(Pxz)\in S$ can be reached.

### Exercise 2

Adopting a notation in which a bird $x$ is _lively_ if and only if
$x \in \mathcal{L}$, the three Laws given are stated as follows:

$$
    \begin{align}
        \mbox{(a)}~& Px(Pxy)\in\mathcal{L} \Rightarrow & Pxy \in \mathcal{L}~,~\forall x,y\;, \\
        \mbox{(b)}~& x\in\mathcal{L}, Pxy\in\mathcal{L} \Rightarrow & y \in \mathcal{L} ~,~\forall x,y\;, \\
        \mbox{(c)}~& \forall x,\exists y ~/~ & Py(Pyx)\in\mathcal{L} ~\wedge~ P(Pyx)y\in\mathcal{L}\;.
    \end{align}
$$

To prove that all birds are lively, one considers a generic bird $x$. By Law (c),
$\exists y$ such that (c1) $Py(Pyx)\in\mathcal{L}$ and (c2) $P(Pyx)y\in\mathcal{L}$.
By Law (a), from (c1) one finds that $Pyx\in\mathcal{L}$, which together with (c2)
imply, by Law (b), that $y\in\mathcal{L}$. The latter two statements, in turn, again
according to Law (b), lead to $x \in \mathcal{L}$.

### Exercise 3

The goal is to prove that Laws (a)-(c) given in the previous Exercise can
be derived from Laws 1-4 of Problem 1, under the identification
$\mathcal{L} \equiv S$, which concludes the reasoning.

To prove Law (a), first recall that if $Px(Pxy)\in\mathcal{L}$,
then $Px(Pxy)\in S$. Then, either $x\in S$ or $s \notin S$. In
the first case, by Law 3 one finds that $Pxy\in S$; in the second
case, immediately by Law 2 the fact that $Pxy\in S$ follows.
The statement can be expressed equivalently as $Pxy\in\mathcal{L}$.

Law (b) is a simple reformulation of Law 3 and requires no proof.

Law (c) can be proven as follows: first, by Law 4, $\forall x, \exists y$ such that
$y\in S \Leftrightarrow Pyx \in S$. Now two lines of reasoning are needed, one for
each of the two statements asserted by Law (c).

It can be that $y\in S$ or $y\notin S$. In the first case, one has that
$Pyx\in S$ by Law 4 and then that $Py(Pyx)\in S$ by Law 1. In the second case,
the first desired statement $Py(Pyx)\in S$ follows directly by Law 2; finally,
it can be stated as $Py(Pyx)\in \mathcal{L}$.

Again, consider the cases $y\in S$ and $y\notin S$. In the former case,
Law 1 yields directly $P(Pyx)y \in S$, while in the latter
Law 4 gives $Pyx\notin S$, hence by Law 2 $P(Pyx)y \in S$. Again, the
statement $P(Pyx)y \in \mathcal{L}$ is equivalent to what has just been proved.
