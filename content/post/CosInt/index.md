---
author: Owen Drummond
title: The Most Beautiful Result in Calculus
date: 2023-07-21
description: The Most Beautiful Result in Calculus
math: true
tags: ["Calculus"]
---

Today, we will evaluate the integral 
$$
\int_{-\infty}^{\infty} \frac{\cos(x)}{x^2+1} dx
$$
using Cauchy's Residue Theorem and contour integration. This is one of the most beautiful results in all of calculus, and the solution is rather elegant. To begin, let us define the following function in 
{{< math.inline >}}
\(\mathbb{C}\)
{{</ math.inline >}}:
$$
f(z)=\frac{e^{iz}}{x^2+1}
$$
and let us use the canonical contour, that is, the top half of a semicircle in the complex plane. Let us define this contour as 
{{< math.inline >}}
\(C\)
{{</ math.inline >}}
, with radius 
{{< math.inline >}}
\(R\)
{{</ math.inline >}}. Note that 
{{< math.inline >}}
\(f(z)\)
{{</ math.inline >}}
had two singularities, one at 
{{< math.inline >}}
\(z=-i\)
{{</ math.inline >}}
and the other at
{{< math.inline >}}
\(z=i\)
{{</ math.inline >}}.
Only 
{{< math.inline >}}
\(z=i\)
{{</ math.inline >}}
is inside of our contour 
{{< math.inline >}}
\(C\)
{{</ math.inline >}}, as seen below:

![C](IMG_1663.png)

Taking the residue of 
{{< math.inline >}}
\(f(z)\)
{{</ math.inline >}}
within this contour, because 
{{< math.inline >}}
\(f(z)\)
{{</ math.inline >}}
only has one singularity at 
{{< math.inline >}}
\(z=i\)
{{</ math.inline >}}
we compute that
$$
Res(f,C)=Res(f,i)=(z-i)\frac{e^{iz}}{(z-i)(z+i)}\rvert_{z=i}=\frac{e^{-1}}{2i}=\frac{1}{2ie}
$$
and thus we have that
$$
\oint_{C} f(z) dx = 2\pi i Res(f,C) = \frac{2\pi i}{2ie} = \frac{\pi}{e}
$$
Now looking at 
{{< math.inline >}}
\(C\)
{{</ math.inline >}}
we have that this contour is made up two other ones, one we can denote 
{{< math.inline >}}
\(\Gamma\)
{{</ math.inline >}},
which is the semicircle itself,
and the other we can denote
{{< math.inline >}}
\(\gamma \)
{{</ math.inline >}}
which is the line from -R to R on the real axis
thus, we have that
$$
\oint_{C} f(z) dz = \int_{\Gamma} f(z) dz + \int_{\gamma} f(z) dz
$$
and we would like to examine the case where 
{{< math.inline >}}
\(R \rightarrow \infty \)
{{</ math.inline >}} . First, computing the integral 
{{< math.inline >}}
\(\int_{\Gamma} f(z) dz \)
{{</ math.inline >}}
we make the substitution 
{{< math.inline >}}
\(z=Re^{i \theta} \implies dz=iRe^{i \theta} d\theta \)
{{</ math.inline >}}
so that 
$$
\int_{\Gamma} \frac{e^{iz}}{z^2+1} dz = \int_{0}^{\pi} \frac{e^{iRe^{i\theta}}}{(Re^{i\theta})^2+1} iRe^{i \theta} d\theta
$$
next, we observe that 
$$
|\int_{\Gamma} \frac{e^{iz}}{z^2+1} dz| \leq \int_{\Gamma} |\frac{e^{iz}}{z^2+1}| dz = \int_{0}^{\pi} |\frac{e^{iRe^{i\theta}}}{(Re^{i\theta})^2+1} iRe^{i \theta}| d\theta = |i||R| \int_{0}^{\pi} |e^{i(\theta+iRe^{i\theta})}|\frac{1}{R^2e^{2i\theta}+1}| d\theta
$$
and using the identity from complex analysis that
{{< math.inline >}}
\(|e^{ia}|=1 \)
{{</ math.inline >}},
we have that 
{{< math.inline >}}
\(|e^{i( \theta+iRe^{i \theta})}|=1 \)
{{</ math.inline >}} . So all in all, we have that
$$
|\int_{\Gamma} \frac{e^{iz}}{z^2+1} dz| \leq R \int_{0}^{\pi} |\frac{1}{R^2e^{2i\theta}+1}| d\theta
$$
since 
{{< math.inline >}}
\(|i|=1 \)
{{</ math.inline >}}
and 
{{< math.inline >}}
\(|R|=R \)
{{</ math.inline >}}.
Next, examining the denominator of our integrand, we have that
$$
|R^2e^{2i\theta}+1|=|R^2e^{2i\theta} - (-1)| \geq ||R^2e^{2i\theta}|-1|=||R^2|-1|=R^2-1
$$
so this implies that
$$
\frac{1}{|R^2e^{2i\theta}+1|} \leq R^2-1
$$
so now we have that 
$$
R \int_{0}^{\pi} |\frac{1}{R^2e^{2i\theta}+1}| \leq R \int_{0}^{\pi}\frac{1}{R^2+1} d\theta = \frac{R}{1+R^2} \pi
$$
and because
{{< math.inline >}}
\(1+R^2\)
{{</ math.inline >}} dominates
{{< math.inline >}}
\(R \)
{{</ math.inline >}}
we have that 
$$
\lim_{R \rightarrow \infty} \frac{R}{1+R^2} = 0
$$
and because 
$$
|\int_{\Gamma} f(z) dz| \leq \frac{R}{1+R^2} \pi
$$
we have that
{{< math.inline >}}
\(|\int_{\Gamma} f(z) dz| \rightarrow 0\)
{{</ math.inline >}}
as
{{< math.inline >}}
\(R \rightarrow \infty\)
{{</ math.inline >}}
which leads us to conclude that
$$
\int_{\Gamma} f(z) dz=0
$$
Thus, we are just left with
$$
\oint_{C} f(z) dz = \frac{\pi}{e}=\int_{\Gamma} f(z) dz +\int_{\gamma} f(z) dz = \int_{\gamma} f(z) dz
$$
so we have that
$$
\frac{\pi}{e}=\int_{\gamma} f(z) dz=\lim_{R \rightarrow \infty} \int_{-R}^{R} \frac{e^{iz}}{z^2+1} dz =  \int_{-\infty}^{\infty} \frac{e^{ix}}{x^2+1} dx
$$
further, because
$$
e^{iz}=\cos(z)+i\sin(z)
$$
we can write
$$
\int_{-\infty}^{\infty} \frac{e^{ix}}{x^2+1} dx = \int_{-\infty}^{\infty} \frac{\cos(x)+i\sin(x)}{x^2+1} dx = \int_{-\infty}^{\infty} \frac{\cos(x)}{x^2+1} dx + \int_{-\infty}^{\infty} \frac{\sin(x)}{x^2+1} dx
$$
and note that because
$$
f(x)=\frac{\sin(x)}{x^2+1} dx
$$
is an odd function, by symmetry, we have that 
$$
\int_{-\infty}^{\infty} \frac{\sin(x)}{x^2+1} dx=0
$$
So finally, we have that 
$$
\oint_{C} f(z) dz = \frac{\pi}{e} = \int_{-\infty}^{\infty} \frac{\cos(x)}{x^2+1} dx + \int_{-\infty}^{\infty} \frac{\sin(x)}{x^2+1} dx
$$
which yields
$$
\boxed{\int_{-\infty}^{\infty} \frac{\cos(x)}{x^2+1} dx=\frac{\pi}{e}}
$$