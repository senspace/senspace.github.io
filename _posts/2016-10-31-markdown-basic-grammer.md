---
layout: post
title: MarkDown语法说明
categories: MarkDown
description: 简要介绍基础语法等等。
keywords: MarkDown
---

## 概述

### 宗旨
Markdown 的目标是实现「易读易写」。

可读性，无论如何，都是最重要的。一份使用 Markdown 格式撰写的文件应该可以直接以纯文本发布，并且看起来不会像是由许多标签或是格式指令所构成。Markdown语法受到一些既有 text-to-HTML 格式的影响，包括 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，而最大灵感来源其实是纯文本电子邮件的格式。

总之， Markdown的语法全由一些符号所组成，这些符号经过精挑细选，其作用一目了然。比如：在文字两旁加上星号，看起来就像*强调*。Markdown 的列表看起来，嗯，就是列表。Markdown 的区块引用看起来就真的像是引用一段文字，就像你曾在电子邮件中见过的那样。

### 兼容 HTML

### 特殊字符自动转换
Markdown 让你可以自然地书写字符，需要转换的由它来处理好了。如果你使用的 & 字符是 HTML 字符实体的一部分，它会保留原状，否则它会被转换成 &amp;。

所以你如果要在文档中插入一个版权符号 ©，你可以这样写：&copy;
Markdown 会保留它不动。而若你写：AT&T
Markdown 就会将它转为：AT&amp;T
类似的状况也会发生在 < 符号上，因为 Markdown 允许 兼容 HTML ，如果你是把 < 符号作为 HTML 标签的定界符使用，那 Markdown 也不会对它做任何转换，但是如果你写：
4 < 5
Markdown 将会把它转换为：4 &lt; 5
不过需要注意的是，code 范围内，不论是行内还是区块， < 和 & 两个符号都一定会被转换成 HTML 实体，这项特性让你可以很容易地用 Markdown 写 HTML code （和 HTML 相对而言， HTML 语法中，你要把所有的 < 和 & 都转换为 HTML 实体，才能在 HTML 文件里面写出 HTML code。）

## 区块元素

### 段落和换行

一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（空行的定义是显示上看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行）。普通段落不该用空格或制表符来缩进。

「由一个或多个连续的文本行组成」这句话其实暗示了 Markdown 允许段落内的强迫换行（插入换行符），这个特性和其他大部分的 text-to-HTML 格式不一样（包括 Movable Type 的「Convert Line Breaks」选项），其它的格式会把每个换行符都转成 <br /> 标签。

如果你确实想要依赖 Markdown 来插入 <br /> 标签的话，在插入处先按入两个以上的空格然后回车。

的确，需要多费点事（多加空格）来产生 <br /> ，但是简单地「每个换行都转换为 <br />」的方法在 Markdown 中并不适合， Markdown 中 email 式的 区块引用 和多段落的 列表 在使用换行来排版的时候，不但更好用，还更方便阅读。

### 标题

Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。(本人一般采用第二种)

1.  类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），例如：

        This is an H1
        =============

        This is an H2
        -------------

    任何数量的 = 和 - 都可以有效果。

2.  类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

        # 这是 H1

        ## 这是 H2

        ###### 这是 H6

### 区块引用

Markdown 标记区块引用是使用类似 email 中用 > 的引用方式。如果你还熟悉在 email 信件中的引言部分，你就知道怎么在 Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上 > ：

        > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
        > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
        > Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
        > 
        > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
        > id sem consectetuer libero luctus adipiscing.

Markdown 也允许你偷懒只在整个段落的第一行最前面加上 > ：

        > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
        consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
        Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

        > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
        id sem consectetuer libero luctus adipiscing.

区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > ：

        > This is the first level of quoting.
        >
        > > This is nested blockquote.
        >
        > Back to the first level.

引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：

        > ## 这是一个标题。
        > 
        > 1.    这是第一行列表项。
        > 2.    这是第二行列表项。
        > 
        > 给出一些例子代码：
        >       
        >       return shell_exec("echo $input | $markdown_script");

任何像样的文本编辑器都能轻松地建立 email 型的引用。例如在 BBEdit 中，你可以选取文字后然后从选单中选择增加引用阶层。

### 列表

Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：

*   Red
*   Green
*   Blue
等同于：

+   Red
+   Green
+   Blue
也等同于：

-   Red
-   Green
-   Blue
有序列表则使用数字接着一个英文句点：

1.  Bird
2.  McHale
3.  Parish
很重要的一点是，你在列表标记上使用的数字并不会影响输出的 HTML 结果，上面的列表所产生的 HTML 标记为：

<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>
如果你的列表标记写成：

1.  Bird
1.  McHale
1.  Parish
或甚至是：

3. Bird
1. McHale
8. Parish
你都会得到完全相同的 HTML 输出。重点在于，你可以让 Markdown 文件的列表数字和输出的结果相同，或是你懒一点，你可以完全不用在意数字的正确性。

如果你使用懒惰的写法，建议第一个项目最好还是从 1. 开始，因为 Markdown 未来可能会支持有序列表的 start 属性。



### 代码区块

### 分隔线

## 区段元素

### 链接

### 强调

### 代码

### 图片

## 其它

### 反斜杠

### 自动链接

## 参考

## Markdown 免费编辑器

