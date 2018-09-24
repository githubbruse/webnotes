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
  
1、**border-style**（边框样式）常见样式有：  

**dashed**（虚线）| **dotted**（点线）| **solid**（实线）  
  
2、**border-color**（边框颜色）中的颜色可设置为十六进制颜色，如:  
  
border-color:#888;//前面的井号不要忘掉。  
  
3、**border-width**（边框宽度）中的宽度也可以设置为：  

**thin** | **medium** | **thick**（但不是很常用），**最常**还是用**象素（px）**。   
  
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
  
流动（Flow）是默认的网页布局模式  
  
流动布局模型具有2个比较典型的特征：  
  
第一点，**块状元素**都会在所处的包含元素内**自上而下**按顺序垂直延伸分布，因为在默认状态下，块状元素的宽度都为100%。实际上，块状元素都会以行的形式占据位置。    
  
第二点，在流动模型下，**内联元素**都会在所处的包含元素内**从左到右**水平分布显示。（内联元素可不像块状元素这么霸道独占一行） 
  
### （2）浮动模型
  
任何元素在默认情况下是不能浮动的，但可以用 CSS 定义为浮动，如 div、p、table、img 等元素都可以被定义为浮动。如下代码可以实现两个 div 元素一行显示。  
  
```
div{
    width:200px;
    height:200px;
    border:2px red solid;
    float:left;
}
<div id="div1"></div>
<div id="div2"></div>
```
  
效果：  
  
