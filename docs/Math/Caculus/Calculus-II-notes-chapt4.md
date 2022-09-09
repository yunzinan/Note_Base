---
title: Calculus-II-notes-chapt4
top: false
cover: false
toc: true
tags: 微积分
categories: Maths
abbrlink: cfa99ce0
date: 2022-06-11 16:57:49
author:
img:
coverImg:
password:
summary:
---

## 8 无穷级数

### 8.1 常数项级数

#### 定义

$$
\sum_{n = 1}^ \infin u_n \\
S_n = u_1 + u_2 + \dots +u_n = \sum_{k=1}^\infin u_k. 部分和数列
$$

#### 等比级数

$$
S_n = {a(1-q^n)\over 1-q}
$$

- 当$|q| < 1$ 收敛到$a\over(1-q)$
- 当$|q| >1$ 发散
- 当$q = 1$ 发散
- 当$q = -1$ $S_n$极限不存在，发散

#### 性质

- 若级数收敛，则可以任意加括号，不改变结果。反之不然。
  - 推论：若加括号的级数发散，则原级数发散。
  - 不能通过加括号后的级数收敛推出原来的级数收敛。

#### 级数收敛的条件

##### 必要条件

- $\lim u_n = 0$

##### 充要条件

- 柯西收敛准则：

  $\forall \epsilon > 0, \exist N, s.t. \forall n > N, \forall p \in \Z^+ \\ |u_{n+1} + u_{n+2} + \dots + u_{n+p}| < \epsilon$

### 8.1 习题

1. 讨论敛散性
   $$
   \text { (4) } \sin \frac{\pi}{6}+\sin \frac{2 \pi}{6}+\cdots+\sin \frac{n \pi}{6}+\cdots \text {. }
   $$

> $Hint.$常见做法：构造列项，利用积化和差公式$ 2 \sin \alpha \sin \beta =\cos (\alpha-\beta)-\cos (\alpha +\beta)$
>
> $\sin \frac{\pi}{12} S_{n}=\sin \frac{\pi}{12}\left(\sin \frac{\pi}{6}+\sin \frac{2 \pi}{6}+\cdots+\sin \frac{n \pi}{6}\right)$
> 由三角积差公式得;
> $\sin \frac{\pi}{12} S_{n}=\frac{1}{2}\left(\cos \frac{\pi}{12}-\cos \left(n+\frac{1}{2}\right) \frac{\pi}{6}\right)$
> $S_{n}=\frac{\cos \frac{\pi}{12}-\cos \left(n+\frac{1}{2}\right) \frac{\pi}{6}}{2 \sin \frac{\pi}{12}}$, 当 $n \rightarrow \infty$ 时极限不存在,原级数发散.

$$
\sum \cos n\theta就乘\sin\theta \rightarrow 2 \cos \alpha \sin \beta =\sin (\alpha+\beta)-\sin (\alpha -\beta)\\
\sum \sin n\theta也配\sin\theta \rightarrow 2 \sin \alpha \sin \beta =\cos (\alpha-\beta)-\cos (\alpha +\beta)\\
(另外两种化出来是和的形式, 用处不大)
$$

2. 求级数和

$$
\sum_{n=1}^\infin {1\over n(n+1)(n+2)} = \sum {1\over 2n+2}\cdot ({1\over n} - {1\over n+2}) \\ = \sum {1\over 2} [({1\over n} - {1\over n+1}) - ({1\over n+1} - {1\over n+2})] = \ ...
$$

3. 利用Cauchy收敛原理判断敛散性。$1+\frac{1}{2}-\frac{1}{3}+\frac{1}{4}+\frac{1}{5}-\frac{1}{6}+\cdots$;
   解 对任意的 $n$, 考察上述级数第 $3 n+1$ 项到第 $6 n$ 项的和 $S$,由:

$$
\begin{aligned}
&S=\frac{1}{3 n+1}+\frac{1}{3 n+2}-\frac{1}{3 n+3}+\cdots+\frac{1}{6 n-2}+\frac{1}{6 n-1}-\frac{1}{6 n^{\prime}} \\
&>\frac{1}{3 n+3}+\frac{1}{3 n+3}-\frac{1}{3 n+3}+\cdots+\frac{1}{6 n}+\frac{1}{6 n}-\frac{1}{6 n} ;
\end{aligned}
$$

