---
author: Owen Drummond
title: Orthonormal Vectors are Linearly Independent
date: 2023-04-13
description: Proof that any set of orthonormals in a vector space are linearly independent
math: true
tags: ["Geometry"]
---

For a set of orthonormal vectors 
{{< math.inline >}}
\((v_1,v_2,...,v_m)\)
{{</ math.inline >}}
in an m-dimensional vector space
, and set of constants 
{{< math.inline >}}
\(r_1,r_2,...r_m \in \mathbb{R}\)
{{</ math.inline >}}
, if we consider the equation
{{< math.inline >}}
\(r_1v_1+r_2v_2+...+r_mv_m=0\)
{{</ math.inline >}} 
with the objective of demonstrating that the vectors in
{{< math.inline >}}
\((v_1,v_2,...,v_m)\)
{{</ math.inline >}} 
are linearly independent, then we must show that 
{{< math.inline >}}
\(r_1=r_2=...=r_m=0\)
{{</ math.inline >}}. If we take the inner product on both sides of the equation , we have that 

$$
<r_1v_1+r_2v_2+...+r_mv_m, v_1> = <0,v_1>
$$

Using the properties of inner products, we have that 

$$
r_1<v_1,v_1> +r_2<v_2,v_1> ... +r_m<v_m,v_1> = 0 \implies r_1=0
$$

Repeating the same process but isolating 
{{< math.inline >}}
\(v_2,v_3,...\)
{{</ math.inline >}} 
on the right hand side using inner products, we will deduce that 
{{< math.inline >}} 
\(r_2=r_3=...=r_m=0\)
{{</ math.inline >}}
. Thus, since 

$$
\(r_1v_1+r_2v_2+...+r_mv_m \iff r_1=r_2=...=r_m=0\)
$$

 , we conclude that 
{{< math.inline >}}
\((v_1,v_2,...,v_m)\)
{{</ math.inline >}} is linearly independent. 
          