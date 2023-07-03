---
author: Owen Drummond
title: Integral of the Day - 7/2/2023
date: 2023-07-02
description: Integral of the day - 7/2/2023
math: true
tags: ["Calculus"]
---

Today, we will be evaluating the integral 
$$
\int_{-\infty}^{\infty} e^{ax^2+bx+c} dx \hspace{1cm} a \in \mathbb{R^{-}}, b \in \mathbb{R}, c \in \mathbb{R}
$$
The restriction of 
{{< math.inline >}}
\(a\)
{{</ math.inline >}}
to 
{{< math.inline >}}
\(\mathbb{R^{-}}\)
{{</ math.inline >}}
is required for the convergence of this integral. My thought process for this integral was initially to minipulate the integrand in such a way that we can employ the result of the Gaussian integral, namely, 
{{< math.inline >}}
\(\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}\)
{{</ math.inline >}}
. To do this, we complete the square on 
{{< math.inline >}}
\(f(x)=ax^2+bx+c\)
{{</ math.inline >}}
:
$$
y=ax^2+bx+c \implies y-c=ax^2+bx=a(x^2+\frac{b}{a}x) \implies \frac{y-c}{a}=x^2+\frac{b}{a}x
$$
Further,
$$
\frac{y-c}{a}+\frac{b^2}{4a^2}=x^2+\frac{b}{a}x+\frac{b^2}{4a^2} \implies \frac{y-c}{a}=(x+\frac{b}{2a})^2-\frac{b^2}{4a^2}
$$
Lastly,
$$
y=a(x+\frac{b}{2a})^2-\frac{b^2}{4a}+c
$$
Thus we have that
$$
I=\int_{-\infty}^{\infty} e^{ax^2+bx+c} dx=\int_{-\infty}^{\infty} e^{a(x+\frac{b}{2a})^2-\frac{b^2}{4a}+c} dx=e^{-\frac{b^2}{4a}+c} \int_{-\infty}^{\infty} e^{a(x+\frac{b}{2a})^2} dx
$$
Given that this integrand spans all of 
{{< math.inline >}}
\(\mathbb{R}\)
{{</ math.inline >}}
we can employ the substitution
{{< math.inline >}}
\(t=x+\frac{b}{2a}\)
{{</ math.inline >}}
and our bounds will remain the same. Thus,
$$
I=e^{-\frac{b^2}{4a}+c} \int_{-\infty}^{\infty} e^{at^2} dt
$$
and since 
{{< math.inline >}}
\(a\)
{{</ math.inline >}}
is negative, we can write 
$$
I=e^{-\frac{b^2}{4a}+c} \int_{-\infty}^{\infty} e^{-(\sqrt{-a}t)^2} dt
$$
Now letting 
{{< math.inline >}}
\(v=\sqrt{-a}t\)
{{</ math.inline >}}
we have that 
{{< math.inline >}}
\(dv=\sqrt{-a} dt \implies \frac{dv}{\sqrt{-a}}=dt\)
{{</ math.inline >}}
and thus
$$
I=e^{-\frac{b^2}{4a}+c} \int_{-\infty}^{\infty} e^{-(v)^2} \frac{dv}{\sqrt{-a}} \implies I=\frac{e^{-\frac{b^2}{4a}+c}}{\sqrt{-a}} \sqrt{\pi} = e^{-\frac{b^2}{4a}+c} \sqrt{-\frac{\pi}{a}}
$$
and we're done.