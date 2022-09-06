---
title: Calculus-II-notes-chapt2
top: false
cover: false
toc: true
tags: 微积分
categories: Maths
abbrlink: 26ca39d5
date: 2022-06-11 16:56:57
author:
img:
coverImg:
password:
summary:
---

## 6 重积分

### 6.1 二重积分的概念和性质

#### 二重积分的概念与性质

$$
divide\ D\ into\ D_i\ deliberately. set \lambda = \max{\{D_i的直径\}} .
任取D_i内一点(\xi_i, \eta_i)的值代表整个小区域的近似值,\\ 计算黎曼和\ \sum_{i = 1}^{n}f(\xi_i, \eta_i)\Delta\sigma_i.\\
let\ \lambda \rightarrow 0, V = \lim_{\lambda\rightarrow0}\sum_{i = 1}^{n}f(\xi_i, \eta_i)\Delta\sigma_i\stackrel{\mathrm{def}}{=}\displaystyle \iint_{D} f(x,y)d\sigma
$$

#### 二重积分的可积条件

- 连续
- 上有界 间断点分布在D内有限条光滑曲线上

#### 性质

- 常数可以提出来
- 积分区域的可加性
- 保向性
- ==估值性质==
  - $m \leq {1\over \sigma(D)}\displaystyle \iint f(x,y)d\sigma \leq M$
