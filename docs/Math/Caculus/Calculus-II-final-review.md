---
title: 微积分II期末复习
top: false
cover: false
toc: true
tags: 微积分
categories: Maths
abbrlink: 6ad1be83
date: 2022-06-11 16:52:35
author:
img:
coverImg:
password:
summary:
---



# 期末复习

## 题型整理

### 空间解析几何

1. 求空间曲线 $\left\{\begin{array}{l}x^{2}+y^{2}+z^{2}=14, \\ 3 x+2 y+z=10\end{array}\right.$ 在点 $P(1,2,3)$ 处的法平面与切线方程.
2. 

### 曲线\曲面积分 Green公式 Gauss公式 Stokes公式

1. 求柱面 $x^{2}+y^{2}=a y(a>0)$ 位于球面 $x^{2}+y^{2}+z^{2}=a^{2}$ 内部分曲面的面积.

2. 计算第二类曲线积分 $I_{1}=\int_{C} \cos \left(x+y^{2}\right) \mathrm{d} x+\left(2 y \cos \left(x+y^{2}\right)-\sqrt{1+y^{4}}\right) \mathrm{d} y$, 其中 $C$ 为旋轮 线 $x=a(t-\sin t), y=a(1-\cos t)$, 由 $O(0,0)$ 到 $A(2 \pi a, 0)$, 其中 $a>0$.

3. 计算第一类曲面积分 $I_{2}=\iint_{S}(x y+y z+z x) \mathrm{d} S$, 其中 $S$ 为圆雉面 $z=\sqrt{x^{2}+y^{2}}$ 被柱面 $x^{2}+y^{2}=$ $2 a x(a>0)$ 所截下的部分.

   > 投影法+利用对称性化简
   > $$
   > I_{2}=\iint_{S}(x y+y z+z x) \mathrm{d} S  =\iint zx dS\\
   > = \iint x\sqrt{x^2+y^2}|(z_1', z_2' ,-1)|dxdy =  \sqrt2\iint x\sqrt{x^2+y^2}dxdy\\
   > = 2\sqrt{2} \iint \rho^3\cos \varphi d\rho d\varphi = \cdots.
   > $$

4. 计算 $I_{3}=\int_{C} y^{2} \mathrm{~d} x+z^{2} \mathrm{~d} y+x^{2} \mathrm{~d} z$, 其中 $C$ 是平面 $x+y+z=1$ 的第一卦限部分与三 个坐标面的交线, 从 $z$ 周正向往 $z$ 轴负向看去是逆时针方向.

   > **法一** 
   > $$
   > I_3 = \oint_c(y^2, z^2, x^2)\cdot d\vec{r}\\
   > =  \iint rot(y^2, z^2, x^2)\times \vec{n}dS\\
   > = \iint (-2z, -2x, -2y)\cdot {(1,1,1)\over \sqrt{3}}dS\\
   > = -{2\over \sqrt{3}}\iint (x+y+z)dS\\
   > = -{2\over \sqrt{3}}\iint 1dS = -{2\over \sqrt{3}}S_\Delta = -1.\square\\
   > $$
   > **注** 这里最后如果没有发现$x+y+z=1$为积分区域的方程来化简的话, 直接嗯算也是可以的(笔者第一次就没发现) 
   > $$
   > \iint_s (x+ y + z)dS = -{2\over \sqrt{3}}\iint (x+ y + (1-x-y))\sqrt{3}dxdy = -1.
   > $$
   > **法二** (直接曲线积分)
   >
   > 1. 由轮换对称性, $I_3 = 3\int (0,0, x^2)\cdot d\vec{r}$
   >
   > 2. 分段, 发现其中一段的切向量与函数方向垂直, 点积为0, 另有一段函数向量为零, 点积为0,因此只要积其中一段.
   >
   > 3. $$
   >    I_3 = 3\int_{C_3} (0, 0, x^2)\cdot (1, 0, -1)dx = -3\int_0^1 x^2dx = -1.
   >    $$

5. 计算 $I_{2}=\displaystyle \oint_{C} \frac{y^{2}}{2} \mathrm{~d} x-x z \mathrm{~d} y+\frac{y^{2}}{2} \mathrm{~d} z$, 其中 $C$ 是 $x^{2}+y^{2}+z^{2}=R^{2}$ 与 $x+y=R$ 的交线, 从 $y$ 轴正向看去是顺时针方向.

   

6.  计算第二类曲面积分 $\displaystyle I_{3}=\iint_{\Sigma} x \mathrm{~d} y \mathrm{~d} z+(z+1)^{2} \mathrm{~d} x \mathrm{~d} y$, 其中 $\Sigma$ 是下半球面 $z=-\sqrt{1-x^{2}-y^{2}}$, 取下侧.

### 无穷级数

#### 判断数项级数绝对收敛/条件收敛

> 可以先判断是否绝对收敛,再判断是否条件收敛.

1. 讨论数项级数 $\sum_{n=1}^{\infty} \frac{n^{n-1}}{\left(2 n^{2}+n+1\right)^{\frac{n+1}{2}}}$ 的敛散性.

   > **法一** 放缩即可.
   >
   > **法二** 根植判别法 $\lim_{n\to \infin} \sqrt[n]{\frac{n^{n-1}}{\left(2 n^{2}+n+1\right)^{\frac{n+1}{2}}}} = {1\over 2} < 1$
   >
   > 注意配凑出比较好的形式$x^n$类.

2. $$
   \text { 考察级数 } \sum_{n=1}^{\infty}\left(\frac{1}{n}-\arctan \frac{1}{n}\right) \text { 的敛散性. }
   $$

   > 先处理$\arctan {1\over n}$.

#### 判断广义积分敛散性

> #### 做题步骤
>
> 1. 判断广义积分的奇点(若有多个,需要分段)
> 2. 对每个部分判断敛散性,方法:
>    1. 比较判别法
>    2. 放缩
>    3. 拆分
>    4. Abel审敛法(有界+积分收敛)
>    5. Dirichlet审敛法(单调趋于零+积分有界)
>    6. 非负项有上界
>
> 

1. 讨论广义积分 $\int_{0}^{+\infty} x^{p-1} \mathrm{e}^{-x} \mathrm{~d} x$ 的敛散性.

   > ==注意==: 
   >
   > - 对可能出现奇点的情况进行讨论.(不要**漏**可能的奇点!!)
   > - $e^x(x\to \infin)$趋近$+\infin$的速度快于任何幂级数.因此$\forall k \in \R,\displaystyle  lim_{x\to +\infin}{x^k\over e^x} = 0$
   > - 但是在说明$\int {x^{p-1}\over e^x}$收敛时,比较好的说法是${x^{p-1}\over e^x} \le {x^{p-1}\over x^{p+1}}$.

2. 讨论数项级数 $\sum_{n=2}^{\infty} \frac{\sin \left(\frac{n \pi}{6}\right)}{\sqrt{n}}$ 的敛散性. 如果收敛，是绝对收敛还是条件收敛?

   > 同**例** 8.3.3

3. 求数项级数 $\sum_{n=1}^{\infty} \frac{(-1)^{n-1}}{n}\left(1-\frac{1}{3^{n}}\right)$ 的和.

   > **解** 考虑函数项级数$\sum {(-1)^n\over n}x^n = S(x)$,
   >
   > 显然收敛域为$(-1,1]$.
   >
   > $S(x)  = S(x) - S(0) = \int_0^x S'(x) = \int \sum_{n=0}^\infin (-x)^n = \int_0^x{1\over 1+ x}= \ln (x+1). $
   >
   > $\therefore 原级数 = S(1) -  S({1\over 3}) = \ln 2 - \ln {4\over 3} = \ln {3\over 2},x\in (-1,1].\square$

4. $$
   \text { 判别级数 } \sum_{n=1}^{\infty} \frac{1+\frac{1}{2}+\frac{1}{3}+\cdots+\frac{1}{n}}{(n+1)(n+2)} \text { 的敛散性; 若收敛, 求其和. }
   $$

   > **注** 这里有一个对$\sum_{i=1}^\infin {1\over k}$的估计.
   >
   > > 解: $x>0$ 时, $\frac{x}{1+x}<\ln (1+x)$, 令 $x=\frac{1}{k}$, 则 $\frac{1}{k+1}<\ln \left(1+\frac{1}{k}\right)$, 取 $k=1,2, \cdots, n-1$, 再将各式相加可得 $a_{n}=1+\frac{1}{2}+\cdots+\frac{1}{n}<\ln n+1<2 \ln n(n \geq 3)$, 所以 $\frac{a_{n}}{(n+1)(n+2)}<\frac{2 \ln r}{n^{2}}$ 而 $\lim _{n \rightarrow \infty} \frac{2 \ln n}{n^{2}} \cdot n^{\frac{3}{2}}=0$, 所以级数 $\sum_{n=1}^{\infty} \frac{2 \ln n}{n^{2}}$ 收玫. 由比较判别法, 级数 $\sum_{n=1}^{\infty} \frac{a_{n}}{(n+1)(n+2)}$ 收敛.
   > > $$
   > > \begin{aligned}
   > > S_{n}=& \sum_{k=1}^{n} \frac{a_{k}}{(k+1)(k+2)}=\sum_{k=1}^{n} a_{k}\left(\frac{1}{k+1}-\frac{1}{k+2}\right)=\frac{a_{1}}{2}+\frac{a_{2}-a_{1}}{3}+\cdots+\frac{a_{n}-a_{n-1}}{n+1}-\frac{a_{n}}{n+2} \\
   > > &=1-\frac{1}{n+1}-\frac{a_{n}}{n+2}, \text { 所以 } \sum_{n=1}^{\infty} \frac{a_{n}}{(n+1)(n+2)}=\lim _{n \rightarrow \infty} S_{n}=1 .
   > > \end{aligned}
   > > $$


#### 根据级数求和函数

> 1. 求收敛半径$l = \lim {a_{n+1}\over a_n}, R = {1\over l}$.
> 2. 带两端端点,判断收敛区间开闭
> 3. 利用和函数的性质,求导/积分/换元($S(f(x)) = \sum a_n(f(x)^n)$) 对和函数变形, 求解后再逆运算得到和函数.
> 4. 若还要求某级数
> 5. 和, 利用和函数带入特定的x即可.
>
> - 有时候可能会先提出/放进去$x^k$之类的, 然后再求剩下级数的和函数.

1. $$
   \text { 求幂级数 } \sum_{n=1}^{\infty} \frac{2 n-1}{2^{n}} x^{2 n-2} \text { 的收敛域、和函数, 并由此计算 } \sum_{n=1}^{\infty} \frac{2 n-1}{2^{n}} \text { 的和. }
   $$

   > **注** 此题判断收敛半径时要么不直接用公式,要么做$t = x^2$的代换.
   >
   > 后面的计算级数是显然的.

#### 将函数展成麦克劳林级数/泰勒级数

> **方法一** 结合*常见函数泰勒级数* 将函数变形至已知函数
>
> **方法二** 利用定义: $f(x) =\displaystyle \sum_{n=0}^\infin {f^{n}(x_0)\over {n!}}x^n +R_n(x_0)$
>
> ==注意==: 用第二种方法不要忘了本来就有阶乘!!
>
> - 往往题目是几个函数的叠加形式,需要先拆分.



### 傅里叶级数

> 计算比较困难.
>
> - 一些常识
>
> $$
> \cos n\pi x = (-1)^n.\\
> \sin n\pi x =0.
> $$
>
> **解题步骤**
>
> 1. 判断函数周期(或题目要求延拓的周期)$2l$,
>
> 2. 计算傅里叶系数$a_0,a_n,b_n$(先判断函数奇偶性,可能减少一半计算量)
>
>    **注意不要乘错,想清楚是乘$\sin nx$还是$\cos nx$, 否则白算**.
>
> $$
> a_n = {1\over \pi} \int_{-\pi}^{\pi}f(x)\cos nx\ dx, n = 0, 1, 2, \cdots\\
> b_n = {1\over \pi} \int_{-\pi}^{pi}f(x) \sin nx\ dx, n = 1, 2, \cdots.\\
> a_n = {1\over l} \int_{-l}^{l}f(x)\cos {n\pi x\over l} dx, n = 0, 1, 2, \cdots\\
> b_n = {1\over l} \int_{-l}^{l}f(x) \sin {n\pi x\over l} dx, n = 1, 2, \cdots.
> $$
>
> 3. 写成傅里叶级数
>
> $$
> {a_0\over 2} + \sum_{n=1}^\infin (a_n \cos nx + b_n \sin nx)\\
> {a_0\over 2} + \sum_{n=1}^\infin (a_n \cos  {n\pi x\over l} + b_n \sin  {n\pi x\over l})
> $$
>
> 

1. 将函数 $f(x)=\pi^{2}-x^{2}$ 在 $(-\pi, \pi)$ 上展开成余弦级数, 并求级数 $\sum_{n=1}^{\infty} \frac{1}{n^{2}}, \sum_{n=1}^{\infty} \frac{(-1)^{n+1}}{n^{2}}$, $\sum_{n=1}^{\infty} \frac{1}{(2 n-1)^{2}}$ 的和.

### 微分方程

> 解题步骤
>
> 1. 确定微分方程类型(往往不那么直接, 需要适当变形:${dy\over dx}\iff {dx\over dy}$/换元/乘积分因子)
> 2. 根据不同类型,按部就班选取相应方法求解.

[常微分方程全是套路？【数二必看知识框架】十分钟带你梳理微分方程知识框架。看完在做题，痛苦少一半！！_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV17v411P7nr?spm_id_from=333.337.search-card.all.click)

#### 各种类型的微分方程

1. 求微分方程 $\frac{\mathrm{d} y}{\mathrm{~d} x}=\frac{3 x^{2}+2 x y-y^{2}}{2 x y-x^{2}}$ 的通积分.
2. 求微分方程 $\frac{\mathrm{d} y}{\mathrm{~d} x}=\frac{x^{4}+y^{3}}{x y^{2}}$ 的通积分.

#### 级数$\sim$微分方程

1. 设 $f(x)=\sum_{n=1}^{\infty} \frac{2(2 n) ! !}{(2 n+1) ! !(n+1)} x^{2(n+1)}, x \in(-1,1)$. 求出 $f(x)$ 满足的微分方程, 并 求解之. 计算 $\sum_{n=1}^{\infty} \frac{n !}{(2 n+1) ! !(n+1)}$.

2. $$
   \text {求微分方程 }\left(\frac{1}{y} \sin \frac{x}{y}-\frac{y}{x^{2}} \cos \frac{y}{x}+5\right) \mathrm{d} x+\left(-\frac{x}{y^{2}} \sin \frac{x}{y}+\frac{1}{x} \cos \frac{y}{x}+\frac{6}{y^{3}}\right) \mathrm{d} y=0 \text { 的通积分. }
   $$

   > ==注意==: 得到诸如$\sin 1, \cos 1, 5$之类的,不要写在上面,而是写到常数C中

3. 

#### 微分方程解的结构

> 主要是要知道解的结构.
>
> 知道特征方程特征值与解的关系.

> ==注意==: 看清题目是要求*求出特解*or*写出特解的形式*.

1. 已知 $y_{1}=x e^{x}+e^{2 x}, y_{2}=x e^{x}+e^{-x}, y_{3}=x e^{x}+e^{2 x}-e^{-x}$ 是某二阶线性非齐次微分方程 的三个解, 求出此微分方程, 写出其通解.

   > 解: $y_{1}-y_{3}=e^{-x}$ 是对应的齐次方程的一个解, 则 $y_{4}=y_{2}-e^{-x}=x e^{x}$ 是非齐次方程的一个 解, $y_{1}-y_{4}=e^{2 x}$ 是对应的齐次方程的另一个解。所以 $-1,2$ 是特征根。
   > 二阶线性非齐次微分方程为 $y^{\prime \prime}-y^{\prime}-2 y=f(x)$, 将 $y_{4}=x e^{x}$ 带入方程可得 $f(x)=(1-2 x) e^{x}$. 所以微分方程为 $y^{\prime \prime}-y^{\prime}-2 y=(1-2 x) e^{x}$, 通解为 $y=C_{1} e^{-x}+C_{2} e^{2 x}+x e^{x}$.

## 知识与技巧

### 形如$\int_0^{\pi\over 2} \sin^n x\ dx$ 的高阶三角函数积分

[点火公式(华理士公式)及其推广的图像助记 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/400024954)

**Wallis公式**

- 华理士公式-基础版

$$
\int_{0}^{\frac{\pi}{2}} \sin ^{n} x \mathrm{~d} x=\int_{0}^{\frac{\pi}{2}} \cos ^{n} x \mathrm{~d} x=\left\{\begin{array}{l}
\frac{n-1}{n} \cdot \frac{n-3}{n-2} \cdots \frac{2}{3} \cdot 1 \quad n \text { is odd. } \\
\frac{n-1}{n} \cdot \frac{n-3}{n-2} \cdots \frac{1}{2} \cdot \frac{\pi}{2} \quad n \text { is even. }
\end{array}\right.
$$

- 华理士公式-推广公式
- 推广公式1

$$
\int_{0}^{\pi} \sin ^{n} x \mathrm{~d} x=2 \int_{0}^{\frac{\pi}{2}} \sin ^{n} x \mathrm{~d} x= \begin{cases}2 \cdot \frac{n-1}{n} \cdot \frac{n-3}{n-2} \cdots \frac{2}{3} \cdot 1 & n \text { is odd } \\ 2 \cdot \frac{n-1}{n} \cdot \frac{n-3}{n-2} \cdots \frac{1}{2} \cdot \frac{\pi}{2} & n \text { is even. }\end{cases}
$$

- 推广公式2
  $\int_{0}^{\pi} \cos ^{n} x \mathrm{~d} x= \begin{cases}0 & n \text { is odd. } \\ 2 \cdot \frac{n-1}{n} \cdot \frac{n-3}{n-2} \cdots \frac{1}{2} \cdot \frac{\pi}{2} & n \text { is even }\end{cases}$
- 推广公式3
  $\int_{0}^{2 \pi} \sin ^{n} x \mathrm{~d} x=\int_{0}^{2 \pi} \cos ^{n} x \mathrm{~d} x= \begin{cases}0 & n \text { is odd } \\ 4 \cdot \frac{n-1}{n} \cdot \frac{n-3}{n-2} \cdots \frac{1}{2} \cdot \frac{\pi}{2} & n \text { is even }\end{cases}$

> 于是
> $$
> \int_0^{\pi\over 2}\sin^3xdx = {2\over 3}.\\
> \int_0^{\pi\over 2}\sin^4xdx = {3\over 4}\cdot {1\over 2}\cdot {\pi\over 2}.
> $$

### 常见函数泰勒级数

$$
\begin{align}
(1)& e^x = \sum_{n=0}^\infin {1\over n!}x^n=1 + x + {1\over 2}x^2 + {1\over 3}x^3 + \cdots, & x \in (-\infin, +\infin)\\
(2)& \sin x = \sum_{k=1}^\infin {(-1)^{k+1}\over (2k-1)!} x^{2k-1} = 1 - {1\over 3!}x^3 + {1\over 5!}x^5 - \cdots,& x \in (-\infin, +\infin)\\
(3)& \cos x = \sum_{k=0}^\infin {(-1)^k\over (2k)!}x^{2k} = 1-{1\over 2!}x^2 +{1\over 4!}x^4 - \cdots,& x \in (-\infin, +\infin)\\
(4)& {1\over 1+x} = \sum_{k=0}^\infin (-1)^kx^k=1-x + x^2-x^3 + \cdots, & x\in (-1,1)\\
(5)& \ln (x+1) = \sum_{k=0}^\infin {(-1)^k\over (k+1)}x^{k+1} = x - {1\over 2}x^2 + {1\over 3}x^3 - \cdots,& x \in (-1,1]\\
(6)& a^x = e^{x\ln a} = \sum_{n=0}^\infin {(\ln a)^n\over n!}x^n,& x \in (-\infin, +\infin)\\
(7)& \arctan x  =\sum_{k=0}^\infin {(-1)^n\over (2n+1)}x^{2n+1},& x\in [-1, 1]\\
(\bold8)& (1+x)^m = 1 + \sum_{n=1}^\infin {m(m-1))\cdots (m-n+1)\over n!}x^n,& x\in (-1,1)
\end{align}
$$

### 和差化积\积化和差

> 该技巧常用于对级数化简(去$\sum$).

$$
\sum \cos n\theta就乘\sin\theta \rightarrow 2 \cos \alpha \sin \beta =\sin (\alpha+\beta)-\sin (\alpha -\beta)\\
\sum \sin n\theta也配\sin\theta \rightarrow 2 \sin \alpha \sin \beta =\cos (\alpha-\beta)-\cos (\alpha +\beta)\\
(另外两种化出来是和的形式, 用处不大)
$$

### 常见的一些曲线\曲面

#### 旋轮线/摆线

> **例** 设 $C: x=a(t-\sin t), y=a(1-\cos t), t: 0 \rightarrow 2 \pi$ 为旋轮线的一拱, 方向由原点 到 $A(2 \pi a, 0), \quad$ 计算 $I_{1}=\int_{C}\left((x+y+1) e^{x}-e^{y}+y\right) \mathrm{d} x+\left(e^{x}-(x+y+1) e^{y}-x\right) \mathrm{d} y$.

旋轮线的题目基本都联系green公式形成套路. 比较好的情况是转化得到的二重积分恰为0, 否则需要计算.

- 一拱的面积
  $$
  S = \int_0^{2\pi }ydx = a^2(1-\cos t)^2dt = a^2\int_0^{2\pi} (1+ {1\over 2})dx = 3\pi a^2.
  $$



## 问题

1. 遇到$\int\ln xdx$什么时候去绝对值?

   > **例** $$
   > \text { 求微分方程 } 2 x y \cdot y^{\prime}-y^{2}+x=0 \text { 的解. }
   > $$

2. 使用高斯公式时, 怎么根据有向曲面的方向判断积分是否要变号?

   > **例** 
   > $$
   > \text { 计算 } I_{2}=\iint_{S} 2 x^{3} \mathrm{~d} y \mathrm{~d} z+2 y^{3} \mathrm{~d} z \mathrm{~d} x+3\left(z^{2}-1\right) \mathrm{d} x \mathrm{~d} y \text  {, 其中 } S \text { 为曲面 } z=1-x^{2}-y^{2}(z \geq 0) \text { 的上侧 }
   > $$
   > 计算 $I_{1}=\iint_{S}\left(x^{3}+a z^{2}\right) \mathrm{d} y \mathrm{~d} z+\left(y^{3}+a x^{2}\right) \mathrm{d} z \mathrm{~d} x+\left(z^{3}+a y^{2}\right) \mathrm{d} x \mathrm{~d} y$, 其中 $S$ 为曲面 $z=$ $\sqrt{a^{2}-x^{2}-y^{2}}(a>0)$ 的上侧.

3. 一个说法问题: 什么叫**从$z$轴正向看去**?

4. 对*投影法* *长公式*的一些思考

## 注意点

1. 解微分方程时如果换元了,==一定要记得最后再换回去==!
2. 将函数展开成级数(傅里叶级数)时, 要注意最后的结果要检查有没有*瑕项* (n带入没有意义的项),如果有就要单独写出来.