$$
\begin{aligned}
&=\frac{1}{3 n+3}+\frac{1}{3 n+6}+\cdots+\frac{1}{6 n} \\
&=\frac{1}{3}\left(\frac{1}{n+1}+\frac{1}{n+2}+\cdots+\frac{1}{2 n}\right) \\
&>\frac{1}{3}\left(\frac{1}{2 n}+\frac{1}{2 n}+\cdots+\frac{1}{2 n}\right)=\frac{1}{6}
\end{aligned}
$$

也就是说,根据柯西准则,对于给定的正数 $\varepsilon<\frac{1}{6}$, 无论 $n$ 取什么值,我们都能攷 到 $p=3 n$ 使得 $S>\frac{1}{6}>\varepsilon$, 因此级数发散.

> 注：这里是利用柯西收敛准则说明发散的例子。其实就是说明$S_n \not \to 0.$注意写法，使用严谨的$\varepsilon-\delta$语言。

### 8.2 正项级数

#### 正项级数收敛的充要条件

部分和数列有上界

#### 比较判别法

只要存在足够大的$N$ ，使得N以后的所有n都满足$0\le u_n \le Cv_n$即可。（“几乎”的概念）

#### 比较判别法的极限形式

$$
\lim {u_n\over v_n} = l\\
$$

#### 比值判别法（达朗贝尔（d'Alembert）判别法）

$$
\lim {u_{n+1}\over u_n} = \rho\\
if\ \rho < 1 \to 收敛\\
if\ \rho > 1 \to 发散\\
if\ \rho = 1 \to 可能发散，也可能收敛。
$$

#### 根式判别法（柯西判别法）

$$
\lim \sqrt[n]{u_n} = \rho\\
if\ \rho < 1 \to 收敛\\
if\ \rho > 1 \to 发散\\
if\ \rho = 1 \to 可能发散，也可能收敛。
$$

#### （柯西）积分判别法

找一个连续的单调减少的函数$f(x)$，使得$u_n = f(n)$，则$\sum u_n$与$\int_k^{+\infin}f(x)dx$有相同的敛散性。

### 8.2 习题

1. 判断

$$
\text { (6) } \sum  \frac{n^n}{\left(n^{2}+3 n+1\right)^{\frac{n+2}{2}}} \text {; }
$$

> 答案：收敛。过程？

2. (4) $\sum_{n=1}^{\infty} \frac{4^{n} \cdot n !}{n^{n}}$;
   解 $\lim _{n \rightarrow \infty} \frac{\frac{4^{n+1} n+1 !}{n+1^{n+1}}}{\frac{4^{n} \cdot n !}{n^{n}}}=\lim _{n \rightarrow \infty} 4\left(\frac{n}{n+1}\right)^{n} = {4\over e}>1$; 发散;

> 注：也可以使用斯特林公式配合根植判别法。

3. $\sum_{n=1}^{\infty} \frac{n}{(\ln n)^{n}}$;
   解 $\lim _{n \rightarrow \infty} \frac{\frac{n+1}{(\ln (n+1))^{n+1}}}{\frac{n}{(\ln n)^{n}}}=\frac{1}{\ln (1+n)}<1$; 收敛;
4. (12) $\sum_{n=2}^{\infty} \frac{1}{n(\ln n)^{p}}(p>0)$;
   解 $\int_{2}^{\infty} \frac{1}{n(\ln n)^{p}} d n=\left.\frac{(\ln n)^{-p+1}}{-p+1}\right|_{2} ^{\infty}$ 当 $1>p>0$ 时, 发散; 当 $1<p$ 时,收敛, 当 $1=p$ 时,发散.

> 注：别忘了柯西积分判别法。

$$
\sum_{n=3}^{\infty} \frac{1}{n(\ln n)^{p}(\ln \ln n)^{q}} \quad(p>0, q>0)
$$

6. $\sum_{n=1}^{\infty}\left(\frac{b}{a_{n}}\right)^{n}$, 其中 $\lim _{n \rightarrow \infty} a_{n}=a>0, b>0$.
7. 讨论实数 $p$ 为何值时, 级数 $\sum_{n=1}^{\infty}\left(\frac{1}{n}-\sin \frac{1}{n}\right)^{p}$ 收敛, 实数 $p$ 为何值时, 级数发散.
8. 讨论实数 $p$ 为何值时, 级数 $\sum_{n=1}^{\infty}\left(\mathrm{e}-\left(1+\frac{1}{n}\right)^{n}\right)^{p}$ 收敛, 实数 $p$ 为何值时, 级数发散.

