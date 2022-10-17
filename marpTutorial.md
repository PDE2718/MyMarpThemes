---
title: Dracula
marp: true
version: 1.0.0
theme: dracula
footer: 使用 VSCode + **Marp**  制作幻灯片
header: Theme-Dracula
paginate: true
math: katex
size: 16:10
---
<!-- 在前面最好加入katex的宏命令 -->
<!-- your katex macros goes here -->
$$
\global\let ħ=\hbar
$$

<style scoped>h1 {
    padding-top: 1em;
    font-size: 1.8em
}</style>

<!-- _paginate: false -->

# VSCode💜 [Marp](https://marp.app)

VSCode + Marp + Markdown
制作简单幻灯片

<br></br>

PDE2718
Date:`2022-08-26 00:48:21`

![bg right](.assets/77995894_p0.png)

<!-- 每一页可以添加额外的注释，在html幻灯片中会呈现 -->

-----------------------------------------

> 目录

目前目录功能还是一个缺点，即可以自动生成，但是样式比较丑，而且不支持跳转。

<twocolumn-block-c>

  - [基本使用](#markdown-mermaid)
    - [Block quote](#markdown-mermaid)
    - [Math block](#markdown-mermaid)
  - [`<HTML>`自定义样式](#markdown-mermaid)
  - [分栏](#markdown-mermaid)
  - [Page Title](#markdown-mermaid)
    - [内容连续的分栏](#markdown-mermaid)
    - [严格分栏（一）](#markdown-mermaid)
    - [严格分栏（二）](#markdown-mermaid)
  - [Auto-scaling](#markdown-mermaid)
  - [多彩的标记](#markdown-mermaid)
  - [其它使用](#markdown-mermaid)
  - [背景图片](#markdown-mermaid)
  - [代码段](#markdown-mermaid)

</twocolumn-block-c>

---------------------------------------

## 基本使用

Marp使用和正常的`markdown`中基本一样。例如这是的一些简单语法和一个表格

| 功能 | 效果 | 实现 |
| :-----------: | :-----------: | :-----------: |
| 文本加粗 | **加粗文本** | `**加粗文本**` |
| 文本斜体 | **_斜体文本_** | `_加粗文本_` |
| 代码字体 | `Code::Inline` |``` `Code::Inline` ```|
| 删除线 | ~~写错了哦~~ |``` ~~写错了哦~~ ```|

<center><mark-purple>Table 1.</mark-purple> markdown的几种常见语法 </center>

---

### Block quote

<div>

> 你可以引用别人的话，This is a Block Quote
> <div style="text-align:right"> By Me </div>

</div>

### Math block

marp 使用它自带的katex引擎，因此诸如` ħ → \hbar `这样的宏要在文件头定义`$\global\let ħ=\hbar$ `。请参考 [katex文档相关页面](https://katex.org/docs/supported.html)

$$\small{
    iħ \frac{d}{dt} |ψ⟩ = \hat{H} |ψ⟩
}$$

--------------------------------------

## `<HTML>`自定义样式

你已经注意到啦，在Marp里面同样支持`HTML`语法自定义样式！

<div style=""></div>

<div style="text-align:center">

例如可以居中和<mark>高亮标记</mark>一段文字

</div>

可以通过HTML自定义更多的样式，你可以大开脑洞。

----------------------------------------

<twocolumn-page-c>

## 分栏

把一个页面分成两个栏目，往往能塞下更多内容。对于连续的内容分栏可以通过下述的代码实现：

```markdown
<twocolumn-page-c>

## Page Title

some content...some content

</twocolumn-page-c>
```

### 内容连续的分栏

需要说明的是，这种方法并不能显式地控制页面两侧的内容，内容到了一定的长度就会自动换行。因此我们也无法使得第二个标题一定在右侧

![w:550 opacity:1.0](.assets/80942286_p0.png) <span style="text-align:center"> <mark-cyan>Figure 1.</mark-cyan> 猫猫 </div>

</twocolumn-page-c>

------------------------------------

<twocolumn-page>

<div>

### 严格分栏（一）

- 项目1
- 项目2

这是一段文字这是一段文字这是一段文字这是一段文字。。。

1. 有序表表表表表表表表
1. 有序表表表表表表表
1. 有序表表表表表表
1. 有序表表表表表
1. 有序表表表表
1. 有序表表表
1. 有序表表
1. 有序表

</div>

<div>

### 严格分栏（二）

css文件中加入了分段的样式：

```css
.twocolumnpage{
    position: relative;
    top: -25px;
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1.0fr));
    column-gap: 50px;
}
```
使用`<div class="twocolumns">`创建一个双栏的环境。可以看到，现在内容即使超出页面也不会换栏

你可以类比实现页面中任意位置的分栏环境

</div>

</twocolumn-page>

--------------

## Auto-scaling

<twocolumn-block>

<div>

对于比较短的公式，缩放比例较大：

$$
    I = \begin{bmatrix}
         1 & 0 \\
         0 & 1 \\
    \end{bmatrix}
$$

而对于长的公式，这个缩放比例会自动减小。

$$
I =
\begin{bmatrix}
    0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
    0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
    0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
    0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0\\
\end{bmatrix}
$$

</div>

<div>

</div>

</twocolumn-block>


-----------
## 多彩的标记

霓虹灯效果：<mark-red>mark-red</mark-red> <mark-purple>mark-purple</mark-purple> <mark-cyan>mark-cyan</mark-cyan>

荧光笔效果：绿色<hlter-green>hlter-green</hlter-green>荧光笔


-------------------------------------------------

## 其它使用

----------------------------------------------

## 背景图片

![bg opacity:20% saturate:2](.assets/83760346_p0.png)

<div style="text-align:right">

`Marp`的背景图片功能不错且易用

功能比beamer来说非常有限

渲染迅速

</div>

----------------------------------------------

## 代码段

```python
class Bat:
    def __init__(name:str, age:int):
        self.__name = name
        self.__age = age
    @property
    def name(self):
        return self.__name
    @property
    def age(self):
        return self.__age
    @property
    def speed(self):
        return 10 - self.age
```

![bg left:45%](.assets/80840480_p0.png)
<!-- ![bg vertical](.assets\83760346_p0.png) -->
<!-- ![contain](.assets\83760346_p0.png) -->

