# CSS

## 选择器

+ id选择器

  id选择器可以为标有特定id的HTML元素指定特定的样式。

  例子

  ```css
  #para1
  {
      text-align:center;
      color:red;
  }
  ```

+ class选择器

  class选择器用于描述一组元素的样式，class选择器可以在多个元素中使用

  下例，将所有拥有center类的HTML元素均为居中

  ```css
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8"> 
  <title>菜鸟教程(runoob.com)</title> 
  <style>
  .center
  {
  	text-align:center;
  }
  </style>
  </head>
  
  <body>
  <h1 class="center">标题居中</h1>
  <p class="center">段落居中。</p> 
  </body>
  </html>
  ```

+ 标签选择器

  使用标签名作为selector名，语法格式：**S{...}**（S为选择器名）。例：所有的p标签都会匹配以下的样式

  ```css
  <style>
  p{
    font-style:italic;
  }
  </style>
  <!--下面的文字是斜体的-->
  <p style="font-style:italic">italic text</p>
  ```

## 文档流

在HTML中任何一个元素其实就是一个**对象**，也是一个盒子。在默认情况下它是按照出现的先后顺序来排列，而这个排列的顺序就是文档流。

文档流是元素在Web页面上的一种呈现方式。所有的HTML元素都是块盒子（Block Boxes，块级元素）或行内框（Inline Boxes，行内元素）。当浏览器开始渲染HTML文档时，它从窗口的顶端开始，经过整个文档内容的过程中，分配元素需要的空间。除非文档的尺寸被CSS规则限定，否则浏览器垂直扩展文档来容纳全部的内容。每个新的块级元素渲染为新行。行内元素则按照顺序被水平渲染直到当前行遇到边界，然后换到下一行垂直渲染。


## 块状元素、内联元素、内联-块状元素

### 块状元素

块状元素最大的特点是可以独占一行。div是html中典型的块状元素。我们可以给块状元素设置宽度（width）、高度（height）、外间距（margin）、内间距（padding）。
块状元素的css样式：

```css
div{
	margin: 20px;
	padding: 10px;
	width: 100px;
	height: 100px;
	background-color: yellow;
}
```

在不设置位置的情况下，每个块状元素都是独占一行，在它后面的元素都是另起一行。
如果要把块状元素设置为内联元素，可以用display:inline来进行转换。

### 内联元素

内联元素和块状元素最大的区别，就是内联元素和其他元素是在同一行显示的，所以也被称为“行内元素”。
内联元素不能设置宽度、高度。但是如果我们给内联元素设置margin和padding会怎么样呢？我们可以试一试：
我们在一个html文档里写入了块状元素、内联元素、内联-块状元素。css文件里我们给内联元素span设置margin、padding和背景颜色：

```css
div{
	margin: 20px;
	padding: 10px;
	width: 100px;
	height: 100px;
	background-color: yellow;
}
span{
	margin: 50px;
	padding: 120px;
	background-color: orange;
}
```

### 内联-块状元素

内联-块状元素同时具有内联元素和块状元素的特征：可以设置宽度、高度、margin 值和padding值，但是又不单独占据一行。
input和image是典型的内联-块状元素。

```css
input{
	margin: 50px;
	padding: 50px;
	width: 100px;
	height: 100px;
	background-color: grey;
}
```

## 盒子模型

### 盒子的组成

盒子模型就是把HTML页面中的元素看作是一个矩形的盒子，也就是一个盛装内容的容器。一个盒子由外到内可以分成四个部分：margin(外边距）、border（边框）、padding（内边距）、content（内容）。会发现margin、border、padding是CSS属性，因此可以通过这三个属性来控制盒子的这三个部分。而content则是HTML元素的内容。

## 浮动

### 浮动元素

浮动元素同时处于常规流内和流外的元素。其中块级元素认为浮动元素不存在，而浮动元素会影响行内元素的布局，浮动元素会通过影响行内元素间接影响了包含块的布局。

**常规流：**页面上从左往右，从上往下排列的元素流，就是常规流
**脱离常规流：**绝对定位，fixed定位的元素有自己固定的位置，脱离了常规流
**包含块：**一个元素离它最近的块级元素是它的包含块

### 浮动元素的摆放会遵循如下的规则：

- 尽量靠上
- 尽量靠左
- 尽量一个挨着一个
- 不能超出包含块，除非元素比包含块更宽
- 不能超过所在行的最高点
- 不能超过它前面浮动元素的最高点
- 行内元素绕着浮动元素摆放：左浮动元素的右边和右浮动元素的左边会出浮动元素

## 定位

### static 定位

HTML 元素的默认值，即没有定位，遵循正常的文档流对象。静态定位的元素不会受到 top, bottom, left, right影响。

```css
div.static {
    position: static;
    border: 3px solid #73AD21;
}
```

### fixed 定位

元素的位置相对于浏览器窗口是固定位置。即使窗口是滚动的它也不会移动：

```css
p.pos_fixed
{
    position:fixed;
    top:30px;
    right:5px;
}
```

### relative 定位

相对定位元素的定位是相对其正常位置。

```css
h2.pos_left
{
    position:relative;
    left:-20px;
}
h2.pos_right
{
    position:relative;
    left:20px;
}
```

### absolute 定位

绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于<html>:

```css
h2
{
    position:absolute;
    left:100px;
    top:150px;
}
```

## CSS样式层叠规则

1. 若本身设置了样式，则继承的样式无效；我认为也可以简单理解为继承的特指度为0；
2. ! important具有最高权限，只要声明中加上这一句，其他样式都会被层叠；我认为可以简单理解为其特指度为无穷大；
3. 行内式仅次于！important；
4. 除上面三者外，其余样式按照(I-C-E)计算特指度。特指度高的层叠特指度低的；
5. 同特指度的，后面的层叠前面的样式。