### 补充：斯特林公式(stiring's approximation)

$n ! \approx \sqrt{2 \pi n}\left(\frac{n}{e}\right)^{n}$
或更精确的

$$
\lim _{n \rightarrow+\infty} \frac{n !}{\sqrt{2 \pi n}\left(\frac{n}{e}\right)^{n}}=1
$$

或

$$
\lim _{n \rightarrow+\infty} \frac{e^{n} n !}{n^{n} \sqrt{n}}=\sqrt{2 \pi}
$$

或

$$
\frac{1}{n !} \sim \frac{1}{\sqrt{2 \pi n}\left(\frac{n}{e}\right)^{n}}, \quad(n \rightarrow+\infty)
$$

或

$$
\frac{1}{n !} \sim \frac{e^{n}}{n^{n} \sqrt{2 \pi n}}, \quad(n \rightarrow+\infty)
$$

### 8.3 任意项级数

#### 交错级数的敛散性判定

莱布尼兹定理：

$$
1) u_{n} \ge u_{n+1}\\
2) \lim u_n= 0\\
则\sum u_n收敛.
$$

#### 绝对收敛与条件收敛

##### 绝对收敛的性质

- 绝对收敛级数的更序级数仍为绝对收敛级数，且其和相同。

##### 级数的乘法运算

- 对角线法：柯西乘积
- 正方形法
- 两个绝对收敛的级数各项之积按照任意方法所构成的级数也绝对收敛

#### 任意项级数收敛性的判别法

##### Abel判别法

$$
如果：\\
1)级数\sum b_n收敛\\
2)数列\{a_n\}单调有界\\
则级数\sum {a_nb_n}收敛.
$$

##### Dirichlet判别法

$$
如果：\\
1)级数\sum b_n的部分和数列S_n有界\\
2)数列\{a_n\}单调趋于0\\
则级数\sum {a_nb_n}收敛.
$$

### 8.3 习题

1. （2）$1 - {1\over 2} + {1\over 3!} - {1\over 4} + {1\over 5!} - \cdots$判断敛散性

> 注：结构很显然是两者拼起来的，不妨拆开来。阶乘项可以放缩成可裂项的形式，只需证明收敛即可。

2. （11）$\sum{1\cdot 3\cdot 5\cdots (2n-1)\over 2\cdot 4\cdot 6\cdots (2n)}$

> 注：放缩$>{1\over 2n}$，故条件收敛。

3. $\sum {(-1)^{n+1}\over n + \sin n}$

4. 2. 判断下列级数敛散性
   3. $\sum_{n=1}^{\infty}\left(2-n \sin \frac{1}{n}-\cos \frac{1}{n}\right)$;
   4. $\sum_{n=2}^{\infty} \frac{(-1)^{n}}{n+(-1)^{n} \sqrt{n}}$.
      Solution. $u_{n}$ 表示通项。
      (1). 首先由于 $\frac{\sin x}{x}<1\left(0<|x|<\frac{\pi}{2}\right)$, 所以

   $$
   u_{n}=\left(1-n \sin \frac{1}{n}\right)+\left(1-\cos \frac{1}{n}\right)=a_{n}+b_{n}>0
   $$

   又因为

   $$
   \lim _{n \rightarrow \infty} \frac{a_{n}}{\frac{1}{n^{2}}}=\lim _{t \rightarrow 0} \frac{2 t-\sin t-t \cos t}{t^{3}}=\frac{1}{6}
   $$

以及

$$
\lim _{n \rightarrow \infty} \frac{3_{n}}{\frac{1}{n^{2}}}=\lim _{t \rightarrow 0} \frac{1-\cos t}{t^{2}}=\frac{1}{2}
$$

所以 $\sum a_{n}, \sum b_{n}$ 收敛。所以 $\sum u_{n}=\sum\left(a_{n}+b_{n}\right)$ 收敛。所以绝对收敛。

> 注：此题是利用泰勒展开构造同敛散性数列来证明的模板题。

(2). 由

$$
\left|u_{n}\right|=\frac{1}{\sqrt{n}\left(\sqrt{n}+(-1)^{n}\right)} \geq \frac{1}{\sqrt{n}(2 \sqrt{n})}=\frac{1}{2 n}
$$

知级数不绝对收敛。
对 $u_{n}$ 分子分母同乘以 $n-(-1)^{n} \sqrt{n}$,

