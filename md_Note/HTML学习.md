# HTML学习

### 第一课、HTML介绍

（1）含义：HTML是一个**超文本标记语言**

（2）center标签：文本居中

（3）浏览器标签兼容性查询

[*]: https://caniuse.com/	"网页标签兼容性"

### 第二课、网页的结构

（1）组成：HTML结构、CSS外观、Js行为

### 第三课、第一个网页设计

（1）基本格式

```
<html>
	<head>
		<title></title>
	</head>
	<body>
	</body>
</html>
```

兄弟标签：位于同一个级别层次的标签

父子标签(后代标签)：后一个节点是当前节点的子节点

（2）语法规范

双标记（常规）标签：要有头有尾的标签<none><none/>

单标签（空标记）标签：只有头没尾标签<none />

（3）br 标签：换行标签 <br />

### 第四课、文档声明与字符编码

文档声明标签： <!DOCTYPE html>

字符编码标签：<meta charset="编码格式">

本质上浏览器不会根据我所写的网页编码格式进行编码而是根据编写工具所指定的内容进行编码，<meta 中的chatset属性>主要用来解码的

### 第五课、HTML基本标签

1、标题标签 <h1~6></h1~6>

![image-20230313164650409](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230313164650409.png)

**特点**：1、文字加粗 2、独占用一行（可以使用display进行修改）3、标题标签只能在网页出现一次

2、段落标签：<p>这是一个段落</p>

特点：1、结构分明 2、p标签之间有一定的间距

3、水平标签：<hr />

修改其中的颜色 <hr color="">

修改标签的宽度<hr width="数值（单位px或%）">

修改标签对齐<hr align=''>

去除水平标签的阴影：<hr noshade />

### 第六课、特殊符号与注释标签

1、显示尖角符号:&lt/;&gt/;

2、空格符号：&nbsp/(系统字符集的约束);&emsp/(占用大小~=一个中文大小);

3、设置表情符号：&#数值/;

4、设置注释标签:<!---->或者按ctrl+/



### 第七课、容器标签

#### 一、div标签

含义：没有具体含义，但可以用于划分网页中的区域

特点：独占一行（方便区域划分）----->块元素

#### 二、span标签

含义：没有具体意义，可以对文本进行修饰

特点：不可单独控制宽度和高度，可以独立控制标签，不会独占一行

------>行标签

### 第八课、列表标签

一、有序标签

格式：

```html
<ol>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
</ol>
<--
type:"设置序号的类型"
start:"设置序号的开始值(数值)"
->
```

显示效果

<ol type='A' start=3>
 <li>这是一个标签li1</li> 
 <li>这是一个标签li2</li>
    <li>这是一个标签li3</li>
    <li>这是一个标签li4</li>
</ol>


二、无序标签

格式：

```html
<ul>
	<li>1</li>
	<li>2</li>
	<li>3</li>
	<li>4</li>
	<li>5</li>
</ul>
```

显示效果

<ul style='list-style:""'>
    <li>这是一个标签li1</li>
    <li>这是一个标签li2</li>
    <li>这是一个标签li3</li>
    <li>这是一个标签li4</li>
</ul>

三、自定义标签

格式：

```
<dl>
	<dt>文字/图片</dt>
	<dd>文字</dd>
</dl>
```

显示效果：

<dl>
    <dt style='text-align:center'>
      <img src='https://ns-strategy.cdn.bcebos.com/ns-strategy/upload/fc_big_pic/part-00746-1667.jpg' alt="图片文字" width='30%' />
    </dt>
    <dd style='text-align:center'>这是一个小内容</dd>
</dl>
### 第九课、图片标签

1、参数含义

```html
<img src="图片路径" alt="图片标签(网页不能加载时显示)" title="移动到图片所显示信息" width="宽度" height="高度">	
```

2、相对路径与绝对路径

相对路径：从当前目录出发，访问文件夹或文件

表达式：

| 路径                       | 表达形式               |
| -------------------------- | ---------------------- |
| 当前目录下的文件           | img(src="./图片")      |
| 不在同一级目录，其父级相同 | img(src="../xxx/图片") |
| 根目录文件下图片           | img(src="/图片")       |

例如结构如下

![image-20230317110658988](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317110658988.png)

那么他访问的路径就是 ./code.gif

绝对路径：显示的是文件的完整的路径

### 第十课、超链接标签

