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

<!-- your katex macros goes here -->
$$
\global\letħ=\hbar
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

-----------------------------------------

## 简单的表格

表格的使用和正常的`markdown`中基本一样
| Year | Title | Actor |
| ----------- | ----------- | ----------- |
| 1970 | Jonathan | Paul Albert Krumm |
| 1995 | Monster Mash | Anthony Crivello|
| 2004 | Blade: Trinity | Dominic Purcell|
| 2008 | Supernatural | Todd Stashwick|
| 2020 | Dracula | Claes Bang|
---

## Block quote

> There are darknesses in life and there are lights, and you are one of the lights, the light of all lights.
>
> -- Bram Stoker, Dracula

## Math block

marp 使用它自带的Katex引擎，因此诸如` ħ → \hbar `这样的宏要在文件头定义。

$$
    iħ \frac{d}{dt} |ψ⟩ = \hat{H} |ψ⟩
$$

----------------------------------------
<style scoped>{
    columns:2;
    column-gap:50px
}</style>

## 分栏

把一个页面分成多栏目的方法，例如这里将一个页面分成了两个栏目，这样能够塞下更多内容。

```html
<!-- scoped: 限制只对本页面有效 -->
<style scoped>{ 
    columns:2;
    column-gap:50px;
}</style>
```

### 这个是另一栏

需要说明的是，这里的**style scoped**是一种简单的hack，并不能显式地控制页面两侧的内容，因此你会发现这一页的第二个标题被挤占到了右边啦

![w:550 opacity:1.0](.assets/80942286_p0.png)


------------------------------------

<!-- <p hidden> a </p> -->

<div class="twocolumnpage">

<div>

### 另一种分栏（左）

- 项目1
- 项目2

这是一段文字这是一段文字这是一段文字这是一段文字。。。

1. 有序表表表表表表表表
1. 有序表表表表表表表表
1. 有序表
1. 有序表
1. 有序表

</div>

<div>

### 另一种分栏（右）

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

</div>

-------------------------------------------------

## 背景

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