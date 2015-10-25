---
layout: post
title: Markdown 基本语法
author: geekepub
comments: true
category: 技术
tags:
- Markdown
---

### Markdown 的设计哲学

> Markdown 的目标是实现「易读易写」。
>
> 可读性，无论如何，都是最重要的。一份使用 Markdown 格式撰写的文件应该可以直接以纯文本发布，并且看起来不会像是由许多标签或是格式指令所构成。Markdown 语法受到一些既有 text-to-HTML 格式的影响，包括 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，而最大灵感来源其实是纯文本电子邮件的格式。
>
> Markdown 语法的目标是：成为一种适用于网络的**书写**语言。

<!-- more -->

### 段落

一个段落有一行或多行连续的文本构成。

两个段落之间用一行或多行连续的空白行分隔。

Markdown 语法：

```
这是第一段，
这还是第一段。

这才是第二段。

```

效果如下：

这是第一段，
这还是第一段。

这才是第二段。


### 标题

使用一个或多个`#`创建标题。

Markdown 语法：

```
# 一级标题 H1
## 二级标题 H2
### 三级标题 H3
#### 四级标题 H4
##### 五级标题 H5
###### 六级标题 H6
```

效果如下：

# 一级标题 H1
## 二级标题 H2
### 三级标题 H3
#### 四级标题 H4
##### 五级标题 H5
###### 六级标题 H6

### 区块引用

使用`>`来标记区块引用。

Markdown 语法：

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```

效果如下：

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.


### 文本式样

使用`*`或`_`对文本进行。**强调**和*斜体*。

Markdown 语法：

```
*This text will be italic*
**This text will be bold**
```

效果如下：

*This text will be italic*
**This text will be bold**

### 列表

#### 无序列表

使用`*`或`-`创建无序列表。

Markdown 语法：

```
* Item
* Item
* Item

- Item
- Item
- Item
```

效果如下：

* Item
* Item
* Item

- Item
- Item
- Item

#### 有序列表

在项目名称前添加数字创建有序列表。

Markdown 语法：

```
1. Item 1
2. Item 2
3. Item 3

1. Item 1
1. Item 2
1. Item 3
```

效果如下：

1. Item 1
2. Item 2
3. Item 3

1. Item 1
1. Item 2
1. Item 3

#### 嵌套列表

Markdown 语法：

```
1. Item 1
  1. SubItem 1
  2. SubItem 2
2. Item 2
  * SubItem A
    * SubSubItem a
    * SubSubItem b
3. Item 3
```

1. Item 1
  1. SubItem 1
  2. SubItem 2
2. Item 2
  * SubItem A
    * SubSubItem a
    * SubSubItem b
3. Item 3

### 图片

Markdown 语法：

```
![GitHub set up](http://zh.mweb.im/asset/img/set-up-git.gif)
```
效果如下：

![GitHub set up](http://zh.mweb.im/asset/img/set-up-git.gif)

### 链接

Markdown 语法：

```
email <example@example.com>
[GitHub](http://github.com)
自动生成链接  <http://www.github.com/>
```

效果如下：

email <example@example.com>
[GitHub](http://github.com)
自动生成链接  <http://www.github.com/>

### 行内代码

使用 ` 进行代码标注。

Markdown 语法：

```
像这样即可：`<addr>` `code`
```

效果如下：

像这样即可：`<addr>` `code`

### 多行或者一段代码

效果如下：

```js
function fancyAlert(arg) {
    if(arg) {
		$.facebox({div:'#foo'})
    }

}
```

### 表格

Markdown 语法：

```
| Tables        | Are           | Cool  |
| :------------ |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```

效果如下：

| Tables        | Are           | Cool  |
| :------------ |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

### 分隔线

使用三个或以上的`*`、`-`或`_`来生成分隔线。

Markdown 语法：

```
---
```

效果如下：

---

参考：[Daring Fireball: Markdown Syntax Documentation](http://daringfireball.net/projects/markdown/syntax)
