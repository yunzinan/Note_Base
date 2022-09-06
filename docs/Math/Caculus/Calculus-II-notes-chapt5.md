---
title: Calculus-II-notes-chapt5
top: false
cover: false
toc: true
tags: 微积分
categories: Maths
abbrlink: b8aeac76
date: 2022-06-11 16:58:11
author:
img:
coverImg:
password:
summary:
---

## 9 傅里叶级数

### 9.1 三角级数·三角函数系的正交性

#### 傅里叶级数（三角级数）形式

$$
{a_0\over 2} + \sum_{n=1}^\infin (a_n \cos nx + b_n \sin nx)
$$

### 9.1 习题

### 9.2 函数展开成傅里叶级数

$$
a_n = {1\over \pi} \int_{-\pi}^{\pi}f(x)\cos nx\ dx, n = 0, 1, 2, \cdots\\
b_n = {1\over \pi} \int_{-\pi}^{pi}f(x) \sin nx\ dx, n = 1, 2, \cdots.
$$

#### Dirichlet收敛定理

$$
设f(x)是周期为2\pi的周期函数，如果它满足，\\
\begin{align}
(1)& f(x)在[-\pi, \pi]上连续或有有限个第一类间断点（左右极限都存在）\\
(2)& f(x)在[-\pi,\pi]上至多只有有限个严格极值点，即函数分段单调.\\
&则函数的傅里叶级数收敛，且\\
&{a_0\over 2} + \sum_{n=1}^\infin (a_n \cos nx + b_n \sin nx) = \begin{cases}f(x),& x为f(x)连续点\\ {f(x^-) + f(x^+)\over 2},& x为f(x)间断点.\end{cases}
\end{align}
$$

### 9.2 习题