$$
u_{n}=\frac{(-1)^{n}\left(n-(-1)^{n} \sqrt{n}\right)}{n^{2}-n}=\frac{(-1)^{n}}{n-1}-\frac{\sqrt{n}}{n^{2}-n}
$$

由莱布尼兹判别法知 $\frac{(-1)^{n}}{n-1}$ 收敛, 而后者因为

$$
\frac{\sqrt{n}}{n^{2}-n}=\frac{1}{n^{3 / 2}-\sqrt{n}} \leq \frac{2}{n^{3 / 2}}
$$

所以收敛。因此 $\sum u_{n}$ 条件收敛。

### 8.4 函数项级数

#### 基本概念

- 收敛点 收敛域 发散点 发散域
- 部分和 余项 级数和

**问题**：什么样的级数，满足：函数项级数的每一项的导数或积分所成级数的和不等于它的和函数的导数或积分？

#### 函数项级数的一致连续

- 对于一般级数：

  $$
  for\ x = x_0,\exist N(x_0,\varepsilon), \forall n > N,\\ |r_n| = |S(x_0) - S_n(x_0)| < \varepsilon.
  $$

- 如果对于一个函数项级数能找到一个$N$，不依赖于$x_0$，只依赖于$\varepsilon$ 对于收敛于上所有点成立，则称该级数一致收敛。

- 一致收敛的判别法

  魏尔斯特拉斯(Weierstrass)判别法

$$
如果函数项级数\sum u_n(x)满足: \\
|u_n(x)| \le a_n,且正项级数\sum a_n收敛,\\
则函数项级数\sum u_n(x)在区间I上一致收敛.
$$

> 又称**强级数**判别法。

- 一致收敛级数的性质：

  - 级数通项$u_n(x)$在$I$上连续，则和函数$S(x)$在$I$上也连续

  - 若级数通项连续（*几乎*连续才能积分），则级数可以逐项积分：

    $$
    \int_a^b S(x)dx = \int_a^b (\sum_{n=1}^\infin u_n(x)\ )\ dx=  \sum_{n=1}^\infin \int u_n(x)dx.
    $$

  - 若级数通项连续（连续才有导数），则级数可以逐项求导，且级数和的导数也连续：

    $$
    S'(x) = {d\over dx}\sum_{n =1}^\infin u_n(x) = \sum_{n=1}^\infin u'_n(x)
    $$

### 8.4 习题

> 考虑到级数中有关一致收敛的知识都不考，笔者就鸽了

### 8.5 幂级数

#### 阿贝尔定理

$$
如果级数\sum a_nx^n 在 x_1处收敛，那么对于满足不等式|x| < |x_1|的一切x，都绝对收敛。 \\
如果在x_2处发散，那么在所有满足|x| > |x_2|的点处都发散。
$$

#### 收敛半径

$$
\begin{aligned}
\lim_{n\to \infin} |{a_{n+1}x^{n+1}\over a_nx^n}| = \lim |{a_{n+1}\over a_n}||x|,由比值判别法,\\
\begin{align}&(1)\lim|{a_{n+1}\over a_n}||x| < 1 \iff |x| < \lim |{a_n\over a_{n+1}}| = R \Rightarrow 收敛\\&(2) \lim|{a_{n+1}\over a_n}||x| > 1 \iff |x| > \lim |{a_n\over a_{n+1}}| = R \Rightarrow 发散\\ \end{align}\\
因此我们很自然的定义\lim|{a_{n+1}\over a_{n}}| = l.\\
R = \begin{cases}{1\over l}, & 0< l < +\infin,\\+\infin, & l = 0,\\ 0, &l = +\infin. \end{cases}
\end{aligned}
$$

$$
类似地，由根值判别法，我们可以得到，\\
\lim \sqrt[n]{|a_n|} = l.
$$

#### 幂级数的性质

- 幂级数的和函数在收敛域上连续
- 幂级数的和函数在收敛域上可积
- 幂级数的和函数在收敛于上可导，存在任意阶导数。

#### 题型总结：求幂级数的和函数

1. 求级数收敛域

2. $$
   利用\sum_{n =1}^\infin \int_0^x a_nt^ndt = \int_0^x S(t)dt或者\\
    {d\over dx}\sum_{n =1}^\infin u_n(x) = \sum_{n=1}^\infin u'_n(x) = S'(x).\\
    间接求和函数.
   $$

