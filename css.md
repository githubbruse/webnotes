# css笔记   
* 【内联式】  
把css代码直接写在现有的HTML标签中  
`<p style="color:red">这里文字是红色。</p>`  

* 【嵌入式】  
  在`<head></head>`中添加  
  ```
  <style type="text/css">
  span{
  color:red;
  }
  </style>
  ```

* 【外部式】  
在`<head></head>`中添加  
`<link href="base.css" rel="stylesheet" type="text/css" />`  

* 【选择器】  
（1）标签选择器  
标签选择器其实就是html代码中的标签  
`p{font-size:12px;line-height:1.6em;}`  
写在head中  

（2）类选择器  
`.类选器名称{css样式代码;}`  
第一步：`<span>胆小如鼠</span>`  
第二步：`<span class="stress">胆小如鼠</span>`  
第三步，设置css样式:`.stress{color:red;}/*类前面要加入一个英文圆点*/`  

（3）ID选择器 (一个id只用一次）  
`<span id="setGreen">公开课</span>`  
```
#setGreen{
   color:green;
}
```

（4）子选择器  
还有一个比较有用的选择器子选择器，即大于符号(>),  
用于选择指定标签元素的第一代子元素  

`.food>li{border:1px solid red;}`  

(5)包含(后代)选择器  
即加入空格,用于选择指定标签元素下的后辈元素  

`.first  span{color:red;}`  

子选择器（child selector）仅是指它的直接后代，  
或者你可以理解为作用于子元素的第一代后代。  
而后代选择器是作用于所有子后代元素  

(6)通用选择器  
匹配html中所有标签元素  
`* {color:red;}`  

(7)
