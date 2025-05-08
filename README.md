# Roots of unity

<p>

This article extends [https://github.com/Z323323/Complex-numbers-background/tree/main].

Wiki reports _"a root of unity is any complex number that yields 1 when raised to some positive integer power n"_.

This means that the roots of unity are the solutions to this kind of equations:

$z^{n} = 1$

or equivalently

$z^{n} - 1 = 0$

$->$<br>
$z = \sqrt[n]{1}$

Finding the roots of unity or the primitive roots of unity is in general a complex problem. We are not really interested in complex analysis while on the relation between the primitive roots of unity in the complex plane and the roots of unity in multiplicative subgroups. Nonetheless I'll try to delve both in order to complete the Stanford cryptography course and because it's important to understand the linkage. You might have guessed that finding the roots of unity in multiplicative groups will basically enable us to find generators for every multiplicative subgroup (which I thought was an impossible thing before delving this topic).

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
 
If you made it this far you'll agree with me that this is not the way to go to compute roots of unity, even though this is a great exercise. Also, we will need to find a way to make these complex solutions to work on multiplicative groups, since the numbers obtained in complex form still don't help us.

The last example for $n = 5$ is quite interesting though, since it seems there are no complex solutions involved, while if you look at the next section it will be quite simple to understand that the $4$ non-trivial solutions we derived can't be considered completely real, that is, if you follow through you'll find 

$\displaystyle x_2 = e^{\frac{2i\pi}{5}}$<br>
$\displaystyle x_3 = e^{\frac{4i\pi}{5}}$<br>
$\displaystyle x_4 = e^{\frac{6i\pi}{5}}$<br>
$\displaystyle x_5 = e^{\frac{8i\pi}{5}}$

thus

$\displaystyle x_2 = \cos(\frac{2i\pi}{5}) + i\sin(\frac{2i\pi}{5})$<br>
$\displaystyle x_3 = \cos(\frac{4i\pi}{5}) + i\sin(\frac{4i\pi}{5})$<br>
$\displaystyle x_4 = \cos(\frac{6i\pi}{5}) + i\sin(\frac{6i\pi}{5})$<br>
$\displaystyle x_5 = \cos(\frac{8i\pi}{5}) + i\sin(\frac{8i\pi}{5})$

which are not real numbers.
  
</p>

## Improvement of context, connection with Euler Identity and primitive roots

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
  - - $\cos(n(\theta + 2k\pi)) + i\sin(n(\theta + 2k\pi)) = e^{i2\pi} = 1$

  Now we know $z$ is a pure complex number of real part which equals $1$, and therefore finding the roots of unity narrows to

  $\displaystyle \cos(\frac{2k\pi}{n}) + i\sin(\frac{2k\pi}{n}) = e^{\frac{i2k\pi}{n}}$

  for

  $k = \\{0, 1, 2, \dots n - 1\\}$

  and therefore

  $\displaystyle \theta_1 = 0$<br>
  $\displaystyle \theta_2 = \frac{2\pi}{n}$<br>
  $\displaystyle \theta_3 = \frac{4\pi}{n}$<br>
  $\displaystyle \theta_4 = \frac{6\pi}{n}$<br>
  $\dots$<br>
  $\displaystyle \theta_{n} = \frac{(n - 1)2\pi}{n}$

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
  $\displaystyle \theta_2 = \frac{2\pi}{2} = \pi$<br>
  $->$<br>
  $z_1 = \cos(\theta_1) + i\sin(\theta_1) = \cos(0) + i\sin(0) = 1$<br>
  $z_2 = \cos(\theta_2) + i\sin(\theta_2) = \cos(\pi) + i\sin(\pi) = - 1 + 0 = - 1$

  ![2](./2.jpg)
  
  $---$

  $n = 3$<br>
  $->$<br>
  $\displaystyle \theta_1 = 0$<br>
  $\displaystyle \theta_2 = \frac{2\pi}{3}$<br>
  $\displaystyle \theta_3 = \frac{4\pi}{3}$<br>
  $->$<br>
  $z_1 = \cos(\theta_1) + i\sin(\theta_1) = \cos(0) + i\sin(0) = 1$<br>
  $z_2 = \cos(\theta_2) + i\sin(\theta_2) = \cos(\frac{2\pi}{3}) + i\sin(\frac{2\pi}{3}) = e^{\frac{i2\pi}{3}}$<br>
  $z_3 = \cos(\theta_3) + i\sin(\theta_3) = \cos(\frac{4\pi}{3}) + i\sin(\frac{4\pi}{3}) = e^{\frac{i4\pi}{3}}$

  ![3](./3.jpg)

  $---$

  $n = 4$<br>
  $->$<br>
  $\displaystyle \theta_1 = 0$<br>
  $\displaystyle \theta_2 = \frac{2\pi}{4} = \frac{\pi}{2}$<br>
  $\displaystyle \theta_3 = \frac{4\pi}{4} = \pi$<br>
  $\displaystyle \theta_4 = \frac{6\pi}{4} = \frac{3\pi}{2}$<br>
  $->$<br>
  $z_1 = \cos(\theta_1) + i\sin(\theta_1) = \cos(0) + i\sin(0) = 1$<br>
  $z_2 = \cos(\theta_2) + i\sin(\theta_2) = \cos(\frac{\pi}{2}) + i\sin(\frac{\pi}{2}) = 0 + i = i$<br>
  $z_3 = \cos(\theta_3) + i\sin(\theta_3) = \cos(\pi) + i\sin(\pi) = - 1 + 0 = - 1$<br>
  $z_4 = \cos(\theta_4) + i\sin(\theta_4) = \cos(\frac{3\pi}{2}) + i\sin(\frac{3\pi}{2}) = 0 - i = - i$

  ![4](./4.jpg)

  Now the process should be more than clear. We can abstract $2i\pi$ for a moment and consider only $k$ and $n$ since the former will be constant [ for which will hold $k \equiv r \mod n$ ].

  Now, consider two different numbers sharing some cofactor $q$ which will map $n_{1}$ and $n_{2}$ roots of unity. We'd have for example

  $n_1 = q$<br>
  $n_2 = qxyz$

  and

  $\displaystyle \frac{k_{1}}{q}$<br>
  $and$<br>
  $\displaystyle \frac{k_{2}}{qxyz}$
  
  Therefore

  $\displaystyle root_{xyz + 1}(n_{2}) = \frac{1}{q} = root_{1 + 1}(n_{1})$
  
  for some $k_{2} = xyz, k_{1} = 1$. [ $+ 1$ is because we start at $k = 0$, so for ex. $root_{1} = 0, root_{2} = \frac{1}{q}, root_{3} = \frac{2}{q}$ and so on ].

  Also, for $k_{2} = Xxyz, 1 \leq X \leq q$

  $\displaystyle root_{k_{2} + 1}(n_{2}) = \frac{k_{2}}{qxyz} = \frac{k_{1}}{q} = root_{k_{1} + 1}(n_{1})$

  thus, $\forall n > m$ such that $n$ has $m$ as cofactor, $n$ will share the same roots of $m$.
  
  Now, consider

  $n_1 = q^{2}$<br>
  $n_2 = qxyz$

  and

  $\displaystyle \frac{k_{1}}{q^{2}}$<br>
  $and$<br>
  $\displaystyle \frac{k_{2}}{qxyz}$
  
  Therefore

  $\displaystyle root_{xyz + 1}(n_{2}) = \frac{1}{q} = root_{q + 1}(n_{1})$
  
  for some $k_{2} = xyz, k_{1} = q$.

  Also, for $k_{2} = Xxyz, 1 \leq X \leq q, k_{1} = Yq, 1 \leq Y \leq q$

  $\displaystyle root_{k_{2} + 1}(n_{2}) = \frac{k_{2}}{qxyz} = \frac{k_{1}}{q^{2}} = root_{k_{1} + 1}(n_{1})$
  
  We define the **primitive roots of unity** of $n$ as the roots of unity which didn't already appear for some $m < n$. This means that in general, the primitive roots of unity of $n$ are $\phi(n)$, because the non-primitive roots of unity will have appeared for every $m < n$ which share some cofactor with $n$. Since we are considering only the numbers $< n$, and the numbers which do not share cofactors with $n$ are coprimes $< n$, the result $\phi(n)$ follows.

  Let's see another example to further clarify $\phi(n)$. Let $n = 12$. We have $1, 2, 3, 4, 6$ which are cofactors, indeed [ skipping $m = 1$ and subtracting $1$ in advance to $12$ where $1 = \phi(1)$, so let's set the counter at $11$ ]

  $m = 2$<br>
  $n = 12$<br>
  $->$<br>
  $\displaystyle root_{1 + 1}(m) = \frac{1}{2}$<br>
  $\displaystyle root_{6 + 1}(n) = \frac{1}{2}$

  indeed $\phi(2) = 1$<br>
  $->$<br>
  $11 - 1 = 10$
  
  [ remember $\phi(2)$ etc. will refer to the primitive roots of unity considering every $m < n$, in turn, every $m$ will have some $w$ such that $w < m$ so in this case the only $w < 2$ is $1$, indeed the only primitive root of $2$ is $\frac{1}{2}$. The number appearing below has been set to show the comparison with the primitive roots of unity of $12$ and the primitive roots of every $m < 12$, which as you can see will be subtracted from $12$ cofactor after cofactor, i.e. $2$ is a cofactor of $12$ and will decrease the number of primitive roots of $12$ by $1$ because the already appeared for $m < n$, that is $2 < 12$, since $2$ is a cofactor of $12$. This is exactly the behaviour of the $\phi$ function. ].

  $m = 3$<br>
  $n = 12$<br>
  $->$<br>
  $\displaystyle root_{1 + 1}(m) = \frac{1}{3}$<br>
  $\displaystyle root_{4 + 1}(n) = \frac{1}{3}$

  and
 
  $\displaystyle root_{2 + 1}(m) = \frac{2}{3}$<br>
  $\displaystyle root_{8 + 1}(n) = \frac{8}{12} = \frac{2}{3}$

  [ remember that I'm considering the first root with $k = 0$, this means that the last root won't be $root_{n - 1}$ but $root_{n}$ ]

  indeed $\phi(3) = 2$<br>
  $->$<br>
  $10 - 2 = 8$

  $m = 4$<br>
  $n = 12$<br>
  $->$<br>
  $\displaystyle root_{1 + 1}(m) = \frac{1}{4}$<br>
  $\displaystyle root_{3 + 1}(n) = \frac{1}{4}$

  and

  $\displaystyle root_{3 + 1}(m) = \frac{3}{4}$<br>
  $\displaystyle root_{9 + 1}(n) = \frac{9}{12} = \frac{3}{4}$

  indeed $\phi(4) = 2$, because $\phi(2^{2}) = 2^{2} - 2 = 2$<br>
  $->$<br>
  $8 - 2 = 6$

  $m = 6$<br>
  $n = 12$<br>
  $->$<br>
  $\displaystyle root_{1 + 1}(m) = \frac{1}{6}$<br>
  $\displaystyle root_{2 + 1}(n) = \frac{1}{6}$

  and

  $\displaystyle root_{5 + 1}(m) = \frac{5}{6}$<br>
  $\displaystyle root_{10 + 1}(n) = \frac{10}{12} = \frac{5}{6}$

  indeed $\phi(6) = \phi(2)\phi(3) = 2$<br>
  $->$<br>
  $6 - 2 = 4$

  As you can see, this is a concatenation of reasons which starts at $1$, indeed every number share the first root, then every even number will share the $n = 2$ roots, then every number which is multiple of $3$ and $2$ will share the $2$ and $3$ roots, which in turn share the $1$ root, and since the $\phi(n)$ function keeps track of this because it's multiplicative then the result follows.

  We can conclude by seeing that 

  $\phi(12) = \phi(2^{2})\phi(3) = 4$

  and the image below which shows the primitive roots of unity of $n = 12$.

  ![12](./12.jpg)
  