![3](http://img.mukewang.com/540e62c60001c56a06760417.jpg)  
  
当然你也可以同时设置两个元素右浮动也可以实现一行显示。  
  
```
div{
    width:200px;
    height:200px;
    border:2px red solid;
    float:right;
}
```
  
![4](http://img.mukewang.com/540e632b0001f5f506760417.jpg)  
  
一左一右  
  
```
div{
    width:200px;
    height:200px;
    border:2px red solid;
}
#div1{float:left;}
#div2{float:right;}
```
  
### (3)层模型
  
#### 1°绝对定位
  
如果想为元素设置层模型中的绝对定位，需要设置position:absolute(表示绝对定位)，这条语句的作用将元素从文档流中拖出来，然后使用left、right、top、bottom属性相对于其最接近的一个具有定位属性的父包含块进行绝对定位。如果不存在这样的包含块，则相对于body元素，即相对于浏览器窗口。  
  
如下面代码可以实现div元素相对于浏览器窗口向右移动100px，向下移动50px。   
  
```
div{
    width:200px;
    height:200px;
    border:2px red solid;
    position:absolute;
    left:100px;
    top:50px;
}
<div id="div1"></div>
```
  
![4](http://img.mukewang.com/53a00b130001e86707360547.jpg)  
  
#### 2°相对定位
  
如果想为元素设置层模型中的相对定位，需要设置`position:relative`（表示相对定位），它通过left、right、top、bottom属性确定元素在正常文档流中的偏移位置。相对定位完成的过程是首先按static(float)方式生成一个元素(并且元素像层一样浮动了起来)，然后**相对于以前的位置移动**，移动的方向和幅度由left、right、top、bottom属性确定，**偏移前的位置保留不动**。  
  
如下代码实现相对于以前位置向下移动50px，向右移动100px;  
  
```
#div1{
    width:200px;
    height:200px;
    border:2px red solid;
    position:relative;
    left:100px;
    top:50px;
}

<div id="div1"></div>
```
  
![5](http://img.mukewang.com/53a00d2b00015c4b06190509.jpg)  
  
#### 3°固定定位
  
fixed：表示固定定位，与absolute定位类型类似，但它的相对移动的坐标是视图（屏幕内的网页窗口）本身。由于视图本身是固定的，它不会随浏览器窗口的滚动条滚动而变化，除非你在屏幕中移动浏览器窗口的屏幕位置，或改变浏览器窗口的显示大小，因此固定定位的元素会始终位于浏览器窗口内视图的某个位置，不会受文档流动影响，这与`background-attachment:fixed;`属性功能相同。以下代码可以实现相对于浏览器视图向右移动100px，向下移动50px。并且拖动滚动条时位置固定不变。  
  
```
#div1{
    width:200px;
    height:200px;
    border:2px red solid;
    position:fixed;
    left:100px;
    top:50px;
}
<p>文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本文本。</p>
....
```
  
#### 4°Relative与Absolute组合使用
  
相对于其它元素进行定位  
  
**1、参照定位的元素必须是相对定位元素的前辈元素：**  
  
```
<div id="box1"><!--参照定位的元素-->
    <div id="box2">相对参照元素进行定位</div><!--相对定位元素-->
</div>
```
  
**2、参照定位的元素必须加入position:relative;**  
  
```
#box1{
    width:200px;
    height:200px;
    position:relative;        
}
```
  
**3、定位元素加入position:absolute，便可以使用top、bottom、left、right来进行偏移定位了。**  
  
```
#box2{
    position:absolute;
    top:20px;
    left:30px;         
}
```
  
这样box2就可以相对于父元素box1定位了（这里注意参照物就可以不是浏览器了，而可以自由设置了）。  
  
## 七、缩写
### (1)盒模型代码简写
  
1、如果top、right、bottom、left的值相同，如下面代码：  
  
`margin:10px 10px 10px 10px;`  
  
可缩写为：  
  
`margin:10px;`  
  
2、如果top和bottom值相同、left和 right的值相同，如下面代码：  
  
`margin:10px 20px 10px 20px;`   
  
可缩写为：  
  
`margin:10px 20px;`  
   
3、如果left和right的值相同，如下面代码：  
  
`margin:10px 20px 30px 20px;`  
  
可缩写为：  
  
`margin:10px 20px 30px;`  
  
*注意：padding、border的缩写方法和margin是一致的。*  
  
### （2）颜色值缩写
  
关于颜色的css样式也是可以缩写的，当你设置的颜色是16进制的色彩值时，如果每两位的值相同，可以缩写一半。  
  
例子1：  
   
`p{color:#000000;}`  
  
可以缩写为：  
  
`p{color: #000;}`    
  
例子2：  
  
`p{color: #336699;}`   
  
可以缩写为：  
  
`p{color: #369;}`  
  
### (3)字体缩写
  
网页中的字体css样式代码也有他自己的缩写方式，下面是给网页设置字体的代码：  
  
```
body{
    font-style:italic;
    font-variant:small-caps; 
    font-weight:bold; 
    font-size:12px; 
    line-height:1.5em; 
    font-family:"宋体",sans-serif;
}
```
  
这么多行的代码其实可以缩写为一句：  
  
```
body{
    font:italic  small-caps  bold  12px/1.5em  "宋体",sans-serif;
}
```
  
*注意：*  
  
1、使用这一简写方式你至少要指定 font-size 和 font-family 属性，其他的属性(如 font-weight、font-style、font-variant、line-height)如未指定将自动使用默认值。  
  
2、在缩写时 font-size 与 line-height 中间要加入“/”斜扛。  
  
一般情况下因为对于中文网站，英文还是比较少的，所以下面缩写代码比较常用：  
  
```
body{
    font:12px/1.5em  "宋体",sans-serif;
}
```
  
只是有字号、行间距、中文字体、英文字体设置。  
  
## 八、单位和值
  
### （1）颜色值
  
1、英文命令颜色  
  
`p{color:red;}`  
  
2、RGB颜色  
  
这个与 photoshop 中的 RGB 颜色是一致的，由 R(red)、G(green)、B(blue) 三种颜色的比例来配色。  
  
`p{color:rgb(133,45,200);}`  
  
每一项的值可以是 0~255 之间的整数，也可以是 0%~100% 的百分数。如：  
  
`p{color:rgb(20%,33%,25%);}`  
  
3、十六进制颜色  
  
这种颜色设置方法是现在比较普遍使用的方法，其原理其实也是 RGB 设置，但是其每一项的值由 0-255 变成了十六进制 00-ff。  
  
`p{color:#00ffff;}`  
  
### (2)长度值
  
长度单位总结一下，目前比较常用到px（像素）、em、% 百分比，要注意其实这三种单位都是相对单位。  
  
1、像素  
  
像素为什么是相对单位呢？因为像素指的是显示器上的小点（CSS规范中假设“90像素=1英寸”）。实际情况是浏览器会使用显示器的实际像素值有关，在目前大多数的设计者都倾向于使用像素（px）作为单位。  
  
2、em  
  
就是本元素给定字体的 font-size 值，如果元素的 font-size 为 14px ，那么 1em = 14px；如果 font-size 为 18px，那么 1em = 18px。如下代码：  
  
`p{font-size:12px;text-indent:2em;}`  
  
上面代码就是可以实现段落首行缩进 24px（也就是两个字体大小的距离）。  
  
下面注意一个特殊情况：  
  
但当给 font-size 设置单位为 em 时，此时计算的标准以 p 的父元素的 font-size 为基础。如下代码：  
  
html:  

`<p>以这个<span>例子</span>为例。</p>`  
  
css:  
  
```
p{font-size:14px}
span{font-size:0.8em;}
```
  
结果 span 中的字体“例子”字体大小就为 11.2px（14 * 0.8 = 11.2px）。  
  
3、百分比  
  
`p{font-size:12px;line-height:130%}`  
  
设置行高（行间距）为字体的130%（12 * 1.3 = 15.6px）。  
  
## 九、css样式设置小技巧
  
### （1)水平居中
  
#### 1°行内元素
  
如果被设置元素为文本、图片等行内元素时，水平居中是通过给父元素设置 `text-align:center` 来实现的。(父元素和子元素：如下面的html代码中，div是“我想要在父容器中水平居中显示”这个文本的父元素。反之这个文本是div的子元素 )如下代码：  
  
html代码：  
  
```
<body>
  <div class="txtCenter">我想要在父容器中水平居中显示。</div>
</body>
```
  
css代码：  
  
```
<style>
  .txtCenter{
    text-align:center;
  }
</style>
```
  
#### 2°定宽块状元素
  
当被设置元素为 块状元素 时用 text-align：center 就不起作用了，这时也分两种情况：定宽块状元素和不定宽块状元素。  
  
这一小节我们先来讲一讲定宽块状元素。(定宽块状元素：块状元素的宽度width为固定值。)  

满足定宽和块状两个条件的元素是可以通过设置“左右margin”值为“auto”来实现居中的。我们来看个例子就是设置 div 这个块状元素水平居中：  
  
html代码：  
  
```
<body>
  <div>我是定宽块状元素，哈哈，我要水平居中显示。</div>
</body>
```
  
```
css代码：

<style>
div{
    border:1px solid red;/*为了显示居中效果明显为 div 设置了边框*/
    
    width:200px;/*定宽*/
    margin:20px auto;/* margin-left 与 margin-right 设置为 auto */
}
</style>
```
  
也可以写成：  
  
```
margin-left:auto;
margin-right:auto;
```
  
*注意：元素的“上下 margin” 是可以随意设置的。*
  
#### 3°不定宽块状元素方法（一）  
  
在实际工作中我们会遇到需要为“不定宽度的块状元素”设置居中，比如网页上的分页导航，因为分页的数量是不确定的，所以我们不能通过设置宽度来限制它的弹性。(不定宽块状元素：块状元素的宽度width不固定。)  
  
不定宽度的块状元素有三种方法居中（这三种方法目前使用的都很多）：  
  
**加入 `table` 标签**   
  
**设置 `display: inline` 方法：与第一种类似，显示类型设为 行内元素，进行不定宽元素的属性设置**  
  
**设置 `position:relative`和 `left:50%`：利用 相对定位 的方式，将元素向左偏移 50% ，即达到居中的目的**    
  
这一小节我们来讲一下第一种方法：  
  
为什么选择方法一加入table标签? 是利用table标签的长度自适应性---即不定义其长度也不默认父元素body的长度（table其长度根据其内文本长度决定），因此可以看做一个定宽度块元素，然后再利用定宽度块状居中的margin的方法，使其水平居中。  
  
**第一步**：为需要设置的居中的元素外面加入一个 `table` 标签 ( 包括 `<tbody>`、`<tr>`、`<td>` )。  
  
**第二步**：为这个 table 设置“左右 margin 居中”（这个和定宽块状元素的方法一样）。
  
举例如下：  
  
html代码：  
  
```
<div>
 <table>
  <tbody>
    <tr><td>
    <ul>
        <li>我是第一行文本</li>
        <li>我是第二行文本</li>
        <li>我是第三行文本</li>
    </ul>
    </td></tr>
  </tbody>
 </table>
</div>
```
  
css代码：  
  
```
<style>
table{
    border:1px solid;
    margin:0 auto;
}
</style>
```
  
#### 4°不定宽块状元素方法（二） 
  
第二种方法：**改变块级元素的 display 为 inline 类型（设置为 行内元素 显示），然后使用 `text-align:center` 来实现居中效果**。如下例子：  
  
html代码：  
  
```
<body>
<div class="container">
    <ul>
        <li><a href="#">1</a></li>
        <li><a href="#">2</a></li>
        <li><a href="#">3</a></li>
    </ul>
</div>
</body>
```
  
css代码：  
  
```
<style>
.container{
    text-align:center;
}
/* margin:0;padding:0（消除文本与div边框之间的间隙）*/
.container ul{
    list-style:none;
    margin:0;
    padding:0;
    display:inline;
}
/* margin-right:8px（设置li文本之间的间隔）*/
.container li{
    margin-right:8px;
    display:inline;
}
</style>
```
  
这种方法相比第一种方法的优势是不用增加无语义标签，但也存在着一些问题：它将块状元素的 display 类型改为 inline，变成了行内元素，所以少了一些功能，比如设定长度值。  
  
#### 5°不定宽块状元素方法（三）
  
方法三：通过给父元素设置 float，然后给父元素设置 position:relative 和 left:50%，子元素设置 position:relative 和 left: -50% 来实现水平居中。  
  
我们可以这样理解：假想ul层的父层（即下面例子中的div层）中间有条平分线将ul层的父层（div层）平均分为两份，ul层的css代码是将ul层的最左端与ul层的父层（div层）的平分线对齐；而li层的css代码则是将li层的平分线与ul层的最左端（也是div层的平分线）对齐，从而实现li层的居中。  
  
代码如下：  
  
```
<body>
<div class="container">
    <ul>
        <li><a href="#">1</a></li>
        <li><a href="#">2</a></li>
        <li><a href="#">3</a></li>
    </ul>
</div>
</body>
css代码：

<style>
.container{
    float:left;
    position:relative;
    left:50%
}

.container ul{
    list-style:none;
    margin:0;
    padding:0;
    
    position:relative;
    left:-50%;
}
.container li{float:left;display:inline;margin-right:8px;}
</style>
 ```
  
这三种方法使用得都非常广泛，各有优缺点，具体选用哪种方法，可以视具体情况而定。  
  
### (2)垂直居中
  
#### 1°父元素高度确定的单行文本
  
父元素高度确定的单行文本的竖直居中的方法是通过设置父元素的 height 和 line-height 高度一致来实现的。(height: 该元素的高度，line-height: 顾名思义，行高（行间距），指在文本中，**行与行之间的基线间的距离**（**字底到字底**)。  
  
line-height 与 font-size 的计算值之差，在 CSS 中成为“行间距”(**css中的“行间距”，第一行字的底部与第二行字的顶部之间空白的距离**）。  
  
这种文字行高与块高一致带来了一个弊端：当文字内容的长度大于块的宽时，就有内容脱离了块。  
  
如下代码：  
  
```
<div class="container">
    hi,imooc!
</div>
```
  
css代码：  
  
```
<style>
.container{
    height:100px;
    line-height:100px;
    background:#999;
}
</style>
```
  
#### 2°父元素高度确定的多行文本（方法一）
  
**使用插入 table  (包括tbody、tr、td)标签，同时设置 `vertical-align：middle`。**  
  
css 中有一个用于竖直居中的属性 vertical-align，在父元素设置此样式时，会对inline-block类型的子元素都有用。下面看一下例子：  
  
html代码：  
  
```
<body>
<table><tbody><tr><td class="wrap">
<div>
    <p>看我是否可以居中。</p>
</div>
</td></tr></tbody></table>
</body>
```
  
css代码：  
  
`table td{height:500px;background:#ccc}`  
  
因为 td 标签默认情况下就默认设置了 vertical-align 为 middle，所以我们不需要显式地设置了。  
  
#### 3°父元素高度确定的多行文本（方法二）
  
在 chrome、firefox 及 IE8 以上的浏览器下可以设置块级元素的 display 为 table-cell（设置为表格单元显示），激活 vertical-align 属性，但注意 IE6、7 并不支持这个样式, 兼容性比较差。  
  
html代码：  
  
```
<div class="container">
    <div>
        <p>看我是否可以居中。</p>
        <p>看我是否可以居中。</p>
        <p>看我是否可以居中。</p>
    </div>
</div>
```
  
css代码：  
  
```
<style>
.container{
    height:300px;
    background:#ccc;
    display:table-cell;/*IE8以上及Chrome、Firefox*/
    vertical-align:middle;/*IE8以上及Chrome、Firefox*/
}
</style>
```  
  
这种方法的好处是不用添加多余的无意义的标签，但缺点也很明显，它的兼容性不是很好，不兼容 IE6、7而且这样修改display的block变成了table-cell，破坏了原有的块状元素的性质。  
  
#### 4°隐性改变display类型
  
有一个有趣的现象就是当为元素（不论之前是什么类型元素，display:none 除外）设置以下 2 个句之一：  
  
 1.` position : absolute `  
  
 2.` float : left `或 `float:right `  
  
简单来说，只要html代码中出现以上两句之一，元素的display显示类型就会自动变为以 display:inline-block（**块状元素**）的方式显示，当然就可以设置元素的 width 和 height 了，且默认宽度不占满父元素。  

如下面的代码，小伙伴们都知道 a 标签是**行内元素**，所以设置它的 width 是没有效果的，但是设置为 position:absolute 以后，就可以了。  
  
```
<div class="container">
    <a href="#" title="">进入课程请单击这里</a>
</div>
```
  
css代码  
  
```
<style>
.container a{
    position:absolute;
    width:200px;
    background:#ccc;
}
</style>
```
