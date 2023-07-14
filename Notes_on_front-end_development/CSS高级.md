# CSS高级

### 第一课、精灵图（整合图）

（1）作用：为了减少图片占的大小，我们会把图片切分成若干个小图片模块展示网页上，但是当我打开网站时，那么他的请求次数此时会变多，那么现在就需要用到精灵技术，所谓的这个技术只不过将若干个网页请求的内容合并成一个大图片，当我进行请求时，我只需要返回这张大图片即可，节省了客户端的请求次数，大大减少服务器的压力。

（2）使用：即通过移动background-position位置操作将图片到盒子里面即可

### 第二课、字体图标（iconmoon）

（1）产生：由于精灵图的图片都是固定的并且每一次修改都是比较麻烦的

注意点：**字体图标本质上修改的还是字体的大小**

（2）使用icon-moon图标

1、将下载文件解压并把font文件夹放到html同文件夹下

2、使用格式进行引用

注意：

1）**引入所有自定义图标的文件**

2）需要**link style.css文件**

3）标签上**输入类名【icon-xxx】**，不用占位，不用@font-face{}

（3）图标的追加

1）登录 [iconmoon](https://icomoon.io/) 选择 app 

2）将之前的json文件选中再添加新的图标

3）下载

### 第三课、CSS三角

1）原理：盒子每一边的边框都是梯形的，盒子大小为0时，梯形上底(边框内边)也为0，所以两边会合并成三角形。

2）使用：只需要设置宽高为0的div,在设置其边框中的三边为透明，一边有颜色即可

![image-20230417195203589](CSS%E9%AB%98%E7%BA%A7.assets/image-20230417195203589.png)

### 第四课、CSS用户界面样式

1、含义：更改用户操作的样式，以提升用户体验

2、用户界面样式：	

#### 1）更改用户鼠标样式

​	（1）格式： 标签 {cursor:样式}

​	（2）作用：设置或检索对象上移动鼠标采用何种形状
​	（3）属性值

![image-20230417195913044](CSS%E9%AB%98%E7%BA%A7.assets/image-20230417195913044.png)

#### 2）去除表单轮廓与防止文本域拖曳	

一、去除表单轮廓

（1）格式：表单标签{outline:none/0}

（2）作用：去除光标定位到表单时出现边框轮廓

二、防止文本域拖曳

（1）格式：文本域标签{resize:none}

（2）作用：去除文本域拖曳

####  3）元素垂直居中

（1）作用：常用于表单（行内）、图片、文字垂直居中，但**只能对行内元素和行内块元素有效**

（2）格式：选择器{vertical-align:值}

（3）值域：

![image-20230418154620130](CSS%E9%AB%98%E7%BA%A7.assets/image-20230418154620130.png)

扩展：顶线、中线、基线、底线

![image-20230418154838797](CSS%E9%AB%98%E7%BA%A7.assets/image-20230418154838797.png)

下面概念有图得出

底线是指上图中j多出来的那个地方

基线是指上图中所有的文字处于一个水平线上

中线是指上图中所有文字最中间的位置

顶线是指上图中所有文字最顶部的位置

其实就是调整图片中的样式和文字之间的垂直对齐

**注意：设置此属性必须将内容放在需要让文本和谁对其的参考那一方的盒子上才可以**，在图片进行设计的时候会发现图片底部留有空白缝隙，那是由于留给图片的文本的，那么去除图片底部的空隙，那么只需要设置vertical-align设置成除了基线对齐之外其他的对齐即可

### 第五课、文字溢出显示

#### 1）单行文字

（1）设置white-space设置不换行(默认是换行）

补充：

white-space:值 是否换行 

值==>normal 设置换行

值==>nowrap设置不换行

（2）设置溢出隐藏

（3）设置文字溢出格式设置省略 text-overflow:ellipsis

格式：

```css
white-space:noswap;
overflow:hidden;
text-overflow:ellipsis
```



#### 2）多行文字

只需设置溢出隐藏和文字溢出样式以及设置webkit内核里面的参数即可

格式：

```css
display:-webkit-box /*将盒子模型转化为弹性盒子模型*/
-webkit-line-clamp:设置数值/*设置第几行后面的文本忽略不显示*/
-webkit-box-orient:vertical/*设置webkit-box盒子里面的内容垂直居中*/
overflow:hidden;/*溢出隐藏*/
text-overflow：ellipsis/*设置文本溢出部分显示省略号*/
```

### 第六课、布局小技巧

#### 1)盒子之间边框重叠问题

技巧：设置已浮动元素的左外边距为-1

=>产生问题：当我使用鼠标经过让边框变红的时候会发现右边框线不见了

=>解决方法1：设置对应的格式上将所移动到需要改变的元素设置为相对定位

设置之前：

![image-20230421145149329](CSS%E9%AB%98%E7%BA%A7.assets/image-20230421145149329.png)

设置之后：

![image-20230421145033560](CSS%E9%AB%98%E7%BA%A7.assets/image-20230421145033560.png)



![image-20230421145218217](CSS%E9%AB%98%E7%BA%A7.assets/image-20230421145218217.png)

=>解决方法2：设置同一个标签相对定位，在设置他们的层级，利用层级控制他们之间的联系

![image-20230421145555768](CSS%E9%AB%98%E7%BA%A7.assets/image-20230421145555768.png)

#### 2)利用浮动特性做文字环绕

浮动特性：将某一个元素设置浮动，那么他所设置的浮动元素的盒子就会浮动压住标准流的盒子但是不会压住文字

![image-20230421152534855](CSS%E9%AB%98%E7%BA%A7.assets/image-20230421152534855.png)

#### 3)行内块巧妙应用

技巧：

**text-align使得行内元素或行块元素居中对齐**

**margin使得块元素居中对齐**
案例：页面翻转

#### 4)CSS三角强化

案例：京东特价清单

#### 5)伪元素选择器与伪类选择器

地址：

[CSS入门]: D:\Study_Files\Web_Front-end_Development\md_Note\CSS入门.md

#### 6)使用伪元素和双伪元素清除浮动

##### 伪元素清除浮动

```css
div::after{
    content:"";//伪元素必须写的属性
    display:block;//插入的元素必须是块级
    height:0;//设置伪元素不能看见
    clear:both;//清除浮动核心代码
    visiblity:hidden;//设置伪元素不可见
}
```

##### 设置双伪元素清除浮动

闭合空间清浮动

```css
div::after,div::before{
    content:"";//伪元素必须要有的属性
    display:table;//这是将伪元素全部显示在同一行上、
    //因为转换表格后，表格不指定宽高和边框也没有内容，是默认看不见的，所以不加那两句，但是本身是占用着的
}
div::after{
    clear:both;//清楚浮动
}
```

![image-20230430092905769](CSS%E9%AB%98%E7%BA%A7.assets/image-20230430092905769.png)

### 第七课、CSS初始化

1、原因：

1).照顾浏览器兼容性	

2).消除不同浏览器HTML呈现的不同（可以简单理解为**浏览器重新设置样式**）实际上就是设置浏览器中的标签的默认格式