3. 

### 8.5 习题

1. 1.（2）$\sum_{n=1}^{\infty} \frac{x^{n}}{\sqrt[n]{n}}$;
   解 设 $a_{n}=\frac{1}{\sqrt[n]{n}}$

$$
\begin{gathered}
\frac{a_{n+1}}{a_{n}}=\frac{n^{\frac{1}{n}}}{(n+1)^{\frac{1}{n+1}}}=e^{\frac{1}{n} \ln n-\frac{1}{n+1} \ln (n+1)} \\
\lim _{n \rightarrow \infty} \frac{a_{n+1}}{a_{n}}=\lim _{n \rightarrow \infty} e^{\frac{n-1}{n} \frac{n}{n+1}}=\lim _{n \rightarrow \infty} e^{-\frac{1}{n(n+1)}}=1
\end{gathered}
$$

得收敛半径为 1 , 故收敛区间为 $(-1,1)$;
当 $x=1$ 时 $\lim_{n \rightarrow \infty} \frac{1}{\sqrt[n]{n}}=1 \neq 0$, 当 $x=-1$ 时 $\lim _{n \rightarrow \infty} \frac{1}{\sqrt[n]{n}}$ 不存在, 故收敛域为 $(-1,1)$.

> 注：不要忘了$A^B = e^{B\ln A}$的变换！！

### 8.6 泰勒级数

#### 常见函数泰勒级数

$$
\begin{align}
(1)& e^x = \sum_{n=0}^\infin {1\over n!}x^n,& x \in (-\infin, +\infin)\\
(2)& \sin x = \sum_{k=1}^\infin {(-1)^{k+1}\over (2k-1)!} x^{2k-1},& x \in (-\infin, +\infin)\\
(3)& \cos x = \sum_{k=0}^\infin {(-1)^k\over (2k)!}x^{2k},& x \in (-\infin, +\infin)\\
(4)& {1\over 1+x} = \sum_{k=0}^\infin (-1)^kx^k, & x\in (-1,1)\\
(5)& \ln (x+1) = \sum_{k=0}^\infin {(-1)^k\over (k+1)}x^{k+1},& x \in (-1,1]\\
(6)& a^x = e^{x\ln a} = \sum_{n=0}^\infin {(\ln a)^n\over n!}x^n,& x \in (-\infin, +\infin)\\
(7)& \arctan x  =\sum_{k=0}^\infin {(-1)^n\over (2n+1)}x^{2n+1},& x\in [-1, 1]\\
(\bold8)& (1+x)^m = 1 + \sum_{n=1}^\infin {m(m-1))\cdots (m-n+1)\over n!}x^n,& x\in (-1,1)
\end{align}
$$

### 8.6 习题

1.求$\ln(x + \sqrt{1 + x^2})$的麦克劳林展开式。
$$
\begin{aligned}
   \ln \left(x+\sqrt{1+x^{2}}\right) &=\int_{0}^{x}\left[\ln \left(t+\sqrt{1+t^{2}}\right)\right]^{\prime} d t=\int_{0}^{x}\left(1+t^{2}\right)^{-\frac{1}{2}} d t \\
   &=\int_{0}^{x}\left(1+\sum_{n=1}^{\infty} \frac{-\frac{1}{2}\left(-\frac{3}{2}\right) \cdots\left(-\frac{1}{2}-n+1\right)}{n !} t^{2 n}\right) d t \\
   &=x+\sum_{n=1}^{\infty} \frac{(-1)^{n}(2 n-1) ! !}{(2 n) ! !} \int_{0}^{x} t^{2 n} d t \\
   &=x+\sum_{n=1}^{\infty} \frac{(-1)^{n}(2 n-1) ! ! x^{2 n+1}}{(2 n) ! !},|x|<1
   \end{aligned}
$$

2. (11) $\int_{0}^{x} \frac{sin t}{t} dt$;
   $$
   \begin{align}
   &\int_{0}^{x} \frac{\sin t}{t} d t=\int_{0}^{x} \frac{1}{t} \sum_{n=0}^{\infty}(-1)^{n} \frac{t^{2 n+1}}{(2 n+1) !} d t=\sum_{n=0}^{\infty} \frac{(-1)^{n}}{(2 n+1) !} \int_{0}^{x} t^{2 n} d t \\
   &=\sum_{n=0}^{\infty} \frac{(-1)^{n}}{(2 n+1) !(2 n+1)} x^{2 n+1}, x \in R, x \neq 0
   \end{align}
   $$

