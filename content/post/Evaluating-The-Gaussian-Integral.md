---
author: Owen Drummond
title: Evaluating the Gaussian Integral
date: 2023-04-25
description: Evaulating the Gaussian Integral Using Calc 3 techniques
math: true
tags: ["Calculus"]
---

The Gaussian Integral is given by 
$$
\int_{-\infty}^{\infty} e^{-x^2} dx
$$
This is a beautiful integral with many important applications to probability and statistic, namely normal distributions. Here, we will evaluate this integral using techniques from Calculus 3. First, if we define
{{< math.inline >}}
\(I=\int_{-\infty}^{\infty} e^{-x^2} dx\)
{{</ math.inline >}} 
we have that 
$$
I^2=\int_{-\infty}^{\infty} e^{-x^2} dx \int_{-\infty}^{\infty} e^{-y^2} dy= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} e^{-x^2-y^2} dy dx= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} e^{-(x^2+y^2)} dy dx
$$
From here, we will preform a change into polar coordinates, with 
{{< math.inline >}}
\((x,y) \rightarrow (t, \theta)\)
{{</ math.inline >}} 
and 
{{< math.inline >}}
\(x=r\cos\theta\)
{{</ math.inline >}}
,
{{< math.inline >}}
\(y=r\sin\theta\)
{{</ math.inline >}}
. From this, since
{{< math.inline >}}
\(r^2=x^2+y^2\)
{{</ math.inline >}}
,
{{< math.inline >}}
\(r \in (0,\infty)\)
{{</ math.inline >}}
and
{{< math.inline >}}
\(\theta \in (0, 2\pi)\)
{{</ math.inline >}}
we have that our integral is now
$$
I^2=\int_{0}^{\infty} \int_{0}^{2\pi} re^{-r^2} d\theta dr
$$
after this change of coordinates. By Fubini's theorem, we have that
$$
I^2=\int_{0}^{\infty} \int_{0}^{2\pi} re^{-r^2} d\theta dr = \int_{0}^{2\pi} d\theta \int_{0}^{\infty} re^{-r^2} dr = 2\pi \int_{0}^{\infty} re^{-r^2} dr
$$
Now evaulating this integral of one dimension with the substitution 
$$
t=r^2 \implies \sqrt{t}=r \implies dt=2rdr \implies rdr=\frac{dt}{2}
$$
we have that

$$
\int_{0}^{\infty} re^{-r^2} dr = \int_{0}^{\infty} \frac{e^{-t}}{2} dt = \frac{1}{2} (-e^{-t})|_{0}^{\infty}) = \frac{1}{2} (0-(-1)) = \frac{1}{2}
$$

Finally, we have that

$$
I^2 = 2\pi \int_{0}^{\infty} re^{-r^2} dr = 2\pi (\frac{1}{2}) = \pi
$$

With

$$
I^2=\pi
$$

we have that 

$$
I=\sqrt(\pi) \implies \int_{-\infty}^{\infty} e^{-x^2} dx
$$