注意：**每一个网页都必须要有css初始化才能保证网页兼容性**

2、分析京东网站CSS初始化

```css
//去除所有默认自带的样式
* {
    margin: 0;
    padding: 0
}
//取消em,i标签的默认斜体样式
em,
i {
    font-style: normal
}
//取消无序列表自带的小圆点
li {
    list-style: none
}

img {
    //照顾低版本浏览器图片添加链接后会有边框问题
    border: 0;
    //取消图片底部空隙
    vertical-align: middle
}
//设置默认按钮鼠标状态是小手
button {
    cursor: pointer
}
//设置a链接默认字体颜色取消超链接自带的下划线
a {
    color: #666;
    text-decoration: none
}

a:hover {
    color: #c81623
}
//设置按钮或者input属性的字体
//\5B8B\4F53代表的是宋体
button,
input {
    font-family: Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif
}

body {
    //css3中新增的属性为了防止文字放大出现锯齿（抗锯齿型）
    -webkit-font-smoothing: antialiased;
    //设置默认的背景颜色
    background-color: #fff;
    //设置默认字体大小是12px行高是18，并设置字体
    font: 12px/1.5 Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB, "\5B8B\4F53", sans-serif;
    color: #666
}

.hide,
.none {
    display: none
}
//清浮动
.clearfix:after {
    visibility: hidden;
    clear: both;
    display: block;
    content: ".";
    height: 0
}
//照顾低端浏览器，清除浮动
.clearfix {
    *zoom: 1
}
```

