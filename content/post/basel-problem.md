---
author: Owen Drummond
title: Basel Problem
date: 2023-03-30
description: Euler's Classical Solution to the Basel Problem
math: true
---

The Basel Problem, named after Leonard Euler's hometown of Basel, Switzerland, is the solution to the infinite series 
{{< math.inline >}}
\(\sum_{n=1}^{\infty} \frac{\pi^2}{6}\)
{{</ math.inline >}}
 Euler was the first to publish his solution one year after having solved this problem in 1734. Since Euler's solution, many alternative proofs have been offered, using complex analysis, symmetric polynomials, and so on. These alternative proofs are more rigorous than Euler's liberal use of infinite polyomial tails, but Euler's solution is perhaps the most elegant. This is the outline of the proof.


### Definition of sin(x) using infinite products

We can construct a definition of 
{{< math.inline >}}
\(f(x)=\sin(x)\)
{{</ math.inline >}} given that 
{{< math.inline >}}
\(f\)
{{</ math.inline >}}
 has infinitely many roots:
$$
\sin(x)=x(1-\frac{x}{\pi})(1+\frac{x}{\pi})(1-\frac{x}{2\pi})(1+\frac{x}{2\pi})\cdots=x(1-\frac{x^2}{\pi^2})(1-\frac{x^2}{2^2\pi^2})\cdots=x\prod_{k=1}^{\infty} (1-\frac{x^2}{k^2\pi^2})
$$
So we have 
$$
    \sin(x)=x\prod_{k=1}^{\infty} (1-\frac{x^2}{k^2\pi^2})
$$


### Constructing {{< math.inline >}} \(\sin_{n}(x)\) {{</ math.inline >}} from {{< math.inline >}} \(\sin_{3}(x)\) {{</ math.inline >}}

Let 
{{< math.inline >}}
\(\sin_{n}(x)\)
{{</ math.inline >}} 
denote the number of products n we take from our definition of 
{{< math.inline >}}
\(\sin(x)\)
{{</ math.inline >}} 
above. We have
$$
    \sin_{3}(x)=x(1-\frac{x^2}{\pi^2})(1-\frac{x^2}{2^2\pi^2})(1-\frac{x^2}{3^2\pi^2})
$$
Which can be written as
$$
     \sin_{3}(x)=x(1-O(x^4)-\frac{x^2}{\pi^2}-\frac{x^2}{{2^2\pi}^2}-\frac{x^2}{{3^2\pi}^2}).
$$

We can disregard all of the polynomial terms degree 4 or greater, so we can write
$$
    \sin_{3}(x)=x(T-\frac{x^2}{\pi^2}-\frac{x^2}{{2^2\pi}^2}-\frac{x^2}{{3^2\pi}^2})=(T-\frac{x^3}{\pi^2}-\frac{x^3}{{2^2\pi}^2}-\frac{x^3}{{3^2\pi}^2}).
$$
where T is some polynomial tail. More generally, we can construct 
{{< math.inline >}}
\(\sin_{n}(x)\)
{{</ math.inline >}} 
from our definition of 
{{< math.inline >}}
\(\sin_{3}(x)\)
{{</ math.inline >}} 
:
$$
    \sin_{n}(x)=T-x^3\sum_{n=1}^{\infty} \frac{1}{n^2\pi^2}.
$$


### Taylor Series for sin(x)
For now, we will denote 
{{< math.inline >}}
\(\sin_{t}(x)\)
{{</ math.inline >}} 
as the Taylor Series expansion of 
{{< math.inline >}}
\(\sin(x)\)
{{</ math.inline >}} 
. We know
$$
    \sin(x)=\sin_{t}(x)=\sum_{n=1}^{\infty} (-1)^{n-1}\frac{x^{2n-1}}{(2n-1)!}
$$
Expanding this, we have 
$$
    \sin_{t}(x)=x-\frac{x^3}{3!}+\frac{x^5}{5!}-...
$$
We will disregard all of the polynomial terms except those with degree 3, so we have
$$
    \sin_{t}(x)=T-\frac{x^3}{3!}
$$
where T is some polynomial tail.



### Comparison of coefficients and completion of the proof
So far we have 
{{< math.inline >}}
\(\sin_{n}(x)\)
{{</ math.inline >}} 
, which is one expression for
{{< math.inline >}}
\(\sin(x)\)
{{</ math.inline >}} 
, and 
{{< math.inline >}}
\(\sin_{t}(x)\)
{{</ math.inline >}} 
, which is another expression for 
{{< math.inline >}}
\(\sin(x)\)
{{</ math.inline >}}
. Therefore,
$$
    \sin(x)=\sin_{n}(x)=\sin_{t}(x)
$$
So, equating 
{{< math.inline >}}
\(\sin_{n}(x)\)
{{</ math.inline >}}
and 
{{< math.inline >}}
\(\sin_{t}(x)\)
{{</ math.inline >}} 
, we have
$$
    \sin_{n}(x)=T-x^3\sum_{n=1}^{\infty} \frac{1}{n^2\pi^2}=T-\frac{x^3}{3!}= \sin_{t}(x)
$$
Since T is the same polynomial tail for both expressions, we can subtract by T on both sides:
$$
    x^3\sum_{n=1}^{\infty} \frac{1}{n^2\pi^2}=\frac{x^3}{6}
$$
Dividing by
{{< math.inline >}}
\(x^3\)
{{</ math.inline >}}
, we have
$$
    \sum_{n=1}^{\infty} \frac{1}{n^2\pi^2}=\frac{1}{6}
$$
Finally, multiplying by 
{{< math.inline >}}
\(\pi^2\)
{{</ math.inline >}}
on both sides yields
$$
    \sum_{n=1}^{\infty} \frac{1}{n^2}=\frac{\pi^2}{6}
$$