1、效果：实现不同链接之间的跳转

2、参数含义

```html
<a href="超链接路径" title="移动鼠标到此处的提示信息" target="在哪里打开文档内容（默认是_self）">内容</a> 
```

<a href="https://www.qq.com" title="这是一个内容" target="_blank">超链接</a>

| 参数   | 参数表达式             | 参数内容                                                   |
| ------ | ---------------------- | ---------------------------------------------------------- |
| href   | 指定跳转的路径         | href="任意链接"                                            |
| title  | 鼠标移动到此链接的信息 | title="文字"                                               |
| target | 规定哪里打开新的标签   | target="_blank"(代表在新标签中打开链接内容) 默认值是 _self |

3、链接分类

1、外部/下载链接：直接在href中输入网址/下载链接信息

2、内部链接：直接在href中输入页面对应的名称（位置+名称）

3、空链接：没有确定链接的时候，直接在href输入#

4、页面内容跳转链接：跳转页面某一个内容

（1）a链接的href属性中设置跳转到的内容的css样式名称

（2）设置对应位置的样式，必须是id选择器(id具有选择性)

### 第十一课、表格标签

一、基本知识

1、效果：显示数据

2、学生成绩显示例题

显示结果

![image-20230317120219597](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317120219597.png)

3、表格的创建

关系:<table> ==>多个<tr> ==>多个<td>

快速创建2行2列的表格：

![image-20230317121247930](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317121247930.png)



二、<table/>标签

| 表格属性        | 表格属性对应的含义     |                             效果                             |
| --------------- | ---------------------- | :----------------------------------------------------------: |
| boder属性       | 设置表格的外边框       | ![image-20230317122017786](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317122017786.png) |
| width属性       | 设置**表格宽度**       | ![image-20230317122411662](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317122411662.png) |
| height属性      | 设置表格高度           | ![image-20230317122411662](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317122411662.png) |
| align属性       | 对齐属性               |          align="left"(靠左)align="center"(居中)...           |
| borderColor属性 | 设置边框颜色           |                      borderColor="颜色"                      |
| bgcolor属性     | 设置背景颜色           |                        bgcolor="颜色"                        |
| cellspacing     | 单元格之间间距         | cellspacing=”间距“![image-20230317141049846](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317141049846.png) |
| cell padding    | 单元格与内容之间的间距 | cellpadding="间距"![image-20230317141915759](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317141915759.png) |

注意点：

1、设置表格宽度百分比是以父元素作为参考，进行平铺。但是**设置高度百分比的时候一定要外嵌一个标签设置具体高度**才行。这是由于**body标签的高度所导致的问题**，因为我们默认不嵌套一个标签的话那么他所做的高度即是表格撑开的高度（图11-1）

![image-20230317123537513](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317123537513.png)

​																								图11-1



三、<tr><td> 标签

| 表格属性  |     表格含义     |                             效果                             |
| :-------: | :--------------: | :----------------------------------------------------------: |
| width(td) |  设置单元格宽度  | ![image-20230317143425691](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317143425691.png) |
|  height   | 设置表格行的高度 | ![image-20230317142518796](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317142518796.png) |
|  bgcolor  |     背景颜色     | ![image-20230317142655109](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317142655109.png) |
|   align   |     水平居中     | ![image-20230317143030964](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317143030964.png) |
|  valign   |     垂直居中     | ![image-20230317143102460](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317143102460.png) |

注：tr与td属性区别

1、td有宽度(width)而tr没有宽度(width)

2、td是设置单元格的样式，而tr是设置表格行的样式

四、表格合并

| 表格属性 | 表格含义                           |
| -------- | ---------------------------------- |
| colspan  | 合并单元格(列合并)=>同行不同列合并 |
| rowspan  | 合并单元格(行合并)=>同列不同行合并 |

最终效果示意图

![image-20230317145725263](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317145725263.png)

补充：

<thead></thead>标签主要是存放表格头部信息

<tbody></tbody>标签主要存放表格内容信息

<tfooter></tfooter>标签主要存放表格尾部信息

以上三个标签有助于我们进行css表格代码编写的时候结构更加清晰

### 第十二课、表单标签

1、作用：收集用户信息

表单控件学习（input）属性：默认不写是text属性

| 属性                                | 类型     |
| ----------------------------------- | -------- |
| <input type="text"></input>         | 文本框   |
| <input type="password"></input>     | 密码框   |
| <input type="submit" value></input> | 提交按钮 |