由于中文不能直接出现在css文件中，否则会出现乱码问题。所以我们在css文件中使用宋体等中文字体时，那么就可以用unicode编码来进行表示

常见中文字体unicode编码

![image-20230423090609912](CSS%E9%AB%98%E7%BA%A7.assets/image-20230423090609912.png)





# HTML5与CSS3增强部分

## HTML5新增影音播放

1、原因：由于我们之前所编写的页面大部分都是div+css模式来进行的，对于各个功能之间的划分比较不清晰。因此我们在HTML原有的基础上新增了一些标签，但是这些新增的标签对于低版本浏览器兼容性比较差，因此我们这些新增的属性主要应用在IE9以上的浏览器。

2、HTML5新增标签

#### （1）新增语义化标签

| 标签                        | 含义                            |
| --------------------------- | ------------------------------- |
| <header>头部标签</header>   | 代指头部区域内的div             |
| <nav>导航栏标签</nav>       | 代指导航栏内的div               |
| <article>内容标签</article> | 代指内容区域的div               |
| <section>区域标签</section> | 代指定义文档的某一块区域内的div |
| <aside>侧边栏标签</aside>   | 代指侧边栏区域内的div           |
| <footer>底部标签</footer>   | 代指底部区域内的div             |

上述所有的新标签本质上就是div，只不过划定每一块区域内的所要操作的功能是不一样的，本质上就是在细化每一个div区域内做的内容是不一样的

#### （2）新增音频/视频标签

| 标签                    | 含义         |
| ----------------------- | ------------ |
| <video>视频标签</video> | 代指视频标签 |
| <audio>音频标签</audio> | 代指音频标签 |

##### 1）视频标签的使用

1、作用：如果我们想要在页面中插入一些比较好看的视频，那么就可以用视频标签进行制作

2、视频格式兼容性支持（由此可以得出，我们一般情况下推荐使用mp4格式的视频文件）

![image-20230423094430428](CSS%E9%AB%98%E7%BA%A7.assets/image-20230423094430428.png)

3、格式

```html
<video src="视频播放地址" control=“control”></video>//control代表播放控件
```



```html
<video width="设置宽度" control="control">
<source src="视频播放地址" type="设置播放的类型">
    <--
        type=视频格式/视频类型
        例如：
        type=video/mp4
        type=video/ogg
        
</video>
    <--设置先后顺序的不同也会有所区别，他一般会先找设置前面的视频进行播放，发现播放不了再找后面 -->  
```

第一种格式（必须设置control属性才能播放）

<video src="../HTML_Native/03-CSS进阶/04/index/src/光亮.mp4" control="control"></video>

第二种格式（video标签只需要设置宽即可，并且在video标签设置control属性，在source标签设置播放地址和播放类型）

<video width="80%" control="control">
    <source src="../HTML_Native/03-CSS进阶/04/index/src/大鱼.mp4" type="video/mp4"/>
</video>

4、视频标签相关的属性

| 属性     | 含义                                                         |
| -------- | ------------------------------------------------------------ |
| autoplay | 自动播放需要加上(muted属性)                                  |
| muted    | 静音播放                                                     |
| control  | 添加播放控件                                                 |
| loop     | 循环播放                                                     |
| width    | 设置宽度                                                     |
| height   | 设置高度                                                     |
| poster   | 等待加载图片                                                 |
| preload  | 预先加载视频<br>（auto 预先加载 none不预先加载）<br>自动播放就不需要设置此属性 |

##### 2）音频标签的使用

1、支持音频播放格式

![image-20230423115641588](CSS%E9%AB%98%E7%BA%A7.assets/image-20230423115641588.png)

2、音频标签相关的属性

| 属性     | 含义         |
| -------- | ------------ |
| autoplay | 自动播放     |
| control  | 添加播放控件 |
| loop     | 循环播放     |

