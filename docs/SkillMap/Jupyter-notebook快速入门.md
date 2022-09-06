---
title: Jupyter notebook快速入门
top: false
cover: false
toc: true
tags: Jupyter-notebook
categories: 技术
abbrlink: c3bfd1c6
date: 2022-06-29 00:39:30
author:
img:
coverImg:
password:
summary:
---

# Jupyter notebook快速上手

<p style = "text-align: center;"><span style = "font-family: fangsong;">作者</span>: yunzinan</p>

> - notebook参见[Jupyter notebook快速上手.ipynb](https://nbviewer.org/github/yunzinan/quick_start_on_jupyter_notebook/blob/main/Jupyter notebook快速上手.ipynb#优点)
> - slide格式参见[Jupyter notebook快速上手 slides (rth7.com)](https://sboys.rth7.com/Jupyter notebook快速上手.slides.html#/)

## 为什么要用Jupyter notebook?

### 优点

1. 编译器与文本文本编辑器二合一: 
   - 支持多种语言(Python R)逐行运行,及时展示结果
   - 支持Markdown文本编辑,具备**强大(因为支持HTML语言)便捷**的文本编辑能力

2. 支持多种格式的导出: .md/.latex/.html

3. 能够快速转换为简洁美观的slides

## 打开方式

- 通过Anaconda navigator打开: 比较简单 但是只能打开**默认**的文件夹
- <span style = "color: red">通过cmd/anaconda prompt操作打开</span>: (preferred)
  - Ctrl+R打开cmd
  - 找到需要打开的目录 复制
  - cd PATH切换到当前目录下
  - 输入jupyter notebook即可打开
  - <span style = "background: yellow;">注: 如果没有直接打开的话,也可以复制cmd中出现的三行地址到浏览器中</span>

## 快捷键


当前处于<span style = "color: blue;">命令模式</span>时:

- 按`Enter`进入输入模式
- 按`Ctrl + Enter`运行本单元
- 按`Y`/`M`/`R`在代码/Markdown/raw模式中切换
- 按`A`向上插入一个单元,按`B`向下插入一个单元
- 按**两次**`D`删除单元,按一次`Z`撤销删除
- 按`Shift + Up`/`Shift + Down`向上/向下多选
- 按`Shift + M`合并选中的单元

当前处于<span style = "color: green;">输入模式</span>时:

- 按`Esc`切换回命令模式
- 按`Crtl + Enter`运行本单元并切换回命令模式
- 按`Alt + Enter`运行本单元并向下新建一行
- 按`Shift + Enter`运行本单元并**选中**下一个单元

在Markdown输入模式下:

   - 遵照markdown语法
   - 习惯使用typora的用户可能需要注意文本如果需要换行的话,要多敲一行空白出来
   - 按`Ctrl + /`快速注释
   - 支持HTML语法,但不支持对`==文字==`的方式高亮,因此可以输入`<span style = "color: red; background: yellow;">文字</span>`的方法高亮
   - 支持`**文字**`加粗,效果如同<b>文字</b>
   - 支持`__文字__`/`*文字*`斜体,效果如同_文字_

## 插入图片的方法

### 插入本地图片

```html
<img src="./img/Left_brain_right_brain.jpg" alt = "Left_brain_right_brain" width = "400px" height = "300px">
```

<img src="C:\Users\Jack_shen\Downloads\img\Left_brain_right_brain.jpg" alt = "Left_brain_right_brain" width = "400px" height = "300px">

> **注**: 这种方法只能在本地有效.

### 插入网络图片

推荐这个方法,结合云图床使用

```html
<img src="https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/06/Left_brain_right_brain.jpg" style="zoom:25%;" />
```

<img src="https://yunzinan-pic-bed.oss-cn-nanjing.aliyuncs.com/2022/06/Left_brain_right_brain.jpg" style="zoom:25%;" />

### 更便捷的方法

![image-2.png](C:\Blog\source\_posts\attachment:image-2.png)

## 注意事项

### 导出为LaTeX

注意默认**只显示英文**,如果需要显示中文,需要手动添加

```latex
\usepackage[UTF8]{ctex}
```

## 可能遇到的问题

### cmd中输入jupyter notebook报错?

应该是环境变量没有正确设置,需要检查环境变量

先找到Anaconda所在的目录记为`PATH`

需要添加以下三个环境变量

- PATH

- PATH\Scripts

- PATH\Library\bin

之后就可以直接cmd运行jupyter notebook了

为了方便,我们也可以直接写一个bat文件

```bat
cd /d (所在文件位置)

jupyter notebook
```

### 导出为PDF报错?

解决方案:

1. 先导出为.tex文件,然后用vscode/tex studio导出为PDF
2. 直接`Ctrl + P`打印
   感觉两个方案都不好 后面再想办法...

## 参考链接

- [15个应该掌握的Jupyter Notebook使用技巧(小结)](http://www.kaotop.com/it/17071.html)
- [来一碗Python工具 - 2. Jupyter Notebook ("Python代码秒变PPT")](https://www.bilibili.com/video/BV1Yv411y72H?spm_id_from=333.337.search-card.all.click&vd_source=4d1339aa01c80d5f92c8bfa68d7b7c41)
- [jupyter notebook常用快捷键](https://www.cnblogs.com/sui776265233/p/9759303.html)

## 高级玩法: 用Jupyter notebook制作slides

以下参考:

- [震惊！90%的人都不知道Jupyter notebook 竟然还能做PPT](https://blog.csdn.net/cainiao_python/article/details/115534960?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_title~default-0-115534960-blog-96261708.pc_relevant_paycolumn_v3&spm=1001.2101.3001.4242.1&utm_relevant_index=3)

只需要几个步骤,就可以轻松导出简洁美观的PPT:

      1. 安装RISE库(安装完成刷新notebook网页,会出现`预览`按钮)
      2. 在`View -> Cell Toolbar`中选择`幻灯片`,然后对每一个单元格(Cell)右上角设置`幻灯片类型`
      3. 点击预览即可查看效果
      4. 在`File -> Download as`中选择`Reveal.js slides`
