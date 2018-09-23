# css笔记  
## CSS样式基本知识
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

## 选择器   

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
  
还有一个比较有用的选择器子选择器，即大于符号(>),  
用于选择指定标签元素的第一代子元素  

`.food>li{border:1px solid red;}`  

### (5)包含(后代)选择器  
  
即加入空格,用于选择指定标签元素下的后辈元素  

`.first  span{color:red;}`  

子选择器（child selector）仅是指它的直接后代，  
或者你可以理解为作用于子元素的第一代后代。  
而后代选择器是作用于所有子后代元素  

### (6)通用选择器  
  
匹配html中所有标签元素  
`* {color:red;}`  

### (7)伪类选择符  
  
给html中一个标签元素的鼠标滑过的状态来设置字体颜色：  
`a:hover{color:red;}`  
  
### (8)分组选择符  

当你想为html中多个标签元素设置同一个样式时，可以使用分组选择符（，）  
`h1,span{color:red;}`  
  
## CSS的继承、层叠和特殊性  

### (1)继承  

继承是一种规则，它允许样式不仅应用于某个特定html标签元素，而且应用于其后代。  
但注意有一些css样式是不具有继承性的。  

### (2)特殊性  

标签的权值为1，类选择符的权值为10，ID选择符的权值最高为100。  
还有一个权值比较特殊--继承也有权值但很低，有的文献提出它只有0.1，所以可以理解为继承的权值最低。  

### (3)层叠  

内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）  

### (4)重要性  

有些特殊的情况需要为某些样式设置具有最高权值  
这时候我们可以使用!important来解决  
```
p{color:red!important;}
p{color:green;}
<p class="first">三年级时，我还是一个<span>胆小如鼠</span>的小女孩。</p>
```
这时 p 段落中的文本会显示的red红色   
#注意：!important要写在分号的前面  

## CSS格式化排版  
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
  
`p{font-weight:bold;}`  
  
### (4)文字排版--斜体 

`p{font-style:italic;}`  
  
### (5)文字排版--下划线 
  
`p{text-decoration:underline;}`  
  
### (6)文字排版--删除线 
  
`p{text-decoration:line-through;}`  
  
### (7)段落排版--缩进  
  
首行缩进两字符：    
`p{text-indent:2em;}`   
  
### （8）段落排版--行间距（行高）

两倍行高：  
`p{line-height:2em;}`  

### （9）段落排版--中文字间距、字母间距

中文字间隔、字母间隔设置：  
如果想在网页排版中设置文字间隔或者字母间隔就可以使用 letter-spacing 来实现  
#注意：这个样式使用在英文单词时，是设置字母与字母之间的间距。  
```
h1{
    letter-spacing:50px;
}
...
<h1>了不起的盖茨比</h1>
```
  
单词间距设置：  
如果我想设置英文单词之间的间距呢？可以使用 word-spacing 来实现。  
```
h1{
    word-spacing:50px;
}
...
<h1>welcome to imooc!</h1>
```
  
### (10)段落排版--对齐



