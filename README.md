



# 前言

一个基本的网站包含多个网页，一个网页由 HTML, CSS 和 JavaScript  组成，其中：

- HTML：结构层，决定网页的结构和内容（ *是什么❓* ）
- CSS：渲染层，设置网页的样式（ *长啥样❓* ）
- Javascript：行为层，控制网页的行为（ *做什么❓* ）

**开发工具：**

工欲善其事必先利其器，推荐使用 VSCode IDE，[点击前往官网下载 >>](https://code.visualstudio.com/download)

# HTML是什么？

HTML（**H**yper**T**ext **M**arkup **L**anguage，超文本标记语言） 是一种描述语言，用来定义网页结构。

# 发展史

1990 年，由于对 [Web](https://developer.mozilla.org/zh-CN/docs/Glossary/World_Wide_Web) 未来发展的远见，Tim Berners-Lee 提出了[超文本](https://developer.mozilla.org/zh-CN/docs/Glossary/Hypertext)的概念，并在第二年在 [SGML](https://developer.mozilla.org/zh-CN/docs/Glossary/SGML) 的基础上将其正式定义为一个标记语言。[IETF](https://developer.mozilla.org/zh-CN/docs/Glossary/IETF) 于 1993 年正式开始制定 HTML 规范，并在经历了几个版本的草案后于 1995 年发布了 HTML 2.0 版本。1994 年，Berners-Lee 为了 Web 发展而成立了 [W3C](https://developer.mozilla.org/zh-CN/docs/Glossary/W3C)。1996 年，W3C 接管了 HTML 的标准化工作，并在 1 年后发布了 HTML 3.2 推荐标准。1999 年，HTML 4.0 发布，并在 2000 年成为 [ISO](https://developer.mozilla.org/zh-CN/docs/Glossary/ISO) 标准。

自那以后，W3C 几乎放弃了 HTML 而转向 [XHTML](https://developer.mozilla.org/zh-CN/docs/Glossary/XHTML)，并于 2004 年成立了另一个独立的小组 [WHATWG](https://developer.mozilla.org/zh-CN/docs/Glossary/WHATWG)。幸运的是，WHATWG 后来又转回来参与了 HTML 标准的制定，这两个组织在 2008 年发布了 [HTML5](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML5) 的第一份草案，并在 2014 年发布了官方标准。HTML5 这个术语只是一个指代 [HTML 动态标准](https://html.spec.whatwg.org/)中一组现代 Web 技术的流行用语。

> 提示：摘自[MDN >>](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML)

# 概念和语法

HTML 文档是包含多个 HTML 元素 的文本文档。每个元素都用一对开始和结束标签包裹，每个标签以尖括号（`<>`）开始和结束，如：

```html
<div>Hello</div>
```

其中 `<div>` 为开始标签，`</div>` 为结束标签， `Hello` 为文本内容。当然，也有一部分标签中不需要包含文本，这些标签称为 **空标签**，如 `<img />`。

你可以使用[属性](https://developer.mozilla.org/zh-CN/docs/Glossary/Attribute)来扩展 HTML 标签。属性用来提供一些附加信息，这些信息可能会影响浏览器对元素的解析：

![](./IMGS/anatomy-of-an-html-element.png)

HTML 文件通常会以 `.htm` 或 `.html` 为扩展名。用户可以从 [Web 服务器](https://developer.mozilla.org/zh-CN/docs/Glossary/Server)中下载，并使用任一 [Web 浏览器](https://developer.mozilla.org/zh-CN/docs/Glossary/Browser)来解析和显示这些文件。

# 元素分类

HTML 元素类型主要分为以下三种：

1. 块级元素（`block`）：

   特性：独占一行，具有完整的盒子模型，可自由设置宽度、高度、内边距、外边距等样式属性。例如 `<div>`、`<p>`、`<h1>` 到 `<h6>` 等元素都属于块级元素。即使你为其设置了宽度和高度，它仍然会独占一行，其宽度默认会撑满父容器的宽度（除非你设置了宽度小于父容器宽度），且可以在其前后添加换行符，使元素之间形成明显的垂直分隔。

2. 行内元素（`inline`）：

   特性：不会独占一行，多个行内元素会排列在同一行上，除非一行排不下才会换行。不具有完整的盒子模型，宽度和高度由元素内部的内容决定，无法直接设置宽度和高度，只能设置水平方向的内边距和外边距，垂直方向的内边距和外边距虽然可以设置，但不会影响元素在垂直方向上占据的空间，即不会推开其他元素。例如 `<span>`、`<a>`、`<em>`、`<strong>` 等元素都是行内元素。

3. 行内块元素（`inline-block`）：

   特性：不独占一行，多个行内块元素可以排列在同一行上，类似于行内元素。但是它具有部分盒子模型的特性，允许设置宽度和高度，同时也可以设置内边距、外边距，对周围元素的布局影响更像块级元素。在某些场景下，它结合了行内元素和块级元素的优点，既能在一行内排列多个元素，又能灵活控制元素的大小。例如 `<input>`、`<img>` 等元素通常表现为行内块元素。

使用不同类型元素的一些常见场景：

1. 当你需要对页面进行大的布局划分，比如划分不同的区域，创建页眉、页脚、侧边栏、主要内容区等，通常使用块级元素，因为它们可以方便地控制布局和元素之间的垂直间距。
2. 当你需要对某段文本进行简单的样式设置，如改变部分文字的颜色、加粗或添加链接，使用行内元素比较合适，它们不会破坏文本的自然排列顺序。
3. 当你需要在一行内排列多个元素，同时又想对元素的大小进行精确控制，例如将多个图标、按钮或小型表单元素排列在一行，并且希望它们的大小一致，行内块元素是一个很好的选择。

**如何判断一个元素的类型？**

在谷歌浏览器中鼠标右键检查元素，然后通过元素选取器选取要查看元素类型的元素，最后在computed中搜索display属性观察其值即可。如下所示：

![](./IMGS/check_display.png)

# 标签嵌套

HTML 标签嵌套是将一个 HTML 标签放置在另一个 HTML 标签内部的做法。例如：

```html
<div>
    <p>This is a paragraph inside a div.</p>
</div>
```

在这个例子中，`<p>` 标签嵌套在 `<div>` 标签内。

**嵌套规则**：

1. 必须保证标签的正确闭合：如果有开始标签 `<tag>`，就必须有对应的结束标签 `</tag>`。例如 `<div></div>`。
2. 正确的嵌套顺序：通常情况下，块级元素可以包含行内元素和其他块级元素，但行内元素一般不能包含块级元素。例如：
   - 正确：`<div><span></span></div>`
   - 错误：`<span><div></div></span>`
3. 避免交叉嵌套：标签的嵌套应该是完整有序的，不能出现 `<div><p></div></p>` 这样的交叉嵌套情况，正确的应该是 `<div><p></p></div>`。

这些规则有助于确保 HTML 文档结构清晰，保证页面在不同浏览器中正确显示和正常运行。遵循这些规则可以避免布局混乱和潜在的显示错误。

# HTML 基本文档结构

HTML基本文档结构是指组成一个基本的HTML页面所必须的元素标签。具体编写格式如下：

```html
<!-- 指定文档类型,确保浏览器以正确的方式解析文档 -->
<!DOCTYPE html>
<!-- 根元素 -->
<html lang="zh-CN">
  <!-- 头部标签，包含了文档的元数据，这些信息不会直接显示在页面上，但对页面的显示和行为起着重要作用 -->
  <head>
    <!-- 指定字符编码 -->
    <meta charset="UTF-8" />
    <!-- IE浏览器兼容性处理 -->
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <!-- 用于设置视口的属性，对于响应式设计很重要 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- 定义网页的标题，会显示在浏览器的标题栏或标签页上 -->
    <title>Document</title>
  </head>
  <!-- 包含了页面的主要内容，用户在浏览器中看到的所有内容都在这个元素内 -->
  <body>
    网页内容
  </body>
</html>
```

HTML 文档就是通过这样的结构，将各种元素组织在一起，以呈现出完整的网页。在 `<body>` 元素中，可以使用更多的 HTML 元素，如 `<div>`、`<span>`、`<a>`、`<img>` 等，来创建丰富的页面内容和布局。根据需要，可以添加不同的元素和属性，为页面添加样式、链接、图像、表单等。通过合理使用 HTML 元素和遵循正确的嵌套规则，可以构建出功能强大、结构清晰的网页。



















