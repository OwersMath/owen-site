---
author: Owen Drummond
title: The Space of Invertible Matricies is Dense in the Space of All Matricies
date: 2023-04-13
description: Analytical Proof from Linear Algebra
math: true
tags: ["Geometry"]
---

To proof that the space of all invetible matricies is dense in the space of all matricies, it will suffice to show that the space of all invertible matricies is dense the space of matricies with distinct eigenvalues, as the space of matricies with distinct eigenvalues is dense in the space of all matricies. Denote E(n, {{< math.inline >}} \(\mathbb{R}\) {{</ math.inline >}}) as the space of matricies with n distinct eigenvalues. Formally,

$$
E(n, \mathbb{R}) = {\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\\
a_{21} & a_{22} & \cdots & a_{2n} \\\
\vdots & \vdots & \ddots & \vdots    \\\
a_{n1} & a_{n2} & \cdots & a_{nn} \\\
\end{bmatrix} : a_{ij} \in \mathbb{R}, and \lambda_{1}, \lambda_{2}, ... \lambda_{n} all distinct evalues
$$

Now, by Schuer's Thm, we have that {{< math.inline >}} \(\exists \) {{</ math.inline >}} a unitary matrix U and upper triangular matrix D such that for any {{< math.inline >}} \(E_0 \in E(n,\mathbb{R}) \) {{</ math.inline >}} we have that {{< math.inline >}} \(E_0 = UDU^{-1}  \) {{</ math.inline >}}, where {{< math.inline >}} \(D = \begin{bmatrix}
\alpha_{1} & c_{12} & \cdots & c_{1n} \\\
0 & \alpha_{2} & c_{23} & ... & c_{2n} \\\
\vdots & \vdots & \ddots & \vdots    \\\
0 & \cdots & \cdots & \alpha_{n} \\\  \) {{</ math.inline >}}, where {{< math.inline >}} \(\alpha_{1}, ..., \alpha_{n} \) {{</ math.inline >}} are the distinct eigenvalues of {{< math.inline >}} \(E_{0} \) {{</ math.inline >}} and {{< math.inline >}} \(c_{ij} \in \mathbb{R} \) {{</ math.inline >}}. Now for each n, {{< math.inline >}} \(\exists \epsilon_{1}^m, \epsilon_{2}^m, ..., \epsilon_{n}^m \) {{</ math.inline >}} such that {{< math.inline >}} \(\epsilon_{i}^{m} \rightarrow 0 \) {{</ math.inline >}} as {{< math.inline >}} \(m \rightarrow \infty \) {{</ math.inline >}} and {{< math.inline >}} \(\alpha_{i}^{m} = \alpha_{i} + \epsilon_{i}^{m} \neq 0 \) {{</ math.inline >}} for {{< math.inline >}} \(1 \leq i \leq n \) {{</ math.inline >}} and all {{< math.inline >}} \(\alpha_{i}^{m} \) {{</ math.inline >}} are distinct. Set {{< math.inline >}} \(D^m = \begin{bmatrix}
\alpha_{1}^{m} & \tilde{c_{12}} & \cdots & \tilde{c_{1n}} \\\
0 & \alpha_{2}^{m} & \tilde{c_{23}} & ... & \tilde{c_{2n}} \\\
\vdots & \vdots & \ddots & \vdots    \\\
0 & \cdots & \cdots & \alpha_{n}^{m} \\\  \) {{</ math.inline >}}, and {{< math.inline >}} \(A^m=UD^{m}U^{*} \) {{</ math.inline >}}. Because {{< math.inline >}} \(A^m \) {{</ math.inline >}} is constructed in such a way that {{< math.inline >}} \(\alpha_{1}^{m}, ..., \alpha_{n}^{m} \) {{</ math.inline >}} are the eigenvalues of {{< math.inline >}} \(A^m \) {{</ math.inline >}}, {{< math.inline >}} \(A^m \) {{</ math.inline >}} has n distinct non-zero eigenvalues, and thus {{< math.inline >}} \(A^m \) {{</ math.inline >}} is invertible. Finally, 
$$
A-A^m=UDU^{*}-UD^{m}U^{*}=U(D-D^{m})U^{*} \implies ||A-A^m|| \leq ||U|| ||D-D^m|| ||U^{*}|| = ||D-D^{m}|| \rightarrow 0 \textnormal{as} m \rightarrow \infty
$$
Thus, the spaces of all {{< math.inline >}} \(n \times n \) {{</ math.inline >}} invertible matricies is dense in {{< math.inline >}} \(E(n, \mathbb{R} \) {{</ math.inline >}}, which suffices to show that the space of all {{< math.inline >}} \(n \times n \) {{</ math.inline >}} matricies is dense in  {{< math.inline >}} \(M(n, \mathbb{R} \) {{</ math.inline >}}, the space of all {{< math.inline >}} \(n \times n \) {{</ math.inline >}} matricies since {{< math.inline >}} \(E(n, \mathbb{R} \) {{</ math.inline >}} is dense in {{< math.inline >}} \(M(n, \mathbb{R} \) {{</ math.inline >}}. 