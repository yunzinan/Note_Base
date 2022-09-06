---
title: Calculus-II-notes-chapt3
top: false
cover: false
toc: true
tags: 微积分
categories: Maths
abbrlink: 51cd0943
date: 2022-06-11 16:57:19
author:
img:
coverImg:
password:
summary:
---

## 7 曲线积分·曲面积分与场论

### 7.1 第一类曲线积分

####  7.1.1 第一类曲线积分的概念与性质

定义 7.1.1 (第一类曲线积分) 设 $C$ 为 $x O y$ 平面上的一条光滑曲线段, 函数 $f(x, y)$ 在 $C$ 上有定义, 在 $C$ 上任意揷入一点列 $M_{0}, M_{1}, \cdots, M_{n}$, 将 $C$ 分为 $n$ 小段, 第 $i$ 段的长度记 为 $\Delta s_{i}(i=1,2, \cdots, n)$. 在第 $i$ 段上任取一点 $\left(\xi_{i}, \eta_{i}\right)$. 令 $\lambda=\max _{1 \leqslant i \leqslant n}\left\{\Delta s_{i}\right\}$, 如果对于曲线的任 意分割及点 $\left(\xi_{i}, \eta_{i}\right)$ 的任意取法, 下面的极限
$$
\lim _{\lambda \rightarrow 0} \sum_{i=1}^{n} f\left(\xi_{i}, \eta_{i}\right) \Delta s_{i}
$$
都存在且唯一, 则称此极限值为函数 $f(x, y)$ 在曲线段 $C$ 上的第一类曲线积分, 也称为对弧 长的曲线积分, 记为 $\int_{C} f(x, y) \mathrm{d} s$, 即
$$
\int_{C} f(x, y) \mathrm{d} s=\lim _{\lambda \rightarrow 0} \sum_{i=1}^{n} f\left(\xi_{i}, \eta_{i}\right) \Delta s_{i} .
$$
其中 $f(x, y)$ 称为被积函数, $C$ 称为积分曲线, $\mathrm{d} s$ 称为弧微分.

#### 7.1.2 第一类曲线积分的计算

