# 每日一题题单
> 说明: 简单做一些记录, 只记一些有价值的点和易错的地方.

[TOC]

---

## 数据结构[1-1] [线性表](https://www.luogu.com.cn/training/113#problems)

### [0x02] 寄包柜

??? warning "100, 但新增的一个点TLE"

    ![0x02code](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/09/20220909174040.png)

??? success "AC"

    ![0x02code2](https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/09/20220909174624.png)

> 自然想到链表, 但是不止为何会有一个Hack的点T了. 另外没有想到用Hash, 如果不需要自己实现的话还是更好的选择.

### [0x03] 后缀表达式

> 注意实现栈的时候, 栈顶指针总是指向下一个带压栈的地址, 因此取出栈顶元素的时候, 需要取栈顶指针下面一个元素.