- 绝对值性质
  - $|\displaystyle \iint f(x,y)d\sigma| \le \iint |f(x,y|d\sigma$

- 对称性质（利用被积函数奇偶性）

定理  (中值定理 1) 设 $D \subset \mathbb{R}^{2}$ 为有界闭区域, 函数 $f(x, y), g(x, y)$ 在 $D$ 上连续, 且对任意的 $(x, y) \in D, g(x, y) \geqslant 0($ 或 $\leqslant 0)$, 则存在 $(\xi, \eta) \in D$, 使得
$$
\iint_{D} f(x, y) g(x, y) \mathrm{d} \sigma=f(\xi, \eta) \iint_{D} g(x, y) \mathrm{d} \sigma
$$
特别的, 取 $g(x, y) \equiv 1$, 有
定理 (中值定理 2) 设 $D \subset \mathbb{R}^{2}$ 为有界闭区域, 函数 $f(x, y)$ 在 $D$ 上连续, 则存在 $(\xi, \eta) \in D$, 使得
$$
\iint_{D} f(x, y) \mathrm{d} \sigma=f(\xi, \eta) \cdot \sigma(D)
$$

### 6.2  二重积分的计算

#### 6.2.1 累次积分法

根据积分区域的形式，选择累次积分的次序，既要关注积分区域的简便划分，又要注意积分过程是否简便。



##### 积分区域形如$D=\{(x,y)|\varphi_1(x)\le y\le \varphi_2(x),a\le x\le b\}$

- 注：这也就告诉我们：固定一个x,有明确的y的变化的上下限，所以可以先对y积分，然后得到关于x的一重积分

二重积分的计算公式
$$
\iint_{D} f(x, y) \mathrm{d} x \mathrm{~d} y=\int_{a}^{b}\left(\int_{\varphi_{1}(x)}^{\varphi_{2}(x)} f(x, y) \mathrm{d} y\right) \mathrm{d} x=\int_{a}^{b} \mathrm{~d} x \int_{\varphi_{1}(x)}^{\varphi_{2}(x)} f(x, y) \mathrm{d} y .
$$
**此公式表明二重积分可化为先对 $y$, 后对 $x$ 的两次定积分.** 上式右端称为先对 $y$, 后对 $x$ 的累次 积分 (二次积分).

##### 积分区间形如$D=\left\{(x, y) \mid \psi_{1}(y) \leqslant x \leqslant \psi_{2}(y), c \leqslant y \leqslant d\right\}$

二重积分的另一计算公式
$$
\iint_{D} f(x, y) \mathrm{d} x \mathrm{~d} y=\int_{c}^{d}\left(\int_{\psi_{1}(y)}^{\psi_{2}(y)} f(x, y) \mathrm{d} x\right) \mathrm{d} y=\int_{c}^{d} \mathrm{~d} y \int_{\psi_{1}(y)}^{\psi_{2}(y)} f(x, y) \mathrm{d} x .
$$
**此公式表明二重积分可化为先对 $x$, 后对 $y$ 的累次积分.**

- 最后指出, 虽然在推导上述两个公式时, 我们假设被积函数 $f(x, y)$ 非负, 但对于一般的 $f(x, y)$, 公式 (6.2.1)、(6.2.2) 仍成立. 另外, 对于不满足公式条件的积分区域 $D$, 我们可将 $D$ 分割为若干子闭区域, 使得在每个子闭区域上满足公式的条件, 将二重积分化为累次积分, 然后应用二重积分对积分区域的可加性, 把它们相加即可.

#### 6.2.2 换元积分法

- 定理 (二重积分的换元积分公式) 设 $D$ 为平面有界闭区域, 函数 $f(x, y)$ 在 $D$ 上 连续, 函数组 $x=x(u, v), y=y(u, v)$ 在 $u v$ 平面的有界闭区域 $D^{\prime}$ 上连续可微, 使得 $D^{\prime}$ 与 $D$的点一一对应, 并且雅可比行列式

$$
J(u, v)=\frac{D(x, y)}{D(u, v)} \neq 0, \quad(u, v) \in D^{\prime},
$$

> > $Pf.M_{1}, M_{2}, M_{3}, M_{4}$ 的坐标分别为

$$
\begin{aligned}
&M_{1}\left(x\left(u_{i}, v_{i}\right), y\left(u_{i}, v_{i}\right)\right) \\
&M_{2}\left(x\left(u_{i}+\Delta u_{i}, v_{i}\right), y\left(u_{i}+\Delta u_{i}, v_{i}\right)\right) \\
&M_{3}\left(x\left(u_{i}+\Delta u_{i}, v_{i}+\Delta v_{i}\right), y\left(u_{i}+\Delta u_{i}, v_{i}+\Delta v_{i}\right)\right) \\
&M_{4}\left(x\left(u_{i}, v_{i}+\Delta v_{i}\right), y\left(u_{i}, v_{i}+\Delta v_{i}\right)\right)
\end{aligned}
$$

> > ​	由于 $x(u, v), y(u, v)$ 连续可微, 当 $\Delta u_{i}, \Delta v_{i}$ 很小时, 若不计高阶无穷小, 则有

$$
\begin{aligned}
\overrightarrow{M_{1} M_{2}} &=\left(x\left(u_{i}+\Delta u_{i}, v_{i}\right)-x\left(u_{i}, v_{i}\right), y\left(u_{i}+\Delta u_{i}, v_{i}\right)-y\left(u_{i}, v_{i}\right)\right) \\
&=\left(x_{u}^{\prime}\left(u_{i}+\theta_{1} \Delta u_{i}, v_{i}\right), y_{u}^{\prime}\left(u_{i}+\theta_{2} \Delta u_{i}, v_{i}\right)\right) \Delta u_{i} \\
& \approx\left(x_{u}^{\prime}\left(u_{i}, v_{i}\right), y_{u}^{\prime}\left(u_{i}, v_{i}\right)\right) \Delta u_{i} \quad\left(0<\theta_{1}, \theta_{2}<1\right),
\end{aligned}
$$

$$
\begin{aligned}
\overrightarrow{M_{4} M_{3}} &=\left(x\left(u_{i}+\Delta u_{i}, v_{i}+\Delta v_{i}\right)-x\left(u_{i}, v_{i}+\Delta v_{i}\right), y\left(u_{i}+\Delta u_{i}, v_{i}+\Delta v_{i}\right)-y\left(u_{i}, v_{i}+\Delta v_{i}\right)\right) \\
&=\left(x_{u}^{\prime}\left(u_{i}+\theta_{3} \Delta u_{i}, v_{i}+\Delta v_{i}\right), y_{u}^{\prime}\left(u_{i}+\theta_{4} \Delta u_{i}, v_{i}+\Delta v_{i}\right)\right) \Delta u_{i} \\
& \approx\left(x_{u}^{\prime}\left(u_{i}, v_{i}\right), y_{u}^{\prime}\left(u_{i}, v_{i}\right)\right) \Delta u_{i} \quad\left(0<\theta_{3}, \theta_{4}<1\right)
\end{aligned}
$$

> > 所以 (为了方便利用向量的运算, 我们把 2 维坐标 $(x, y)$ 写成 3 维坐标 $(x, y, 0)$ )

$$
\overrightarrow{M_{1} M_{2}} \approx \overrightarrow{M_{4} M_{3}} \approx\left(x_{u}^{\prime}\left(u_{i}, v_{i}\right), y_{u}^{\prime}\left(u_{i}, v_{i}\right), 0\right) \Delta u_{i}
$$

> >  同理可得

$$
\overrightarrow{M_{1} M_{4}} \approx \overrightarrow{M_{2} M_{3}} \approx\left(x_{v}^{\prime}\left(u_{i}, v_{i}\right), y_{v}^{\prime}\left(u_{i}, v_{i}\right), 0\right) \Delta v_{i},
$$

> >  因而曲边四边形 $M_{1} M_{2} M_{3} M_{4}$ 可近似地看作平行四边形, 它的面积为

$$
\Delta \sigma \approx\left|\overrightarrow{M_{1} M_{2}} \times \overrightarrow{M_{1} M_{4}}\right|=\left|\frac{D(x, y)}{D(u, v)}\right|_{\left(u_{i}, v_{i}\right)} \Delta u_{i} \Delta v_{i}=\left|J\left(u_{i}, v_{i}\right)\right| \Delta u_{i} \Delta v_{i},
$$

> >  所以 $\Delta \sigma$ 与 $\Delta \sigma^{\prime}$ 之比为 $\left|J\left(u_{i}, v_{i}\right)\right|$. 由于 $J(u, v)$ 在 $D^{\prime}$ 上连续且不等于 0 , 所以 $\lambda \rightarrow 0 \Longleftrightarrow$ $\lambda^{\prime} \rightarrow 0$. 由二重积分的定义得

$$
\begin{aligned}
\iint_{D} f(x, y) \mathrm{d} \sigma &=\lim _{\lambda \rightarrow 0} \sum_{i=1}^{n} f\left(x_{i}, y_{i}\right) \Delta \sigma_{i} \\
&=\lim _{\lambda^{\prime} \rightarrow 0} \sum_{i=1}^{n} f\left(x\left(u_{i}, v_{i}\right), y\left(u_{i}, v_{i}\right)\right)\left|J\left(u_{i}, v_{i}\right)\right| \Delta u_{i} \Delta v_{i} \\
&=\iint_{D^{\prime}} f(x(u, v), y(u, v))|J(u, v)| \mathrm{d} u \mathrm{~d} v
\end{aligned}
$$

​	则有换元积分公式:
$$
\iint_{D} f(x, y) \mathrm{d} \sigma=\iint_{D^{\prime}} f(x(u, v), y(u, v))|J(u, v)| \mathrm{d} u \mathrm{~d} v
$$

- 其中 $\mathrm{d} \sigma=|J(u, v)| \mathrm{d} u \mathrm{~d} v$ 是曲线坐标下的面积微元.

##### 极坐标变换

> > 在二重积分中, 极坐标换元是最常用的换元变换. 我们知道, 直角坐标与极坐标的换元 变换有公式

$$
x=\rho \cos \theta, \quad y=\rho \sin \theta
$$

> > 此时

$$
J(\rho, \theta)=\frac{D(x, y)}{D(\rho, \theta)}=\left|\begin{array}{cc}
  \cos \theta & -\rho \sin \theta \\
  \sin \theta & \rho \cos \theta
  \end{array}\right|=\rho
$$

> > 据定理 6.2.3 可得:

$$
  \iint_{D} f(x, y) \mathrm{d} \sigma=\iint_{D^{\prime}} f(\rho \cos \theta, \rho \sin \theta) \rho \mathrm{d} \rho \mathrm{d} \theta
$$

> > 其中 $D^{\prime}$ 是在极坐标变换下原积分区域 $D$ 所对应的区域, $\mathrm{d} \sigma=\rho \mathrm{d} \rho \mathrm{d} \theta$ 是极坐标下的面积 微元.

### 6.3 三重积分

#### 6.3.2 累次积分法

##### 先一后二

$$
对于积分区域为\Omega = \{(x,y,z)|z_1(x,y)\leq z(x,y) \leq z_2(x,y), (x,y)\in D\}\\
\iiint f(x,y,z)dxdydz = \iint d\sigma \int_{z_1(x,y)}^{z_2(x,y)} f(x,y,z)dz\\
进一步，对于二重积分，可以运用之前的知识，根据情况改写为\\
= \int_a^b dx\int _{y_1(x)}^{y_2{(x)}}dy \int_{z_1(x,y)}^{z_2(x,y)} f(x,y,z)dz\\
$$

##### 先二后一

$$
我们可以用一个垂直于z轴的平面截积分区域，得到足够多的“薄片”\\
每一层可以二重积分，积分区域为D(z)\\
\iiint f(x,y,z)dxdydz = \int_a^b dz \iint f(x,y,z)d\sigma\\
$$

##### 经验与技巧

- 同一道题，不同的积分顺序对计算过程的影响很大。优先对无关的变量进行积分
- 还原积分要画图确定积分区域
- 还原积分的目的：
  - 简化被积函数
  - 简化积分区域
  - 更多时候，是一种二者的权衡（Trade off）

#### 6.3.3 换元积分法

$Thm.$ (三重积分的换元积分公式) 设 $\Omega \subset \mathbb{R}^{3}$ 为有界闭区域, 函数 $f(x, y, z)$ 在 $\Omega$ 上连续, 函数组 $x=x(u, v, w), y=y(u, v, w), z=z(u, v, w)$ 在有界闭区域 $\Omega^{\prime}$ 上连续可微, 使得 $\Omega$ 与 $\Omega^{\prime}$ 的点一一对应, 并且雅可比行列式
$$
J(u, v, w)=\frac{D(x, y, z)}{D(u, v, w)}=\left|\begin{array}{lll}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} & \frac{\partial x}{\partial w} \\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v} & \frac{\partial y}{\partial w} \\
\frac{\partial z}{\partial u} & \frac{\partial z}{\partial v} & \frac{\partial z}{\partial w}
\end{array}\right| \neq 0, \quad(u, v, w) \in \Omega^{\prime}
$$
则有三重积分换元积分公式:
$$
\iint_{\Omega} \int_{\Omega} f(x, y, z) \mathrm{d} V=\iint_{\Omega^{\prime}} \int_{J} f(x(u, v, w), y(u, v, w), z(u, v, w))|J(u, v, w)| \mathrm{d} u \mathrm{~d} v \mathrm{~d} w .
$$
其中 $\mathrm{d} V=|J(u, v, w)| \mathrm{d} u \mathrm{~d} v \mathrm{~d} w$ 是曲线坐标下的体积微元.