google浏览器考虑到用户体验感，把音频和视频里面的自动播放取消掉了

3、格式：

```html
<audio src="音频播放文件路径" autoplay control loop></audio>
```



<audio src="../HTML_Native/03-CSS进阶/04/index/src/周深-人是_.mp3" outline="none"></audio>

## HTML5新增表单内容

（1）类型：

![image-20230423124836962](CSS%E9%AB%98%E7%BA%A7.assets/image-20230423124836962.png)

（2）作用：限制用户输入数据格式

（3）属性（新增）

![image-20230424140350261](CSS%E9%AB%98%E7%BA%A7.assets/image-20230424140350261.png)

input::placeholder 修改输入框内显示的文字格式

（4）浏览器私有前缀

1) 作用：兼容老版本浏览器，较新的版本浏览器无需添加

2)主流浏览器私有前缀格式：

-moz-:代表firefox浏览器私有属性

-ms-：代表IE浏览器私有属性

-webkit-:代表safari、chrome私有属性

-o-：代表opera私有属性

3)使用写法

浏览器私有前缀+CSS

例如：

firefox浏览器设置边框 -moz-border-radio



## CSS3新特性

### CSS3盒子模型

1）作用：我们可以通过box-sizing指定盒子模型，来解决之前加上内边距或边框导致盒子宽高变大问题

2）参数值

box-sizing:content-box(盒子大小+内边距+边框)

注意：需要计算以上操作之后重新设置盒子大小

box-sizing:border-box（盒子大小）

注意：box-sizing:border-box之后无论你加了边框或内边距盒子还是**保持原来的大小**，他是不会撑开盒子，**除非你所操作的这个属性超出了他的宽度或高度，他才会变大，但是他的兼容性比较差**

### CSS3其他特性

#### 1、CSS3滤镜Filter

1)格式：filter:	函数()

具体函数见

[filter函数]: https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter#%E5%87%BD%E6%95%B0

2)作用：本次介绍blur函数，主要用于处理图像模糊

3)blur函数格式：filter: blur(数值（单位px）) 

4)提示：

(1)、其数值越大，那么呈现的效果就越模糊

(2)、 img {}里添加 transition：0.5s，就是模糊到不模糊的时间就是过渡。

#### 2、CSS3计算属性

1)作用：可以在CSS样式中做出一些计算并不是编写固定的内容

2)格式：属性:calc( 计算表达式 ) 

注意：表达式与数值之间要有空格进行分割

### CSS3过渡

1)、含义：CSS3中具有颠覆性的特征之一，在不使用flash或者js的情况下从一种状态变成另一种状态

2)、优缺点：

优点：使页面效果更好看

缺点：不能向低版本浏览器兼容

3)、使用：经常搭配:hover一起使用

4)、格式和参数分析：transaction：过渡属性	花费时间	过渡的路线	什么时候开始

属性：指定内容发生哪一些变化

花费时间：单位是s(秒),指定内容从一个状态变成另一个状态（必须指定单位）

运动曲线：默认是EASE(可忽略)

![image-20230505142455646](CSS%E9%AB%98%E7%BA%A7.assets/image-20230505142455646.png)

何时开始：单位是s(秒),可以设置延迟触发效果，默认为0s

5)、注意事项：

**1、过渡效果加在哪里？谁做过渡就给那一个属性进行添加**

**2、如果要添加多个效果只需要在效果之间添加一个逗号进行分割即可**

另外一种多属性的过渡写法（是给属性都发生变化的情况下使用）

transaction:all 1s ease 0.5s

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="../HTML_Native/03-CSS进阶/04/小米图标变化/css/css.css">
    <link rel="stylesheet" href="../HTML_Native/03-CSS进阶/04/小米图标变化/icon/style.css">
</head>

<body>
    <div class="box">
        <div class="div_box">
            <div class="icon-xiaomi icon1"></div>
            <div class="icon-home icon2"></div>
            <!-- <img src="./img/logo2.jpg" alt="" class="img1">
            <img src="./img/logo1.jpg" alt="" class="img2"> -->
        </div>
    </div>

</body>

