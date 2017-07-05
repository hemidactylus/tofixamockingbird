# Page 202

<img src="../../pictures/correction_blue.svg" style="width: 32px; height: 32px;"/>
__Location:__ Chapter 22, additional questions after Problem 17 and before "Kestrels and infinity"

## Questions

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

(In an extensional, or _sparse_, forest, this amounts to the statement
that the six birds in the above set are all different).

## Answers

### Nonegocentricity

For each bird $\beta$, the nonegocentricity is proven by first assuming that $\beta\beta=\beta$,
and then by deriving from the assumption some contradiction involving Kestrels and Identity birds
such as $K=KK$, $K=I$. To get to the contradiction, the assumption is applied to two, three or more
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

It is $Oxy=y(xy)$. The assumption $OO=O$ implies:

$$
    \begin{align}
    OOxy=Oxy \to & x(Ox)y=y(xy) \stackrel{x=y=K}{\longrightarrow}
        K(OK)K=K(KK) \to OKz=K(KK)z \to \\
    \stackrel{z=I}{\longrightarrow} &
            I(KI)=KK \to K=I\;,
    \end{align}
$$

(where the left cancellation law for Kestrels has been used)
which goes against Problem 2.

#### Quixotic bird

Since $Q_1xyz=x(zy)$, from $Q_1Q_1=Q_1$ one gets:

$$
    Q_1xyz=Q_1Q_1xyz \to x(zy)w=Q_1(yx)zw \to x(zy)w=yx(wz)\;,
$$

i.e., setting $x=y=z=K$,

$$
    K(KK)w=KK(wK) \to KK=K\;,
$$

thereby contradicting Problem 6.

#### Quizzical bird

It is $Q_2xyz=y(zx)$, hence from $Q_2Q_2=Q_2$ one finds:

$$
    Q_2Q_2xyz=Q_2xyz \to x(yQ_2)z=y(zx)\;,
$$

which choosing $x=K$ and $y=z=I$ becomes

$$
    K(IQ_2)I=I(IK) \to Q_2=K\;.
$$

Applying the last identity to $a,b,c$ and then specialising to $a=c=I, b=K$ one finds:

$$
    Q_2abc=Kabc \to b(ca)=ac \to K(II)=II \to KI=I\;,
$$

a contradiction of Problem 1.

#### Quirky bird

Since $Q_3xyz=z(xy)$, in case of egocentricity one would have

$$
    Q_3Q_3xyz=Q_3xyz \to y(Q_3x)z=z(xy)\;,
$$

i.e., when $x=I$ and $y=z=K$,

$$
    K(Q_3I)K=K(IK) \to Q_3Iab=KKab \to ba=Kb\;;
$$

finally, the choice $a=b=I$ leads to $I=KI$, again contradicting Problem 1.

#### Quacky bird

From the definition $Q_4xyz=z(yx)$, $Q_4Q_4=Q_4$ implies

$$
    \begin{align}
    Q_4Q_4xyz=Q_4xyz \to & y(xQ_4)z=z(yx) \stackrel{y=K}{\longrightarrow}
        K(xQ_4)z=z(Kx) \stackrel{x=I}{\longrightarrow} Q_4=z(KI) \\
    \stackrel{z=K}{\longrightarrow} & Q_4abc=K(KI)abc \to
        c(ba)=KIbc \;,
    \end{align}
$$

which choosing $a=b=I, c=K$ yields the statement $K=KI$, incompatible
with Problem 6.

#### Converse warbler

From $W'xyz=yxx$, the assumption $W'W'=W'$ leads to

$$
    \begin{align}
    W'W'xyz=W'xyz \to & xW'W'y=yxx \stackrel{x=I, y=K}{\longrightarrow}
        KW'W' = I \\
    \to & W'ab=Iab \to baa=ab \stackrel{a=I, b=K}{\longrightarrow} I=K\;,
    \end{align}
$$

a contradiction of Problem 2.

#### Cardinal once removed

Since $C^\star xyzw=xywz$, if the bird were egocentric it would be:

$$
    C^\star C^\star xyzw = C^\star xyzw \to C^\star xzyw=xywz
        \to xzwy=xywz\;,
$$

then, choosing $x=y=w=I$ and $z=K$ one gets $IKII=IIIK$, i.e.
$I=K$, incompatible wiith Problem 2.

#### Cardinal twice removed

It is $C^{\star\star} xyzwv=xyzvw$; assuming egocentricity implies

$$
    C^{\star\star} C^{\star\star} xyzwv=C^{\star\star} xyzwv
        \to C^{\star\star} xywzv=xyzvw
        \to xywvz=xyzvw\;,
$$

which choosing $x=y=z=v=I$ and $w=K$ yields

$$
    IIKII=IIIIK \to I=K\;,
$$

contradicting Problem 2.

#### Warbler once removed

It is $W^\star xyz=xyzz$; now, if $W^\star W^\star =W^\star$ one would have

$$
    W^\star W^\star xyz=W^\star xyz \to W^\star xyyz=xyzz \to
        xyyyz=xyzz\;;
$$

by setting $x=z=I$ and $y=K$ this is seen to lead to