##### 柱坐标变换

采用柱坐标计算三重积分时, 雅可比行列式
$$
J(\rho, \theta, z)=\frac{D(x, y, z)}{D(\rho, \theta, z)}=\left|\begin{array}{ccc}
\cos \theta & -\rho \sin \theta & 0 \\
\sin \theta & \rho \cos \theta & 0 \\
0 & 0 & 1
\end{array}\right|=\rho,
$$
据定理 6.3.1 可得
$$
\iiint_{\Omega} f(x, y, z) \mathrm{d} x \mathrm{~d} y \mathrm{~d} z=\iiint_{\Omega^{\prime}} f(\rho \cos \theta, \rho \sin \theta, z) \rho \mathrm{d} \rho \mathrm{d} \theta \mathrm{d} z,
$$
其中 $\mathrm{d} V=\rho \mathrm{d} \rho \mathrm{d} \theta \mathrm{d} z$ 是柱坐标下的体积微元.

##### 球坐标变换

点 $M$ 的直角坐标 $(x, y, z)$ 与其球坐标 $(r, \varphi, \theta)$ 之间有关系式
$$
x=r \sin \varphi \cos \theta, \quad y=r \sin \varphi \sin \theta, \quad z=r \cos \varphi,
$$
此式称为球坐标变换.

