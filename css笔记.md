# css笔记  
  
## 一、CSS样式基本知识  
  
### (1)内联式  
  
把css代码直接写在现有的HTML标签中  
  
`<p style="color:red">这里文字是红色。</p>`  

### (2)嵌入式    
  在`<head></head>`中添加  
    
  ```
  <style type="text/css">
  span{
  color:red;
  }
  </style>
  ```

### (3)外部式  
  
在`<head></head>`中添加  
  
`<link href="base.css" rel="stylesheet" type="text/css" />`  

## 二、选择器   

### (1)标签选择器  
  
标签选择器其实就是html代码中的标签  
  
`p{font-size:12px;line-height:1.6em;}`  
  
写在head中  

### (2)类选择器  
  
`.类选器名称{css样式代码;}` 
  
第一步：`<span>胆小如鼠</span>`  
第二步：`<span class="stress">胆小如鼠</span>`  
第三步，设置css样式:`.stress{color:red;}/*类前面要加入一个英文圆点*/`  

### (3)ID选择器 (一个id只用一次）  
  
`<span id="setGreen">公开课</span>`  
```
#setGreen{
   color:green;
}
```

### (4)子选择器  
  
还有一个比较有用的选择器子选择器，即大于符号(>),用于选择指定标签元素的第一代子元素  
  
`.food>li{border:1px solid red;}`  

### (5)包含(后代)选择器  
  
即加入空格,用于选择指定标签元素下的后辈元素  

`.first  span{color:red;}`  

子选择器（child selector）仅是指它的直接后代，或者你可以理解为作用于子元素的第一代后代。而后代选择器是作用于所有子后代元素   

### (6)通用选择器  
  
匹配html中所有标签元素  
  
`* {color:red;}`  

### (7)伪类选择符  
  
给html中一个标签元素的鼠标滑过的状态来设置字体颜色：  
  
`a:hover{color:red;}`  
  
### (8)分组选择符  

当你想为html中多个标签元素设置同一个样式时，可以使用分组选择符（，）  
  
`h1,span{color:red;}`  
  
## 三、CSS的继承、层叠和特殊性  

### (1)继承  
  
继承是一种规则，它允许样式不仅应用于某个特定html标签元素，而且应用于其后代。但注意有一些css样式是不具有继承性的。  

### (2)特殊性  
  
标签的权值为1，类选择符的权值为10，ID选择符的权值最高为100。  
还有一个权值比较特殊--继承也有权值但很低，有的文献提出它只有0.1，所以可以理解为继承的权值最低。  
  
### (3)层叠  
  
内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）  
  
### (4)重要性  
  
有些特殊的情况需要为某些样式设置具有最高权值  
这时候我们可以**使用 !important**来解决  
```
p{color:red!important;}
p{color:green;}
<p class="first">三年级时，我还是一个<span>胆小如鼠</span>的小女孩。</p>
```
这时 p 段落中的文本会显示的red红色  
  
*注意：!important要写在分号的前面*  
  
## 四、CSS格式化排版  
  
### （1）文字排版--字体  
  
为网页中的文字设置字体为宋体： 
  
`body{font-family:"宋体";}`  
  
现在一般网页喜欢设置“微软雅黑”，如下代码：  
  
`body{font-family:"Microsoft Yahei";}`  
或  
`body{font-family:"微软雅黑";}`  

### (2)文字排版--字号、颜色  
  
可以使用下面代码设置网页中文字的字号为12像素，并把字体颜色设置为#666(灰色)： 
  
`body{font-size:12px;color:#666}`  

### (3)文字排版--粗体 
  
**font-weight**  
  
`p{font-weight:bold;}`  
  
### (4)文字排版--斜体 
  
**font-style**  
  
`p{font-style:italic;}`  
  
### (5)文字排版--下划线 
  
`p{text-decoration:underline;}`  
  
### (6)文字排版--删除线 
    
`p{text-decoration:line-through;}`  
  
### (7)段落排版--缩进  
  
**text-indent**  
  
首行缩进两字符：  
  
`p{text-indent:2em;}`   
  
### （8）段落排版--行间距（行高）
  
**line-height** 
  
两倍行高：  
  
`p{line-height:2em;}`  

### （9）段落排版--中文字间距、字母间距

**中文字间隔、字母间隔设置**：  
  
如果想在网页排版中设置文字间隔或者字母间隔就可以使用 **letter-spacing** 来实现  
  
*注意：这个样式使用在英文单词时，是设置字母与字母之间的间距。*    
  
```
h1{
    letter-spacing:50px;
}
...
<h1>了不起的盖茨比</h1>
```
  
**单词间距设置**：  
  
如果我想设置英文单词之间的间距呢？可以使用 word-spacing 来实现。  
```
h1{
    word-spacing:50px;
}
...
<h1>welcome to imooc!</h1>
```
  
### (10)段落排版--对齐
  
**居中**:      
```
h1{
    text-align:center;
}
```
   
**居左**:left  
  
**居右**：right    

## 五、CSS盒模型

### （1）元素分类
  
在CSS中，html中的标签元素大体被分为三种不同的类型：块状元素、内联元素(又叫行内元素)和内联块状元素。  
   
**常用的块状元素有:**    
  
`<div>`、`<p>`、`<h1>`...`<h6>`、`<ol>`、`<ul>`、`<dl>`、`<table>`、`<address>`、`<blockquote>`、`<form>`  
  
**常用的内联元素有：**   
  
`<a>`、`<span>`、`<br>`、`<i>`、`<em>`、`<strong>`、`<label>`、`<q>`、`<var>`、`<cite>`、`<code>`  
  