</html>
```

## 综合案例、品优购网站

一、原型图

在此操作之前需要跟客户进行沟通，客户沟通后并确定下来了，开始设计原型图。

所谓原型图就是在不插入图片的情况下构造出网页最原始的样子与客户确定布局，并制作成效果图

网站的基本步骤（附图）

![image-20230505191019028](CSS%E9%AB%98%E7%BA%A7.assets/image-20230505191019028.png)

二、品优购网站设计

（1）项目名称：品优购电商平台网站

（2）项目描述：品优购是电商网站，我们要完成pc端和移动端的页面制作

（3）学习原因：此网站包含了大量布局以及常见的技术，并且巩固所学的内容，并且对pc网站制作有着清晰的认识

（4）模块化开发：所谓模块化开发即是每一个项目进行单独的开发，每一个模块之间互不影响，并且具有维护性高的说法

（5）favicon图标制作

1、使用ps切图切好图标之后，将其图标保存

2、访问网址转化成ico文件，并保存到网站根目录

[比特虫]: https://www.bitbug.net/

3、使用以下代码进行应用即可

```html
<link rel="shortcut icon" href=" /favicon.ico" />
```

（6）SEO(搜索引擎优化)：我们可以设置网站的属性，使得提升搜索引擎排名，提高网站访问量，主要设置title、describe、keyword，使得这三个内容满足SEO里面的需求

title 网站标题具有不可替代性，并且是网站的重要标签，也是搜索引擎判断是否满足其关键字的重要标签

格式：网站名+网站描述

describe地方添加内容，具体内容由产品经理确定，格式

```html
<meta name="description" content="品优购致力于构造性价比，品质优的购物，给你带来家的感觉">
```

设置其关键字，建议不超过3个，最多不超过5个

参考案例网址：[品优购电商网站](https://submask.github.io/PinYouGou)

# CSS转换 transform

## CSS转换基础知识

（1）含义：css3中具有颠覆性的特征之一，可实现位移（translate）、旋转(rotate)、缩放(scale)等效果

（2）直角坐标系：

![image-20230513141153677](CSS%E9%AB%98%E7%BA%A7.assets/image-20230513141153677.png)

### 2D转换

#### （1）位移（translate）

1)作用：改变自身的位置

2)格式:

(1)一起设置x轴和y轴：

transform:translate(x轴,y轴)

transform:translateX(数值)	translateY(数值)

(2)单独设置

transform:translateX(数值)

transform:translateY(数值)

3)注意事项

1、定义2D移动它是沿着X轴和Y轴进行移动

2、优点：移动位置时不会影响到其他的元素

3、translate中百分比相对的是自身的元素的宽高的长度进行位移

4、对行内元素没有效果

5、设置盒子水平垂直 

#### （2）旋转(rotate)

1)作用：在二维平面内设置顺时针旋转或逆时针旋转

2)格式:translate:rotate(度数)

3)注意事项

1、旋转的单位是deg(度),这个内容是必须要写的

2、度数如果是正数那么就是顺时针旋转而负数是逆时针旋转

3、默认旋转的中心是元素的中心

案例：下拉框小三角制作

产生问题：中心点问题

4)设置旋转的中心点

格式：translate-origin:x y

注意：

(1)设置中心点之间的x轴和y轴中间是用空格隔开的

(2)xy默认的转换的位置是50% 50%（即宽高的一半）

(3)其设置内容可以是像素也可以是方位名词

#### （3）缩放(scale)

1)作用：对元素进行放大或者是缩小

2)语法：transform：scale(x,y)

3)注意事项：

(1)x和y中间是用逗号进行分隔

(2)

transform:scale(1,1)代表原比例不做任何缩放

transform:scale(2,2)代表放大原比例的2倍 =>transform:scale(2)

transform:scale(0.5,0.5)代表缩小原来的0.5倍

那么可以得出放大几倍是以1作为原点进行累增的，而缩小几倍是以1作为原点进行累减，并且**数值不跟单位**，如果是等比例缩放那么数值只需写一个内容即可。

(3)**如果scale的数值为负数那么他就会转化成此数值的绝对值再进行放大或缩小**

4)scale属性和单独设置宽高的区别

1、单独设置宽高他不是以自身中心向两边延展而是通过原本宽高的长度再进行扩展，而scale是以中心点向两边进行扩展延伸

2、scale进行缩放不会影响下面的元素而改变宽高会影响到下面的元素

3、scale也可以设置中心点，那么其所在的缩放就以当前中心点的位置向反方向进行缩放

###	2D转换综合写法

1）写法：transform:translate（平移） rotate（旋转）

2）注意事项：一旦他们之间的顺序发生变化那么就会影响到转换的效果，如果有位移那么请先写位移再写后面的属性

### 3D转换

#### （1）相关理论性知识

1、区别：2D的图形是一个平面图形而3D的图形是一个立体图形

2、特点：远大进小，物体遮挡不可见

3、三维坐标系

图例：

![image-20230608090415568](CSS%E9%AB%98%E7%BA%A7.assets/image-20230608090415568.png)

x轴：水平向右 （**右边是正的**，左边是负的）

y轴：垂直向下（**下边是正的**，上边是负的）

z轴：垂直于屏幕（**前边是正的**，后边是负的）

#### （2）位移（Translate3D）

1、概念：即在原有2D的基础之上在添加了Z轴进行移动

2、格式：

translate3DX(像素/百分比) 只是调整X轴

translate3DY(像素/百分比) 只是调整Y轴

translate3DZ(像素) 只是调整Z轴

translate3D(x轴,y轴,z轴)

(1)一起设置x轴和y轴：

transform:translate3d(x轴,y轴,z轴)

transform:translateX(数值)	translateY(数值) 	translateZ(像素)

(2)单独设置

transform:translateX(数值)

transform:translateY(数值)

transform:translateZ(像素)

**注意：translateZ设置Z轴的像素必须还要设置他的透视效果**

#### （3）透视（perspective）

1、概念：即人眼到屏幕的距离，也就是视距

![image-20230608092722711](CSS%E9%AB%98%E7%BA%A7.assets/image-20230608092722711.png)

2、特点：近大远小

3、注意点：

1、透视的单位是像素

2、使用透视时必须要把元素中所要设置透视加在父盒子身上

3、规律：

translateZ轴的值是固定：设置透视的值越大视距越大物体也变小，反之设置透视的值越小视距越小物体变大

视距固定：设置translateZ轴的值越大，那么物体也会变大，反之物体就会变小

注意点：当视距固定的情况下，一旦设置的z值大于人眼到屏幕之间的距离，那么就会消失不见

#### （4） 旋转（rotate3D）

1、概念：可以使元素沿着x轴、y轴、z轴进行旋转，甚至可以自定义旋转

2、格式：

transformrotateX(数值)

transform:rotateY(数值)

transform:rotateZ(像素)

transform:rotate3d(x,y,z,deg)自定义旋转

3、参数介绍

transform：rotateX(数值) 设置物体随着x轴而转动

transform：rotateY(数值) 设置物体随着y轴而转动

transform：rotateZ(数值) 设置物体随着z轴而转动（类似于2D旋转）

transform：rotate3d(x,y,z,deg) 自定义设置旋转（**x,y,z的值为1即为旋转，否则为0则是不旋转**）

**注意：translate:transform(x,y,z)固定的情况下，改变透视的距离，透视越大，物体越小，透视越小,物体越大，通过观察的方向可以得出左手法则：向里面的是正方形反之是反方向，并且大拇指的朝向必须跟着坐标轴中的箭头方向，在自定义设置旋转中，如果同时设置了x轴与y轴，那么就会以矢量方向进行旋转**

#### （5）3D呈现（translate-style）

1、作用：我们本身将盒子转换为3D之后但在进行错位展示时会变成2D的图像，为了保持子元素和父元素的展示一样那么就通过这个属性将它变成3D立体空间

2、translate-style：present-3d（保持3D的效果）

注意：虽然这个属性写在父盒子身上但是他作用于子盒子

# css动画

1）作用：css3中颠覆性的特征可以通过多节点控制一个或一组动画，用来实现复杂效果

2）动画基本使用

1、使用keyframes定义动画

2、再调用动画

2）格式：

(1)定义动画

```css
@keyframes 动画名 {
    0%{
        
    }
    100%{
        
    }
}
```

(2)使用动画

```css
标签{
    animation-name:"动画名称"，
    animation-duration：“持续时间”
}
```

3)动画序列

(1)含义：0%代表动画的开始，而100%代表动画结束

(2)使用：所编写的样式必须写在keyframes里面

(3)注意事项：

@keyframes（关键帧动画）中的0% 100%代表这个范围内发生的变化也可以使用from to进行替代

如果想要有多个状态可以将动画序列划分成多个部分，它是将我们动画整个的时间进行划分

3）动画属性

![image-20230514115053625](CSS%E9%AB%98%E7%BA%A7.assets/image-20230514115053625.png)

*常用属性：

| 属性                      | 含义                                                     |
| ------------------------- | -------------------------------------------------------- |
| @keyframes                | 规定动画                                                 |
| animation                 | 所有动画的简写属性                                       |
| animation-name            | 规定动画的名称（必须写）                                 |
| animation-duration        | 规定动画所完成的时间（必须写的）                         |
| animation-iteration-count | 规定动画重复次数（infinite 无限次）                      |
| animation-direction       | 规定动画是否反方向进行移动(alternate 相反方向)           |
| animation-fill-mode       | 规定动画完成后是否回到初始位置（forward 停留在结束状态） |
| animation-play-state      | 规定动画是否继续 pause(暂停) play继续                    |

animation 简写：

格式：animation: name duration timing-function delay iteration-count direction fill-mode;

注：如果没有延迟时间不要在简写中直接写上0s而是不写延迟时间，如果写了0s那么他整个动画将不可用

案例：大数据热点图

易错点：直接使用scale进行缩放，会导致设置中的阴影也一起跟着缩放

代码：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>热点图</title>
    <style>
        body {
            background-color: #414341;
        }
        
        .map {
            position: relative;
            width: 747px;
            height: 617px;
            background-image: url(./img/map.png);
            background-repeat: no-repeat;
            margin: 0 auto;
            background-color: #414341;
        }
        
        .bj {
            position: absolute;
            right: 178px;
            top: 225px;
        }
        
        .gz {
            position: absolute;
            right: 198px;
            bottom: 83px;
        }
        
        .tb {
            position: absolute;
            right: 75px;
            bottom: 127px;
        }
        
        .dotted {
            width: 8px;
            height: 8px;
            background-color: skyblue;
            border-radius: 50%;
        }
        
        .bj>div[class^="pulse"],
        .gz>div[class^="pulse"],
        .tb>div[class^="pulse"] {
            width: 8px;
            height: 8px;
            position: absolute;
            box-shadow: 0 0 10px 0 skyblue;
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation-name: point;
            animation-duration: 1s;
            animation-iteration-count: infinite;
            /* animation: name duration timing-function delay iteration-count direction fill-mode; */
        }
        
        .pulse2 {
            animation-delay: 0.4s;
        }
        
        .pulse3 {
            animation-delay: 0.8s;
        }
        
        @keyframes point {
            50% {
                width: 40px;
                height: 40px;
                opacity: 1;
            }
            100% {
                width: 60px;
                height: 60px;
                opacity: 0;
            }
        }
    </style>
</head>

<body>
    <div class="map">
        <div class="bj">
            <div class="dotted"></div>
            <div class="pulse1"></div>
            <div class="pulse2"></div>
            <div class="pulse3"></div>
        </div>
        <div class="gz">
            <div class="dotted"></div>
            <div class="pulse1"></div>
            <div class="pulse2"></div>
            <div class="pulse3"></div>
        </div>
        <div class="tb">
            <div class="dotted"></div>
            <div class="pulse1"></div>
            <div class="pulse2"></div>
            <div class="pulse3"></div>
        </div>
    </div>
</body>

</html>
```

补充：

1、opacity 作用设置某一个元素的透明度

2、如果更换坐标是使用视频里面的方法不能使用bottom，因为不能将之前的样式层叠掉

速度曲线细节

animation-timing-function：规定动画的速度曲线，默认是ease

参数：

![image-20230514193705141](CSS%E9%AB%98%E7%BA%A7.assets/image-20230514193705141.png)

steps 代表步长意思是使用几步来完成动画
