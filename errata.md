Introduction to Computational Physical Chemistry
(c) Joshua Schrier and University Science Books
Publisher's Website: http://www.uscibooks.com/schrier.htm
Buy it on Amazon: https://amzn.to/2xMeVbL

# Errata (first printing) — Version: 16 Mar 2020

*Thanks to:*  Robert DiStasio (Cornell), Yang Yang (Lehigh), Peter Atkins (Oxford), Roderick M. Macrae (Marian), and Enrique Peacock-Lopez (Williams) 


## Chapter 1: The Particle in a Box

p. 2 — Sixth line of text, typo, should read “Fr*i*edrich” [Thanks Y. Yang]

p. 10. — Bottom of p.10 (second equation), $\psi$ on LHS should have subscript “$_n$” [Thanks R. DiStasio]

p. 11 — In top equation of Eqn 1.6, $\psi$ on LHS should have subscript “$_n$” [Thanks R. DiStasio]

p. 22 - (Newer versions of Mathematica enforce an ordering on integration and
plotting operations that breaks this code.)  In last code block, 
change `x` to ``xx``.  That is, code should read:

```
Plot[
  {NIntegrate[ Conjugate[equalSuperposition[xx, L, t]]*
    equalSuperposition[xx, L, t], {xx,0,L}]
...etc.
```

Alternatively, one can circumvent this problem by defining the
integral as a separate function, `intX[]`, and then calling it as shown
below:

```
hbar=1; m=1; L=5; (*define mass and length in atomic units*)

(*define the integral to plot*)
intX[L_, t_] := NIntegrate[Conjugate[equalSuperposition[x, L, t]]*
   equalSuperposition[x, L, t], {x, 0, L}] (*function performs integration*)

Plot[
 intX[L, t], {t, 0, 100},
 AxesLabel -> ...etc.
```

## Chapter 2: The Finite Difference Method: Bound States

p. 38 -- first line of code.  Missing "`{`" and "`}`" around first two
arguments in `Table[]` function.  Should read:
```
estate2withcoords = Table[{N[a*j], estate2[[j]]}, {j, 1, nPoints}];
```

p. 39 — To be completely analogous to the earlier code entry, the second code entry should include the complex conjugation function, as shown:
```
 Timing[ Conjugate[estate2].(xcoords*estate2)*a ]
```
(Note that this has no effect on the calculation because all the entries in the eigenvector are real.) [Thanks R. Macrae]

## Chapter 3: The Finite Difference Method: Tunneling

p. 52 — In Eq. 3.6, the term $[E- V_j]$ should be $[V_j - E]$.  [Thanks R. Macrae]

p. 64 — Problem 3-7, units in grid specification are incorrectly specified in terms of the real-space grid spacing, when what is intended is the sampling of kinetic energy points.  Should read:
“sample the transmission as a function of kinetic energy at intervals $\Delta E = 0.001\, E_{h}$… sample at intervals $\Delta E = 0.1\, E_{h}$  

## Chapter 4: Variational Method

p. 70 — Above last section of code.  There are in fact “six parameters”, and not “five parameter” as stated in the text. [Thanks R. Macrae]

p. 72-73 -- The default `NMinimize[]` settings in Mathematica 11.1.1.0 find
a slightly lower minimum.  The outputs for the remainder of this 
subsection read, in order:
```
{0.197401, {a -> -0.0000120652, b -> 22.719, c -> 0.908926, 
  d -> -2.2186, e -> 0.238221, f -> -0.00252193}}

0.00469079

{0.197401, {a -> -0.0000120652, b -> 22.719, c -> 0.908926, 
  d -> -2.2186, e -> 0.238221, f -> -0.00252193}}

{a -> -0.0000120652, b -> 22.719, c -> 0.908926, d -> -2.2186, 
 e -> 0.238221, f -> -0.00252193}

a -> -0.0000120652

-0.0000120652
```

p. 80 — The fifth term in the output for `increasingBasis` should read “0.433845” [Thanks R. Macrae]

p. 85 — The terms on the right hand side of Eq. (4.25) should all have the numerator  $L^(1 + 2*i + 2*j)$.  Alternatively, the right hand side of this equation can  be written more compactly as: $\frac{i j (3 i+3 j+2) L^{2 i+2 j+1}}{(i+j+1) (2 i+j+1) (i+2 j+1) (2 i+2 j+1)}$ [Thanks R. Macrae]

p. 95 — In Problem 4-9 (d), exact value is "−2.903*724375*". 

## Chapter 5: Hartree-Fock Self-Consistent Field

p. 110 -- The second term in the output of evals, is incorrect.  
The first output on this page should read: 
```
{-0.917935, 2.05685}
```

p. 119 — In definition of `twoElecInt[]`, the first `propK[]` function is missing the closing “`]`”.  The function should read:
```
twoElecInt[alpha_,rA_,beta_,rB_,gamma_,rC_,delta_,rD_]:=   
  propK[alpha,rA,beta,rB]*propK[gamma,rC,delta,rD]*
  ...etc.
```
## Chapter 6: Huckel Molecular Orbital Theory

*Not an erratum, but a shameless advertisement:* Check out my [HuckelTheory](https://github.com/jschrier/HuckelTheory) package

## Chapter 7: Quantum Theory of Solids

p.178 — expand name (better Chinese orthography), to: "postdoctoral fellow Lu J*eu& Sham" [Thanks Y. Yang]

p. 181 — In last line of code on this page, the argument should be 100, not 10.  
This last line should read:
```
ringLineComparison[100]} ]
```

p. 189 — Code input at bottom of page is unnecessarily printed twice.

p. 190 — In first line of code output on page should read: `{-3, 3}`

## Chapter 8: Density Functional Theory

p. 202—  Fact check correction:  ”the first Nobel Prize awarded to a Japanese *chemist*” [Thanks Y. Yang]

## Chapter 9: Quantum Monte Carlo

p. 224 — In Eq.(9.5), the second to last term, LHS denominator is missing the r-squared term.  The denominator should read $2 \mu r^2$ (the code on the next page contains the correct expression).[Thanks E. Peacock-Lopez]

## Chapter 14: Molecular Dynamics

p. 367 — The data supplied in the first line of code displays the L=11 case, but should display the L=9 case.  This first line should read:
```
ListPlot[ calcGr[coordList9, 9., 0.01], …etc.
```
## Chapter 15: Kinetics

p. 375 — Missing “`{`“ in last argument of `NDSolve[]`, second line of code on this page.  Line should read:
```
soln1 = NDSolve[ {a'[t] == -k1*a[t], a[0] == 1}, a, {t, 0, 10}][[1]]  
```

## Appendix A: Computer Programming in a Nutshell

p. 409 — Code output lines after the inputs `?x` and `?z` should read: `Global`x` and `Global`z` , respectively. 

p. 426 — In problem A-2, second line delete “2” superscript.  Should read, “and principal quantum number $n$. (Recall: …”

p. 428 — In the first sentence of problem A-15, only one $f(x)$  should be present in the integrand. [Thanks R. Macrae]

## Appendix B: Data Analysis

p. 440 — In data table for Problem B-1, the value of the molar heat capacity at T = 1000K should read *45.98* 

p. 443 — In Problem B-8, part (b), modify inline equation to read $PM/(\rho RT)-1$

## Appendix C: Energy Levels of Non-interacting Molecules

p. 447 - Second to last output on this  page should be changed from "01."  to "0*.*1"

