---
author: Owen Drummond
title: Dirichlet Integral - Two Ways
date: 2023-07-02
description: Dirichlet Integral - Two Ways
math: true
tags: ["Calculus"]
---

Here we will solve the Dirichlet Integral using two different techniques. The Dirichlet Integral is defined as
$$
\int_{0}^{\infty} \frac{\sin(x)}{x} dx
$$

### Feynman Integration

We employ Feynman's Integration trick here by first defining the function
$$
I(\alpha)=\int_{0}^{\infty} \frac{\sin(x)}{x} e^{-\alpha x} dx
$$

and notice that because 
{{< math.inline >}}
\(|\frac{\sin(x)}{x}| \leq 1 \)
{{</ math.inline >}} 

$$
\lim_{\alpha \rightarrow \infty 0} |\int_{0}^{\infty} \frac{\sin(x)}{x} e^{-\alpha x} dx| \leq \int_{0}^{\infty} e^{-\alpha x} dx = \frac{1}{\alpha}
$$

so 
{{< math.inline >}}
\(I(\alpha) \)
{{</ math.inline >}} 
vanishes as 
{{< math.inline >}}
\(\alpha \rightarrow \infty \)
{{</ math.inline >}} 
and thus we can continue with Fenyman's technique:
$$
\frac{\partial I(\alpha)}{\partial \alpha} = \frac{\partial}{\partial \alpha} \int_{0}^{\infty} \frac{\sin(x)}{x} e^{-\alpha x} dx = -\int_{0}^{\infty} x \frac{\sin(x)}{x} e^{-\alpha x} dx = -\int_{0}^{\infty} \sin(x) e^{-\alpha x} dx
$$
now by integration by parts, we have that
$$
-\int_{0}^{\infty} \sin(x) e^{-\alpha x} dx = -1+\alpha \int_{0}^{\infty} \cos(x) e^{-\alpha x} dx
$$

using integration by parts once more, we have that 
$$
-1+\alpha \int_{0}^{\infty} \cos(x) e^{-\alpha x} dx= -1+\alpha^2 \int_{0}^{\infty} \sin(x) e^{-\alpha x} dx = -1 - \alpha^2 I'(\alpha)
$$
and thus
$$
I'(\alpha)=-1 - \alpha^2 I'(\alpha) \implies I'(\alpha)(1+\alpha^2)=-1 \implies I'(\alpha)=-\frac{1}{1+\alpha^2}
$$

Next, observe that 

$$
\int I'(\alpha) d\alpha = \int -\frac{1}{1+\alpha^2} d\alpha = -\arctan(\alpha) + C = I(\alpha) 
$$

by the fundamental theorem of Calculus. In solving for C, we have

$$
I(\infty)=\int_{0}^{\infty} \frac{\sin(x)}{x} e^{-\infty x} dx = 0 = -\arctan(\infty) + C \implies C=\arctan(\infty)=\frac{\pi}{2}
$$

finally, we have that

$$
\int_{0}^{\infty} \frac{\sin(x)}{x} dx = I(0)= -\arctan(0)+\frac{\pi}{2}=\frac{\pi}{2}
$$

and thus
$$
\boxed{\int_{0}^{\infty} \frac{\sin(x)}{x} dx = \frac{\pi}{2}}
$$

### Contour Integration

Here, we will use Cauchy's Residue Theorem, which states that 

$$
\oint_{C} f(z) dx = 2\pi i Res(f,C)
$$

where C is a simple closed curve. Let us define
{{< math.inline >}}
\(f(z)=e^{iz}/z\)
{{</ math.inline >}}
and note that 
{{< math.inline >}}
\(f\)
{{</ math.inline >}}
has a singularity at 
{{< math.inline >}}
\(z=0\)
{{</ math.inline >}}.
Thus, in constructing a countor for 
{{< math.inline >}}
\(f\)
{{</ math.inline >}},

we will have a path which is a semicircle of radius R traveling counterclockwise, then on the real axis across an smaller semicircle radius 
{{< math.inline >}}
\(\epsilon\)
{{</ math.inline >}}

![Contour](IMG_1442.svg)

the result of the integral along this path C is 

