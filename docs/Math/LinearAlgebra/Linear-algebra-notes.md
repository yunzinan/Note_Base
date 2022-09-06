---
abbrlink: '0'
---
# 线性代数复习笔记

## 行列式

**行列式交换两行要变号**！

行列式的交换在证明题更推荐每次只交换相邻行。（如副对角行列式、副对角分块行列式）

### 一些特殊行列式

- **范德蒙行列式**

> 形如
> $$
> \left|\begin{array}{cccc}
> 1 & 1 & \ldots & 1 \\
> x_{1} & x_{2} & \ldots & x_{n} \\
> \vdots & \vdots & & \vdots \\
> x_{1}^{n-1} & x_{2}^{n-1} & \ldots & x_{n}^{n-1}
> \end{array}\right|
> $$
> 的n阶行列式称为范德蒙行列式。
> 若 $D_{n}$ 为 $n$ 阶范德蒙行列式 $(n \geq 2)$ ，则有 
> $$
> D_{n}=\prod_{1 \leq j<i \leq n}\left(x_{i}-x_{j}\right)
> $$
> **注意是后面的减前面的！！**

- 分块行列式
- 上下三角行列式和主对角行列式
- 副对角行列式

### 行列式的计算

- 三阶不含参行列式直接降阶成二阶，除非一眼看出特殊性
- 含参行列式一定要先化简！对行列式的化简会比多项式容易直观
- 四阶及以上行列式先看看有没有特殊性（**每行（列）元素相等、能产生零行**），不行一般化为上三角行列式，利用对角行列式的结论。
- 行列式方程的求解形如$Ax =0$
  - 先猜根，根据行列式为零的情形
    - 行列式每一行或列相加相等
    - 行列式有两行相同
  - n阶行列式最多有n次多项式，因此最多有n的不同的解，猜不到的解就化简行列式，化简+降阶展开，最后得到多项式
- 证明行列式相等：
  - 左推右
  - 右推左
  - 两遍分别转化或者直接求出答案，判断是否相等
- 对于沿对角线存在自相似关系的行列式，尝试降阶得到$D_n与D_{n-1}\ D_{n-2}$的递推关系，有时还要借助数学归纳法（先找规律，再证明）
- 如果行列式中每个元素均为（可以看成）两个数之和，利用行列式的线性性，化为$2^n$个行列式之和，很多为零，或者很好求。
- 范德蒙行列式要能看出来
- 看看能不能交换一些行或者列，转化成分块行列式。

## 矩阵

> 反对称阵：$A^T = -A$

矩阵不满足消去律！即使$AB = AC \and A \ne O$！，除非A可逆！

- 对于含参较为复杂的矩阵方程，化为行梯形后，不方便再化为行简化，那么就可以直接退化为方程组，解方程组。

- 对于含参的矩阵，尽可能把含参的部分放到下边，右边（如果允许列变换）

  - 求解线性方程组讲增广矩阵化为梯形矩阵的过程中，不能用倍加列变换和倍乘列变换，而两列交换可以用，此时相对应的未知元也要对换。
  - 尽可能避免将某行$\times {k \over a}$加到别的行上去，这样需要对a是否为0进行讨论。这也就是为什么需要尽可能将含参数的部分换到右下角去的原因。

- 为使消元计算比较方便，要尽可能先用初等行变换将第1行第1列的元素化为1，然后再将其余行化为0，对于2，3，4，列同理。

- 求$A^n$的题目

  - 先求求$A^2, A^3$，找规律
  - 看$A能否拆成(B+kI)的形式$，利用二项式定理，往往$B^k, k \geq k_0$时$B^k = 0$

- 求$(AB)^n 或者(\alpha \beta)^n$的题目

  - 利用结合律，看看$BA 或者\beta \alpha$是否方便

- 求可逆矩阵

  - 思考这个矩阵对应的线性变换，直观的推导出出逆矩阵

  - 利用伴随阵$A^{-1} = {1\over |A|}A^*$

  - $(A\ E) \rightarrow (E\ A^{-1})$ 仅利用初等行变换

  - 分块矩阵（尤其是分块对角阵）
    $$
    \left(\begin{array}{cc}A & O\\
    O & B\end{array}\right)^{-1} = 
    \left(\begin{array}{cc}A^{-1} & O\\ O & B^{-1}\end{array}\right).\\
    \left(\begin{array}{cc}A & C\\
    O & B\end{array}\right) \left(\begin{array}{cc}X_1 & X_2\\
    X_3 & X_4\end{array}\right) = E\\
    \Rightarrow \begin{cases}AX_1 + CX_3 = E\\ AX_2 + CX_4 = O\\ BX_3 = O\\ BX_4 = E \end{cases}\\
    \Rightarrow \begin{cases}X_4 =B^{-1}\\
    X_3 = O\\
    X_2 = -A^{-1}CB^{-1}\\
    X_1 = A^{-1}
    \end{cases}\\
    \Rightarrow\left(\begin{array}{cc}A & C\\
    O & B\end{array}\right)^{-1} = 
    \left(\begin{array}{cc}A^{-1} & -A^{-1}CB^{-1}\\ O & B^{-1}\end{array}\right).\\
    $$

- 求解线性方程组

  - $Ax = 0$
    - $|A| \ne 0 \iff r(A) = n \iff 列向量组线性无关 \iff x = A^{-1}0 = 0 \iff 方程只有零解$
    - $|A| = 0 \iff r(A) < n \iff 列向量线性相关 \iff \exist \vec{\alpha} = {(k_1, k_2, \cdots,k_n)}^T,s.t\ A\vec{\alpha} = 0\\ \iff 对于任意k倍\alpha,都是方程组的解\ 方程组有无穷多解，i.e.有非零解$ 
    - 注意：$|A| \ne 0 \iff 列向量线性无关，同时行向量也是线性无关的\iff |A^T| \ne 0$
  - $Ax = b$ 
    - $|A| \ne 0 \iff r(A) = n \iff x= A^{-1}b \iff 有唯一解$
    - $|A| = 0 \iff r(A) < n \iff 列向量线性相关$

## 线性方程组

### 线性相关

