---
title: 博客写作说明
author: xiaotian-feng
tags: others
---

<!-- excerpt start -->
本篇文章介绍如何写作文章并发布在实验室网站上。
<!-- excerpt end -->

## 创建文章

{% capture hint %}
本篇文章的所有内容，以及更详细、更高级的用法都可以在[官方文档](https://greene-lab.gitbook.io/lab-website-template-docs)上找到，如果需要可以仔细阅读。
{% endcapture %}

{%
  include alert.html
  type="tip"
  content=hint
%}

文章遵循Markdown语法，可以用Typora, Marktext甚至VS Code等编辑器书写。

要创建文章，直接在`_posts`目录下新建一个`.md`文件，命名格式遵循

```
YEAR-MONTH-DAY-title.md
```

<br/>

## 书写文章

### 基本内容

参见[官方说明文档](https://greene-lab.gitbook.io/lab-website-template-docs/basics/write-basic-content)。

插图请放在`asset/img`文件夹下，即

```
asset/img/yyyy-mm-dd-picname.png
```

### 数学

数学公式的显示由MathJax引擎驱动，遵循 $\LaTeX$ 语法。书写行内公式可以使用`$...$`或`\(...\)`，例如${}^{171}\mathrm{Yb}^+$与`${}^{171}\mathrm{Yb}^+$`。

书写行间公式可以使用`$$...$$`，例如

```latex
$$
E = mc^2
$$
```

给出
$$
E=mc^2
$$

### Capture

Capture相当于创建一个变量，其它页面元素的`content`的属性可以调用这个变量。
