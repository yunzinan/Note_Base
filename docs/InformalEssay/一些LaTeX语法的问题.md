# 都是语法惹的祸---写博客时的一些坑

??? tip "motivation"

    之前一直使用Typora进行写作, 可能是因为Typora兼容性太好, 以及具备一些拓展语法的缘故, 一些不合规范的写法也能渲染出预期效果, 但是一旦换到其他平台(vscode, blog)上就立马出现问题, 因而不得不重新纠正, 于是索性做一次整理, 把一些常见的容易出错的写法列出来.

---

## 一些可能导致渲染失败的写法

### 1. 个别软件对markdown的拓展语法

!!! warning "文字高亮显示"

    文字高亮属于拓展语法, 因此并不是在所有的情况下都适配和兼容, 例如:

    - `==abc==` 是Typora的高亮语法
    
    - ![](https://cyent.github.io/markdown-with-mkdocs-material/img/hl_critic.png) mkdocs(主要是pymdownx模块)的高亮语法(mkdocs也支持`==abc==`, 但是要求必须前后都有空格)

    然而, 这样的写法在vscode等未做适配的环境下都无法正常显示.

!!! success "替代方案"

    为了获得更好的兼容性, 我决定直接使用HTML语法来进行文字高亮, 这样可以使得在绝大多数的网页中显示正常.(不过vscode还是不支持)

    ```html
    <span style = "background: yellow;">abc</span>
    ```
    效果: <span style = "background: yellow;">abc</span>

    或者, 对于文字的强调, 多使用 **abc**(文字加粗) /`abc`(代码块)来表示.

### 2. LaTeX数学公式

> 由于之前写的时候不注意(不知道), 当我把写好的文章放上去时, 结果显示成这个样子:
> 
> ![](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/09/20220910112856.png)
> 或者这样:
>
> ![](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/09/20220910113014.png)

> 总之一把辛酸泪啊...所以说一定要看官方说明文档

!!! note "可能会导致无法渲染的语法"

    1.$\wedge, \vee$

    !!! fail

        `$\and$`

        `$\or$`

    !!! success 

        `$\wedge$`

        `$\vee$`

    2.$\exists$

    !!! fail 

        `$\exist$`

    !!! success

        `$\exists$`

    3.$\infty$

    !!! fail 

        `$\infin$`

    !!! success 

        `$\infty$`

    4.加粗, 效果: $\mathbf{abc}$

    !!! fail

        `$\bold{abc}$`

    !!! success 

        `$\mathbf{abc}$`

    5.集合符号

    !!! fail

        - $\R$: `$\R$`

        - $\N^*$: `$\N^*$`

        - $\Z^+$: `$\Z^+$`


    !!! success

        - $\mathbf{R}$: `$\mathbf{R}$`

        - $\mathbf{N}^*$: `$\mathbf{N}^*$`

        - $\mathbf{Z}^+$: `$\mathbf{Z}^+$`



## 一些不美观的写法[^1]

!!! note "行内公示显示"

    !!! warning

        - $\int$: `$\int$`

        - $\frac{1}{2}$: `$\frac{1}{2}$`

        - $\sum$: `$\sum$`

        - $\prod$: `$\prod$`

    !!! success

        - $\displaystyle\int$: `$\displaystyle\int$`

        - $\dfrac{1}{2}$: `$\dfrac{1}{2}$`

        - $\displaystyle\sum$: `$\displaystyle\sum$`

        - $\displaystyle\prod$: `$\displaystyle\prod$`

        > 尽管加上`$\displaystyle$`可以使一些符号看起来更好看, 但是更加推荐把这些公式写到行间公式里去.

!!! note "不规范的符号"

    !!! warning

        - $\emptyset$: `$\emptyset$`

        - $a \% b$: `$a \% b$` or $a\ mod\ b$: `$a\ mod\ b$`

    !!! success

        - $\varnothing$: `$\varnothing$`

        - $a \bmod b$: `$a \bmod b$`

## 附录: 一些可能会用到, 但总是要查的符号

- $\leftrightharpoons$: `$\leftrightharpoons$`

[^1]: 参考[OI-Wiki|格式手册](https://oi-wiki.org/intro/format/)