3. (3) $\frac{1}{x}, x_{0}=3$;

   > **法一** 解 $\left(\frac{1}{x}\right)^{(n)}=\frac{(-1)^{n} n !}{x^ {n+1}}$
   > 故展开式为
   > $$
   > \sum_{n=0}^{\infty} \frac{(-1)^{n}}{3^{n+1}}(x-3)^{n}, 0<x<6
   > $$

4. 

**法二** 
$$
令\ t = x - 3 \iff x = t + 3.\\
\frac{1}{x} = \frac{1}{t + 3} = {1\over 3}\cdot {1\over 1 + {t\over 3}}.\\
\because{1\over 1+x} = \sum_{k=0}^\infin (-1)^kx^k, & x\in (-1,1)\\
\therefore{1\over x} = {1\over 3}\sum_{k = 0}^\infin {(-1)^k\over 3^k}(x-3)^k\quad \square
$$

### 8.7 广义积分敛散性

#### 柯西收敛定理

$$
对于给定的\varepsilon > 0, 存在R > a,使得当A_1,A_2 > R时,恒有\\
|\int_{A_1}^{A_2}f(x)| < \varepsilon.
$$

#### 非负可积函数判别法

非负可积函数$\int_0^{+\infin}f(x)dx$收敛的充要条件是函数有上界.

#### 比较判别法

####  比较判别法的极限形式

#### Dirichlet判别法

#### Abel判别法



#### 做题步骤

1. 判断广义积分的奇点(若有多个,需要分段)
2. 对每个部分判断敛散性,方法:
   1. 比较判别法
   2. 放缩
   3. 拆分
   4. Abel审敛法(有界+积分收敛)
   5. Dirichlet审敛法(单调趋于零+积分有界)
   6. 非负项有上界

### 8.7 习题

1. 

$$
-\sum_{k = 1}^\infin {1\over 2k-1} + \sum _{k = 1}^\infin{1\over 2k} =\ ?
$$

2. $$
   讨论\int_0^{+\infin} x^pe^{-x}\mathrm{d}x敛散性.
   $$

3. $\int_{0}^{\frac{\pi}{2}} \ln \cos x d x$
   解 $x=\frac{\pi}{2}$ 是奇点
   $$
   \begin{aligned}
   \lim _{x \rightarrow\left(\frac{\pi}{2}\right)^{+}}\left(\frac{\pi}{2}-x\right)^{p} \ln \cos x=\lim _{t \rightarrow 0^{+}} t^{p} \ln \sin t=\lim _{t \rightarrow 0^{+}} \frac{\ln \sin t}{t^{-p}}=\lim _{t \rightarrow 0^{+}} \frac{\frac{1}{\sin t} \cos t}{-p t^{-p-1}} \\
   &=\lim _{t \rightarrow 0^{+}}-\frac{t^{p}}{p}=0
   \end{aligned}
   $$
   故原式收敛

4. $\int_{0}^{+\infty} x^{p} \ln (1+x) d x$
   解 $\int_{0}^{+\infty} x^{p} \ln (1+x) d x=\int_{0}^{1} x^{p} \ln (1+x) d x+\int_{1}^{+\infty} x^{p} \ln (1+x) d x$

   1. x = 0(可能奇点)
      当 $x \rightarrow 0, x^{p} \ln (1+x) \sim x^{p+1}$,

   $$
   \int_{0}^{1} x^{p} \ln (1+x) d x=\left\{\begin{array}{l}
   \text { 收敛, 若 } p+1>-1, \text { 即 } p>-2 \\
   \text { 发散, 若 } p+1<-1, \text { 即 } p \leq-2
   \end{array}\right.
   $$

   2. 当 $x \gg 1$ 时

   $$
   \begin{gathered}
   x^{p} \ln (1+x) \leq C x^{p+\varepsilon}, \forall 0<\varepsilon<1 \\
   \int_{0}^{1} x^{p} \ln (1+x) d x=\left\{\begin{array}{l}
   \text { 收敛, 若 } p+\varepsilon<-1 \\
   \text { 发散, 若 } p+\varepsilon \geq-1
   \end{array}\right.
   \end{gathered}
   $$

   所以当 $-2<p<-1$ 时, $\int_{0}^{1} x^{p} \ln (1+x) d x$ 收敛

   > 结论: $\ln x \ll $