- 如果向量组A:$\{\alpha_1,\alpha_2,\dots,\alpha_l\}$能由向量组B:$\{\beta_1,\beta_2\dots,\beta_s\}$表示，那么$r(A) \le r(B)$
  - $l > r(A) \Rightarrow A线性相关\\ l = r \Rightarrow A线性无关$
  - 特别的，若A线性无关，$l = r(A) \le r(B) \le s$
  - 推论：若$l > s$，则A必然线性相关，事实上，若$l > r(B)$，那么A线性相关。

#### 判断线性相关性

- $向量数>向量维数\Rightarrow  线性相关$
- 如果向量数=向量维数，可以考虑直接算行列式。
- 观察法：如果直接看出一个向量可以由别的向量表示，则相关
- 作成矩阵，化简，计算秩与列向量数的关系
- 若几个向量线性相关，那取它们的一部分维度构成的新向量们也线性相关

#### 求向量组的一个极大无关组

将各列向量作成矩阵，仅通过行初等变换，化成行梯形，则非零行数即为秩（亦即极大无关组向量个数），且每行第一个非零数对应的列所对应的向量构成一个极大无关组。

==注==：找到极大无关组后还要说明它们线性无关！（可以构造分块矩阵的行列式）

>  行满秩矩阵： *若矩阵秩等于行数，称为行满秩*
>
>  ==注意==: 行满秩矩阵的列数一定大于等于行数.

#### 秩的不等式

$$
1)\quad &r(A+B) \le r(A) + r(B)\\ 
 2)\quad &r(AB) \le \min\{r(A),r(B)\} \\
 3)\quad &对于方阵A,B,r(AB) \ge r(A) + r(B) - n;\\
 4)\quad &若A，B分别是m\times n, n\times s矩阵,且AB=O,则r(B) \le n - r(A)\\
 5)\quad &若A为m\times n矩阵，则r(A^TA) = r(A) = r(A^T)
$$

- 证明：

$$
4)& B的每一个列向量都是Ax = 0的一个解，而Ax= 0的基础解系构成的向量组r = n - r(A)\\
 &所以r(B) \le n - r(A).\\
5)& Hint. 证明Ax= 0 与A^TAx = 0是同解方程组，具有相同的基础解系，故秩相等.
$$

- 若两个方程组为**同解方程组**，那么它们的系数矩阵的秩相同。

#### 解线性方程组

##### 齐次方程

- 一个方程的自由变量数 = $n - r(A)$，n为列向量数，也是基础解系中向量数。
- 通过对自由变量自由赋值，来确定非自由变量的取值。

##### 非齐次方程

- 非齐次方程解的存在性：$r(A\ b) = r(A)$，即$\vec{b}$与A线性相关，或者说方程的最下面一条等式左边要有系数。
- $Ax = b 的解为x = \eta + k_1\alpha_1 + k_2\alpha_2 + \dots k_{n-r}\alpha_{n-r}\\ 式中A\eta = b \quad A\alpha_i = \theta\\ \Rightarrow A(\eta + \alpha_i) = b$
- 对增广矩阵做行变换。
- 计算基础解系的方法同解齐次（注意：这里解的是$Ax =\theta$！！），还要再对自由变量赋值一次（一般全赋0），解$Ax= b$，求出一个特解$\eta$.

#### 非齐次方程组解的结构

##### 无解

- $r(A) \ne r(A\ b)$
- 两个方程矛盾（其实可以化归到上一类）

##### 有唯一解

- $r(A) = r(A\ b) = n$

##### 有无穷多解

- $r(A) = r(A\ b) < n$

##### 解答矩阵（非常有用的技巧）

> 注：一定要先化成行简化！

![](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428200550659.png)

![image-20220428201056100](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428201056100.png)

![ ](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428202829132.png)

## 特征值和特征向量

### 特征值和特征向量的性质

- $\lambda$可以是0，但是$\xi$不可以是0.

  >  $\lambda$为0$\iff|A| = 0.$若$\xi = \theta$则$A\xi = \lambda\xi$的$\lambda$可以是任何值。

- 每个特征向量只属于一个特征值。

- 特征多项式$f(\lambda) = 0$在**复数域**内有n重根！！（很可能有虚根，因此特征方程的实数根的重数可能小于n）。

- 每个特征值至少对应一个线性无关的非零的特征向量，这意味着$(\lambda E- A)x = \theta$有非零解。因此$\lambda E - A$不可能满秩。

- $\lambda$也是$A^T$的特征值

- 若$A$可逆，且$\lambda\ne 0$，$A\xi = \lambda \xi$，则$\xi 是 A^{-1}, A^*, f(A)关于特征值\lambda^{-1},\lambda^{-1}|A|,f(\lambda)的一个特征向量.$

  > ==注意==:需要强调特征多项式$f(A)\sim f(\lambda)$ 的关系,任意矩阵的多项式与其特征值有同样的关系,往往结合$|A| = \Pi\lambda_i$来操作.

- 属于同一个特征值的不同特征向量的线性组合同样是特征向量。

- 不同特征值的特征向量线性无关。

- **$k$重特征值最多有$k$个线性无关的特征向量。**

- 若n阶方阵的n个特征值分别为$\lambda_i, 1\le i\le n$，则$\prod \lambda_{i}=|A|, \sum \lambda_i = tr(A).$

### 特征值与秩的关系

  - ![1](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220610211626079.png)




### 矩阵相似

$$
对于矩阵A,B,如果存在\bold{可逆}矩阵P,使得B = P^{-1} A P,则称A \sim B .
$$

- $A \sim B \Rightarrow f(A) \sim f(B)$

- 相似矩阵的特征值都相同。

  $A\xi = \lambda \xi, A = P^{-1}BP \\ \Rightarrow P^{-1}BP \xi = \lambda \xi \\ \Rightarrow B(P\xi) = \lambda (P\xi)\ \square.$
  $$
  |\lambda E-A| = |\lambda E - P^{-1}BP| = |P^{-1}(\lambda E- B) P| = |P^{-1}||\lambda E -B||P| = |\lambda E -B|.
  $$

  > 相似矩阵具有相同的特征多项式。因此有相同的特征值。因此有相同的行列式，有相同的迹。

  ### 矩阵可对角化的条件

  n阶矩阵A与对角阵$\Lambda$相似的条件是**A有n个线性无关的特征向量**。或**A关于每个特征值对应的线性无关的特征向量的个数等于该特征值的重数。**

