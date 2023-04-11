---
author: Owen Drummond
title: A Fascinating Integral
date: 2023-04-10
description: A fascinating integral involving the natural logarithm
math: true
tags: ["Calculus"]
---
We will evalute the integral
{{< math.inline >}}
\(\int_0^1 \frac{ln(x)}{1+x} dx \)
{{</ math.inline >}}
using Taylor Series expansion and switching the order of integration and summation.

Firstly, we notice that 
$$
\frac{1}{1+x}=\sum_{n=0}^{\infty} (-1)^n x^n
$$

by taylor series expansion. This series coverges for 
{{< math.inline >}}
\(x \in (0,1)\)
{{</ math.inline >}}

so we can substitute this into the integral:

$$
\int_0^1 \frac{ln(x)}{1+x} dx = \int_0^1 ln(x) \sum_{n=0}^{\infty} (-1)^n x^n dx
$$

Further, by changing the order of integration and summation, we have
$$
\int_0^1 ln(x) \sum_{n=0}^{\infty} (-1)^n x^n dx = \sum_{n=0}^{\infty} (-1)^n \int_0^1 x^n ln(x) dx
$$

Next, we evaluate the integral 
{{< math.inline >}}
\(\int_0^1 x^n ln(x) dx\)
{{</ math.inline >}}
, which, by integration by parts with 
{{< math.inline >}}
\(u=ln(x)\)
{{</ math.inline >}}
and 
{{< math.inline >}}
\(v=x^n+1\)
{{</ math.inline >}}
, we have that

$$
\int_0^1 x^n ln(x) dx = \frac {ln(x)x^(n+1)}{n+1}\Big|_0^1 - \int_0^1 \frac{x^n}{n+1} dx = -\frac{x^{n+1}}{(n+1)^2}\Big|_0^1 = -\frac{1}{(n+1)^2}
$$

From this, we now have that
$$
\sum_{n=0}^{\infty} (-1)^n \int_0^1 x^n ln(x) dx = \sum_{n=0}^{\infty} (-1)^n (-\frac{1}{(n+1)^2}) = \sum_{n=0}^{\infty} (\frac{(-1)^{n+1}}{(n+1)^2}) = \sum_{n=1}^{\infty} (\frac{(-1)^{n}}{(n)^2}) = -\frac{\pi^2}{12}
$$

Thus, we have that 
$$
\int_0^1 \frac{ln(x)}{1+x} dx = -\frac{\pi^2}{12}
$$