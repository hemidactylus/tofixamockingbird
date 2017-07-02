# Pages 178, 185

<img src="/pictures/correction_blue.svg" width="32px"/>
__Location:__ Chapter 18, very last suggestion in the chapter; and Chapter 19, Appendix

## Suggestion given in the book

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

_Note_: it was not very common to possess a __home computer__ back in 1982.

## The program

The code given here performs the required task. In particular,
it asks for the combinator equation to solve, such as `Axyz=z(xx(Ky))`,
and returns the expression for $A$ in terms of the allowed primitive birds
(e.g. `A=(S(K(S(K(SI))))(S(K(S(KK)))(S(S(KS)(S(KK)(SII)))(KK))))`
for the ${S,K,I}$ primitive bird set).

Through command-line parameters either set of primitive birds can be specified,
and a debug mode is available. For more information (including the full code) see below.

## Short explanation

The code is composed of two parts: an input validator/parser and
the part that actually applies the algorithm (i.e. "the Secret" or
its counterpart for Chapter 19).

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

```
#!/usr/bin/env python3
'''
    combinatorSolver.py : a solver for combinators,
    either based on the SKI- or the BCSI-basis,
    that outputs the solution A to an expression
    of type
        Axyz...=X
    where:
        - "A" has to be literally "A"
        - variables are lowercase letters
        - X is an expression made of (properly parenthesized)
            combinators in the basis and variables.
    Depending on the basis chosen, X may be subject
    to additional constraints. See below for the
    (very limited) command-line options.
    
    This programs solves the coding exercises of
    "To Mock a Mockingbird", chapters 18 & 19.
    
    [
        Written by hemydactylus,
        https://github.com/hemidactylus.
        The general idea for parsers comes from:
            "Programming in Haskell",
            Graham Hutton,
            Cambridge University Press,
            (Chapter 8, 'Functional parsers')
    ]
'''

import sys

# variables are all lowercase letter symbols
variables=list(map(chr,range(ord('a'),ord('z')+1)))

'''
    PARSERS. Each of those returns a pair (a 2-tuple)
        (item,unconsumed part).
    If there are some troubles,
        (None,unconsumed part)
    is returned.
    
    Note there is no explicit parser combinator,
    since the job of parsing here is, all-in-all,
    rather simple.
    
    The parsed expression has single birds (variables, primitive-birds)
    represented as (single-char) items in a list, each nesting
    of parentheses being mapped to a nesting of lists.
    Thus, for instance, expression
        "x(y(yx))"
    is parsed to:
        ['x', ['y', ['y', 'x']]]
    (enable debugging with the 'D' option to see this representation)
    
    All parser here inherit and pass forward an argument
    specifying the mode of operation of the exercise,
    i.e. SKI or BCSI.
'''

def parseFromList(inStr,charList):
    '''
        A general parser that extract a single char
        from the input string, if the former falls
        within a list of allowed ones.
        
        It is used later, curried in the second argument,
        to generate a parser for variables.
    '''
    if inStr:
        fChar=inStr[0]
        if fChar in charList:
            return fChar,inStr[1:]
        else:
            return None,inStr
    else:
        return None,inStr


def parseBracket(inStr,mode):
    '''
        A parser for "(expression)" type of structures.
    '''
    if inStr and inStr[0]=='(':
        inExpr,rst=parseTerm(inStr[1:],mode)
        if inExpr and rst[0]==')':
            return inExpr,rst[1:]
        else:
            return None,inStr
    else:
        return None,inStr


def parseFactor(inStr,mode):
    '''
        A parser for a single factor of some kind:
        either a bracket, a var or a (primitive-)bird.
    '''
    parseBird=lambda inStr,mode: parseFromList(inStr,modesMap[mode])
    parseVariable=lambda inStr,mode: parseFromList(inStr,variables)
    factorOptions=[parseVariable,parseBird,parseBracket]
    some=False
    for parserOption in factorOptions:
        subterm,subrest=parserOption(inStr,mode)
        if subterm:
            some=True
            return subterm,subrest
    if not some:
        return None,inStr
    
def parseTerm(inStr,mode):
    '''
        A parser for a full expression, which packs the result
        into a list, thereby building the nested-list structure
        of the parsed expression.
    '''
    terms=[]
    rst=inStr
    while True:
        subfac,subrest=parseFactor(rst,mode)
        if subfac:
            terms.append(subfac)
            rst=subrest
        else:
            break
    if terms:
        return terms,rst
    else:
        return None,rst
# End of the parsers part.

'''
    ELIMINATORS. This part implements the alpha-eliminate
    and distinguished-alpha-eliminate calculation according
    to the recursive algorithms presented in Chapters 18 and 19.
    They are collected in a single entry-point function
    as seen in the 'alphaEliminate' function.
    
    Again, the mode of operation is passed along.
'''

def unwrap(uexp):
    '''
        this removes unnecessary parentheses from a structured expression.
    '''
    if isinstance(uexp,list) and len(uexp)==1:
        return unwrap(uexp[0])
    else:
        return uexp

def alphaEliminate(expr,var,mode):
    return eliminatorMap[mode](expr,var,mode)
    
def SKIalphaEliminate(expr,var,mode):
    '''
        returns a 'var'-eliminate of expression 'expr',
        by trying to apply principles 1-4 of Chapter 18,
        in that order.
        
        'mode' is passed just to keep the same calling pattern,
        but at this point is ignored.
    '''
    # de-normalise 1-item lists to simple letters
    if isinstance(expr,list) and len(expr)==1:
        expr=unwrap(expr)
    # P1
    if not isinstance(expr,list) and expr==var:
        return 'I'
    # P2
    if var not in collectVariables(expr):
        return ['K',expr]
    # P3
    if isinstance(expr,list):
        if var not in collectVariables(expr[:-1]) and unwrap(expr[-1])==var:
            return unwrap(expr[:-1])
    # P4 if all else fails
    return ['S',alphaEliminate(expr[:-1],var,mode),alphaEliminate(unwrap(expr[-1]),var,mode)]

def distinguishedAlphaEliminate(expr,var,mode):
    '''
        returns a distinguished 'var'-eliminate of expression 'expr',
        by applying the principles at the end of Chapter 19

        'mode' is passed just to keep the same calling pattern,
        but at this point is ignored.
    '''
    # raise an error if var does not occur at all in expr:
    if var not in collectVariables(expr):
        raise ValueError(('Variable "%s" absent in expression:'+ \
                         ' cannot find distinguished eliminate') % var)
    # de-normalise 1-item lists to simple letters
    if isinstance(expr,list) and len(expr)==1:
        expr=unwrap(expr)
    # R1
    if not isinstance(expr,list) and expr==var:
        return 'I'
    # R2
    if var not in collectVariables(expr[:-1]) and expr[-1]==var:
        return unwrap(expr[:-1])
    # R3, the recursive one. expr must be (...X...)Y
    exprY=expr[-1]
    exprX=expr[:-1]
    # R3a
    if var in collectVariables(exprX) and var in collectVariables(exprY):
        return [
            'S',
            unwrap(distinguishedAlphaEliminate(exprX,var,mode)),
            unwrap(distinguishedAlphaEliminate(exprY,var,mode)),
        ]
    # R3b
    elif var not in collectVariables(exprX) and var in collectVariables(exprY):
        return [
            'B',
            unwrap(exprX),
            unwrap(distinguishedAlphaEliminate(exprY,var,mode)),
        ]
    # R3c
    elif var in collectVariables(exprX) and var not in collectVariables(exprY):
        return [
            'C',
            unwrap(distinguishedAlphaEliminate(exprX,var,mode)),
            unwrap(exprY),
        ]
    else:
        raise ValueError('Unclassified case found with var "%s" and expr=%s' % (var,expr))

# various utilities employed in calculating eliminates    
def collectVariables(twig):
    '''
        collection, as a set, of all variables
        encountered traversing the
        provided tree. Depth-first.
    '''
    varSet=set()
    for elem in twig:
        if isinstance(elem,list):
            varSet.update(collectVariables(elem))
        else:
            varSet.add(elem)
    return varSet & set(variables)
    
def nestedMultilinePrintExpr(e,lvl=0):
    '''
        Debugging tool, not used in the final code.
        Returns None!
        A pretty print of any expression in a hierarchical fashion, e.g.
            x(y(xKx)x(xx))
        becomes
            x
             y
              x
              K
              x
             x
              x
              x
    '''
    if isinstance(e,list):
        for itm in e:
            nestedMultilinePrintExpr(itm,lvl+1)
    else:
        print('%s%s' % (' '*lvl,e))

def nicePrint(expr):
    '''
        a nice printer for expression, which restores the single-line
        parenthesized form.
    '''
    uexp=unwrap(expr)
    if isinstance(uexp,list):
        return '(%s)' % ''.join(map(nicePrint,uexp))
    else:
        return uexp

# SETTINGS
'''
    For the modes of operation, a dictionary is formed for each of:
        - the allowed primitive birds
        - the exact *-eliminator calculation function
        - the example to show in the console print
'''
modesMap={
    'SKI': 'SKI',
    'BCSI': 'BCSI',
}
eliminatorMap={
    'SKI': SKIalphaEliminate,
    'BCSI': distinguishedAlphaEliminate,
}
exampleMap={
    'SKI': 'Axy=xy(Sx(Ky))',
    'BCSI': 'Axyz=xz(zy)',
}

def main():
    '''
        The core of the program, which handles interaction with
        the user, performs the calculation and prints the result.
    '''
    # command-line options
    params=sys.argv[1:]
    debugMode=False
    mode='SKI'
    for p in params:
        if p in modesMap:
            mode=p
        elif p=='D':
            debugMode=True
        else:
            print('# Unknown command-line option "%s", ignoring it' % p)
    # messages to the user
    print('*'*50)
    print('**              Combinator Solver               **')
    print('** (command-line option: SKI (default) or BCSI) **')
    print('** (               Also: D for debug          ) **')
    print('*'*50)
    print('>> Enter the expression to solve [e.g. "%s"]' % exampleMap[mode])
    print('      ',end='')
    sys.stdout.flush()
    fullExpr=sys.stdin.readline().strip()
    # retrieval and parsing of the input from the user
    parts=[part.strip() for part in fullExpr.split('=')]
    if len(parts)!=2:
        print('# Please provide an expression with exactly one equal sign')
        return
    else:
        definition,rawExpression=parts
    # check for expression X validity
    parsedExpr,rest=parseTerm(rawExpression,mode)
    if parsedExpr is None or rest!='':
        print('# Syntax error in expression X')
        return
    # is the definition a proper definition?
    if len(definition)==0 or definition[0]!='A':
        print('# Definition must start with "A"')
        return
    varlist=list(definition[1:])
    if len(varlist)==0 or any(map(lambda l: l not in variables, varlist)):
        print('# Definition must contain only one or more a-z variables')
        return
    if len(varlist)!=len(set(varlist)):
        print('# Duplicate variables in definition not allowed')
        return
    # Everything seems OK
    # Proceed with the solution
    if debugMode:
        print('    --> List of variables:\n      %s' % varlist)
        print('    --> Expression X:\n      %s' % parsedExpr)
    # iteratively, eliminate after eliminate, construct the full solution
    thisExpr=parsedExpr
    for alpha in varlist[::-1]:
        if debugMode:
            print('       --> %s-eliminate of %s: ' % (alpha,thisExpr))
        thisExpr=alphaEliminate(thisExpr,alpha,mode)
        if debugMode:
            print('         %s' % thisExpr)
    print('>> Final result:\n      A=%s' % nicePrint(thisExpr))

if __name__=='__main__':
    main()
```
## Credits

I wrote the code from scratch. However, the organisation of the parser
system, used here to reduce the given expression (a string) into a structured
object made of nested lists, is a simplified adaptation of concepts taken from this
useful [book on Haskell programming](http://www.cs.nott.ac.uk/~pszgmh/pih.html):

```text
"Programming in Haskell",
Graham Hutton,
Cambridge University Press,
(Chapter 8, 'Functional parsers')
```