### 矩阵对角化

#### 矩阵可对角化的充要条件

1. n阶矩阵有n个无关的特征向量.

2. 每个$k_i$重特征值$\lambda_i$对应的特征矩阵$\lambda_iE-A$的秩为$n - k_i$.

   > **条件2**非常重要!! 想要说明有这么多的不相关的特征向量, 要么采用构造法, 找到这么多的特征向量, 并说明无关. **要么(常常)是转化为线性方程组解的问题, 与$\lambda_i E -A$的秩有关!!**

### 实对称矩阵的对角化

  #### 实对称矩阵的性质

  - 特征值都是实数。特征向量也是实向量。

  - 属于不同特征值的特征向量是**正交**的

  > 这意味着求的对应特征值的特征向量时,只需要对这个特征值对应的几个特征向量正交化即可,不同特征值对应的特征向量已经是正交的了.
  >
  > ==注意==: 由于不同特征值的特征向量是正交的,因此如果3阶实对称矩阵已知两个属于不同特征值的特征向量,那么剩下来的那个特征向量也是必然是与这两个特征向量正交的,于是可以求得第三个特征向量.

  - **实对称矩阵一定和对角阵相似**。

    > 1. 实矩阵都有n个特征值(含重根),然而有些特征值为复数.而实对称矩阵保证了所有的特征值都是实数.
    > 2. **实对称阵保证了每个特征值对应的不相关特征向量数都达到最大值**(推论)

  - 实对称矩阵一定有n个不相关的特征向量.

  - 存在**正交阵**$P$使得$P^TAP = P^{-1}AP = diag(\lambda_1,\lambda_2,\dots,\lambda_n).$**注意这里的正交阵是不唯一的（基的选取方式不唯一），但是得到的对角阵是唯一的（相似标准型）。**

#### 正交矩阵的性质

1. $A^T = A^{-1}$
2. $AA^T = A^TA = E$
3. $A$的列向量\行向量构成**标准**正交向量组.
4. $|A|^2= 1$
5. $|\lambda| = 1$

#### 将向量组施密特正交化\标准正交化

1. 施密特正交化$\xi_i = \alpha_i - \sum_{j=1}^{i-1}{(\alpha_i,\xi_j)\over ||\xi_j||^2}\xi_j$.

   > **问** 为什么这样操作能保证$\xi_i$与之前得到的$\xi_1, \xi_2, \dots $正交?
   >
   > **答** (强数学归纳法) $I.S.\forall j < i, (\xi_i,\xi_j) = (\alpha_i, \xi_j) - {(\alpha_i, \xi_j)\over ||\xi_j||^2}(\xi_j,\xi_j) = 0.$

2. 标准化$\eta_i = {1\over ||\xi_i||}\xi_i$.(使模长为1)

#### 对角化的方法(相似变换矩阵P的求法)

1. 求解$|A -\lambda I| = 0$得到A的特征值
2. 对于每一个特征值,求解$(A - \lambda I)x = \theta $解得对应重数的不相关的特征向量
3. 将所有特征向量按顺序排列得到相似变换矩阵$P$.对应的特征值按序组成对角阵$\Lambda$.于是有$P^{-1}AP =\Lambda $.

![image-20220603105152613](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220603105152613.png)

#### 正交矩阵的求法

> ==注意==: 只有实对称阵才存在正交矩阵$P^T = P^{-1}$!!

1. 求解$|A -\lambda I| = 0$得到A的特征值
2. 对于每一个特征值,求解$(A - \lambda I)x = \theta $解得对应重数的不相关的特征向量
3. 由于实对称阵,**任意属于不同特征值的特征向量已经是正交的了**,因此只需要对属于同一个特征值的$k_{i}$个特征向量**标准正交化**即可.
4. 将所有标准正交化的特征向量按顺序排列得到正交矩阵$P$.对应的特征值按序组成对角阵$\Lambda$.于是有$P^TAP = P^{-1}AP = \Lambda$.

 ## 二次型

  ### 合同关系

  二次型$x^TAx$通过非退化的线性变换$x = Cy$，化为$y_1, y_2, \cdots, y_n$的二次型$$x^TAx = y^T(C^TAC)y = y^TBy$$，则$B = C^TAC$，$B与A合同.$

- 任意两个n阶实对称矩阵合同的充分必要条件是有相同的规范型。

  ### 将实二次型化为标准型（平方和）的方法

  - 正交变化法（即求变换A的**正交矩阵**P,利用$P^TAP  =diag(\lambda_i)$）

  - 配方法

  - 合同变换法
    $$
    \left(\begin{array}{l}
    A \\
    I
    \end{array}\right) \rightarrow\left(\begin{array}{c}
    C^{T} A C \\
    C
    \end{array}\right)
    = \left(\begin{array}{c}
    \Lambda \\
    C
    \end{array}\right)
    $$

### 惯性定理

> ==注意==: 讨论范围是**实二次型**矩阵,即实对称阵!

- 正惯性指数 p，负惯性指数r-p

- $A一定合同于diag(1,1,\dots, 1,-1,-1,\dots, -1, 0, 0,\dots,0)$，其中1的个数等于正惯性指数。

#### 惯性指数的求法

1. 求特征值.正特征值数等于正惯性指数.负特征值数等于负惯性指数.
1. 直接合同变换

### 正定矩阵

对于任意非零向量x，关于x的**实二次型**$x^TAx > 0$恒成立

> ==注意==: 在满足这些性质之前,首先要满足的性质是**实对称阵/实二次型**!!
>
> 因此在证明一个矩阵是否为正定矩阵时,先要说明其为实对称阵,然后说明符合一条等价条件.

