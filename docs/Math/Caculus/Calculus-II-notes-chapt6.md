---
title: Calculus-II-notes-chapt6
top: false
cover: false
toc: true
tags: 微积分
categories: Maths
abbrlink: 21a7fdcc
date: 2022-06-11 16:58:35
author:
img:
coverImg:
password:
summary:
---

## 10 常微分方程初步

### 10.1 微分方程的基本概念

#### 常微分方程 偏微分方程

#### 通解 奇解

#### 解的形式

- 显式给出:$y = f(x)$.
- 隐式通解(**通积分**): $\Phi(x, C_1,C_2, \cdots, C_n) = 0$

### 10.2 一阶微分方程的初等解法

#### 可分离类型

$$
{d y\over dx} = f(x)g(y)\\
\Rightarrow {dy\over g(y)} = f(x)dx.
$$

#### 几种可化为可分离类型

- $$
  {dy \over dx} = f({y\over x}).\\
  令u = {y\over x} \Rightarrow {dy \over dx} = u + x\cdot {du\over dx}
  $$

- $$
  {dy\over dx} = {a_1x + b_1 y + c_1 \over a_2 x +b_2 y + c_2}\\
  令\begin{cases} u = a_1x + b_1 y + c_1\\
  v = a_2 x +b_2 y + c_2
  \end{cases}\\
  解一个二元一次方程组得到dx, dy.\\
  可能还要用上一种方法再换一次元.
  $$

- 观察法: $u = xy, u = ax + by$, etc.

### 10.3 一阶线性微分方程

#### 解法的推导

$$
考虑一阶线性常微分方程的形式,\\
y' + P(x)y = Q(x)\\
我们给等式两端乘以一个不为零的\bold{积分因子}\mu(x) \\
\mu(x)y' + \mu(x)P(x)y = \mu(x)Q(x)\quad (*)\\
另外的,我们可以设\\
\mu y' + \mu P y =  (\mu y)'\quad(**)\\
\iff \mu P y = \mu' y \iff \mu ' = \mu P\\
\Rightarrow \mu(x) = e^{\int P(x)dx}\\
由(*)(**)\\
(\mu y)' = \mu Q\\
由此得到通积分,\\
\mu(x) y = \int \mu(x) Q(x) dx +C\\
\Rightarrow y =(\mu (x))^{-1} [\int \mu(x) Q(x) dx +C],\\
式中\mu(x) = e^{\int P(x)dx}.
$$



#### Bournelli方程

$$
对于一阶常微分方程的更广泛形式,\\
y' + Py = Qy^\alpha,\\
当y \ne 0时,两边同乘y^{-\alpha},\\
y^{-\alpha}y' + Py^{1-\alpha} = Q.\\
\iff {1\over 1- \alpha}\cdot {d(y^{1-\alpha})\over dx} +  Py^{1-\alpha} = Q\\
令u = y^{1-\alpha},\\
\Rightarrow u' + (1 - \alpha)Pu = (1-\alpha ) Q.\\
于是方程转化为关于u(x) 的线性微分方程.
$$















### 10.4 全微分方程与积分因子

### 10.6 高阶微分方程

### 10.6.2 二阶线性方程

#### 线性相关性的判断

- 线性无关
  $$
  \begin{align}
  (1)& Wronski \to \exist x_0\in [a,b], s.t.\quad W(x_0) \ne 0\\
  \Rightarrow (2)& Liouville \to \forall x \in [a,b], W(x) \ne 0.
  \end{align}
  $$

- 线性相关
  $$
  \begin{align}
  (1)& Liouville \to \forall x \in [a,b], W(x) = 0.\\
  (2)& Wronski \to \exist x_0\in [a,b], s.t.\quad W(x_0) = 0.\\
  
  \end{align}
  $$

### 10.7 级数与微分方程

- 例子: $1 + x + x^2 +\cdots =  {1\over 1- x}$

> **观察**
>
> 法一: 
> $$
> S(x) = 1 + x + x^2 + x^3 + \cdots\\
> xS(x) = x +x^2 +x^3 + \cdots =  S(x) -  1.\\
> \Rightarrow xS(x) = S(x) -1.\\
> $$
> 法二:
> $$
> S'(x) = 1+ 2x + 3x^2 +\cdots\\
> xS'(x) =  x + 2x^2 + 3x^3 + \cdots\\
> (1-x)S'(x) = S(x)\\
> \iff y'(1-x) = y
> $$

例10.7.3 求级数$\displaystyle 1+ \sum {(2n-1)!!\over 2^n\cdot n!}x^n$的和函数$S(x)$.

> $$
> S'(x) =\displaystyle  \sum_{n=1}^\infin {(2n-1)!!\over 2^n\cdot (n-1)!}x^{n-1}  = {1\over 2} + \sum_{n=2}^\infin {(2n-1)!!\over 2^n\cdot (n-1)!}x^{n-1} = {1\over 2} + \sum_{n=1}^\infin {(2n+1)!!\over 2^{n+1}\cdot (n)!}x^{n}\\
> xS'(x) = \sum {(2n-1)!!\over 2^n\cdot (n-1)!}x^{n} = \sum {(2n-1)!!\cdot n\over 2^n\cdot (n-1)!\cdot n}x^{n}\\
> S'(x) - xS'(x) = {1\over 2} + \sum_{n=1}^\infin {(2n-1)!!\over 2^nn!}({2n+1\over 2} -n)x^n  = {1\over 2} +{1\over 2}\sum {(2n-1)!!\over 2^n\cdot n!}x^n = {1\over 2 }S(x)\\
> \Rightarrow y'- xy' = {1\over 2 } y\quad y|_{x= 0} = 1 \quad y'|_{x=0} = {1\over 2}.
> $$
>
> 