-采用球坐标计算三重积分时, 雅可比行列式
$$
J(r, \varphi, \theta)=\frac{D(x, y, z)}{D(r, \varphi, \theta)}=\left|\begin{array}{ccc}
\sin \varphi \cos \theta & r \cos \varphi \cos \theta & -r \sin \varphi \sin \theta \\
\sin \varphi \sin \theta & r \cos \varphi \sin \theta & r \sin \varphi \cos \theta \\
\cos \varphi & -r \sin \varphi & 0
\end{array}\right|=r^{2} \sin \varphi,
$$
据定理 6.3.1 可得
$$
\iiint_{\Omega} f(x, y, z) \mathrm{d} x \mathrm{~d} y \mathrm{~d} z=\iint_{\Omega^{\prime}} f(r \sin \varphi \cos \theta, r \sin \varphi \sin \theta, r \cos \varphi) r^{2} \sin \varphi \mathrm{d} r \mathrm{~d} \varphi \mathrm{d} \theta,
$$
其中 $\mathrm{d} V=r^{2} \sin \varphi \mathrm{d} r \mathrm{~d} \varphi \mathrm{d} \theta$ 是球坐标下的体积微元.
一般情况下, 如果积分区域中含有球面、雉面或过 $z$ 轴的半平面, 采用球坐标会比较简 单. 将三重积分化为球坐标下的三重积分后, 还要将它化为球坐标下的累次积分, 这时, 一般 情况下最先对 $r$ 积分, 然后对 $\varphi$ 积分, 最后对 $\theta$ 积分. 