- 几种等价的表述

  - A为正定矩阵

  - 正惯性指数为n, $A \sim I.$

  - 存在**可逆**阵$P$,$A = P^TP.$

    > 这条很重要!

  - A的n个特征值都大于0

    > 只要说明A的所有特征值都大于0即可.
    >
    > 典型的题目是: $(A-E)(A-2E) = O$.

  - A的各阶顺序主子式都大于零(一共n个)。

  - (A的所有主子式都大于0)

- $x^TAx = (Ax)^Tx = (Ax, x)$

- 正定矩阵的一些性质

  - $A正定\iff A有分解A= D^TD(D可逆)$.

    > $P^TAP =E\Rightarrow A = (P^T)^{-1}P^{-1}.$

## 线性空间

### 线性空间的判定

$V是一个非空集合,K是一个数域,定义加法和数乘运算，满足以下条件:$

1. 加法和数乘对$V$封闭：

   1. $v_1 + v_2 \in V$
   2. $k \cdot v_1 \in V$

2. 加法满足以下性质：
   $$
   (1)& v_1 + v_2 = v_2 + v_1\\
   (2)& v_1 + (v_2 + v_3) = (v_1 + v_2 ) + v_3\\
   (3)& \exist \bold{0}, \bold{0} + v = v\\
   (4)& \forall v_1 \in V, \exist v_2 \in V, v_1 + v_2 = \bold{0}\\
   $$

3. 数乘满足以下性质:
   $$
   (1)& (a + b)\cdot v = a\cdot v + b\cdot v \\
   (2)& a\cdot (v_1 + v_2) = a\cdot v_1 + a\cdot v_2\\
   (3)& a\cdot (b\cdot v) = (ab)\cdot v\\
   (4)& 1 \cdot v = v\\
   $$

### 线性空间的性质

- 零元素唯一

- 任一元素的负元是唯一的

- $$
  设0,1,-1,\lambda \in K, x, -x, \bold{0}\in V\ 则有\\
  \begin{align}(1)& 0x = \bold{0} \\
  (2)& (-1)x = -x\\
  (3)& \lambda \bold{0} = \bold{0}\\
  (4)& \lambda x = \bold{0} \to \lambda = 0 \or x = \bold{0}.\\
  \end{align}
  $$

- 

### 空间的基、维数、坐标

- $\dim (V) = n$记作维数

- $$
  设\alpha_1,\alpha_2,\cdots,\alpha_n为一组基,则n个向量(\beta_1\ \beta_2\ \cdots\ \beta_n) = (\alpha_1\ \alpha_2\ \cdots\ \alpha_n)D为一组基的充要条件是\\
  |D| \ne 0.
  $$

### 基(底)变换与坐标变换

$$
(\beta_1\ \beta_2\ \cdots\ \beta_n) = (\alpha_1\ \alpha_2\ \cdots\ \alpha_n)P,\\
P = (a_{ij})_{n\times n}.\\
P称作从基底\Phi:\alpha_i,1\le i\le n到\Psi:\beta_i,1\le i\le n的\bold{过渡矩阵}.\\
\left(\begin{array}{c} x_1 \\ x_2 \\ \vdots \\ x_n \end{array}\right) = 
P\left(\begin{array}{c} y_1 \\ y_2 \\ \vdots \\ y_n \end{array}\right)\\
\left(\begin{array}{c} y_1 \\ y_2 \\ \vdots \\ y_n \end{array}\right) = P^{-1}\left(\begin{array}{c} x_1 \\ x_2 \\ \vdots \\ x_n \end{array}\right).
$$

> **注**: 注意到基变换将基底由$\alpha_i$变为$\beta_i$,乘以了过度矩阵P,但是由原先$\alpha_i$下的坐标$(x_i)$变换过程却是乘了$P^{-1}$.这其实很容易理解,举例来说,若基向量由原先的拉伸3倍,那么对应的坐标也就收缩了3倍,相当于拉伸了$3^{-1}$倍.不难发现这个坐标变换过程中有这样的关系$\xi = (\alpha_i)\vec{x} = (\beta_i)\vec{y}$,而不变量是$\xi$,因此基底变换与坐标变换间存在**互逆**的关系.

#### 判断两组基下是否存在相同坐标的非零向量

问题转化为判断$\exist \xi \ne \theta, \xi = P\xi$ 是否为真 $\iff (P-E)x = \theta$是否有非零解。

### 线性子空间

$$
dim(W_1 + W_2) + dim(W_1 \cap W_2)= dim(W_1) + dim(W_2).
$$



#### 直和

- $W_1 +W_2$中任意向量都只能惟一的表示为$W_1$中一个向量$+W_2$中一个向量.
- $dim(W_1\cap W_2) = 0,i.e. W_1 \cap W_2 = \{\bold{0}\}$.

### 线性变换

定义运算:线性映射$T:V_1\to V_2, \alpha \to Ta$

- 线性组合的线性变换=线性变换的线性组合
- 若两个线性变换对一组基的映射得到的像都相同,则两个线性变换相等.
- 线性变换对应着基的变换

#### 线性变换的矩阵表示

> 线性变换是对线性空间进行变换,如沿某方向拉伸\旋转\切变等,这个变换将所有的$V$中的向量$\alpha$变为其像$T\alpha$.
>
> 但是,空间中有无数个向量,我们无法对每一个向量都描述其像是什么.于是,我们利用向量空间的线性性质,即任何向量都可以表示为基向量的线性组合,以及线性变换的线性性质,即线性组合的线性变换等于线性变换的线性组合,这样,我们就可以通过描述有限个基向量的变换情况,来给出获得任意向量的像的构造方式: 选取一组基,将向量用基向量线性表示,也就是对应基向量的坐标,这样,线性变换改变基向量,但不改变线性组合方式(坐标),我们仍可以用这组坐标表示出映射的结果.
>
> 同时,注意到既然线性变换将基向量改变,那相当于得到了一组新的基向量,那么这个A就是过渡矩阵, 因为基变换对应坐标变换, 因此, 如果我们想用原先的基向量来表示像, 就需要进行左边变换,即$y = Ax$.
>
> ==注意==: 为什么这个地方不是$y = A^{-1}x$? 
>
> $(T\varepsilon_1, T\varepsilon_2, \dots ,T\varepsilon_n)x = (\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n)Px = (\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n)y $. 相当于过渡回去了.