我们将第一类曲线积分化为我们熟悉的定积分来计算.
**定理 7.1.2** 设 $f(x, y)$ 为定义在曲线段 $C$ 上的连续函数, $C$ 的参数方程为
$$
\left\{\begin{array}{l}
x=\varphi(t), \\
y=\psi(t),
\end{array} \quad(a \leqslant t \leqslant b)\right.
$$
其中 $\varphi(t), \psi(t)$ 在 $[a, b]$ 上具有连续的一阶导数, 且 $\left[\varphi^{\prime}(t)\right]^{2}+\left[\psi^{\prime}(t)\right]^{2} \neq 0$, 则第一类曲线积分 $\int_{C} f(x, y) \mathrm{d} s$ 存在, 且
$$
\int_{C} f(x, y) \mathrm{d} s=\int_{a}^{b} f(\varphi(t), \psi(t)) \sqrt{\left[\varphi^{\prime}(t)\right]^{2}+\left[\psi^{\prime}(t)\right]^{2}} \mathrm{~d} t
$$

### 7.2 第二类曲线积分

#### 7.2.1 第二类曲线积分的概念与性质

**定义** $7.2 .1$ (第二类曲线积分) 设 $C$ 是 $x O y$ 平面上从点 $A$ 到点 $B$ 的一条有向光滑曲 线段, 向量函数 $\boldsymbol{F}(x, y)=P(x, y) \boldsymbol{i}+Q(x, y) \boldsymbol{j}$ 在 $C$ 上有定义, 沿 $C$ 的方向用分点
$$
A=M_{0}\left(x_{0}, y_{0}\right), M_{1}\left(x_{1}, y_{1}\right), \cdots, M_{n-1}\left(x_{n-1}, y_{n-1}\right), M_{n}\left(x_{n}, y_{n}\right)=B,
$$
将 $C$ 分为 $n$ 个有向小弧段 $\widehat{M_{i-1} M_{i}}(i=1,2, \cdots, n), \widehat{M_{i-1} M_{i}}$ 的弧长记为 $\Delta s_{i}(i=1,2, \cdots, n)$. 设 $\lambda=\max _{1 \leqslant i \leqslant n}\left\{\Delta s_{i}\right\}, \Delta x_{i}=x_{i}-x_{i-1}, \Delta y_{i}=y_{i}-y_{i-1}$. 在 $\widehat{M_{i-1} M_{i}}$ 上任取一点 $\left(\xi_{i}, \eta_{i}\right)$. 如果 极限
$$
\lim _{\lambda \rightarrow 0} \sum_{i=1}^{n} \boldsymbol{F}\left(\xi_{i}, \eta_{i}\right) \cdot \overrightarrow{M_{i-1} M_{i}}=\lim _{\lambda \rightarrow 0} \sum_{i=1}^{n}\left[P\left(\xi_{i}, \eta_{i}\right) \Delta x_{i}+Q\left(\xi_{i}, \eta_{i}\right) \Delta y_{i}\right]
$$
存在唯一 (不依赖于对曲线的分割及 $\widehat{M}_{i-1} M_{i}$ 上点 $\left(\xi_{i}, \eta_{i}\right)$ 的选取), 则称此极限为向量函数 $\boldsymbol{F}(x, y)$ 沿曲线 $C$ 从 $A$ 点到 $B$ 点的第二类曲线积分. 记为
$$
\int_{C} P(x, y) \mathrm{d} x+Q(x, y) \mathrm{d} y \text { 或 } \int_{C} \boldsymbol{F}(x, y) \cdot \mathrm{d} \boldsymbol{r},
$$
其中 $\mathrm{d} \boldsymbol{r}=(\mathrm{d} x, \mathrm{~d} y)$, 有向曲线 $C=\overparen{A B}$ 称为积分路径. 第二类曲线积分也称为对坐标的曲线积分.

> 注：此处我们可以对积分变量做直观的表示$d\boldsymbol{r} = (dx, dy)$，那么$\int_cF(x,y)\cdot d\bold{r} = \int_c (P(x,y),Q(x,y))\cdot (dx, dy)$

#### 7.2.2 第二类曲线积分的计算

与第一类曲线积分的计算类似, 第二类曲线积分也可以化为定积分来计算. 我们首先讨论平面曲线的情况.
定理 $7.2 .2$ 设 $P(x, y), Q(x, y)$ 在有向曲线 $C$ 上有定义且连续, $C$ 的参数方程为
$$
\left\{\begin{array}{l}
x=\varphi(t) \\
y=\psi(t)
\end{array}\right.
$$
当 $t$ 单调地由 $\alpha$ 变到 $\beta$ 时, 点 $M(x, y)$ 从 $C$ 的起点 $A$ 沿 $C$ 运动到终点 $B, \varphi(t), \psi(t)$ 在以 $\alpha, \beta$ 为端点的闭区间上具有一阶连续的导数, 且 $\left[\varphi^{\prime}(t)\right]^{2}+\left[\psi^{\prime}(t)\right]^{2} \neq 0$. 则第二类曲线积分
$$
\int_{C} P(x, y) \mathrm{d} x+Q(x, y) \mathrm{d} y
$$

存在, 且
$$
\int_{C} P(x, y) \mathrm{d} x+Q(x, y) \mathrm{d} y=\int_{\alpha}^{\beta}\left[P(\varphi(t), \psi(t)) \varphi^{\prime}(t)+Q(\varphi(t), \psi(t)) \psi^{\prime}(t)\right] \mathrm{d} t .
$$

>  注：其实还是参数化，转化为一元的积分

#### 7.2.3 两类曲线积分之间的联系

虽然两类曲线积分的定义不同, 但在一定条件下可以互相转化, 我们先讨论平面曲线. 设有向曲线 $C$ 的起点为 $A$, 终点为 $B$, 曲线 $C$ 的参数方程为
$$
\left\{\begin{array}{l}
x=\varphi(t) \\
y=\psi(t)
\end{array}\right.
$$
起点 $A$, 终点 $B$ 分别对应于参数 $t_{1}, t_{2}$, 不妨设 $t_{1}<t_{2} .\left(\varphi^{\prime}(t), \psi^{\prime}(t)\right)$ 是曲线的切向量, 因而
$$
\mathrm{d} \boldsymbol{r}=(\mathrm{d} x, \mathrm{~d} y)=\left(\varphi^{\prime}(t), \psi^{\prime}(t)\right) \mathrm{d} t
$$
也是 $C$ 的切向量且其方向与积分路径的方向一致, 又 $\mathrm{d} r$ 的模正好是弧微分
$$
|\mathrm{d} r|=\sqrt{(\mathrm{d} x)^{2}+(\mathrm{d} y)^{2}}=\mathrm{d} s
$$
设 $\mathrm{d} \boldsymbol{r}$ 的方向余弦为 $\cos \alpha, \cos \beta$, 则有
$$
(\cos \alpha, \cos \beta)=\frac{\mathrm{d} r}{|\mathrm{~d} r|}=\left(\frac{\mathrm{d} x}{\mathrm{~d} s}, \frac{\mathrm{d} y}{\mathrm{~d} s}\right)
$$
所以
$$
\mathrm{d} x=\cos \alpha \mathrm{d} s, \quad \mathrm{~d} y=\cos \beta \mathrm{d} s
$$
因此
$$
\int_{C} P(x, y) \mathrm{d} x+Q(x, y) \mathrm{d} y=\int_{C}(P(x, y) \cos \alpha+Q(x, y) \cos \beta) \mathrm{d} s .
$$
其中 $(\cos \alpha, \cos \beta)$ 为曲线 $C$ 上点 $(x, y)$ 处的单位切向量 $\vec{T} =  {r'(t)\over |r'(t)|}$(且其方向与积分曲线方向一致). 

### 7.3 格林公式

定理 7.3.1 (格林 $\left(\right.$ Green $\left.^{*}\right)$ 公式) 设有界闭区域 $D$ 由逐段光滑曲线 $C$ 围成, 函数 $P(x, y)$ 及 $Q(x, y)$ 在 $D$ 上具有**一阶连续偏导数**, 则
$$
\oint_{C} P \mathrm{~d} x+Q \mathrm{~d} y=\iint_{D}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right) \mathrm{d} x \mathrm{~d} y .
$$
其中 $C$ 的方向按 $D$ 的**正向边界**曲线所取.

#### 推论：求闭区域的面积

在公式中取 $P(x, y)=-y, Q(x, y)=x$, 即得
$$
{1\over 2}\oint_{C} x \mathrm{~d} y-y \mathrm{~d} x= \iint_{D} \mathrm{~d} x \mathrm{~d} y = \sigma(S).
$$
设闭区域 $D$ 的面积为 $A$, 则有
$$
A=\frac{1}{2} \oint_{C} x \mathrm{~d} y-y \mathrm{~d} x .
$$

### 7.3.2 平面上第二类曲线积分与路径无关的条件

$$
{\part Q\over \part x} - {\part P \over \part y }  = 0 \iff \exist u(x,y), du = Pdx + Qdy 
$$



#### 曲线积分的基本公式

设区域 $D$ 是一个单连通区域, 函数 $P(x, y), Q(x, y)$ 在 $D$ 内具有一阶连续 偏导数, 对于 $D$ 内的任意两点 $A, B$, 曲线积分 $\int_{\overparen{A B}} P \mathrm{~d} x+Q \mathrm{~d} y$ 与路径无关的充分必要条件 是: $P \mathrm{~d} x+Q \mathrm{~d} y$ 恰是某个函数 $u(x, y)$ 的全微分, 即 $\mathrm{d} u=P \mathrm{~d} x+Q \mathrm{~d} y$ (这时我们称 $P \mathrm{~d} x+Q \mathrm{~d} y$ 为恰当微分). 此时有
$$
\int_{\overparen{A B}} P \mathrm{~d} x+Q \mathrm{~d} y=\int_{A}^{B} \mathrm{~d} u=u(B)-u(A)
$$

### 7.4 第一类曲面积分

$$
\iint f(x,y,z)dS
$$

补充：$dS$的等价表示
$$
{\begin{cases}x  =x(u,v)\\ y = y(u,v)\\ z = z (u,v)
\end{cases}}\\
r_1'= (x_1', y_1', z_1') \quad r_2' = (x_2',y_2',z_2')\\
d\vec{S} = r_1' \times r_2' = \left|\begin{array}{ccc}
i & j & k \\
x_{1}^{\prime} & y_{1}^{\prime} & z '_1 \\
x_{2}^{\prime} & y_{2}^{\prime} & z_{2}^{\prime}
\end{array}\right| = (y_1'z_2'-y_2'z_1', x_2'z_1'- x_1'z_2', x_1'y_2'-x_2'y_1')\\ = (|\begin{array} {ccc} y_1' & y_2'\\ z_1' & z_2' \end{array}|,|\begin{array}{ccc}z_1' & z_2' \\ x_1' & x_2'  \end{array}|,|\begin{array}{ccc}x_1' & x_2' \\ y_1' & y_2'  \end{array}|) =  (A, B, C)\\
dS = |d\vec{S}| = \sqrt{A^2+B^2+C^2}dudv\\
E = r_1'\cdot r_1' \quad F = r_1' \cdot r_2' \quad G = r_2'\cdot r_2'\\
EG-F^2= A^2+B^2+C^2\\
\therefore dS = \sqrt{EG-F^2}dudv
$$
当曲面 $S$ 由参数方程
$$
\left\{\begin{array}{l}
x=x(u, v), \\
y=y(u, v), \\
z=z(u, v),
\end{array} \quad(u, v) \in D\right.
给出时, 由第 6 章的讨论知, 曲面的面积微元可表示成 \mathrm{d} S=\sqrt{E G-F^{2}} \mathrm{~d} u \mathrm{~d} v, 其中
$$

$$
E=\boldsymbol{r}_{u}^{\prime} \cdot \boldsymbol{r}_{u}^{\prime}, \quad F=\boldsymbol{r}_{u}^{\prime} \cdot \boldsymbol{r}_{v}^{\prime}, \quad G=\boldsymbol{r}_{v}^{\prime} \cdot \boldsymbol{r}_{v}^{\prime}, \quad \boldsymbol{r}=(x(u, v), y(u, v), z(u, v)),
$$

因此, 有下面的计算公式
$$
\iint_{S} f(x, y, z) \mathrm{d} S=\iint_{D} f(x(u, v), y(u, v), z(u, v)) \sqrt{E G-F^{2}} \mathrm{~d} u \mathrm{~d} v .
$$
特别的，若$x =x ,y= y, z = z(x,y)$
$$
d\vec{S} =(-z_1', -z_2', 1)
dS = \sqrt{1+z_1'^2+z_2'^2}dxdy
$$

> 实际上, 投影法是比较常见的情形.

### 7.5 第二类曲面积分

$$
\iint_s \bold F(x,y,z) \cdot \bold n(x,y,z)dS, \bold n = (\cos\alpha, \cos\beta, \cos\gamma),|\bold n| = 1.\\
\cos\gamma\ dS = dxdy,  \dots\\
\therefore \iint \bold F\cdot \bold ndS = \iint Pdydz+Qdzdx+Rdxdy.
$$

> 第二类曲面积分与第一类的联系: $\vec{n}= {r'_1\times r'_2\over |r'_1 \times r'_2|}$
>
> ==注意==: 对于第二类曲面积分, 总是要先判断我们所积区域的法向量方向.

### 7.6 高斯公式和斯托克斯公式

#### Gauss公式

**空间闭区域上三重积分**与其**边界曲面上的曲面积分**之间的关系

- 使用条件: 分片光滑 $P\ Q \ R在空间V上有一阶连续偏导数$

$$
则有 \\
\iint _S Pdydz + Qdzdx + Rdxdy = \iiint_V ({\part P\over \part x} + {\part Q \over \part y } + {\part R\over  \part z})dxdydz
$$

建立了第二类曲面积分与三重积分的联系

> 注: Gauss的使用路径往往只能是将一个第二类曲面积分转化为三重积分.
>
> **特例** $\displaystyle \iiint1dV = \iint zdz  =  \iint xdx$

#### Stokes公式

将格林公式由平面推广到曲面, 使在具有光滑边界曲线的光滑曲面上的曲面积分与其边界上的曲线积分联系起来.

- 使用条件: 设$S$为分片光滑的**有向曲面**, 其边界$\Gamma$逐段光滑 **有向闭曲线** $\Gamma 与S$符合右手法则 $P\ Q\ R $有一阶连续偏导数,则有

$$
\oint_{\Gamma} P \mathrm{~d} x+Q \mathrm{~d} y+R \mathrm{~d} z=\iint_{S}\left|\begin{array}{ccc}
\mathrm{d} y \mathrm{~d} z & \mathrm{~d} z \mathrm{~d} x & \mathrm{~d} x \mathrm{~d} y \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
P & Q & R
\end{array}\right| = \iint \nabla \times (P,Q,R)\cdot  \vec{n}dS .
$$

> Stokes的使用路径往往只能是将一个闭合的第二类曲线积分转化为第二类曲面积分. 因为反方向是不容易求得的.

## 各类积分归纳整理

### 一重积分

#### 第一类曲线积分$\int f(x,y) ds$（立体侧面积、物质曲线的质量）

- 注意：这里不是$f \cdot ds$，因为这里的积分变量是标量（长度） 
- 计算：参数化

$$
{\begin{cases}x = \varphi(t) \quad dx = \varphi'(t)dt\\ y = \psi(t) \quad dy = \psi'(t)dt\end{cases}} \\
then\ ds = \sqrt{(dx)^2+(dy)^2} = \sqrt{\varphi'(t)^2 + \psi'(t)^ 2}dt \\
\int_c f(x，y)ds = \int f(\varphi(t),\psi(t))|r'(t)|dt, \quad r'(t) = (\varphi'(t) , \psi'(t))\\
特别的，若y可以表示成y = y(x), 那么\int_c f(x,y(x))ds = \int_c f(x,y(x))\sqrt{1 + y'(x)^2}dx
$$

#### 特例：曲线长度

$$
对于第一类曲线积分，若f(x,y)  = 1, 则 \int_c 1 \cdot ds = len(c), i.e 曲线长度.
$$

#### 一重积分和二重积分的联系：格林公式(可以求面积)

$$
\oint_{C} P \mathrm{~d} x+Q \mathrm{~d} y=\iint_{D}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right) \mathrm{d} x \mathrm{~d} y .
$$



在公式中取 $P(x, y)=-y, Q(x, y)=x$, 即得
$$
\oint_{C} x \mathrm{~d} y-y \mathrm{~d} x=2 \iint_{D} \mathrm{~d} x \mathrm{~d} y
$$
设闭区域 $D$ 的面积为 $A$, 则有
$$
A=\frac{1}{2} \oint_{C} x \mathrm{~d} y-y \mathrm{~d} x .
$$

#### 第二类曲线积分

- 注意：第二类曲线积分的积分方向改变时，积分结果变号。这是因为矢量的方向性。

$$
\int \bold F(x,y)\cdot d \bold r = \int P(x,y)dx + Q(x,y)dy.（三维同理）
$$

- 计算：
  $$
  {\begin{cases}x = \varphi(t) \quad dx = \varphi'(t)dt\\ y = \psi(t) \quad dy = \psi'(t)dt\end{cases}} \\
  \int_c P(x,y)dx + Q(x,y)dy =  \int_\alpha^\beta  [(P(\varphi(t),\psi(t))]\varphi'(t)+(Q(\varphi(t),\psi(t)))\psi'(t)]dt\\
  特别的， 若y = y(x), \\
  \begin{cases}dx = dx \\
  dy = y'(x)dx
  \end{cases}
  $$

- 

- $注：d\bold r = (\cos\alpha, \cos \beta)ds = (dx,dy)$

### 二重积分

$$
\iint f(x)g(y)dxdy = (\int f(x)dx)(\int g(y)dy)\\
$$

3. 三重积分（质量）

4. 曲面面

$$
S:\begin{cases}x = \varphi(u,v)\\
y = \psi(u,v)\\
z = \omega(u,v)
\end{cases}\\
引入向量函数r(u,v) = (\varphi(u,v), \psi(u,v),\omega(u,v))\\
\sigma(S) = \iint |r'_u \times r'_v|\ dudv\\
特别的，若可以表示为\\
S:\begin{cases}x = u\\
y = v\\
z = \omega(u,v)
\end{cases}\\
\sigma(S) = \iint \sqrt{1 + \omega_u'^2 + \omega_v'^2}\ dudv
$$

> 叉乘表示面积

### Green公式 Gauss公式 Stokes公式

格林公式
$$
\int_c Pdx + Qdy =\iint ({\part Q\over \part x} - {\part P\over \part y})dxdy
$$

> 第二类曲线积分$\iff$二重积分
>
> 又因为第一类曲线积分与第二类曲线积分的关系
> $$
> 
> $$

高斯公式
$$
\iint _S Pdydz + Qdzdx + Rdxdy = \iiint_V ({\part P\over \part x} + {\part Q \over \part y } + {\part R\over  \part z})dxdydz
$$

> gauss公式是将green公式的思想推广到三维.
>
> 闭合曲线的曲线积分等于曲面内部的平面上的二重积分
>
> 闭合曲面的曲面积分等于曲面内部的空间上的三重积分

斯托克斯公式 
$$
\int_{\Gamma} P \mathrm{~d} x+Q \mathrm{~d} y+R \mathrm{~d} z=\iint_{S}\left|\begin{array}{ccc}
\mathrm{d} y \mathrm{~d} z & \mathrm{~d} z \mathrm{~d} x & \mathrm{~d} x \mathrm{~d} y \\
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\
P & Q & R
\end{array}\right| .
$$


> stokes公式其实就是三维空间里的green公式
>
> 将三维空间中曲面上的曲面积分转化为曲面边界的曲线积分

### 第二类曲面积分 - 投影法

投影法是将形如$\displaystyle \iint Pdxdy + Qdydz + dzdx$的积分转化为

换元
$$
(1) r_1'\times r'_2 = (f'_x, f'_y, -1)
$$
投影与法向量的联系
$$
\iint Rdxdy  = (0,0,R)\cdot (*, *, 0)dS = 0
$$
