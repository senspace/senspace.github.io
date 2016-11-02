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
### 标题
### 区块引用
### 列表
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