##### 广义球坐标变换

例 6.3.9 计算三重积分 $\iiint_{\Omega} x^{2} \mathrm{~d} x \mathrm{~d} y \mathrm{~d} z$, 其中 $\Omega$ 是椭球体 $\frac{x^{2}}{a^{2}}+\frac{y^{2}}{b^{2}}+\frac{z^{2}}{c^{2}} \leqslant 1$. 解 采用广义球坐标变换, 令
$$
x=a r \sin \varphi \cos \theta, \quad y=b r \sin \varphi \sin \theta, \quad z=c r \cos \varphi,
$$
雅可比行列式
$$
J(r, \varphi, \theta)=\left|\begin{array}{ccc}
a \sin \varphi \cos \theta & a r \cos \varphi \cos \theta & -a r \sin \varphi \sin \theta \\
b \sin \varphi \sin \theta & b r \cos \varphi \sin \theta & b r \sin \varphi \cos \theta \\
c \cos \varphi & -c r \sin \varphi & 0
\end{array}\right|=a b c r^{2} \sin \varphi
$$
在球坐标下将 $\Omega$ 变为 $\Omega^{\prime}$, 其中
$$
\Omega^{\prime}: \quad 0 \leqslant r \leqslant 1, \quad 0 \leqslant \varphi \leqslant \pi, \quad 0 \leqslant \theta \leqslant 2 \pi,
$$

### 6.4 重积分的应用

#### 6.4.1  重积分在几何上的应用

##### 立体的体积

### 广义重积分



