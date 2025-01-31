# Roots of unity

<p>

This article extends [https://github.com/Z323323/Complex-numbers-background/tree/main].

Wiki reports _"a root of unity is any complex number that yields 1 when raised to some positive integer power n"_.

This means that the roots of unity are the complex solutions to this kind of equations:

$z^{n} = 1$<br>
$->$<br>
$z = \sqrt[n]{1}$

or equivalently

$z^{n} - 1 = 0$

Solving this kind of equations could enable us to find generators for well defined (we know the order of them, but we don't know the generators until we solve the roots of unity) multiplicative subgroups, which by the way, before approaching this topic, I believed impossible (indeed it's going to be really hard).

</p>

## Cyclotomic equations

<p>
  The equations mentioned previously are called cyclotomic equations, and it's quite simple to derive the equivalent form

  $x^{n} - 1 = (x - 1)(x^{n - 1} + x^{n - 2} + \dots + 1) = 0$

 Since I basically followed the entire course at [https://crypto.stanford.edu/pbc/notes/numbertheory/] let's follow [https://crypto.stanford.edu/pbc/notes/numbertheory/cyclo.html] for the moment. This section is made for completeness purposes mostly. Solving these kind of equations is in general a challenging math game, so, for the moment, we will find the solutions for $n = 1, 2, 3, 4$ and $5$ using the most elementary methods (such as [https://github.com/Z323323/Quadratic-formula-derivation]). It's possible to find solutions even for $n \gt 5$ but it's hard, and in general the $n = 5$ case already show pretty clearly that the quadratic formula is not the way to go, especially for $n$ $odd$ (we are interested in primes mostly by the way).

 $n = 1$<br>
 $->$<br>
 $x = 1$

 $---$

 $n = 2$<br>
 $->$<br>
 $x^{2} = 1$<br>
 $->$<br>
 $\sqrt{x} = 1$<br>
 $->$<br>
 $x = \pm 1$<br>
 $->$<br>
 $x_1 = 1$<br>
 $x_2 = - 1$

 $---$

 $n = 3$<br>
 $->$<br>
 $x^{3} - 1 = 0$<br>
 $->$<br>
 $(x - 1)(x^{2} + x + 1) = 0$<br>
 $->$<br>
 $x_1 = 1$<br>
 $and$<br>
 $\displaystyle x_{2,3} = \frac{- 1 \pm \sqrt{1 - 4}}{2}$<br>
 $->$<br>
 $\displaystyle x_2 = \frac{- 1 + i\sqrt{3}}{2}$<br>
 $\displaystyle x_3 = \frac{- 1 - i\sqrt{3}}{2}$

 $---$

 $n = 4$<br>
 $->$<br>
 $x^{4} - 1 = 0$<br>
 $->$<br>
 $(x - 1)(x + 1)(x^{2} + 1) = 0$<br>
 $->$<br>
 $x_1 = 1$<br>
 $x_2 = - 1$<br>
 $and$<br>
 $x^{2} + 1 = 0$<br>
 $->$<br>
 $x_{3, 4} = \pm \sqrt{- 1}$<br>
 $->$<br>
 $x_3 = i$<br>
 $x_4 = - i$

 $---$

 $n = 5$<br>
 $->$<br>
 $x^{5} - 1 = 0$<br>
 $->$<br>
 $(x - 1)(x^{4} + x^{3} + x^{2} + x + 1) = 0$<br>
 $->$<br>
 $x_1 = 1$<br>
 $and$<br>
 $x^{4} + x^{3} + x^{2} + x + 1 = 0$<br>
 $->$<br>
 $\displaystyle x^{2} + x + 1 + \frac{1}{x} + \frac{1}{x^{2}} = 0$<br>
 $->$<br>
 $\displaystyle (x + \frac{1}{x})^{2} = x^{2} + 2 + \frac{1}{x^{2}}$<br>
 $->$<br>
 $\displaystyle x^{2} + x + 1 + \frac{1}{x} + \frac{1}{x^{2}} = (x + \frac{1}{x})^{2} + (x + \frac{1}{x}) - 1$<br>
 $->$<br>
 $\displaystyle y = x + \frac{1}{x}$<br>
 $->$<br>
 $\displaystyle (x + \frac{1}{x})^{2} + (x + \frac{1}{x}) - 1 = y^{2} + y - 1 = 0$<br>
 $->$<br>
 $y^{2} + y - 1 = 0$<br>
 $->$<br>
 $\displaystyle y_{1,2} = \frac{- 1 \pm \sqrt{5}}{2}$<br>
 $->$<br>
 $\displaystyle y = x + \frac{1}{x}$<br>
 $->$<br>
 $\displaystyle yx = x^{2} + 1$<br>
 $->$<br>
 $\displaystyle x^{2} - yx + 1 = 0$<br>
 $->$<br>
 $\displaystyle x_{2,3,4,5} = \frac{y \pm \sqrt{y^{2} - 4}}{2} = \frac{\frac{- 1 \pm \sqrt{5}}{2} \pm \sqrt{(\frac{- 1 \pm \sqrt{5}}{2})^{2} - 4}}{2} = \frac{\pm \sqrt{5} - 1}{4} \pm \frac{\sqrt{(\frac{- 1}{2} \pm \frac{\sqrt{5}}{2})^{2} - 4}}{2} = \frac{\pm \sqrt{5} - 1}{4} \pm \frac{\sqrt{\frac{1}{4} \pm (\frac{5}{4} - \frac{\sqrt{5}}{2}) - 4}}{2}$<br>
 $\displaystyle x_{2,3} = \frac{\sqrt{5} - 1}{4} \pm \frac{\sqrt{\frac{1}{4} + \frac{5}{4} - \frac{\sqrt{5}}{2} - 4}}{2} = \frac{\sqrt{5} - 1}{4} \pm \frac{\sqrt{\frac{1}{4} + \frac{5}{4} - \frac{2\sqrt{5}}{4} - \frac{16}{4}}}{2} = \frac{\sqrt{5} - 1}{4} \pm \frac{\sqrt{1 + 5 - 2\sqrt{5} - 16}}{4} = \frac{\sqrt{5} - 1 \pm \sqrt{- 2\sqrt{5} - 10}}{4}$<br>
 $\displaystyle x_{4,5} = \frac{- \sqrt{5} - 1}{4} \pm \frac{\sqrt{\frac{1}{4} + \frac{5}{4} + \frac{\sqrt{5}}{2} - 4}}{2} = \frac{- \sqrt{5} - 1}{4} \pm \frac{\sqrt{\frac{1}{4} + \frac{5}{4} + \frac{2\sqrt{5}}{4} - \frac{16}{4}}}{2} = \frac{- \sqrt{5} - 1}{4} \pm \frac{\sqrt{1 + 5 + 2\sqrt{5} - 16}}{4} = \frac{- \sqrt{5} - 1 \pm \sqrt{2\sqrt{5} - 10}}{4}$<br>
 
If you made it this far you'll agree with me that this is not the way to go to compute roots of unity, even though this is a great exercise. Also, we will need to find a way to make these complex solutions to work on multiplicative groups, since the numbers obtained in complex form still don't help us finding our generators.
  
</p>

## Improvement of context and connection with Euler Identity

<p>
  Let's set up our new scenario and a couple of definitions.

  We said roots of unity are defined as the solutions of

  $z^{n} = 1$<br>

  This means that we have

  $|z|^{n}(\cos(n(\theta + 2k\pi)) + i\sin(n(\theta + 2k\pi))) = 1$

  then

  - $|z|^{n} = 1$
  - - $|z| = 1$ because $|z|$ is obtained only considering the real part of $z$, and the real part gets squared (hence it can't be $- 1$).
  - $\cos(n(\theta + 2k\pi)) + i\sin(n(\theta + 2k\pi)) = 1$
  - - $\cos(n(\theta + 2k\pi)) + i\sin(n(\theta + 2k\pi)) = e^{i2k\pi}$
   
  that is

  $z^{n} = 1 \cdot e^{i2k\pi} = e^{i2k\pi} = 1$

  This means that $z$ is a pure complex number (we already knew it since $|z| = 1$, how?) and finding the roots of unity narrows to

  $\displaystyle \cos(\frac{2k\pi}{n}) + i\sin(\frac{2k\pi}{n}) = e^{\frac{i2k\pi}{n}}$

  for

  $k = \\{0, 1, 2, \dots n - 1\\}$

  and therefore

  $\displaystyle \theta_1 = 0$<br>
  $\displaystyle \theta_2 = \theta_1 + \frac{2\pi}{n}$<br>
  $\displaystyle \theta_3 = \theta_2 + \frac{2\pi}{n}$<br>
  $\dots$<br>
  $\displaystyle \theta_{n - 1} = \theta_{n - 2} + {2\pi}{n}$

  Now we can further analyze the previous cases being aware $z$ is a pure complex number.

  $n = 1$<br>
  $->$<br>
  $\displaystyle \theta_1 = 0$<br>
  $->$<br>
  $z_1 = \cos(\theta_1) + i\sin(\theta_1) = \cos(0) + i\sin(0) = 1 + 0 = 1$

  $---$

  $n = 2$<br>
  $->$<br>
  $\displaystyle \theta_1 = 0$<br>
  $\displaystyle \theta_2 = \theta_1 + \frac{2\pi}{2} = 0 + \pi = \pi$<br>
  $->$<br>
  $z_1 = \cos(\theta_1) + i\sin(\theta_1) = \cos(0) + i\sin(0) = 1$<br>
  $z_2 = \cos(\theta_2) + i\sin(\theta_2) = \cos(\pi) + i\sin(\pi) = - 1 + 0 = - 1$
  
  $---$

  $n = 3$<br>
  $->$<br>
  $\displaystyle \theta_1 = 0$<br>
  $\displaystyle \theta_2 = \theta_1 + \frac{2\pi}{2} = 0 + \pi = \pi$<br>
  $->$<br>
  $z_1 = \cos(\theta_1) + i\sin(\theta_1) = \cos(0) + i\sin(0) = 1$<br>
  $z_2 = \cos(\theta_2) + i\sin(\theta_2) = \cos(\pi) + i\sin(\pi) = - 1 + 0 = - 1$
 
</p>