- 线性变换与其对应的矩阵构成**双射**:$T(\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n) = (\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n)A$.

#### 线性变换在不同基底下的矩阵的关系

若$(\beta_i) = (\alpha_i)P$,则$B = P^{-1}AP$.

**证明** (1) $\xi$在两基底下相等: $\xi = (\beta_i)y = (\alpha_i)P y = (\alpha_i)x \Rightarrow y = P^{-1}x$

(2)$T\xi$在两基底下相等: $T\xi = (\beta_i)By = (\alpha_i)PBy = (\alpha_i)PBP^{-1}x = (\alpha_i)Ax \Rightarrow A = PBP^{-1}$.

**推论** 两矩阵相似的充要条件是它们是某个线性变换在不同基底下的矩阵.

#### 线性变换的特征值与特征向量

$T\xi = T(\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n)x = (\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n)Ax \\ = \lambda \xi = \lambda(\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n)x = (\varepsilon_1, \varepsilon_2, \dots ,\varepsilon_n)\lambda x\\ \Rightarrow Ax = \lambda x$

**步骤**

1. 求出T下的矩阵A
2. 求出A的特征值和对应的特征向量
3. A的特征值就是T的特征值,A的特征向量就是T的特征向量在基底下的坐标.

**定理**

线性变换在不同基下的特征值和特征多项式(矩阵的特征多项式,因为相似矩阵有相同的特征多项式)与所选基底无关.

# 常用技巧

## 矩阵的秩相关

### 秩不等式

$$
1)\quad &r(A+B) \le r(A) + r(B)\\ 
 2)\quad &r(AB) \le \min\{r(A),r(B)\} \\
 3)\quad &对于方阵A,B,r(AB) \ge r(A) + r(B) - n;\\
 4)\quad &若A，B分别是m\times n, n\times s矩阵,且AB=0,则r(B) \le n - r(A)\\
 5)\quad &若A为m\times n矩阵，则r(A^TA) = r(A) = r(A^T)
$$

> **注** 比较常用的有(1),**(2)**,(3)
>
> (2) $r(A) = r(\alpha\beta^T) \le \min\{r(\alpha),r(\beta^T) \} = 1$.

### 秩的等式

$$
\begin{align}
(1)& 若A,B为n阶矩阵,r(A) = n,则r(AB) = r(B)\\
\end{align}
$$



# 好题荟萃

## 书本习题

### 习题1

#### 5（2）

$$
\left|\begin{array}{llll}
x & a & b & c \\
a & x & c & b \\
b & c & x & a \\
c & b & a & x
\end{array}\right|
$$

> 很明显的分块阵 要尽量利用分块阵行列式的结论。

- 设A是$m\times n$的矩阵($m < n$)，且$r(A) = m$，证明存在$n\times m$阶矩阵B，使得$AB = I_m$

$$
Hint.利用(1)标准型:A = P\left(\begin{array}{cc}
I_{r} & 0 \\
0 & 0
\end{array}\right)Q \\这个过程不改变秩.\\
(2)分块阵的切分证明.
$$

- 对矩阵、行列式化简时，
  - 避免造成引入更多的参数$\rightarrow$导致讨论变得复杂
  - 尽量避免分数的出现（尽量让“第一行”变成1或者-1）

### 习题2

#### 37

$证明若A,B可逆,A+B也可逆,\\则A^{-1} + B^{-1}也可逆，并求逆阵$

![image-20220428103408983](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428103408983.png)

- 可逆阵A乘一个矩阵B，$r(AB) = r(B)$

#### 56 

求两个含参向量组何时能够等价

==推广：证明两个矩阵等价的方法==



#### 60

> 注：把两个向量组并起来也是比较有用的手段

![image-20220428105345261](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428105345261.png)

### 习题4

#### 4

![image-20220428113724967](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428113724967.png)

#### 6

![image-20220428114500525](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428114500525.png)

#### 11

> 根据特征值和特征向量求原方程
>
> 写出P 硬算.

#### 12

![image-20220428115736048](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428115736048.png)

#### 16

![image-20220610200942777](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220610200942777.png)

#### 17

已知n阶矩阵满足$M^2 - 3M + 2E = O$,试证M可对角化.

> **法一** $\lambda^2 - 3\lambda + 2 = 0 \Rightarrow \lambda = 1或2$,因此所有特征值均大于0,因此A为正定对称阵.而正定阵*是*实对称阵,实对称阵一定可对角化.
>
> **法二** 
>
> > 回顾矩阵可对角化的充要条件
> >
> > 1. n阶矩阵有n个无关的特征向量.
> > 2. 每个$k_i$重特征值$\lambda_i$对应的特征矩阵$\lambda_iE-A$的秩为$n - k_i$.
>
> 利用2. 设$\lambda = 1$(a重根), $\lambda = 2$(b重根)(a+b = n), 令$A = E-M, B = 2E - M$.
> $$
> (1)&r(O) = r(AB) \ge r(A) + r(B) - n \Rightarrow r(A) + r(B) \le n\\
> (2)&r(A) \ge n- a, r(B)\ge n-b\Rightarrow r(A) + r(B)\ge n\\
> &\Rightarrow r(A) + r(B) = n \Rightarrow r(A) = n-a, r(B) = n-b.\square
> $$

#### 18

![image-20220428115922533](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428115922533.png)

#### 28

![image-20220428115950421](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220428115950421.png)

### 习题5

> 实对称阵这部分内容,感觉比较常见的操作有: 结合特征值, "开根号拆分", 结合秩与无关解的个数

#### 7

设$A\in R^{m\times n}$为列满秩矩阵, 证明$B = A^TA$为对称正定矩阵.

> **注** 列满秩矩阵是指矩阵的秩等于列数n,==这意味着$m \ge n$==.
> $$
> A列满秩\Rightarrow \forall x\ne \theta, Ax \ne \theta, x^TBx = x^TA^TAx = (Ax)^T(Ax)  = (Ax, Ax) > 0.\square
> $$

#### 9