$$
    IKKKI=IKII \to KI=I\;,
$$

a contradiction of Problem 1.

#### Warbler twice removed

Since $W^{\star\star} xyzw=xyzww$, egocentricity would imply:

$$
    W^{\star\star} W^{\star\star} xyzw=W^{\star\star} xyzw \to W^{\star\star} xyzzw=xyzww
        \to xyzzzw=xyzww\;,
$$

which choosing $x=y=z=I$ and $w=K$ yields

$$
    IIIIIK=IIIKK \to K=KK\;,
$$

a statement at odds with Problem 6.

#### Turing bird

Since $Uxy=y(xxy)$, assuming $UU=U$ would lead to:

$$
    UUxy=Uxy \to x(UUx)y=y(xxy) \stackrel{x=K}{\longrightarrow}
        K(UUK)y=y(KKy) \to UUK=yK\;;
$$

by taking $y=I$ and $y=K$ one gets respectively $UUK=K$ and $UUK=KK$,
hence $K=KK$ in contradiction with Problem 6.

_Note: similar proofs would hold for other birds, but see the
related [open problems](page202b.md) for less obvious cases._

### Inequality

For each pair $(\beta_1,\beta_2)$ of birds, the fact that they
are distinct will be proven according
to the following procedure:

- assumption of identity $\beta_1=\beta_2$;
- application of their identity to three generic birds: $\beta_1 xyz=\beta_2 xyz$;
- assignment of particular values $\in \{K,I\}$ to the birds $x,y,z$;
- a paradox, i.e. a contradiction of some of the results found throughout the Chapter, will be found,
    which invalidates the original identity assumption.

The action of the birds considered on the birds $xyz$ is the following:

$$
    \begin{align}
        Bxyz = & \; x(yz) \;, \\
        Cxyz = & \; xzy \;, \\
        Wxyz = & \; xyyz\;, \\
        Sxyz = & \; xz(yz)\;, \\
        Rxyz = & \; yzx\;, \\
        Txyz = & \; yxz\;. \\
    \end{align}
$$

#### Cardinal & Bluebird

If $Cxyz=Bxyz$, then $xzy=x(yz)$; hence, with $x=y=I$ and $z=K$, one has:

$$
    IKI=I(IK) \to KI=K\;,
$$

contradicting Problem 6.

_Note_: other choices are also possible for
most of these proofs. In this case, for instance,
the assignment $x=z=K$ and $y=I$ would lead to
$KKI=K(IK) \to K=KK$, against a contradiction of Problem 6.

#### Warbler and Bluebird

$$
    Wxyz=Bxyz \to xyyz=x(yz)\;.
$$

Taking $x=I, y=z=K$:

$$
    IKKK=I(KK) \to K=KK\;,
$$

against Problem 6.

#### Starling and Bluebird

$$
    Sxyz=Bxyz \stackrel{x=z=K, y=I}{\longrightarrow} KK(IK)=K(IK) \to K=KK\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Robin and Bluebird

$$
    Rxyz=Bxyz \stackrel{x=I, y=z=K}{\longrightarrow} KKI=I(KK) \to K=KK\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Thrush and Bluebird

$$
    Txyz=Bxyz \stackrel{x=y=z=K}{\longrightarrow} KKK=K(KK) \to K_1=K_3\;\nLeftrightarrow\mbox{Prob. 19}
$$

#### Warbler and Cardinal

$$
    Wxyz=Cxyz \stackrel{x=y=z=K}{\longrightarrow} KKKK=KKK \to K=KK\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Starling and Cardinal

$$
    Sxyz=Cxyz \stackrel{x=z=I, y=K}{\longrightarrow} II(KI)=IIK \to KI=K\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Robin and Cardinal

$$
    Rxyz=Cxyz \stackrel{x=z=K, y=K}{\longrightarrow} IKK=KKI \to KK=K\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Thrush and Cardinal

$$
    Txyz=Cxyz \stackrel{x=y=I, z=K}{\longrightarrow} IIK=IKI \to K=KI\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Starling and Warbler

$$
    Sxyz=Wxyz \stackrel{x=y=z=K}{\longrightarrow} KK(KK)=KKKK \to K=KK\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Robin and Warbler

$$
    Rxyz=Wxyz \stackrel{x=y=I, z=K}{\longrightarrow} IKI=IIIK \to KI=K\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Thrush and Warbler

$$
    Txyz=Wxyz \stackrel{x=z=K, y=I}{\longrightarrow} IKK=KIIK \to KK=K\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Robin and Starling

$$
    Rxyz=Sxyz \stackrel{x=K, y=z=I}{\longrightarrow} IIK=KI(II) \to K=I\;\nLeftrightarrow\mbox{Prob. 2}
$$

#### Thrush and Starling

$$
    Txyz=Sxyz \stackrel{x=K, y=z=I}{\longrightarrow} IKI=KI(II) \to KI=I\;\nLeftrightarrow\mbox{Prob. 6}
$$

#### Thrush and Robin

$$
    Txyz=Rxyz \stackrel{x=y=I, z=K}{\longrightarrow} IIK=IKI \to K=KI\;\nLeftrightarrow\mbox{Prob. 6}
$$
