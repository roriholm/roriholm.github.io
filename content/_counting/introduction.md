---
title: Introduction
lesson: 1
---

I want to lay out some basic logic for counting things: Permutations, combinations, etc.

An alphabet of size $$n$$. The alphabet is a set of letters $$A = \{\alpha_1, \alpha_2, \dots, \alpha_n\}$$.

Let's start with the basic concept of a **string**.

Choose some number of elements in a row. $$\alpha_1 alpha_3 alpha_8 alpha_{44}$$.

$$|A| = n$$

A lot of counting problems become easier when you put them in terms of strings.

**Permutations** are strings that use every letter __exactly__ once.

**Combinations** are strings that use every letter __at most__ once.

$$
\begin{align*}
  & \phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right)
  = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \\
  & (x_1, \ldots, x_n) \left( \begin{array}{ccc}
      \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \\
      \vdots & \ddots & \vdots \\
      \phi(e_n, e_1) & \cdots & \phi(e_n, e_n)
    \end{array} \right)
  \left( \begin{array}{c}
      y_1 \\
      \vdots \\
      y_n
    \end{array} \right)
\end{align*}
$$
