---
author: Owen Drummond
title: First Fundamental Form
date: 2023-05-04
description: Overview of the First Fundamental Form
math: true
tags: ["Geometry"]
---

In this article, we will examine the nature and utility of the first fundamental form, a quadratic form on a surface. Given a curve parametrized by 
{{< math.inline >}}
\(u=u(t)\)
{{</ math.inline >}}
and
{{< math.inline >}}
\(v=v(t)\)
{{</ math.inline >}}
which lies on a surface 
{{< math.inline >}}
\(X\)
{{</ math.inline >}}
parametrized by
{{< math.inline >}}
\(X=X(u,v)\)
{{</ math.inline >}}
we have that 
$$
ds=|\frac{dX}{dt}|dt=|X_{u} \frac{du}{dt} + X_{v} \frac{dv}{dt}|dt = \sqrt{(X_u \dot{u} + X_v \dot{v}}) \dot (X_u \dot{u} + X_v \dot{v}})}dt
$$
Now defining the coefficients, called the First Fundamental Form coefficients E, F and G, we have 
$$
E=X_u \dot X_u, F=X_u \dot X_v, G=X_v \dot X_v
$$
and moreover,
$$
\sqrt{(X_u \dot{u} + X_v \dot{v}}) \dot (X_u \dot{u} + X_v \dot{v}})} = \sqrt{Edu^2 + 2F du dv + Gdv^2}
$$
by direct computation. Now the **First Fundamental Form**, denoted I, is defined as
$$
I=ds^2=dX \dot dX = Edu^2 + 2F du dv + Gdv^2
$$
This quadratic form allows us to derive the curvature and metric properties of any surface, namely arc length and area. We see that 
$$
(X_{u} \cross X_{v})^2=(X_{u} \cross X_{v}) \dot (X_{u} \cross X_{v}) = (X_{u} \dot X_{u})(X_{v} \dot X_{v})-(X_{u} \dot X_{v})^2=EG - F^2 \geq 0
$$ 
and because 
{{< math.inline >}}
\(E>0\)
{{</ math.inline >}}
we have that I is positive definite, i.e. 
{{< math.inline >}}
\(I \geq 0\)
{{</ math.inline >}}
and 
{{< math.inline >}}
\(I=0 \iff du=dv=0\)
{{</ math.inline >}}
It is worth nothing that I also has the symmetric matrix representation
$$
I=x^T \begin{bmatrix}
E & F \\
F & G 
\end{bmatrix} y
$$
where
{{< math.inline >}}
\(x,y\)
{{</ math.inline >}}
are vectors in 
{{< math.inline >}}
\mathbb(R)^3
{{</ math.inline >}}