**常用的内联块状元素有：**   
  
`<img>`、`<input>`  
  
### （2）块级元素
  
在html中`<div>`、`<p>`、`<h1>`、`<form>`、`<ul>` 和 `<li>`就是块级元素。设置`display:block`就是将元素显示为块级元素。如下代码就是将**内联元素a**转换为**块状元素**，从而使a元素具有**块状元素**特点。  
  
`a{display:block;}`
  
**块级元素特点：**
  
1、**每个**块级元素都**从新的一行开始**，并且**其后**的元素也**另起一行**。（真霸道，一个块级元素独占一行）  
  
2、元素的**高度**、**宽度**、**行高**以及顶和底**边距**都**可设置**。  
  
3、元素宽度在不设置的情况下，是它本身父容器的100%（和父元素的宽度一致），除非设定一个宽度。  
  
### (3)元素分类--内联元素
  
在html中，`<span>`、`<a>`、`<label>`、`<strong>`和`<em>`就是典型的**内联元素**（**行内元素**）（inline）元素。当然**块状元素**也可以通过代码`display:inline`将元素设置为**内联元素**。如下代码就是将**块状元素div**转换为**内联元素**，从而使 div 元素具有**内联元素**特点。  
  
```
div{
     display:inline;
 }

......

<div>我要变成内联元素</div>
```  
  
**内联元素特点：**
  
1、和其他元素都**在一行上**；  
  
2、元素的**高度**、**宽度**及顶部和底部**边距** **不可设置**；  
  
3、元素的宽度就是它包含的文字或图片的**宽度**，**不可改变**。  
  
### (4)元素分类--内联块状元素
  
**内联块状元素**（inline-block）就是同时具备内联元素、块状元素的特点，代码`display:inline-block`就是将元素设置为内联块状元素。(css2.1新增)，<img>、<input>标签就是这种内联块状标签。  
  
inline-block 元素特点：  
  
1、和其他元素都**在一行上**；  
  
2、元素的**高度**、**宽度**、**行高**以及顶和底**边距**都**可设置**。  
  
### (5)盒模型--边框（一）
  
盒子模型的边框就是围绕着内容及补白的线，这条线你可以设置它的粗细、样式和颜色(边框三个属性)。  
  
如下面代码为 div 来设置边框粗细为 2px、样式为实心的、颜色为红色的边框：  
  
```
div{
    border:2px  solid  red;
}
```
   
*注意：*  
  
1、border-style（边框样式）常见样式有：  

dashed（虚线）| dotted（点线）| solid（实线）  
  
2、border-color（边框颜色）中的颜色可设置为十六进制颜色，如:  
  
border-color:#888;//前面的井号不要忘掉。  
  
3、border-width（边框宽度）中的宽度也可以设置为：  

thin | medium | thick（但不是很常用），最常还是用象素（px）。  
  
### (6)盒模型--边框（二）
  
css 样式中允许只为一个方向的边框设置样式：  
  
`div{border-bottom:1px solid red;}`  
  
同样可以使用下面代码实现其它三边(上、右、左)边框的设置：  
  
`border-top:1px solid red;`  
`border-right:1px solid red; `  
`border-left:1px solid red;`  
  
### (7)盒模型--宽度和高度
  
盒模型宽度和高度和我们平常所说的物体的宽度和高度理解是不一样的，css内定义的宽（width）和高（height），指的是填充以里的**内容范围**。  
  
因此一个元素实际宽度（盒子的宽度）=左边界+左边框+左填充+内容宽度+右填充+右边框+右边界。  
  
![1](http://img.mukewang.com/539fbb3a0001304305570259.jpg)  
  
元素的高度也是同理。  
  
比如：  
  
css代码：  
  
```
div{
    width:200px;
    padding:20px;
    border:1px solid red;
    margin:10px;    
}
```
  
html代码：  
  
```
<body>
   <div>文本内容</div>
</body>
```
  
元素的实际长度为：10px+1px+20px+200px+20px+1px+10px=262px。在chrome浏览器下可查看元素盒模型，如下图：  
  
![2](http://img.mukewang.com/543b4cae0001b34304300350.jpg)  
  
### (8)盒模型--填充
  
元素内容与边框之间是可以设置距离的，称之为“填充”。填充也可分为上、右、下、左(顺时针)。如下代码：  
  
`div{padding:20px 10px 15px 30px;}`  
  
顺序一定不要搞混。可以分开写上面代码：  
  
```
div{
   padding-top:20px;
   padding-right:10px;
   padding-bottom:15px;
   padding-left:30px;
}
```
  
如果上、右、下、左的填充都为10px;可以这么写:  
  
`div{padding:10px;}`  
  
如果上下填充一样为10px，左右一样为20px，可以这么写：  
  
`div{padding:10px 20px;}`  
  
### (9)盒模型--边界
  
元素与其它元素之间的距离可以使用边界（margin）来设置。边界也是可分为上、右、下、左。如下代码：  
  
`div{margin:20px 10px 15px 30px;}`  
  
也可以分开写：  
  
```
div{
   margin-top:20px;
   margin-right:10px;
   margin-bottom:15px;
   margin-left:30px;
}
```
  
如果上右下左的边界都为10px;可以这么写：  
  
`div{ margin:10px;}`  
  
如果上下边界一样为10px，左右一样为20px，可以这么写  
  
`div{ margin:10px 20px;}`  
  
*总结一下：padding和margin的区别，padding在边框里，margin在边框外。*  
  
## 六、CSS布局模型
  
### （1）流动模型
  
