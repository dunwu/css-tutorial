# CSS3 快速入门

CSS3 是最新的 CSS 标准。

CSS3 完全向后兼容，因此您不必改变现有的设计。浏览器通常支持 CSS2。

## 简介

CSS3 被划分为模块。

其中最重要的 CSS3 模块包括：

- 选择器
- 框模型
- 背景和边框
- 文本效果
- 2D/3D 转换
- 动画
- 多列布局
- 用户界面

## 框模型

通过 CSS3，您能够创建圆角边框，向矩形添加阴影，使用图片来绘制边框 - 并且不需使用设计软件，比如 PhotoShop。

在本章中，您将学到以下边框属性：

- border-radius
- box-shadow
- border-image


### 圆角边框

在 CSS2 中添加圆角矩形需要技巧。我们必须为每个圆角使用不同的图片。

在 CSS3 中，创建圆角是非常容易的。

在 CSS3 中，`border-radius` 属性用于创建圆角：

这个矩形有圆角哦！

**实例**

向 div 元素添加圆角：

```css
div {
  border:2px solid;
  border-radius:25px;
  -moz-border-radius:25px; /* Old Firefox */
}
```

### 边框阴影

在 CSS3 中，`box-shadow` 用于向方框添加阴影：

**实例**

向 div 元素添加方框阴影：

```css
div {
  box-shadow: 10px 10px 5px #888888;
}
```

### 边框图片

通过 CSS3 的 border-image 属性，您可以使用图片来创建边框：

border-image 属性允许您规定用于边框的图片！

用于创建上面的边框的原始图片：

**实例**

使用图片创建围绕 div 元素的边框：

```
div
{
border-image:url(border.png) 30 30 round;
-moz-border-image:url(border.png) 30 30 round; /* 老的 Firefox */
-webkit-border-image:url(border.png) 30 30 round; /* Safari 和 Chrome */
-o-border-image:url(border.png) 30 30 round; /* Opera */
}
```

## 样式

### 背景

CSS3 包含多个新的背景属性，它们提供了对背景更强大的控制。

在本章，您将学到以下背景属性：

- background-size
- background-origin

您也将学到如何使用多重背景图片。

#### background-size 属性

`background-size` 属性规定背景图片的尺寸。

在 CSS3 之前，背景图片的尺寸是由图片的实际尺寸决定的。在 CSS3 中，可以规定背景图片的尺寸，这就允许我们在不同的环境中重复使用背景图片。

您能够以像素或百分比规定尺寸。如果以百分比规定尺寸，那么尺寸相对于父元素的宽度和高度。

**实例：调整背景图片的大小**

```css
div {
  background:url(bg_flower.gif);
  -moz-background-size:63px 100px; /* 老版本的 Firefox */
  background-size:63px 100px;
  background-repeat:no-repeat;
}
```

**实例：对背景图片进行拉伸，使其完成填充内容区域**

```css
div {
  background:url(bg_flower.gif);
  -moz-background-size:40% 100%; /* 老版本的 Firefox */
  background-size:40% 100%;
  background-repeat:no-repeat;
}
```

#### background-origin 属性

`background-origin` 属性规定背景图片的定位区域。

背景图片可以放置于 content-box、padding-box 或 border-box 区域。

![background-origin](../assets/images/css3/background-origin.gif)

**实例：在 content-box 中定位背景图片**

```css
div {
  background:url(bg_flower.gif);
  background-repeat:no-repeat;
  background-size:100% 100%;
  -webkit-background-origin:content-box; /* Safari */
  background-origin:content-box;
}
```

#### 多重背景图片

CSS3 允许您为元素使用多个背景图像。

**实例：为 body 元素设置两幅背景图片**

```css
body { 
  background-image:url(bg_flower.gif),url(bg_flower_2.gif);
}
```

### 文本

CSS3 包含多个新的文本特性。

在本章中，您将学到如下文本属性：

- text-shadow
- word-wrap

#### 文本阴影

在 CSS3 中，text-shadow 可向文本应用阴影。

您能够规定水平阴影、垂直阴影、模糊距离，以及阴影的颜色：

**实例：向标题添加阴影**

```css
h1 {
  text-shadow: 5px 5px 5px #FF0000;
}
```

#### 自动换行

单词太长的话就可能无法超出某个区域：

This paragraph contains a very long word: thisisaveryveryveryveryveryverylongword. The long word will break and wrap to the next line.

在 CSS3 中，word-wrap 属性允许您允许文本强制文本进行换行 - 即使这意味着会对单词进行拆分：

This paragraph contains a very long word: thisisaveryveryveryveryveryverylongword. The long word will break and wrap to the next line.

下面是 CSS 代码：

**实例：允许对长单词进行拆分，并换行到下一行**

```css
p {word-wrap:break-word;}
```

### 字体

#### @font-face 规则

在 CSS3 之前，web 设计师必须使用已在用户计算机上安装好的字体。

通过 CSS3，web 设计师可以使用他们喜欢的任意字体。

当您您找到或购买到希望使用的字体时，可将该字体文件存放到 web 服务器上，它会在需要时被自动下载到用户的计算机上。

您“自己的”的字体是在 CSS3 @font-face 规则中定义的。

## 浏览器支持

| 属性         | 浏览器支持 |      |      |      |      |
| ---------- | ----- | ---- | ---- | ---- | ---- |
| @font-face |       |      |      |      |      |

Firefox、Chrome、Safari 以及 Opera 支持 .ttf (True Type Fonts) 和 .otf (OpenType Fonts) 类型的字体。

Internet Explorer 9+ 支持新的 @font-face 规则，但是仅支持 .eot 类型的字体 (Embedded OpenType)。

注释：Internet Explorer 8 以及更早的版本不支持新的 @font-face 规则。

## 使用您需要的字体

在新的 @font-face 规则中，您必须首先定义字体的名称（比如 myFirstFont），然后指向该字体文件。

如需为 HTML 元素使用字体，请通过 font-family 属性来引用字体的名称 (myFirstFont)：

### 实例

```
<style> 
@font-face
{
font-family: myFirstFont;
src: url('Sansation_Light.ttf'),
     url('Sansation_Light.eot'); /* IE9+ */
}

div
{
font-family:myFirstFont;
}
</style>

```

[亲自试一试](http://www.w3school.com.cn/tiy/t.asp?f=css3_font-face_rule)

## 使用粗体字体

您必须为粗体文本添加另一个包含描述符的 @font-face：

### 实例

```
@font-face
{
font-family: myFirstFont;
src: url('Sansation_Bold.ttf'),
     url('Sansation_Bold.eot'); /* IE9+ */
font-weight:bold;
}

```

[亲自试一试](http://www.w3school.com.cn/tiy/t.asp?f=css3_font-face_rule_bold)

文件 "Sansation_Bold.ttf" 是另一个字体文件，它包含了 Sansation 字体的粗体字符。

只要 font-family 为 "myFirstFont" 的文本需要显示为粗体，浏览器就会使用该字体。

通过这种方式，我们可以为相同的字体设置许多 @font-face 规则。



