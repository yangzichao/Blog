# Homework2 Zichao Yang

## p1

The ratio should be roughly around 10/3. So those orange nuclei would have a rotor spectrum.

![image-20190129222338382](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190129222338382.png)

## p2

80keV and 800keV would be two energy scales. There is a separation of scales.

## p3

```Gnuplot
gnuplot> f(x) = A*x*(x+1)
gnuplot> fit f(x) 'Dy162.txt' using 1:2 via A
iter      chisq       delta/lim  lambda   A            
   0 3.1285627000e+07   0.00e+00  1.67e+02    1.000000e+00
   1 3.1062295097e+05  -9.97e+06  1.67e+01    1.062090e+01
   2 5.2498174836e+04  -4.92e+05  1.67e+00    1.158203e+01
   3 5.2497917227e+04  -4.91e-01  1.67e-01    1.158299e+01
iter      chisq       delta/lim  lambda   A            

After 3 iterations the fit converged.
final sum of squares of residuals : 52497.9
rel. change during last iteration : -4.90704e-06

degrees of freedom    (FIT_NDF)                        : 9
rms of residuals      (FIT_STDFIT) = sqrt(WSSR/ndf)    : 76.3747
variance of residuals (reduced chisquare) = WSSR/ndf   : 5833.1

Final set of parameters            Asymptotic Standard Error
=======================            ==========================
A               = 11.583           +/- 0.1446       (1.249%)
```

Global fit would give a result of A = 11.583. 

![image-20190129235834939](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190129235834939.png)

EFT would only use the two lowest state since it is low energy theory. The energy shall not beyond the breakdown energy scale.

```octave
octave:3> 80.7/6
ans =  13.450
```

In EFT, we should get A = 13.450. 

```
gnuplot> g(x) = 13.45*x*(x+1)
gnuplot> plot 'Dy162.txt', g(x)
```

![image-20190130001027771](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190130001027771.png)

## p4

```
Final set of parameters            Asymptotic Standard Error
=======================            ==========================
A               = 13.0648          +/- 0.05021      (0.3843%)
B               = -0.00551188      +/- 0.0001793    (3.253%)

```

Fitting results shows that A = 13.0648, which is $C_0$. B = -0.00551188, which is $\frac{C_2}{C_0^4}$, and it is the expansion coefficient of higher order.

The minus sign comes from the Legendre transform.

The theory breaks down at the scale of 0.8MeV.

![image-20190130004744734](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190130004744734.png)

## p5

###spherical  

I will choose $R = \sqrt[3]{A} R_0$ and $R_0 = 1.25 fm, m_N = 931.5 MeV$

Thus the moment of inertia is $\Theta = \frac{2}{5} A m_N R^2 = 0.4*162*931.5MeV *46.4334 fm^2 \simeq 71.98 MeV^{-1}$ 

$\frac{1}{2\Theta} = \frac{1}{143.96} MeV = 6.94637 keV$

While from **p3**, we know that $A\simeq 13$ 

###elliptical

If we change our assumption from spherical to elliptical nuclei, we would keep the mass to be the same. This means that we should have $\rho V = constant$ and $R^3 = a^2 b​$ 

Now we look at the expression, we should compare these two expression

$spherical \propto 2R^2​$, $elliptical \propto (a^2 + b^2) = (R^3/b + b^2)​$ 

Assume $b = xR$, we get $elliptical \propto (1/x + x^2)R^2$ 

Thus we have $d(1/x + x^2) = (-1/x^2 + 2x) dx = 0$ 

We get that $x \simeq 0.8R$ to get the minimum moment of inertia. And it is $(1/0.8 + 0.64)R^2 = 1.89 R^2 < 2R^2$

But this assumption does not change too much of the moment of inertia.

### assumption

We shall not assume that the mass is distributed homogeously. We should consider that most of the mass is distributed near the center but still in the shape of American football. So that we could decrease the moment of inertia and keep the symmetry. 

##p6

![image-20190130121918130](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190130121918130.png)

Band 2 has an $A\simeq 12.357$ , it is close to the ground state band.

## p7

That is because excited state would have larger radius/principle axis.



## p8

![image-20190130013225031](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190130013225031.png)

![image-20190130013336993](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190130013336993.png)



Best rigid rotors is $^{240}_{92} U_{148}$，whose $E_{4+}/E_{2+}$value is closer to 10/3 than any other nuclei.

## p9

$ ^{10}Be$ ,$^{12}C$, $^{34}Mg$, are closed to rigid rotors.

$^8Be$, $^{24}Mg$, $^{38}Mg$, are also deformed.

## p10

We need to simply calculate the low energy levels. 

$^{163}Dy$ : $A \simeq 10.456​$

$^{161}Dy​$ : $A \simeq 6.275​$

$^{161}Tb$ : $A \simeq 11.260 $

$^{163}Ho$ : $A \simeq 11.112 $

## p11

```
1-	1275.8
2-	1863.
3-	1210.1
4-	1862.7
5-	1485.7
```

This should be the Yrast Line.

## p12

I searched table, maybe the value is not correct. But what I've got is that 

$2+ \rightarrow 0+: 5.23​$, $ \frac{4+\rightarrow2+}{2+\rightarrow0+} = 1.42​$

Clebsch-Gordon: $(C^{20}_{4020})^2 = 0.286225$, $(C^{00}_{2020})^2 = 0.19981$ 

The ratio of Clebsch Gordon coeffiecients is $1.432$, so we could say that $B(E2;i\rightarrow f) \propto (C^{I_f0}_{I_i020})^2  $

## p13

###$^{154}$Gd

![img](/Users/yangzichao/Library/Application Support/typora-user-images/image-20190201172240949.png)

We get $A = 20.5167$ So it has a pretty small moment of inertia

$2+ \rightarrow 0+: 3.87$, $ \frac{4+\rightarrow2+}{2+\rightarrow0+} =1.56​$

$^{154}$Gd does not have a very good separation of scales.

## p14

There are some empty orbits for those nucleons near the surface to go. Thus those nuclei would have the degrees of freedoms of quadrupole oscillations, which dominatly induced the deformation.

 ## p15

This is hard to say. Maybe it is because to have a oblate nuclei, you need to have a negative quadrupole value, which is naturally harder to achieve such a structure since nuclei is positive charged in relatively macroscopic scale.

