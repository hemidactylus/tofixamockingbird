# Page 202

<img src="/pictures/correction_blue.svg" width="32px"/>
__Location:__ Chapter 22, additional questions before "Kestrels and infinity"

## Questions (paragraph after Problem 17)

### Nonegocentricity

For several birds, it is suggested to try and prove their nonegocentricity.
In the following, the birds listed in the following are considered:

$$
    \forall \beta \in \{ D, E, F, G, H, L, J, O, Q_1, Q_2, Q_3,
        Q_4, W', C^\star, C^{\star\star}, W^\star, W^{\star\star},
        U \}~~\Rightarrow~~\beta\beta\neq\beta\;.
$$

### Inequality

It is also suggested to prove that any two
distinct birds taken from $\{B,C,W,S,R,T\}$
are not even _similar_ (i.e. they can always be distinguished
by their action on some birds).

Considering the birds in the set are all proper birds of order $\leq 3$,
proving this amounts to proving that

$$
    \forall \beta_1, \beta_2 \in \{B,C,W,S,R,T\},
        \beta_1\neq\beta_2 \Rightarrow \beta_1 xyz \neq \beta_2 xyz\;.
$$

(In an extensional, or _sparse_ forest, this amounts to the statement
that the six birds in the above set are all different).

## Answers

### Nonegocentricity

For each bird $\beta$, the nonegocentricity is proven by first assuming that $\beta\beta=\beta$,
and then by deriving from the assumption some contradiction involving Kestrels and Identity birds
such as $K=KK$, $K=I$. To get to the contradiction, the assumption is applied to three (or more)
variables and then values $\in \{K,I\}$ are assigned to some of them.

#### Dove

It is $Dxyzw=xy(zw)$. Starting from $DD=D$, it is

$$
    Dxyzw=DDxyzw \to xy(zw)v=Dx(yz)wv
        \to xy(zw)v=x(yz)(wv)\;.
$$

With $x=v=K, y=z=I$:

$$
    KI(Iw)K=K(II)(wK) \to IK=II \to K=I\;,
$$

a contradiction (Problem 2).

#### Eagle

It is $Exyzwv=xy(zwv)$. If $EE=E$,

$$
    EExyzwv=Exyzwv \to Ex(yzw)vqr=xy(zwv)qr
        \to x(yzw)(vqr)=xy(zwv)qr\;.
$$

With $x=w=K$ and $y=z=q=r=I$:

$$
    K(IIK)(vII)=KI(IKv)II
        \to IIK=III \to K=I\;,
$$

a contradiction (Problem 2).

#### Finch

It is $Fxyz=zyx$. From $FF=F$,

$$
    FFxyz=Fxyz \to yxFzwv=zyxwv \to yxvwz=zyxwv\;,
$$

then setting $x=y=z=I, w=v=K$:

$$
    IIKKI=IIIKK \to K=KK\;,
$$

another contradiction (Problem 6).

#### Goldfinch

It is $Gxyzw=xw(yz)$. If $GG=G$,

$$
    GGxyzw=Gxyzw \to Gz(xy)wq=xw(yz)q
        \to zq(xyw)=xw(yz)q \;,
$$

then when $x=z=w=K$ and $q=I$:

$$
    KI(KyK)=KK(yK)I \to I=KI\;,
$$

contradicting Problem 1.

#### Hummingbird

It is $Hxyz=xyzy$. Now, $HH=H$ implies

$$
    HHxyz=Hxyz \to Hxyxz=xyzy \to xyxyz=xyzy\;;
$$

setting $x=z=K, y=I$ one finds

$$
    KIKIK=KIKI \to IIK=II \to K=I\;,
$$

which is against Problem 2.

#### Lark

Since $Lxy=x(yy)$, if one had $LL=L$ it would follow that

$$
    LLxy=Lxy \to L(xx)y=x(yy) \to xx(yy)=x(yy)\;,
$$

and then immediately, with $x=K$ and $y=I$,

$$
    KK(II)=K(II) \to K=KI\;,
$$

at odds with Problem 6.

#### Jaybird

It is $Jxyzw=xy(xwz)$. From $JJ=J$:

$$
    \begin{align}
    JJxyzw= & Jxyzw \to
        Jx(Jzy)wq=xy(xwz)q \to
        x(Jzy)(xqw)=xy(xwz)q  \to \\
    \stackrel{x=K}{\longrightarrow} &
        K(Jzy)(kqw)=Ky(Kwz)q \to
        Jzy\alpha\beta=yz\alpha\beta \to
        zy(z\beta\alpha) = yq\alpha\beta\;;
    \end{align}
$$

finally, setting $y=z=K$, $q=\alpha=\beta=I$, one gets

$$
    KK(KII)=KIII \to K=I\,,
$$

i.e. a contradiction of Problem 2.

#### Owl

page 82 of my notes!

#### Quixotic bird (Q1)

#### Quizzical bird (Q2)

#### Quirky bird (Q3)

#### Quacky bird (Q4)

#### Converse warbler

#### Cardinal once removed

#### Cardinale twice removed

#### Warbler once removed

#### Warbler twice removed

#### Turing bird

### Inequality