2、组成：表单域、表单控件、提示信息

3、表单的组成

#### 一、表单域

1、作用：将表单的范围内的数据提交给服务器

2、标签：form标签

3、格式：<form action="提交服务器地址" method="提交方式(get/post)" name="区分不同的表单域"></form>

#### 二、input类型设置

1、input标签作用：输入内容信息提交数据（收集用户信息）

2、input类型设置：

![image-20230319110615554](HTML%E5%85%A5%E9%97%A8.assets/image-20230319110615554.png)

3、input其他属性设置

![image-20230319112648066](HTML%E5%85%A5%E9%97%A8.assets/image-20230319112648066.png)

**注意：**

**1、多选单选框的name属性必须设置同一个内容，其中name与value是提交给后台管理人员使用的数据**

2、**checked属性是设置默认选中的内容格式：checked=checked**

3、maxlength属性是限制字符输入长度。

4、**指定地址提交信息:action属性**，**设置提交信息方式（method）：get/post**默认是get请求

##### 1、文本框与密码框

（1）文本框设置

1、设置文本框类型：text

2、设置文本框提示信息(输入后提示信息消失)：placeholder

3、设置name属性：提交给后台数据所需要使用的属性

（2）密码框设置

1、设置密码框类型：password

2、其余内容与文 本框一致

##### 2、单选框与复选框

（1）单选框设置

1、设置单选框类型:radio

2、特点：只能选择一个

3、其余内容设置与文本框一致

（2）复选框

1、设置多选框类型：checkbox

2、特点：可以多选

##### 3、提交与重置按钮

（1）提交按钮设置

1、设置提交按钮类型:submit

2、格式：

<input type="submit" value="提交按钮"></input>

<button type="submit" >提交按钮</button>

3、特点：将当前页面所填写的数据通过form的action属性提交到后台

4、设置显示内容：value

（2）重置按钮设置

1、设置提交按钮类型：reset

2、设置显示内容：value属性

3、作用：清除已填写表单信息

**注意：get与post都是表单提交，但是get提交会将我们所提交的内容显示在地址栏里面，而post不会显示**

#### 三、按钮与文件域标签

（1）普通按钮标签

1、设置普通按钮：<button >这是一个普通文本按钮</button>

2、特点：本身不可以做其他事情，必须搭配js进行操作

3、其标签：button

（2）文件域标签

1、设置文件域标签：<input type="file">上传照片</input>

2、特点：将电脑里面的文件通过此控件上传到后端，需搭配js使用

3、其标签：input type="file"

#### 四、label标签

1、作用：label绑定对应的表单元素，当点击label内的文字，浏览器就会自动对焦到对应的表单元素上，增加用户体验感

2、格式：

<label for="绑定的input标签里面的id值">男</label>

<input type="radio" name="sex" id="sex">男</input>

#### 五、下拉表单

1、作用：提供给用户多种内容选择

2、默认选中：selected="selected"（**写在option属性内**）

3、必备要求：select下必须包含一对option

4、格式

```html
<select >
    <option>请选择班级</option>
    <option>大数据1班</option>
    <option>大数据2班</option>
    <option selected="selected">大数据3班</option>
    <option>人工智能1班</option>
    <option>软件工程1班</option>
    <option>软件工程2班</option>
</select>
```

样例：

<select >
    <option>请选择班级</option>
    <option>大数据1班</option>
    <option>大数据2班</option>
    <option selected="selected">大数据3班</option>
    <option>人工智能1班</option>
    <option>软件工程1班</option>
    <option>软件工程2班</option>
</select>

#### 六、文本域

1、作用：输入大量的文字等功能

2、设置文本域的大小（通常用css样式设置）

使用cols设置每行显示多少字

使用rows设置要显示几行

**其中cols和rows可以通过css样式进行设置，无需记住这些熟悉**

3、格式

```html
<textarea rows="10" cols="100">
这是默认显示内容//设置默认的文本    
</textarea>
```

样例：

<textarea rows="5" cols="20">
这是默认显示内容    
</textarea>

#### 七、案例

（1）案例：模拟表单提交

![image-20230317163214699](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230317163214699.png)

案例链接：

[1]: D:\Study_Files\Web_Front-end_Development\HTML_Native\01-HTML入门\08-表单的使用.html

（2）案例：注册页面