</p>

## Obtaining the almighty power on multiplicative groups analysing Gauss' heptadecagon and gaussian periods

<p>
  Refer to [https://crypto.stanford.edu/pbc/notes/numbertheory/17gon.html], [https://crypto.stanford.edu/pbc/notes/numbertheory/gaussperiod.html], and [https://s3.us-east-1.amazonaws.com/sjcdigitalarchives/original/4076cf9a600178cf678478821f331c65.pdf].
  The two linked resources about the heptadecagon are the exact opposite approach to solve the same problem, that is, one is formal and the other one is raw. I felt free to steal a couple of images from the second link because they were really well made and important (hope this won't be a problem).
  
  When he was a teenager Gauss found a clever way to compute primitive roots of unity while trying to draw an heptadecagon using a straight-edge and a compass. What we are really interested in is not to draw the heptadecagon but to generalize the tactic Gauss used to find the primitive roots of unity, and extract some valuable results which include the main result we are interested in.

  $x^{17} - 1 = 0$<br>
  $->$<br>
  $(x - 1)(1 + x + \dots + x^{16}) = 0$

  We know

  $\zeta = e^{\frac{2i\pi}{17}} \neq 1$

  and that the only real solution is $\zeta = 1$ because $17$ is an $odd$ prime (doesn't share $4$ roots), thus

  $1 + x + \dots + x^{16} = 0$<br>
  $->$<br>
  $x + \dots + x^{16} = - 1$<br>
  $->$<br>
  $\zeta + \dots + \zeta^{16} = - 1$

  We can rewrite the sum of the primitive roots of unity (thus not considering $1$) of $17$ as $x_1 + x_2$ where

  $x_1 = \zeta^{3^{0}} + \zeta^{3^{2}} + \dots + \zeta^{3^{14}}$<br>
  $x_2 = \zeta^{3^{1}} + \zeta^{3^{3}} + \dots + \zeta^{3^{15}}$

  since we know our roots exponent term $k$ is periodic $\mod 17$.
  
  We can see that $x_1$ terms will be such that

  $\zeta^{3^{2s} \mod 17}$

  for $s \geq 0$. The same goes for $x_2$ being defined by

  $\zeta^{3^{2s + 1} \mod 17}$

  $-----$

  You might have already spot that our relation with multiplicative groups lies here.

  We can set every primitive root of unity for some number $n$ (thus only removing $e^{0}$ from non-primitive ones if $n$ is prime) as the set $H$ built by 
  
  $H = \\{\zeta^{G \mod n}, \zeta^{G^{2} \mod n}, \dots, \zeta^{G^{\phi(n)} \mod n}\\}$

  with

  $|H| = \phi(n)$

  Also, we can further indentify that if we consider the set of the squares of the primitive roots of unity our set becomes

  $H_2 = \\{\zeta^{G^{2} \mod n}, \zeta^{G^{4} \mod n}, \dots, \zeta^{G^{\phi(n)} \mod n}\\}$

  and
  
  $\displaystyle |H_2| = \frac{|H|}{2} = \frac{\phi(n)}{2}$

  To better clarify this step which basically explains the others too, imagine to square $H$ values. This basically means that we are doubling the order of the elements we take from the subgroup generated by $G$ which is of course $Z_{\phi(n)}^{\ast}$. This means that since the order of $Z_{\phi(n)}^{\ast}$ is $\phi(n)$ and is (always) $even$, it won't be possible that an even order obtained by the squares will become $odd$ once it goes beyond $\phi(n)$, and not only this, it holds also for $odd$ powers, that is an even $\phi(n)$ doesn't alter the oddness, but again, it's even more than this. Imagine to take the $4-t\lambda$ power; now the problem is being sure we won't have orders $o$ which verify $o | 2, o \nmid 4$; if we are checking this is because we know $4 | \phi(n)$, and this means that every number we get as resulting order will be a multiple of $4$ and so on. I'm clarifying this because I think this step is not really intuitive, and is important because it's the basis of the halving etc. of the solutions of the squares etc. of the roots of unity of $\phi(n)$, and it's itself the proof about conjugates you'll find later.
  
  If we keep reasoning this way we get [ setting the hypothesis $4 | \phi(n)$ ]

  $H_4 = \\{\zeta^{G^{4} \mod n}, \zeta^{G^{8} \mod n}, \dots, \zeta^{G^{\phi(n)} \mod n}\\}$

  and 
  
  $\displaystyle |H_4| = \frac{|H|}{4} = \frac{\phi(n)}{4}$
  
  and

  $H_{\phi(n)} = \\{\zeta^{G^{\phi(n)} \mod n} = \zeta^{1} = \zeta\\}$

  with 
  
  $\displaystyle |H_{\phi(n)}| = \frac{|H|}{\phi(n)} = \frac{\phi(n)}{\phi(n)} = 1$

  We can see that we can consider the exponents of the primitive roots of unity of $n$ as the roots of unity of $\phi(n)$ in $Z_{\phi(n)}^{\ast}$ because $H_{exps}^{\phi(n)} \equiv 1 \mod n$. The funny part of this is that we didn't really need to delve the roots of unity in the complex plane to understand this thing, but it turns out that they are a big clue. Computing the squares for the primitive roots of unity of $n$, that is, finding the exponents for $\zeta$ is the same as finding the roots of unity of $\frac{\phi(n)}{2}$ in $Z_{\phi(n)}^{\ast}$ because

  $\displaystyle (sqrt[\phi(n)]\\{n\\})^{2} = sqrt[\frac{\phi(n)}{2}]\\{n\\}$

  I had to use this form for the root because the rendering of the root symbol is messed up in Markdown.

  We can conclude that our resulting set of exponents for $H_2$ represents the roots of unity of $\frac{\phi(n)}{2}$ in $Z_{\phi(n)}^{\ast}$, that is, it will represent the set of numbers which being elevated at $\phi(n)/2$ produce $1$ which we already know it's half of the set since the Euler's Criterion, but now we have a much powerful knowledge, indeed if you check this beautiful result, for ex. eusing $Z_{17}^{\ast}$ and Zn.py, you'll find out that computing $H_2$ OR checking the second position in every subgroup and collecting elements (and removing duplicates), you'll find out that the resulting set $R$ is such that
  
  $R_{\frac{\phi(17)}{2}} = sqrt[\frac{\phi(n)}{2}]\\{n\\} = sqrt[8]\\{n\\}$

  That is, every number which produces $1$ at the $8t\lambda$ position, or in other words, the roots of unity of $8$ in $Z_{17}^{\ast}$, or in other words, every number which produces $1$ at $\phi(n)$ (every number) but squared, that is, $H_2$ OR every element you'll find at the second position in every subgroup (removing dups).
  
  If we keep making the square or cube or quartic or quintic or whatever number we know divides $\phi(n)$ we can basically get every generator for any subgroup of $Z_{\phi(n)}^{\ast}$ as long as we know the divisors, but note that in order to know the generators for a subgroup of order $o | \phi(n)$ we won't compute $H_o$, instead, we will need to compute

  $\displaystyle \frac{\phi(n)}{o} = o_r$

  and then compute $H_{o_{r}}$, because

  $\displaystyle (sqrt[\phi(n)]\\{n\\})^{o_r} = sqrt[\frac{\phi(n)}{o_r}]\\{n\\} = sqrt[o]\\{n\\}$

  Also, we know that the roots of unity will include $1$ because $1$ is always a solution, hence to get the generators for some subgroup we will exclude $G^{\phi(n)} \mod n$ because we know it will only generate the $\\{1\\}$ set, and this is probably the reason you'll read 'primitive roots of unity' of $n$ when talking about multiplicative groups.

  Last but not least, since we basically found two ways to get the roots of unity in multiplicative groups, what do you think is better, finding results for every subgroup at the position $Z$ and removing dups or compute $H_{o_{r}}$?<br>
  The first one has the problem of wasting computation, but we can use smaller exponents, while the second doesn't waste computation but uses bigger exponents.

  #### Ex $p = 79$

  $\phi(79) = 78$<br>
  $78 = 2 \cdot 3 \cdot 13$

  We want to know the generators for the subgroups of order $13$, that is, following our reasoning this means to find

  $\displaystyle \frac{\phi(n)}{o} = o_r = \frac{78}{13} = 6$<br>
  $->$<br>
  $H_{6} = \\{G^{6} \mod 79, G^{12} \mod 79, G^{18} \mod 79, \dots, G^{78 - 6} \mod 78\\}$

  We have $3$ as generator for $Z_{79}^{\ast}$ hence

  $H_{6} = \\{3^{6} \mod 79, 3^{12} \mod 79, 3^{18} \mod 79, \dots, 3^{78 - 6} \mod 78\\}$<br>
  $->$<br>
  $H_{6} = \\{18, 8, 65, 64, 46, 38, 52, 67, 21, 62, 10, 22\\}$

  If you check this result you'll find out we just got the almighty power on multiplicative subgroups.
  
  Now we can get back to our complex analysis.

  $-----$
  
  Since our reasoning about orders, $x_1$ and $x_2$ will contain pairs of roots being each other conjugates. 

  The complex conjugate of a complex number $z = x + iy$ is defined as

  $\overline{z} = x - iy$

  that is, is the same number mirrored over the $x - axis$. This means that if this number is a root of unity $\neq 1$ it will be such that

  $\displaystyle z = e^{\frac{2ki\pi}{n}} = \cos(\frac{2k\pi}{n}) + i\sin(\frac{2k\pi}{n})$

  for some $k \neq xn, x \geq 0$ and its conjugate will be

  $\displaystyle \overline{z} = e^{- \frac{2ki\pi}{n}} = \cos(- \frac{2k\pi}{n}) + i\sin(- \frac{2k\pi}{n}) = \cos(\frac{2k\pi}{n}) - i\sin(\frac{2k\pi}{n})$

  In general we will always have pairs of conjugates when dealing with roots of unity, if we remove $e^{0}$. A clear example of this is

  $x^{3} - 1 = 0$

  which you can find above along with its picture.

  It's quite intuitive at this point to recognise that $x_1$ and $x_2$ will both contain pairs of conjugates. The process is nontheless not intuitive so I'm going to derive the real structure of $x_1$ and $x_2$ and provide a picture. We had

  $x_1 = \zeta^{3^{0}} + \zeta^{3^{2}} + \dots + \zeta^{3^{14}}$<br>
  $x_2 = \zeta^{3^{1}} + \zeta^{3^{3}} + \dots + \zeta^{3^{15}}$

  Solving congruences leads to

  $3^{0} = 1 \mod 17$<br>
  $3^{2} = 9 \mod 17$<br>
  $3^{4} \equiv 13 \mod 17$<br>
  $3^{6} \equiv 15 \mod 17$<br>
  $3^{8} \equiv 16 \mod 17$<br>
  $3^{10} \equiv 8 \mod 17$<br>
  $3^{12} \equiv 4 \mod 17$<br>
  $3^{14} \equiv 2 \mod 17$<br>
  $---$<br>
  $3^{1} = 3 \mod 17$<br>
  $3^{3} \equiv 10 \mod 17$<br>
  $3^{5} \equiv 5 \mod 17$<br>
  $3^{7} \equiv 11 \mod 17$<br>
  $3^{9} \equiv 14 \mod 17$<br>
  $3^{11} \equiv 7 \mod 17$<br>
  $3^{13} \equiv 12 \mod 17$<br>
  $3^{15} \equiv 6 \mod 17$

  hence

  $x_1 = \zeta + \zeta^{9} + \zeta^{13} + \zeta^{15} + \zeta^{16} + \zeta^{8} + \zeta^{4} + \zeta^{2}$<br>
  $x_2 = \zeta^{3} + \zeta^{10} + \zeta^{5} + \zeta^{11} + \zeta^{14} + \zeta^{7} + \zeta^{12} + \zeta^{6}$

  To better clarify everything the picture below shows clearly the previous reasoning about conjugates.

  ![17](./17.jpg)

  Now Ben starts by showing

  $(x_1 - x_2)^{2} = (x_1 + x_2)^{2} = a_0 + a_1\zeta^{3^{1}} + a_2\zeta^{3^{2}} + \dots + a_{16}\zeta^{3^{16}}$<br>
  
  where the second step is because we are basically doing this

  $- \zeta = \overline{\zeta}$<br>
  $and$<br>
  $- \overline{\zeta} = \zeta$

  and the third step is because

  $(x_1 + x_2)^{2} = (x_1 + x_2)(x_1 + x_2)$

  and
  
  $e^{\frac{2ik_1\pi}{17}}e^{\frac{2ik_2\pi}{17}} = e^{\frac{2i(k_1 + k_2)\pi}{17}}$<br>
  $-clearerForm>$<br>
  $\displaystyle \frac{2ik_1\pi}{17} + \frac{2ik_2\pi}{17} = \frac{2i(k_1 + k_2)\pi}{17}$

  Now, I'm going to take a different way to solve the chapter which I believe being clearer and easier (I showed the first step of the chapter because it can help figuring out things, and may be helpful to understand Ben's proof). If we consider $x_1x_2$ we have that this last multiplication covers every $x_1$ and $x_2$ term, but $x_1$ terms are never multiplied by themselves and the same goes for $x_2$. Also, we have $x_1$ and $x_2$ terms holding their respective conjugates hence we won't have $1$ as result of $\frac{2i(k_1 + k_2)\pi}{17}$, and since the multiplication has distributive property, any result which has multiples of $16$ elements will cover every root of unity with potential repetitions, that is, $x_1x_2$ will produce the whole $\zeta + \zeta^{3^{1}} + \zeta^{3^{2}} + \dots + \zeta^{3^{15}}$ or equivalently $\zeta^{3^{1}} + \zeta^{3^{2}} + \dots + \zeta^{3^{16}}$, but it's not over, because the result of $x_1x_2$ will have $64$ elements. Now, if we manually compute the whole multiplication $(\zeta + \zeta^{9} + \zeta^{13} + \zeta^{15} + \zeta^{16} + \zeta^{8} + \zeta^{4} + \zeta^{2})(\zeta^{3} + \zeta^{10} + \zeta^{5} + \zeta^{11} + \zeta^{14} + \zeta^{7} + \zeta^{12} + \zeta^{6})$ we will get this result

  ![x1x2](x1x2.jpg)

  It's quite clear that we will have $\zeta^{3^{1}} + \zeta^{3^{2}} + \dots + \zeta^{3^{16}}$ repeated $4$ times $(64/4 = 16)$. Now, since

  $\zeta^{3^{1}} + \zeta^{3^{2}} + \dots + \zeta^{3^{16}} = x_1 + x_2 = - 1$

  and we have this result repeated $4$ times (just look at the first two lines of the picture above) it follows that

  $x_1x_2 = (- 1) \cdot 4 = - 4$

  Let's go over. How would you compute the values of $x_1$ and $x_2$ knowing $x_1 + x_2 = a$ and $x_1x_2 = b$? I don't know if I'm stupid or what but I found this challenging, hence I'm delving this below.

  Setting

  $(x - x_1)(x - x_2) = 0$

  we'll find the values of $x$ which are equal to $x_1$ and $x_2$, and solving
  
  $x^{2} - xx_2 - xx_1 + x_1x_2 = 0$<br>
  $->$<br>
  $x^{2} - x(x_1 + x_2) + x_1x_2 = 0$<br>
  $->$<br>
  $x^{2} - x(- 1) + (- 4) = 0$<br>
  $->$<br>
  $x^{2} + x - 4 = 0$

  This is the general form of a second degree polynomial $ax^{2} + bx + c = 0$ which can be solved using

  $\displaystyle x_{1,2} = \frac{- b \pm \sqrt{b^{2} - 4ac}}{2a}$<br>
  $->$<br>
  $\displaystyle x_1 = \frac{- 1 + \sqrt{1 + 16}}{2} = \frac{- 1 + \sqrt{17}}{2}$<br>
  $\displaystyle x_2 = \frac{- 1 - \sqrt{1 + 16}}{2} = \frac{- 1 - \sqrt{17}}{2}$

  where $x_1$ is the higher one because looking at the complex plane it's pretty clear that it has less negative terms and more positive ones.

  Let's now split $x_1$ and set

  $y_1 = \zeta^{3^{0}} + \zeta^{3^{4}} + \zeta^{3^{8}} + \zeta^{3^{12}}$<br>
  $->$<br>
  $y_1 = \zeta + \zeta^{13} + \zeta^{16} + \zeta^{4}$<br>
  $y_2 = \zeta^{3^{2}} + \zeta^{3^{6}} + \zeta^{10} + \zeta^{3^{14}}$<br>
  $->$<br>
  $y_2 = \zeta^{9} + \zeta^{15} + \zeta^{8} + \zeta^{2}$

  Since $y_1y_2$ must have $16$ terms we end up having

  $y_1y_2 = - 1$

  following the previous reasoning about distributive property or manually calculating. Now we could proceed as above to compute $y_1, y_2$ solving a quadratic, but let's go over, since our goal here is to get $\zeta$.

  We can further split $y_1$ and get

  $z_1 = \zeta + \zeta^{16}$
  $z_2 = \zeta^{13} + \zeta^{4}$

  We can either proceed like above and compute $z_1 + z_2 = y_1$, and $z_1z_2$ manually or proceed, so let's get over. At this point it's quite simple to split $z_1$ and see that
  
  $\displaystyle \zeta + \zeta^{16} = 2\cos(\frac{2\pi}{17})$

  which means

  $\displaystyle \zeta = \zeta^{16} = \cos(\frac{2\pi}{17})$

  Why all of this is so important? Because we see that the actual values of roots of unity is actually only dependent on $cos$.
  
</p>

## Eisenstein irreducibility criterion and Gauss' extension lemma

<p>
  
  Refer to [https://crypto.stanford.edu/pbc/notes/numbertheory/eisenstein.html].

  Eisenstein criterion has a cryptic statement, but I guess (don't take me for granted I may be wrong) it basically states that having a polynomial $P(x)$, if we don't have a prime $p$ which divides the whole polynomial's terms coefficients, then $P(x)$ is irreducible over the integers, that is, it won't exist any integer divisor for the polynomial, nor another polynomial which divides it. The clarification $p^{2} \nmid a_1$ I guess is to set the structure of $P(x)$, that is, it will follow the proof structure, I'm not sure by the way, there may be some other reason because I guess the proof holds even if $p^{2} | a_1$. The proof proceeds proving that having a polynomial defined as the multiplication of two polynomials where one of them is divisible by $p$, it must be that $p$ divides $a_{n}$ therefore proving that if we don't have such $p$ then the polynomial is irreducible (but again, I might be wrong, verify).

  Gauss' lemma basically extends the proof by stating that a polynomial is irreducible over integers iff it is irreducible over the rationals. This means that if we manage to prove that a polynomial is irreducible over the integers it will be irreducible over the rationals too. This one is quite intuitive even without a formal proof.
  
</p>

## Gauss' generalized method to find primitive roots of unity

<p>
  TODO
</p>

