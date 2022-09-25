
# Table of Contents

1.  [Interpretation. part 1](#org90c381d)
2.  [Parsing and other friends](#org50094ff)
    1.  [The simplest expressions you can think of](#org5205161)
        1.  [Integer values](#orgb3e01db)
        2.  [Addition](#orgcec154c)
        3.  [Multiplication](#org60eaf14)
    2.  [Representing expressions in a code](#org8a7f43e)
    3.  [The simplest parser you can think of](#orgc41dcf9)
    4.  [What else can we add to the expressions](#org82d82d2)
3.  [Evaluating expressions for fun and profit](#org9ec7b1d)
    1.  [Expressions vs statements](#orgeb23a45)
    2.  [Evaluating integers. As simple as it gets](#org3978f30)
    3.  [Evaluating addition](#orgbe48125)
    4.  [Evaluating multiplication](#orge7a3015)
4.  [Core language, host language and a lot of sugar](#org1aacb00)
    1.  [difference between core, host and sugared](#org6e5fad7)
    2.  [Adding sugar](#org8a4cfe7)
        1.  [Subtraction](#org1edcfc7)
        2.  [Unary minus](#org9ccc37d)
    3.  [Pros and cons of sugaring](#orgc890434)
5.  [Errors and strange things](#orgf2e0a34)
    1.  [adding division](#org28b9501)
    2.  [what should happen if we divide by zero?](#orgb9b3c6f)
6.  [Adding variables to the mix](#org3462741)
    1.  [It&rsquo;s all about environment](#orgb14ff3b)
    2.  [adding environment to our expressions](#orgd8d0983)
    3.  [if you change the environment, expression changes as well.](#orge2cde02)
7.  [Defining variables for fun and profit](#orga1d1939)
    1.  [Where do our variables live?](#org3d23c5f)
    2.  [Mutalbe vs immutable variables](#org90a4177)
    3.  [should variables have a type?](#orgfbad3cc)
8.  [Adding primitive functions to the language](#org890880d)
    1.  [powers, exponents, mods and so on](#orgdfd3464)
    2.  [adding string support to the language](#org7a2f919)
9.  [Evaluating parameters of the funciton. Order matters](#org895f0b3)
    1.  [lazy vs eager evaluation. Pros, cons, implementation](#org3fa1727)
10. [Adding functions to the language.](#org928f04d)
    1.  [function definition syntax](#org2eec27d)
    2.  [function calls syntax](#org7e02dc5)
    3.  [What should happen if you define function within the function?](#orgd9bea88)
    4.  [What should happen if you call function within the function?](#org9a943ed)
    5.  [Few words on recursive calls](#org1da9412)
11. [Adding conditional expressions](#org3b60e95)
    1.  [adding boolean expression to the language](#orgd5c789c)
    2.  [adding IFs to the mix](#orga08bfe4)
    3.  [control flow is not as straighforward as you might think of it](#org2b8f6d4)
12. [Adding lists to the language](#org3259a38)
    1.  [how generic is your generic?](#org260f82e)
    2.  [how generic is your function?](#orgcf64122)
    3.  [adding foreach](#org095a9e0)
    4.  [adding list comprehension](#orgf655e00)
13. [Typing and optimisation. part 2](#org5c24e67)
14. [Something about evaluation speed](#orge4c5f32)
    1.  [environments again](#org5dd3ec1)
    2.  [tail call optimisation](#orgb0d1c72)
    3.  [JZ, JNZ, JMP, Lisp & WebAssembly](#org03ae858)
15. [Adding types to the language](#orgd297e2d)
    1.  [number vs float vs int32 vs int64](#orgc7075fb)
    2.  [function should know about types as well](#org43b610a)
16. [Minimal required type theory](#org285b6ba)
    1.  [Why golang avoided generics for so long](#org4828eb1)
    2.  [How to read typing expressions](#orgfcfe503)
17. [type inferencing  the language. Simple version](#org5b3d5ec)
18. [Generating WebAssembly for fun and profit](#orgea6ec41)
19. [Generating JVM based things for fun and profit](#org179bce7)
20. [type inferencing on steroids](#org4f39856)
    1.  [How haskell, scala and friends work under the hood](#org26012c2)



<a id="org90c381d"></a>

# Interpretation. part 1


<a id="org50094ff"></a>

# Parsing and other friends


<a id="org5205161"></a>

## The simplest expressions you can think of


<a id="orgb3e01db"></a>

### Integer values


<a id="orgcec154c"></a>

### Addition


<a id="org60eaf14"></a>

### Multiplication


<a id="org8a7f43e"></a>

## Representing expressions in a code


<a id="orgc41dcf9"></a>

## The simplest parser you can think of


<a id="org82d82d2"></a>

## What else can we add to the expressions


<a id="org9ec7b1d"></a>

# Evaluating expressions for fun and profit


<a id="orgeb23a45"></a>

## Expressions vs statements


<a id="org3978f30"></a>

## Evaluating integers. As simple as it gets


<a id="orgbe48125"></a>

## Evaluating addition


<a id="orge7a3015"></a>

## Evaluating multiplication


<a id="org1aacb00"></a>

# Core language, host language and a lot of sugar


<a id="org6e5fad7"></a>

## difference between core, host and sugared


<a id="org8a4cfe7"></a>

## Adding sugar


<a id="org1edcfc7"></a>

### Subtraction


<a id="org9ccc37d"></a>

### Unary minus


<a id="orgc890434"></a>

## Pros and cons of sugaring


<a id="orgf2e0a34"></a>

# Errors and strange things


<a id="org28b9501"></a>

## adding division


<a id="orgb9b3c6f"></a>

## what should happen if we divide by zero?


<a id="org3462741"></a>

# Adding variables to the mix


<a id="orgb14ff3b"></a>

## It&rsquo;s all about environment


<a id="orgd8d0983"></a>

## adding environment to our expressions


<a id="orge2cde02"></a>

## if you change the environment, expression changes as well.


<a id="orga1d1939"></a>

# Defining variables for fun and profit


<a id="org3d23c5f"></a>

## Where do our variables live?


<a id="org90a4177"></a>

## Mutalbe vs immutable variables


<a id="orgfbad3cc"></a>

## should variables have a type?


<a id="org890880d"></a>

# Adding primitive functions to the language


<a id="orgdfd3464"></a>

## powers, exponents, mods and so on


<a id="org7a2f919"></a>

## adding string support to the language


<a id="org895f0b3"></a>

# Evaluating parameters of the funciton. Order matters


<a id="org3fa1727"></a>

## lazy vs eager evaluation. Pros, cons, implementation


<a id="org928f04d"></a>

# Adding functions to the language.


<a id="org2eec27d"></a>

## function definition syntax


<a id="org7e02dc5"></a>

## function calls syntax


<a id="orgd9bea88"></a>

## What should happen if you define function within the function?


<a id="org9a943ed"></a>

## What should happen if you call function within the function?


<a id="org1da9412"></a>

## Few words on recursive calls


<a id="org3b60e95"></a>

# Adding conditional expressions


<a id="orgd5c789c"></a>

## adding boolean expression to the language


<a id="orga08bfe4"></a>

## adding IFs to the mix


<a id="org2b8f6d4"></a>

## control flow is not as straighforward as you might think of it


<a id="org3259a38"></a>

# Adding lists to the language


<a id="org260f82e"></a>

## how generic is your generic?


<a id="orgcf64122"></a>

## how generic is your function?


<a id="org095a9e0"></a>

## adding foreach


<a id="orgf655e00"></a>

## adding list comprehension


<a id="org5c24e67"></a>

# Typing and optimisation. part 2


<a id="orge4c5f32"></a>

# Something about evaluation speed


<a id="org5dd3ec1"></a>

## environments again


<a id="orgb0d1c72"></a>

## tail call optimisation


<a id="org03ae858"></a>

## JZ, JNZ, JMP, Lisp & WebAssembly


<a id="orgd297e2d"></a>

# Adding types to the language


<a id="orgc7075fb"></a>

## number vs float vs int32 vs int64


<a id="org43b610a"></a>

## function should know about types as well


<a id="org285b6ba"></a>

# Minimal required type theory


<a id="org4828eb1"></a>

## Why golang avoided generics for so long


<a id="orgfcfe503"></a>

## How to read typing expressions


<a id="org5b3d5ec"></a>

# type inferencing  the language. Simple version


<a id="orgea6ec41"></a>

# Generating WebAssembly for fun and profit


<a id="org179bce7"></a>

# Generating JVM based things for fun and profit


<a id="org4f39856"></a>

# type inferencing on steroids


<a id="org26012c2"></a>

## How haskell, scala and friends work under the hood