$$
\oint_C f(z) dz = \int_{\Gamma} f(z) dx + \int_{\gamma} f(z) dx + \int_{-R}^{-\epsilon} f(z) dz + \int_{\epsilon}^{R} f(z) dz
$$

We want to examine the case where
{{< math.inline >}}
\(R \rightarrow \infty\)
{{</ math.inline >}}
and 
{{< math.inline >}}
\(\epsilon \rightarrow 0\)
{{</ math.inline >}} since these are the bounds of our integral.
Firstly, note that because 
{{< math.inline >}}
\(f\)
{{</ math.inline >}}
has no singularities within the contour C, we observe that
$$
\oint_C f(z) dz = \oint_C \frac{e^{iz}{z}} dz = 2\pi i Res(f,C) = 2\pi i (0) = 0
$$
now solving for each integral, we have that

$$
\int_{\Gamma} f(z) dx = \int_{\Gamma} \frac{e^{iz}}{z} dz = \int_{0}^{\pi} \frac{e^{iRe^{i\theta}}}{Re^{i\theta}} iRe^{i\theta} d\theta = \int_{0}^{\pi} ie^{iRe^{i\theta}} d\theta 
$$

and now note that 
$$
|\int_{\Gamma} f(z) dx| \leq \int_{0}^{\pi} |ie^{iRe^{i\theta}}| d\theta =  \int_{0}^{\pi} |ie^{iR\cos(\theta)-R\sin(\theta)}| d\theta \leq \int_{0}^{\pi} |e^{-Rsin\theta}| d\theta 
$$

and as 
{{< math.inline >}}
\(R \rightarrow \infty , e^{-Rsin\theta} \rightarrow 0\)
{{</ math.inline >}}

so we have that 
$$
\int_{\Gamma} f(z) dx \leq \int |e^{-Rsin\theta}| d\theta \rightarrow_{R \rightarrow \infty} 0 \implies \int_{\Gamma} f(z) = 0
$$

Next,

$$
\int_{\gamma} f(z) dx = \int_{\pi}^{0} \frac{e^{i \epsilon e^{i\theta}}}{\epsilon e^{i\theta}} i \epsilon e^{i\theta} d\theta = -\int_{0}^{\pi} i e^{i \epsilon e^{i\theta}} d\theta
$$ 

and note that as 
{{< math.inline >}}
\(\epsilon \rightarrow 0\)
{{</ math.inline >}},
{{< math.inline >}}
\(e^{i \epsilon e^{i\theta}} \rightarrow 1\)
{{</ math.inline >}}
so

$$
\int_{\gamma} f(z) dx = -\int_{0}^{\pi} i e^{i \epsilon e^{i\theta}} d\theta = -\int_{0}^{\pi} i d\theta = -i \pi
$$

so far, we have that
$$
\oint_C f(z) dz = \int_{\Gamma} f(z) dx + \int_{\gamma} f(z) dx + \int_{-R}^{-\epsilon} f(z) dz + \int_{\epsilon}^{R} f(z) dz \implies
0=0-i \pi + \int_{-R}^{-\epsilon} f(z) dz + \int_{\epsilon}^{R} f(z) dz 
$$
now as
{{< math.inline >}}
\(R \rightarrow \infty\)
{{</ math.inline >}}
and 
{{< math.inline >}}
\(\epsilon \rightarrow 0\)
{{</ math.inline >}},
we have
$$
i \pi = \int_{-\infty}^{0} f(z) dz + \int_{0}^{\infty} f(z) dz = \int_{-\infty}^{\infty} \frac{e^{iz}}{z} dz
$$
Further,
$$
\mathnormal{Im}(i \pi)= \pi =\mathnormal{Im}(\int_{-\infty}^{\infty} \frac{e^{iz}}{z} dz)=\int_{-\infty}^{\infty} \mathnormal{Im}(\frac{e^{iz}}{z}) dz= \int_{-\infty}^{\infty} \frac{\sin(x)}{x} dx
$$
so we conclude that 
$$
\pi= \int_{-\infty}^{\infty} \frac{\sin(x)}{x} dx \implies \boxed{\frac{\pi}{2} = \int_{0}^{\infty} \frac{\sin(x)}{x} dx}
$$
by the symmetry of 
$$
f(x)=\frac{\sin(x)}{x}
$$