设$A\in R^{m\times m}, B\in R^{n\times n}$均为对称矩阵, 证明存在$\xi \in R^{m+n}, \xi \ne \theta $, $\xi^T\left({\begin{array}{cc} A &   0 \\ 0 & -B\end{array}}\right)\xi  = 0.$

> 将$\xi $分块$(\xi_1, \xi_2)$,乘进去,得到$\xi_1^TA\xi_1 - \xi_2^TB\xi_2 = 0$
>
> 下面的问题在于: 怎么找到满足要求的$\xi_{1,2}$? 
>
> **一个比较常见的做法**
>
> 令$\xi_1 = (\sqrt{a_{11}}, 0, 0, \dots)^T, \xi_2 = (\sqrt{b_{11}}, 0, 0, \dots)^T$(利用到了1阶顺序主子式大于0)

#### 18

证明$A是正定矩阵\iff A有分解A = B^2, B为正定阵.$

> $$
> A = P^T\Lambda P = P^T\Lambda'\Lambda'P = P^T\Lambda'PP^T\Lambda'P = B^2.
> $$

#### 19

设A为n阶正定阵,B为n阶对称阵,证明存在合同变换矩阵P,使得$P^TAP$与$P^TBP$均为对角矩阵.

> ==这题很重要==!!
>
> 关键在于**建立A与B的联系**
> $$
> 因为A正定,所以存在可逆R,A = R^TR\\
> 而((R^{-1})^TBR^{-1})^T仍然是一个对称阵.
> 而对于一个对称阵,一定存在合同变换矩阵(正交阵)Q^{-1},\\
> 使得(Q^{-1})^T((R^{-1})^TBR^{-1})Q^{-1}  = \Lambda,\\
> 因为Q为正交阵, Q^TQ = E,\\
> 所以A = R^TQ^TQR,\\
> ((QR)^{-1})^TA(QR)^{-1} = E\\
> ((QR)^{-1})^TB(QR)^{-1} = \Lambda.
> $$

#### 20

证明若A正定,则$|A+E|> 1$

> 正定阵常常利用特征值来解题
>
> **法一**(比较好说的做法) 
> $$
> 令B = A+E,记A的特征值为\lambda_i > 0,则B的特征值为\lambda_i+1 > 1.\\
> \therefore  |A+E|=|B| = \Pi (\lambda_i+1) > 1.\square
> $$
> **法二**(比较暴力的做法)
> $$
> |A+E| = |P^T\Lambda p + E| = |P^T||\Lambda+E||P| = |\Lambda+E| = \Pi (\lambda_i+1) >1.
> $$



## 往年真题

### 2014-2015-1

4. 若 $A$ 为 $n$ 阶可逆矩阵, $u, v$ 为 $n$ 维列向量, 若矩阵 $A+u v^{T}$ 有形式为 $A^{-1}+t\left(A^{-1} u v^{T} A^{-1}\right)$ 的逆矩阵, 其 中t为实数, 则 $t$ 为何值?
   解: $\left(A+u v^{T}\right)\left(A^{-1}+t\left(A^{-1} u v^{T} A^{-1}\right)\right)=E+u v^{T} A^{-1}+t u v^{T} A^{-1}+t\left(u v^{T} A^{-1} u v^{T} A^{-1}\right)=E$, 故 $u v^{T} A^{-1}+t u v^{T} A^{-1}+t u v^{T} A^{-1} u v^{T} A^{-1}=O$, 两边右乘 $A^{\prime}$ 得 $u v^{T}+t u v^{T}+t u v^{T} A^{-1} u v^{T}=u\left(1+t+t v^{T} A^{-1} u\right) v^{T}=O$,
   $\therefore u, v$ 不全为零时, 有 $t=-1 /\left(1+v^{T} A^{-1} u\right) ; u=\theta$ 或 $v=\theta$ 时, 有 $t$ 为任意实数。

