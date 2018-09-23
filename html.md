# html学习笔记
* 【基本结构】  
```
<html>   
    <head>...</head>       
    <body>...</body>        
</html>    
```

* 【注释】  
`<!--注释文字-->`  

* 【p标签】  
`<p>段落文本</p>`  

* 【h标签】  
`<h1>标题文本</h1>`  
(h1~h6)  

* 【强调语气】  
`<em>需要强调的文本</em>` （斜体）  
`<strong>需要强调的文本</strong>` （加粗）  

* 【<span>标签】  
为文字设置单独样式  
`<span>文本</span>`  
在head中加入:  
```
  <style>   
  span{    
      
  }    
  </style>  
  ```

7.【`<q>`标签，短文本引用】  
`<q>引用文本</q>` (效果：自动添加双引号）  

8.【`<blockquote>`标签】 长文本引用  
`<blockquote>引用文本</blockquote>` （引用文本左右两侧有缩进）  

9.【`<br>`或`<br />`标签】 分行显示文本  

10. 【`&nbsp;`】 空格  

11.【`<hr>`或`<hr />`标签】 添加水平横线  

12.【`<address>`添加地址】  
`<address>联系地址信息</address>` （斜体）  

13.【添加代码】  
`<code>代码语言</code>`  
`<pre>语言代码段</pre>`  

14. 【列表】  

  【ul 无序列表】 
  ```
<ul>  
  <li>信息</li>  
  <li>信息</li>  
   ......  
</ul>  
```

  【ol 有序列表】  
  ```
<ol>  
   <li>信息</li>  
   <li>信息</li>  
   ......  
</ol>  
```

16. 【表格】   

`<table>…</table>`：整个表格以`<table>`标记开始、`</table>`标记结束。  

`<tbody>…</tbody>`：如果不加`<thead>``<tbody>``<tfooter>` , table表格加载完后才显示。  
加上这些表格结构，tbody包含行的内容下载完优先显示，不必等待表格结束后在显示，  
同时如果表格很长，用tbody分段，可以一部分一部分地显示。  
（通俗理解 table 可以按结构一块块的显示，不在等整个表格加载完后显示。）  

`<tr>…</tr>`：表格的一行，所以有几对tr 表格就有几行。  

`<td>…</td>`：表格的一个单元格，一行中包含几对`<td>...</td>`，说明一行中就有几列。  

`<th>…</th>`：表格的头部的一个单元格，表格表头。  

表格中列的个数，取决于一行中数据单元格的个数。  

```
<table>
  <tbody>
    <tr>
      <th>班级</th>
      <th>学生数</th>
      <th>平均成绩</th>
    </tr>
    <tr>
      <td>一班</td>
      <td>30</td>
      <td>89</td>
    </tr>
    <tr>
      <td>二班</td>
      <td>35</td>
      <td>85</td>
    </tr>
        <td>三班</td>
        <td>32</td>
        <td>80</td>
    </tr>
  </tbody>
</table>

```
效果：  
<table>
  <tbody>
    <tr>
      <th>班级</th>
      <th>学生数</th>
      <th>平均成绩</th>
    </tr>
    <tr>
      <td>一班</td>
      <td>30</td>
      <td>89</td>
    </tr>
    <tr>
      <td>二班</td>
      <td>35</td>
      <td>85</td>
    </tr>
        <td>三班</td>
        <td>32</td>
        <td>80</td>
    </tr>
  </tbody>
</table>

【摘要】  
`<table summary="表格简介文本">` 浏览器中不显示  

【标题】  
```
<table>
    <caption>标题文本</caption>
    <tr>
        <td>…</td>
        <td>…</td>
        …
    </tr>
…
</table>
```

17.【`<a>`标签】  
`<a  href="目标网址"  title="鼠标滑过显示的文本">链接显示的文本</a>`  
新窗口中打开 target="_blank"  

18.【插入图片】  
`<img src="图片地址" alt="下载失败时的替换文本" title = "提示文本">`  

19.【表单】  
`<form   method="传送方式"   action="服务器文件">`  

`<form> `：`<form>`标签是成对出现的，以`<form>`开始，以`</form>`结束。  
action ：浏览者输入的数据被传送到的地方,比如一个PHP页面(save.php)。  
method ： 数据传送的方式（get/post）  

【文本/密码输入框】  
```
<form>
   <input type="text/password" name="名称" value="文本" />
</form>
```
  
```
<form>
  姓名：
  <input type="text" name="myName">
  <br/>
  密码：
  <input type="password" name="pass">
</form>
```

【文本域】  
`<textarea  rows="行数" cols="列数">文本</textarea>`  

```
<form  method="post" action="save.php">
        <label>联系我们</label>
        <textarea cols="50" rows="10" >在这里输入内容...</textarea>
</form>
```

【单选框/复选框】  
`<input   type="radio/checkbox"   value="值"    name="名称"   checked="checked"/>`

type:  
   当 type="radio" 时，控件为单选框  
   当 type="checkbox" 时，控件为复选框  
value：提交数据到服务器的值（后台程序PHP使用）  
name：为控件命名，以备后台程序 ASP、PHP 使用  
checked：当设置 checked="checked" 时，该选项被默认选中  
 *注意！同一组的单选按钮，name 取值一定要一致  

【下拉列表】  
```
<form action="save.php" method="post" >
    <label>爱好:</label>
    <select>
      <option value="看书">看书</option>
      <option value="旅游" selected="selected">旅游</option>
      <option value="运动">运动</option>
      <option value="购物">购物</option>
    </select>
</form>
```

selected="selected"：  
设置selected="selected"属性，则该选项就被默认选中。  

【下拉列表多选】  
`<select multiple="multiple">`  

【提交按钮】  
`<input   type="submit"   value="提交">`  

type：只有当type值设置为submit时，按钮才有提交作用  
value：按钮上显示的文字  

【重置按钮】  
`<input type="reset" value="重置">`  

【label标签】  
`<label for="控件id名称">控件</label>`  
点击文本时对应的控件被选中  