二.(15分) 解线性方程组
$$
\left\{\begin{array}{l}
m x_{1}+n x_{2}+n x_{3}=n \\
n x_{1}+m x_{2}+n x_{3}=n \\
n x_{1}+n x_{2}+m x_{3}=n
\end{array}\right.
$$
其中参数 $m, n$ 不全为 0 。
解：方程组的增广矩阵 $B=\left(\begin{array}{ccc|c}m & n & n & n \\ n & m & n & n \\ n & n & m & n\end{array}\right) \stackrel{r}{\rightarrow}\left(\begin{array}{ccc|c}m+2 n & m+2 n & m+2 n & 3 n \\ n & m & n & n \\ n & n & m & n\end{array}\right)$. 当 $m+2 n \neq 0$ 时, $B \rightarrow\left(\begin{array}{ccc|c}1 & 1 & 1 & 3 n /(m+2 n) \\ 0 & m-n & 0 & (m-n) n /(m+2 n) \\ 0 & 0 & m-n & (m-n) n /(m+2 n)\end{array}\right)$,
故当 $m+2 n \neq 0$ 且 $m \neq n$ 时, $B \rightarrow\left(\begin{array}{lll|l}1 & 0 & 0 & n /(m+2 n) \\ 0 & 1 & 0 & n /(m+2 n) \\ 0 & 0 & 1 & n /(m+2 n)\end{array}\right)$,得唯一解 $\left(\begin{array}{c}n /(m+2 n) \\ n /(m+2 n) \\ n /(m+2 n)\end{array}\right)$. 当 $m+2 n \neq 0$ 且 $m=n$ 时, $B \rightarrow\left(\begin{array}{lll|l}1 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0\end{array}\right)$,得通解为 $\left(\begin{array}{c}1 \\ 0 \\ 0\end{array}\right)+k_{1}\left(\begin{array}{c}-1 \\ 1 \\ 0\end{array}\right)+k_{2}\left(\begin{array}{c}-1 \\ 0 \\ 1\end{array}\right)$. 当 $m+2 n=0$ 时, $B \rightarrow\left(\begin{array}{ccc|c}n & m & n & n \\ n & n & m & n \\ 0 & 0 & 0 & 3 n\end{array}\right)$, 若 $n=0$, 则 $m=0$, 与 $m, n$ 不全为 0 矛盾, 故 $n \neq 0$, 矩阵 最后一行得矛盾方程, 故无解。

五.(10分) 设 $n$ 阶矩阵 $C=\left(e_{i_{1}}, e_{i_{2}}, \cdots, e_{i_{n}}\right)$, 其中 $e_{j}=(0,0, \cdots, 1,0, \cdots, 0)^{T}($ 第 $j$ 个分量为 1 , 其余为 0$), j=$ $1,2, \cdots, n$, 而 $\left(i_{1}, i_{2}, \cdots, i_{n}\right)$ 为 $(1,2, \cdots, n)$ 的一个排列, 证明: (1) $C^{-1}=C^{T}$,
(2) $C^{-1} \operatorname{diag}\left(d_{1}, d_{2}, \cdots, d_{n}\right) C=\operatorname{diag}\left(d_{i_{1}}, d_{i_{2}}, \cdots, d_{i_{n}}\right)$.
证:
$\operatorname{diag}\left(d_{1}, d_{2}, \cdots,\left(\begin{array}{c}e_{i_{1}}^{T} \\ e_{i_{2}}^{T} \\ \vdots \\ e_{i_{n}}^{T}\end{array}\right)\left(e_{i_{1}}, e_{i_{2}}, \cdots, e_{i_{n}}\right)=\left(a_{k j}\right)_{n \times n}=\left(e_{i_{k}}^{T} e_{i_{2}}, \cdots, e_{i_{j}}\right)_{n \times n}=E\right.$, 故 $C^{-1}=\left(d_{i_{1}} e_{i_{1}}, d_{i_{2}} e_{i_{2}}, \cdots, d_{i_{n}} e_{i_{n}}\right)$,
(2) $\operatorname{diag}\left(d_{1}, d_{2}, \cdots, d_{n}\right)\left(e_{i_{1}}, e_{i_{2}}, \cdots, e_{i_{n}}\right)=\left(d_{i_{1}} e_{i_{1}}, d_{i_{2}} e_{i_{2}}, \cdots, d_{i_{n}} e_{i_{n}}\right)$, 故 $C^{-1} \operatorname{diag}\left(d_{1}, d_{2}, \cdots, d_{n}\right) C=C^{T}\left(d_{i_{1}} e_{i_{1}}, d_{i_{2}} e_{i_{2}}, \cdots, d_{i_{n}} e_{i_{n}}\right)=\operatorname{diag}\left(d_{i_{1}}, d_{i_{2}}, \cdots, d_{i_{n}}\right)$.

### 2014-2015-2

六. (15分) 设 $A=\left(\begin{array}{ccc}1 & -1 & -1 \\ -1 & 1 & 1 \\ 0 & -4 & -2\end{array}\right) \quad, \quad \beta_{1}=\left(\begin{array}{c}-1 \\ 1 \\ -2\end{array}\right)$,
(1) 求满足 $A \beta_{2}=\beta_{1}, A^{2} \beta_{3}=\beta_{1}$ 的所有向量 $\beta_{2}, \beta_{3}$;
(2) 对(1)中任意向量 $\beta_{1}, \beta_{2}, \beta_{3}$, 证明 $\beta_{1}, \beta_{2}, \beta_{3}$ 线性无关。
解: (1) $\left(A, \beta_{1}\right)=\left(\begin{array}{ccc|c}1 & -1 & -1 & -1 \\ -1 & 1 & 1 & 1 \\ 0 & -4 & -2 & -2\end{array}\right) \rightarrow\left(\begin{array}{ccc|c}1 & 0 & -\frac{1}{2} & -\frac{1}{2} \\ 0 & 1 & \frac{1}{2} & \frac{1}{2} \\ 0 & 0 & 0 & 0\end{array}\right), \therefore \beta_{2}=\left(\begin{array}{c}-\frac{1}{2} \\ \frac{1}{2} \\ 0\end{array}\right)+k_{1}\left(\begin{array}{c}\frac{1}{2} \\ -\frac{1}{2} \\ 1\end{array}\right)$, $\left(A^{2}, \beta_{1}\right)=\left(\begin{array}{ccc|c}2 & 2 & 0 & -1 \\ -2 & -2 & 0 & 1 \\ 4 & 4 & 0 & -2\end{array}\right) \rightarrow\left(\begin{array}{ccc|c}1 & 1 & 0 & -\frac{1}{2} \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0\end{array}\right), \therefore \beta_{2}=\left(\begin{array}{c}-\frac{1}{2} \\ 0 \\ 0\end{array}\right)+k_{2}\left(\begin{array}{c}-1 \\ 1 \\ 0\end{array}\right)+k_{3}\left(\begin{array}{l}0 \\ 0 \\ 1\end{array}\right)$.
(2) 易知 $A \beta_{1}=\theta$, 设 $t_{1} \beta_{1}+t_{2} \beta_{2}+t_{3} \beta_{3}=\theta$, 则 $\left\{\begin{array}{l}t_{1} \beta_{1}+t_{2} \beta_{2}+t_{3} \beta_{3}=\theta, \\ A\left(t_{1} \beta_{1}+t_{2} \beta_{2}+t_{3} \beta_{3}\right)=\theta, \\ A^{2}\left(t_{1} \beta_{1}+t_{2} \beta_{2}+t_{3} \beta_{3}\right)=\theta,\end{array}\right.$ 由 $\left\{\begin{array}{l}A \beta_{1}=\theta, \\ A \beta_{2}=\beta_{1}, \\ A^{2} \beta_{3}=\beta_{1},\end{array}\right.$ 可得 $\left\{\begin{array}{l}t_{1} \beta_{1}+t_{2} \beta_{2}+t_{3} \beta_{3}=\theta, \\ t_{2} \beta_{1}+t_{3} A \beta_{3}=\theta, \\ t_{3} \beta_{1}=\theta .\end{array}\right.$ 解得 $t_{1}=t_{2}=t_{3}=0$, 故 $\beta_{1}, \beta_{2}, \beta_{3}$ 线性无关.

> 注：第二问的证明方法不一般。要善于利用题目条件。

![image-20220507172119628](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220507172119628.png)

### 2018-2019-1

3. 设矩阵 $A$ 的秩 $\mathrm{r}(A)=2$, 求 $x, y$ 的值, 其中 $A=\left(\begin{array}{ccccc}1 & 1 & 1 & 1 & 1 \\ 3 & 2 & 1 & -3 & x \\ 0 & 1 & 2 & 6 & 3 \\ 5 & 4 & 3 & -1 & y\end{array}\right)$.
   解: $A \rightarrow\left(\begin{array}{ccccc}1 & 1 & 1 & 1 & 1 \\ 0 & 1 & 2 & 6 & 3 \\ 0 & 0 & 0 & 0 & x \\ 0 & 0 & 0 & 0 & y-2\end{array}\right)$, 且 $\mathrm{r}(A)=2$, 故有 $x=0, y=2$.
   解法二：显然矩阵 $A$ 中有 2 阶子式不为零, 例如左上角的一个二阶子式: $D_{2}=\left|\begin{array}{ll}1 & 1 \\ 3 & 2\end{array}\right|=-1 \neq 0$. 为使 $\mathrm{r}(A)=2$, 必须使 $A$ 的所有三阶子式都等于零, 特别是应使下列含 $x$ 和 $y$ 的三阶子式 $\left|\begin{array}{ccc}1 & 1 & 1 \\ 1 & -3 & x \\ 2 & 6 & 3\end{array}\right|=-4 x=0,\left|\begin{array}{ccc}1 & 1 & 1 \\ 2 & 6 & 3 \\ 3 & -1 & y\end{array}\right|=4 y-8=0$, 即 $x=0, y=2$.

> **另解** A的秩为2,说明列向量组中最多只有两个无关向量, 取第1,2列向量,发现无关,说明最后一列的列向量可以由1,2线性表示,解一个二元一次方程组,有唯一解.
>
> **总结** 利用秩条件进行转化的可能方向
>
> 1. 暴力转化, 直接化成行梯形
> 2. 矩阵的秩=列秩=行秩,转化为列(行)向量的无关性
> 3. 秩的定义: 最大的非零子式(说明:$a. \exist r(A)阶的非零子式 \quad b. \forall r(A)+1阶子式都为0$)

七. (本题12分) 设 $n$ 阶矩阵 $A=\left(\begin{array}{cccc}a_{1} b_{1} & a_{1} b_{2} & \cdots & a_{1} b_{n} \\ a_{2} b_{1} & a_{2} b_{2} & \cdots & a_{2} b_{n} \\ \vdots & \vdots & & \vdots \\ a_{n} b_{1} & a_{n} b_{2} & \cdots & a_{n} b_{n}\end{array}\right)$, 已知矩阵的迹 $\operatorname{tr}(A)=a \neq 0$, 试问: 矩阵 $A$ 是否能相似于对角矩阵?

> 证：设 $\alpha=\left(a_{1}, a_{2}, \cdots, a_{n}\right)^{\mathrm{T}}, \beta=\left(b_{1}, b_{2}, \cdots, b_{n}\right)^{\mathrm{T}}$,
> 则 $A=\alpha \beta^{\mathrm{T}}, A^{2}=\left(\alpha \beta^{\mathrm{T}}\right)\left(\alpha \beta^{\mathrm{T}}\right)=\alpha\left(\beta^{\mathrm{T}} \alpha\right) \beta^{\mathrm{T}}=\left(\sum_{i=1}^{n} a_{i} b_{i}\right) \cdot A=a A$.
> 设 $\lambda$ 是 $A$ 的特征值, $\xi$ 是 $A$ 的属于特征值 $\lambda$ 的特征向量, 则 $A \xi=\lambda \xi, A^{2} \xi=a A \xi=a \lambda \xi$,
> 又 $A^{2} \xi=A \cdot A \xi=A \lambda \xi=\lambda A \xi=\lambda^{2} \xi$, 所以, $a \lambda \xi=\lambda^{2} \xi$, 即 $\left(\lambda^{2}-a \lambda\right) \xi=0$.
> 因为 $\xi \neq 0$, 故 $\lambda^{2}-a \lambda=0, \lambda=0$ 或 $\lambda=a$.
> ==又 $\sum_{i=1}^{n} \lambda_{i}=\operatorname{tr}(A)=a \neq 0$, 所以 $\lambda=a$ 是 $A$ 的单特征值, $\lambda_{2}=\lambda_{3}=\cdots=\lambda_{n}=0$ 是 $A$ 的 $n-1$ 重特征值.==
> 对于特征值 $\lambda_{2}=\lambda_{3}=\cdots=\lambda_{n}=0$, 齐次线性方程组 $(0 E-A) X=0$ 的系数矩阵的秩为: ==$\mathrm{r}(0 E-A)=\mathrm{r}(-A)=\mathrm{r}(A)=\mathrm{r}\left(\alpha \beta^{\mathrm{T}}\right) \leq \min \left\{r(\alpha), r\left(\beta^{\mathrm{T}}\right)\right\}=1 .$==
> 又 $\operatorname{tr}(A)=\sum_{i=1}^{n} a_{i} b_{i}=a \neq 0$, 故 $a_{i}, b_{i}(i=1,2, \cdots, n)$ 不全为零,
> ==故 $\mathrm{r}(A) \geq 1$, 因此 $\mathrm{r}(0 E-A)=1$.==
> 因此矩阵 $A$ 的属于 $n-1$ 重特征值 0 的线性无关的特征向量的个数为 $n-1$, 故 $A$ 有 $n$ 个线性无关 的特征向量, 所以 $A$ 相似于对角矩阵.
>
> > 这题对秩的考察以及对对角化的条件的考察还是很充分的.

### 2021-2022-1

![image-20220611203927630](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220611203927630.png)

![image-20220611204611161](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220611204611161.png)

> 非常综合的一道题.

![image-20220611205939858](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220611205939858.png)

> 比较难
>
> **另解**
> $$
> 利用到\lambda^m|\lambda E_n - AB| = \lambda^n|\lambda E_m - BA|\\
> $$
> ![image-20220611210145618](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220611210145618.png)
>
> 

![image-20220611213815903](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/05/image-20220611213815903.png)