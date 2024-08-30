# 1.0基础选择器

## 1.1标签选择器

> 直接用 HTML 标签名作为选择器，按标签名称分类，**为页面某一类标签指定统一的 CSS 样式。**

<font color=red size=4>语法</font>

```css
标签名 {
    属性1： 属性值1;
    属性2： 属性值2;
    属性3： 属性值3;
}类选择器
```

## 1.2类选择器

```css
.类名 { 
属性1: 属性值1;   
... 
}
//将所有拥有 red 类的 HTML 元素均为红色。
.red { 
color: red; 
}
<div class=‘red’> 变红色 </div>
```

## 1.3 id 选择器

```css
#id名 {
    属性1: 属性值1;
    ...
}
//将 id 为 nav 元素中的内容设置为红色。
#nav { 
color:red; 
} 

```

## 1.4通配符选择器

> 选取页面中所有元素

```css
* {
    属性1: 属性值1;
    ...
}
```



```HTML
* {
    margin: 0;
    padding: 0;
}
```

## 1.5基础选择器总结

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291247709.png)

## 1.6后代选择器

```css
元素1 元素2 { 

}
/*  选择 ul 里面所有的 li标签元素  */
ul li { 

}   
```

## 1.7子选择器

```css
元素1 > 元素2 { 样式声明 }
//选择 div 里面所有最近一级 p 标签元素
div > p { 样式声明 }   
```

## 1.8并集选择器

```css
元素1,元素2 { 样式声明 }   
//选择 ul 和  div标签元素
ul,div { 样式声明 } 
```

## 1.9伪类选择器

## 1.9.1链接伪类选择器

```css
/* a 是标签选择器  所有的链接 */  
a {        
	color: gray; 
} 
/* :hover 是链接伪类选择器 鼠标经过 */ 
a:hover {    
    color: red;  /* 鼠标经过的时候，由原来的灰色字体变成了红色 */
    background-color: green;/*鼠标经过的时候背景变绿色*/
}  
```

### 1.9.2 :focus 伪类选择器

> :focus 伪类选择器用于选取获得焦点的表单元素。  焦点就是光标，一般情况  类表单元素才能获取，因此这个选择器也主要针对于表单元素来说。

```css
input:focus {  
	background-color:yellow; 
}  
```

## 1.9.3链接伪类选择器

> **注意事项**
>
> 确保样式生效，要按照 LVHA 的顺序声明：link,visited,hover, active。
>
> a 链接在浏览器中有默认样式，所以实际开发都需要给链接单独指定样式。

```css
a:link /*选择所有未被访问的链接*/
a:visited /*选择所有已被访问的链接*/
a:hover /*选择鼠标指针位于其上的链接*/
a:active /*选择活动链接（鼠标按下未弹起的链接）*/
```

```css
/***开发中实际写法***/
a {
  color: gray;
  text-decoration: none;
}
a:hover {
  color: #369;
  text-decoration: underline;
}
```

## 1.10 其他标准伪类选择器

### 1.10.1first-child

> :first-child  是 CSS 伪类，表示父元素的第一个子元素。

### 1.10.2last-child

> :last-child  CSS 伪类 代表父元素的最后一个子元素。

### 10.3nth-child(n)

> :nth-child(an+b)  这个 CSS 伪类首先找到所有当前元素的兄弟元素，然后按照位置先后顺序从 1 开始排序，选择的结果为 CSS 伪类  :nth-child 括号中表达式  (an+b)  匹配到的元素集合  (n=0，1，2，3...) 

### 1.10.4:not(p)

> :not()  用来匹配不符合一组选择器的元素。由于它的作用是防止特定的元素被选中，它也被称为反选伪类（negation pseudo-class）。

##  1.10.5::after (:after)

CSS 伪元素  ::after  用来创建一个伪元素，作为已选中元素的最后一个子元素。通常会配合  content  属性来为该元素添加装饰内容。这个虚拟元素默认是行内元素。

```css
.exciting-text::after {
  content: "<- 让人兴兴兴奋!";
  color: green;
}
```

## 1.10.6::before (:before)

> CSS 中， ::before  创建一个伪元素，其将成为匹配选中的元素的第一个子元素。常通过  content  属性来为一个元素添加修饰性的内容。此元素默认为行内元素。
> 使用  ::before  伪元素的一个简单示例就是用于加入引号。

```css
q::before {
  content: "«";
  color: blue;
}
q::after {
  content: "»";
  color: red;
}
<q>一些引用</q>, 他说, <q>比没有好。</q>.
```

### 2.5 复合选择器总结

| 选择器         | 作用                   | 特征             | 使用情况 | 隔开符号及用法            |
| -------------- | ---------------------- | ---------------- | -------- | ------------------------- |
| 后代选择器     | 用来选择后代元素       | 可以是子孙后代   | 较多     | 符号是空格  .nav a        |
| 子代选择器     | 选择最近一级元素       | 只能选亲儿子     | 较少     | 符号是大于  .nav>p        |
| 并集选择器     | 选择某些相同样式的元素 | 可以用于集体声明 | 较多     | 符号是逗号， .nav, a      |
| 链接伪类选择器 | 选择不同状态的链接     | 跟链接相关       | 较多     | 重点记住 a{} 和 a:hover{} |
| :focus 选择器  | 选择获得光标的表单     | 跟表单相关       | 较少     | 记住 input:focus 用法     |

# 2.0CSS 字体

## 2.1 字体系列

>  font-family 属性定义文本字体系列。

```css
body {
  font-family: "微软雅黑", Arial, Helvetica, sans-serif;
}
```

## 2.2 字体大小

>  font-size 属性定义字体大小。
>
>  谷歌浏览器默认是 16px

```css
body {
  font-size: 16px;
}
```

## 2.3 字体粗细

> font-weight 属性设置字体粗细
>
> 实际开发中，更常用数字来表示加粗或变细。 400 为 normal ， 700  为  bold 。

```css
p {
  font-weight: 700;
}
```

| 属性值  | 描述                                       |
| ------- | ------------------------------------------ |
| normal  | 默认值                                     |
| bold    | 定义粗体                                   |
| 100-900 | 400 等价于 normal，700 等价于 bold，无单位 |

## 2.4 文字样式

> font-style 属性设置文本风格。

```html
p { font-style: normal; }
```

| 属性值 | 描述     |
| ------ | -------- |
| normal | 正常显示 |
| italic | _斜体_   |

## 2.5 字体复合属性写法

> 严格遵守顺序，且  font-sieze  和  font-family  必须有。

```css
body {
  font: font-style font-weight font-size/line-hight font-family;
}
```

## 2.6字体属性总结

| 字体属性    | 表示     | 注意                             |
| ----------- | -------- | -------------------------------- |
| font-size   | 字号     | 单位是  px                       |
| font-family | 字体     | 按照团队约定来写                 |
| font-weight | 字体粗细 | 400=normal，700=bold             |
| font-style  | 字体样式 | italic，normal，常用 normal      |
| font        | 属性连写 | 顺序不能变，字体和字号属性必须有 |

# 3.0 CSS 文本

## 3.1 文本颜色

>  color  属性定义文本颜色。

```css
div {
  color: red;
}
```

<font color=red size=4>属性值</font>

| 表示颜色       | 属性值           |
| -------------- | ---------------- |
| 预定义的颜色值 | red,green,pink   |
| 十六进制       | #FF0000，#FF6600 |
| RGB 代码       | rgb(255,0,0)     |

## 3.2 对齐文本

>  text-align  属性用于设置元素文本内容的对齐方式。
>
>  文本垂直居中
>
>  text-align：center
>
>  height=line-height

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291326680.png)

```css
div {
  text-align: center;
}
//文本垂直居中
.box{
      height: 300px;
      line-height: 300px;
      text-align: center;
}
```

| 属性值 | 解释           |
| ------ | -------------- |
| left   | 左对齐（默认） |
| right  | 右对齐         |
| center | 居中对齐       |

##3.3装饰文本

>  text-decoration  属性规定添加到文本的修饰。可以给文本添加下划线、删除线、上划线等。

```css
text-decoration: none;//给链接去掉下划线
```

| 属性值       | 描述                       |
| ------------ | -------------------------- |
| none         | 默认，无装饰（最常用）     |
| underline    | 下划线，a 标签自带（常用） |
| overline     | 上划线。（几乎不用）       |
| line-through | 删除线。（不常用）         |

## 3.4 文本缩进

>  text-indent 定义段落首行缩进。
>
>  em  是一个相对单位， 1em  就是一个字符所占大小。当  text-indent=2em ，则恰好缩进两个文字。

```css
p {
  text-indet: 2em;
}
```

## 3.5 行间距

>  line-height  设置行间的距离，行间距=文本高度+上间距+下间距

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291303127.png)

## 3.6 文本属性总结

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291307075.png)

# 4.0 引用方式

## 4.1 内部样式表

```css
<style> 
	div { 
		color: red; 
		font-size: 12px; 
	}	 
</style> 
```

## 4.2行内样式表

```html
<div style="color: red; font-size: 12px">行内样式表</div>
```

## 4.3 外部样式表

```html
<link rel="stylesheet" href="css文件路径" />
```

# 5.0块元素

> 常见的块元素有  h1-h6 、 p 、 div 、 ul 、 ol 、 li 等。
> 块级元素的特点：
>
> 独占一行。
>
> 高度、宽度、外边距以及内边距都可以控制。
>
> 宽度默认是容器（父级宽度）的 100%。
>
> 是一个容器及盒子，里面可以方行内或块级元素。

## 5.1行内元素

> 常见行内元素： a 、 strong 、 b 、 em 、 i 、 del 、 s 、 ins 、 u 、 span ，典型行内元素是  span ，行内元素也叫内联元素。
>
> 行内元素的特点：
>
> 1. 相邻行内元素在一行上，一行可以显示多个。
> 2. 高、宽直接设置是无效的。
> 3. 默认宽度就是它本身内容宽度。
> 4. 行内元素只能容纳文本或其他行内元素。

## 5.2行内块元素

> 在行内元素中有几个特殊标签—— img ,  input 、 td ，它们同时具有块元素和行内元素的特点。
>
> 行内块元素的特点：
>
> 1. 和相邻元素（行内块）在一行上，之间存在空白缝隙，一行可以显示多个。
> 2. 默认宽度是本身内容宽度。
> 3. 高度、行高、外边距、内边距都可以控制（块级元素特点）。

## 5.3 元素显示模式总结

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291323996.png)

## 5.4 元素模式转换

> 行内元素可以转换为块元素，块元素也能转换为行内元素。

```css
//行内->块级
a {
  display: block;
}
```



```css
//块级->行内
div {
  display: inline;
}
```



```css
//行内/块级-> 行内块元素
span {
  display: inline-block;
}
```

# 5.0. 背景

> 背景属性可以设置背景颜色、背景图片、背景平铺、背景图片位置、背景图像固定等。

## 5.1 背景颜色

>  background-color  定义了元素的背景颜色。

```css
background-color: 颜色值;
```

## 5.2 背景图片

>  background-image  属性描述了元素的背景图像，实际开发用于 logo 或者一些装饰性开发的小图片或者是超大的背景图片，优点是便于控制位置。

```css
background-image: url("/");
```

## 5.3 背景平铺

> 若需要在 HTML 页面上对背景图进行平铺，可以使用  background-repeat  属性。

```css
background-repeat: repeat(默认) | no-repeat | repeat-x | repeat-y;
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291338667.png)

```css
<style>
    .box{
      width: 1200px;
      height: 1200px;
      background-repeat: no-repeat;//不平铺
      background-image: url("./src/assets/images/colthes_left.png");
    }
  </style>
</head>
<body>

<div class="box">
  
</div>
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291340778.png)

```css
<style>
    .box{
      width: 1200px;
      height: 1200px;
      background-repeat: repeat;//平铺
      background-image: url("./src/assets/images/colthes_left.png");
    }
  </style>
</head>
<body>

<div class="box">
  
</div>
```

## 5.4 背景图片位置

>  background-position  可以改变图片在背景中的位置。
>
>  参数 x 和 y 指 x 左边和 y 坐标，可以使用方位名词或者精确定位。

```css
background-position: center;
background-position: 20px,50px;
```

| 参数值   | 说明                                                   |
| -------- | ------------------------------------------------------ |
| length   | 百分数 / 由浮点数字和单位字符组成的长度值              |
| position | top / center / bottom / left / center / right 方位名词 |

## 5.5 背景图像固定

>  background-attachment  属性设置背景图像是否随着页面其余部分滚动。
>
>  background-attachment  后期可以制作视差滚动效果。

```css
background-attachment: scroll | fixed;
```

| 参数   | 作用                     |
| ------ | ------------------------ |
| scroll | 背景图像随着对象内容滚动 |
| fixed  | 背景图像固定             |

## 5.6 背景属性复合写法

> background 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置

```css
background: transparent url(image.jpg) repeat-y fixed top;
```

## 5.7 背景颜色半透明

>  background: rgba(r,g,b,a)  属性设置图片透明度。

```css
background: rgba(0, 0, 0, 0.3);
```

## 5.8在盒子里放图片

```css
 <style>
    a{
      display: inline-block;
      text-decoration: none;
      color: white;
      width: 130px;
      height: 60px;
      line-height: 60px;
      text-align: center;
      background-color: pink;
    }
    .box .bg1{
      background-image: url("./src/assets/images/clothes1.png");
    }
    
<div class="box">

    <a href="#" class="bg1">五彩导航</a>
    <a href="#">五彩导航</a>
    <a href="#">五彩导航</a>
    <a href="#">五彩导航</a>
    <a href="#">五彩导航</a>

</div>
```

## 5. CSS 的三大特性

### 5.1 层叠性

> 样式冲突：遵循的原则是就近原则，哪个样式离结构近，就执行哪个样式
>
> 就是后面的覆盖前面的样式

```css
  <style>
    div{
      color: red;
    }
    div{
      color: pink;//pink颜色把red覆盖掉了
    }
  </style>
<body>
    <div>长江后浪推前浪，前浪死在沙滩上</div>
</body>
```

### 5.2 继承性

> CSS 中子标签会继承父标签的某些样式，如文本颜色和字号。
>
> 恰当使用继承可以简化代码，降低 CSS 的复杂性
>
> 子元素可以继承父元素的样式（text-, font-, line-这些元素开头的可以继承，以及 color 属性）

```css
  <style>
    div{
      color: pink;
      font-size: 14px;
    }
  </style>
<body>
    <div>
      <p>龙生龙，凤生凤</p>//p标签继承了div的color和font-size
    </div>
```

#### 5.2.1 行高的继承性

> 行高可以跟单位也可以不跟单位
>
> 如果子元素没有设置行高，则会继承父元素的行高为 1.5
>
> 此时子元素的行高是：当前子元素的文字大小\*1.5
>
> body 行高 1.5 这样写法最大优势就是里面的子元素可以根据文字大小自动调整行高

```css
<style>
   body {
  	   font: 12px/1.5 Microsoft Yahei;//1.5是当前文字大小的1.5倍
	}
	div{
      font-size: 14px;//14 * 1.5 = 21px
    }，
	p{
      font-size: 16px;//16 * 1.5 = 24px
    }
  </style>

<body>
    <div>
      龙生龙凤生凤
    </div>
    <p>龙生龙凤生凤</p>

</body>
```

```css
<style>
    body{
      color: pink;
      line-height: 24px;
      font-size: 14px;
    }

  </style>
<body>
    <div>
      龙生龙凤生凤//行高24px
    </div>
    <p>龙生龙凤生凤</p>//行高24px

</body>
```

### 5.3 优先级

> 当一个元素指定多个选择器时，就会有有优先级的产生。
>
> 选择器相同，则执行层叠性
>
> 选择器不同，则根据选择器权重执行

选择器权重如下所示。

| 选择器               | 选择器权重 |
| -------------------- | ---------- |
| 继承或者 *           | 0,0,0,0    |
| 元素选择器           | 0,0,0,1    |
| 类选择器，伪类选择器 | 0,0,1,0    |
| ID 选择器            | 0,1,0,0    |
| 行内样式  style=""   | 1,0,0,0    |
| !important           | ∞ 无穷大   |

```css
p {
  color: pink !important;
}
```

**复合选择器权重的叠加**

权重可以叠加，需要计算权重，但是没有进位。

# 6.0盒子模型

## 6.1 盒子模型（Box Model）组成

> CSS 盒子模型本质上是一个盒子，封装周围的 HTML 元素，包括：边框、外边距、内边距和实际内容。

![box-model](https://s3.ax1x.com/2021/01/29/yilgJO.gif)



![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291519534.png)

## 6.2 边框（border）

> border 可以设置元素边框。边框有三个组成： border-width 、 border-style 、 border-color 

```css
/*属性可连写*/
border: border-width || border-style || border-color;
```


| 属性         | 作用                  |
| ------------ | --------------------- |
| border-width | 定义边框粗细，单位 px |
| border-style | 边框样式              |
| border-color | 边框颜色              |

```css
<style>
    div{
      width: 300px;
      height: 200px;
      border-width: 5px;
      border-style: solid;
    }
  </style>
<body>

<div></div>

</body>
```

**边框属性简写**

```css
/*习惯顺序*/
border: 5px solid pink;
```

**边框属性分写**

```css
/*注意层叠性*/
div{
    width:200px;
    height:200px;
    border-top: 1px solid red;
    border-buttom: 1px solid red;
    border-left: 1px solid red;
    border-right: 1px solid red;
}
```

## 6.4 表格的细线边框

> border-collapse  属性控制浏览器绘制表格边框的方式。它控制相邻单元格的边框。
>
> collapse 是合并的意思
>
> border-collapse:collapse;  表示将相邻边框合并在一起

```css
border-collapse: collapse;

<style>
    table{
      width: 500px;
      height: 249px;
    }
    table,
    td
    {
        border: 1px solid pink;
      border-collapse: collapse;
    }
    td{
      text-align: center;
      line-height: 20px;
    }

  </style>
<body>

<table  cellspacing="0" align="center">
  <tr>
    <td>排名</td>
    <td>关键词</td>
    <td>趋势</td>
    <td>进入趋势</td>
    <td>相关链接</td>
  </tr>
  <tr>
    <td>排名</td>
    <td>关键词</td>
    <td>趋势</td>
    <td>进入趋势</td>
    <td>相关链接</td>
  </tr>
  <tr>
    <td>排名</td>
    <td>关键词</td>
    <td>趋势</td>
    <td>进入趋势</td>
    <td>相关链接</td>
  </tr>

</table>

```

## 6.5 边框会影响盒子实际大小

> 边框会额外增加盒子的实际大小，
>
> 因此有两种方案解决。
>
> 1.测量盒子大小的时候，不测边框。
>
> 2.若测量的时候包含了边框，则需要 width/height-边框宽度。

```css
  <style>

    div{
      width: 200px;
      height: 200px;
      background-color: pink;
      border: 5px solid red;
    }

  </style>
<body>

<div></div>//大小=content + border * 2因为有左右两个边框所以210px
```

## 6.6 内边距 padding

> padding  属性设置内边距，即边框与内容之间的距离。
>
> padding-left : 左内边距
>
> padding-right : 右内边距
>
> padding-top : 上内边距
>
> padding-bottotm : 下内边距
>
> **padding 属性简写**
>
> padding  的值的个数：
>
> 1 个值：上下左右
>
> 2 个值：上下，左右
>
> 3 个值：上，左右，下
>
> 4 个值：上，右，下，左，顺时针

### 6.6.1padding 会影响盒子实际大小

> 当给盒子指定了  padding  值以后，发生了两件事情：
>
> 内容和边框有了距离，增加内边距
>
> padding 值影响了盒子实际大小
>
> 也就是说，当盒子已经有了宽度和高度，再指定内边距，会撑大盒子。
>
> 要保证盒子和效果图一样大，则让  width/height -多出来的内边距大小即可。

```css
  <style>

    div{
      width: 160px;
      height: 160px;
      background-color: pink;
      padding: 20px;//要保证div是长宽是200px，padding又要是20px，
        那么width和height - 20 * 2有两条边
    }
  </style>
<body>

<div>
  盒子内容是content
</div>

```

### 6.6.2盒子里面的字数不一样

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291635121.png)

```css
 <style>
    .nav{
      border-top: 3px solid #ff8500;
      border-top: 1px solid #edeef0;
      height: 41px;
      background-color: #fcfcfc;
      line-height: 41px;
    }
    .nav a{
      display: inline-block;
      height: 41px;
      text-decoration: none;
      color: #4c4c4c;
      padding:0 20px;
    }
    a:hover{
      background-color: #eee;
      color: rgb(206, 141, 72);
    }


  </style>
</head>
<body>

<div class="nav">
  <a href="#">新浪导航</a>
  <a href="#">手机新浪网</a>
  <a href="#">移动客户端</a>
  <a href="#">微博</a>
  <a href="#">三个字</a>
</div>
```

### 6.6.3不会撑开盒子大小

> 如果盒子本身没有指定width/height属性, 则此时padding不会撑开盒子大小.

### 6.6.4box-sizing 属性解决方案

> CSS 中的  box-sizing  属性定义了  user agent  应该如何计算一个元素的总宽度和总高度。
>
> 在设置了一个盒子的  width/height  后，再设置其  border/padding  会影响盒子实际大小。当进行响应式布局时，这个尤其烦人。
>
> box-sizing 属性可以被用来调整这些表现。

- content-box  是默认值。如果你设置一个元素的宽为 100px ，那么这个元素的内容区会有  100px  宽，并且任何边框和内边距的宽度都会被增加到最后绘制出来的元素宽度中。

  ```css
  box-sizing: content-box;
  ```

- border-box  告诉浏览器：你想要设置的边框和内边距的值是包含在  width  内的。也就是说，如果你将一个元素的  width  设为  100px ，那么这 100px 会包含它的  border  和  padding ，内容区的实际宽度是  width  减去  (border + padding)  的值。大多数情况下，这使得我们更容易地设定一个元素的宽高。

  ```css
  box-sizing: border-box;
  ```



## 6.7外边距

> margin  属性用于设置外边距，即控制盒子与盒子之间的距离。
>
> margin-left : 左外边距
>
> margin-right : 右外边距
>
> margin-top : 上外边距
>
> margin-bottotm : 下外边距

### 6.7.1 外边距典型应用

>  外边距可以让块级盒子 **水平居中**，但是必须满足两个条件：
>
>  1.盒子必须指定宽度（width）
>
>  2.盒子左右的外边距都设置为  auto 

```css
.header {
  width: 960px;
  margin: 0 auto;
}
```

### 6.7.2使行内元素或行内块元素水平居中

> 行内元素或者行内块元素水平居中给其父元素添加 text-align:center 

```css
<style>
      .header{
        width: 900px;
        height: 200px;
        background-color: pink;
        margin: 0 auto;
        text-align: center;
      }
      
</style>
<body>

    <div class="header">
      <span>里面的文字</span>
    </div>

</body>
```

是table水平居中

```css
align: center;
```

### 6.7.3外边距塌陷

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291931473.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291933715.png)

```css
 <style>
      .father{
        height: 400px;
        width: 400px;
        background-color: purple;
        margin-top: 50px;
        border: 1px solid red;//①为父亲上边框
        padding: 1px//②为父亲上内边距
        overfolow: hidden//③
      }
      .son{
        width: 200px;
        height: 200px;
        background-color: pink;
        margin-top: 50px;
      }

  </style>
  <body>

    <div class="father">
      <div class="son"></div>
    </div>

</body>
```

### 6.7.4清除内外边距

> 网页元素很多都带有默认的内外边距，而且不同浏览器默认的也不一致。因此我们在布局前，首先要清除下网 页元素的内外边距。 

```css
* { 
	padding:0;   /* 清除内边距 */ 
	margin:0;    /* 清除外边距 */
}
```

## 6.8圆角边框

border-radius  属性用于设置元素的外边框圆角。

```css
border-radius: length;

<style>
    div{
      width: 200px;
      height: 200px;
      background-color: pink;
      border-radius: 5px;
    }
</style>
<body>

   <div></div>

</body>
```

# 7.0案例

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408291941626.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    body{
      background-color: #f5f5f5;
    }
    .box{
      width: 298px;
      height: 415px;
      background-color: #fff;
      margin: 100px auto;
    }
    .box img{
      /*图片的宽度和父亲一样宽*/
      width: 100%;
    }
    .review{
      height: 70px;
      font-size: 14px;
      /*因为这个段落没有width属性 所有padding不会撑开盒子的宽度*/
      padding: 0 20px;
      margin-top: 20px;
    }
    .appraise{
      font-size: 12px;
      color: #b0b0b0;
      margin-top: 0px;
      padding: 0 20px;
    }
    .box .info h4{
      display: inline-block;
      font-size: 14px;
      font-weight: 400;
      margin-top: 14px;
      padding: 0 20px;
    }
    .info span{
      color: #ff6700;
    }
    .info em{
      font-style: normal;
      color: #ebe4e0;
      margin-left: 20px;
      margin-right: 6px;
    }
    .info a{
      text-decoration: none;
      color: #333;
    }
  </style>
</head>
<body>

    <div class="box">
      <img src="./src/assets/images/kitchen1.png" alt="">
      <p class="review">快递牛，整体不错蓝牙可以说秒连，红牛给力</p>
      <div class="appraise">来自于11754546</div>
      <div class="info">
        <h4><a href="#">Redmi AirDots真无线蓝...</a></h4>
         <em>|</em>
        <span>99.9</span>
      </div>
    </div>

</body>
</html>

```

## 7.1案例2

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292021888.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    .box{
      width: 248px;
      height: 163px;
      background-color: rgb(252, 255, 252);
      margin: 100px auto;
      border: 1px solid #ccc;
    }
    li{
      list-style: none;

    }
    .box h3{
      height: 32px;
      line-height: 32px;
      border-bottom: 1px dotted #ccc;
      font-size: 14px;
      font-weight: 400;
      padding-left: 15px;
    }
    .box ul li a{
      font-size: 12px;
      padding: 15px;
      color: #666666;
      text-decoration: none;
    }
    .box ul li{
      height: 23px;
      line-height: 23px;
    }
  </style>
</head>
<body>

    <div class="box">
      <h3>评优购快递</h3>
      <ul>
        <li><a href="#">【劲爆】上海奥迪吉拉的看法尽量</a></li>
        <li><a href="#">【劲爆】罚款砥砺奋进阿市大抗打</a></li>
        <li><a href="#">【劲爆】发撒戴假发当家拉法基打</a></li>
        <li><a href="#">【劲爆】发咖啡斯利康戴假发老大</a></li>
      </ul>
    </div>

</body>
</html>

```

## 7.2图片跟盒子不一样

> 图片放在一个div里，图片的大小跟div的大小不一样怎么办，
>
> 那就让img和他的父亲一样宽就行

```
.box img{
      width: 100%;//如果只写width那么宽度就是填满div
      height: 100%;//如果width和height都写那么就完全填充div
}
```

# 8.0 盒子阴影

```css
bxo-shadow: h-shadow v-shadow blur spread color inset;
```

| 值       | 描述                                           |
| -------- | ---------------------------------------------- |
| h-shadow | 必需，水平阴影的位置，允许负值                 |
| v-shadow | 必需，垂直阴影的位置，允许负值                 |
| blur     | 可选，模糊距离                                 |
| spread   | 可选，阴影的尺寸                               |
| color    | 可选，阴影的颜色                               |
| inset    | 可选，将外部阴影改为内部阴影（默认是外部阴影） |

```css
  <style>
    div{
      width: 200px;
      height: 200px;
      background-color: pink;
      margin: 100px auto;
    }
    div:hover{
      /*原来没有影子鼠标经过div就有影子*/
      box-shadow: 10px 10px 10px -4px rgb(0,0,0,0.3) ;
    }
  </style>
<body>

<div></div>

</body>
```

## 8.1. 文字阴影

CSS3 中，使用  text-shadow  属性设置文本阴影。

| 值       | 描述                           |
| -------- | ------------------------------ |
| h-shadow | 必需，水平阴影位置。允许负值。 |
| v-shadow | 必须，垂直阴影。允许负值。     |
| blur     | 可选，模糊距离。               |
| color    | 可选，阴影颜色。               |

# 9.0浮动

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292059940.png)

> 多个块级元素纵向排列找标准流，多个块级元素横向排列找浮动。 

```css
选择器 { float: 属性值; }
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292102845.png)

```css
<style>
      .left{
        float: left;
        width: 200px;
        height: 200px;
        background-color: pink;
      }
      .right{
        float: right;
        width: 200px;
        height: 200px;
        background-color: green;
      }
  </style>
<body>

    <div class="left">左青龙</div>
    <div class="right">右白虎</div>

</body> 
```

## 9.1浮动特性

> 浮动元素会脱离标准流，脱离标准流的盒子，会漂浮在标准流的盒子上面，不占位置。
>
> 浮动元素会一行内显示并且元素顶部对齐，如果多个盒子都设置了浮动，则它们会按照属性值一行显示并且顶端对齐排列。
>
> 浮动的元素会具有行内块元素的特性，任何元素都可以浮动。不管原先是什么模式的元素，添加浮动之后具有行内块元素相似的特性。 span是行内元素不能设置宽高，如果加了浮动就有了宽高
>
> 行内元素只要加了浮动就不需要转成行内元素了

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292107452.png)

```css
  <style>
      .left{
        float: left;
        width: 200px;
        height: 200px;
        background-color: pink;
      }
      .right{
        width: 400px;
        height: 400px;
        background-color: green;
      }
  </style>
<body>

    <div class="left">浮动的盒子</div>
    <div class="right">标准流的盒子</div>

</body>
```



![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292112194.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
      .one{
        float: left;
        width: 200px;
        height: 200px;
        background-color: pink;
      }
      .two{
        float: left;
        width: 200px;
        height: 200px;
        background-color: green;
      }
      .three{
        float: left;
        width: 200px;
        height: 200px;
        background-color: skyblue;
      }
      .four{
        float: left;
        width: 200px;
        height: 200px;
        background-color: yellow;
      }
  </style>
</head>
<body>
  <div class="one"></div>
  <div class="two"></div>
  <div class="three"></div>
  <div class="four"></div>

</body>
</html>

```



![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292115071.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
      span{
        float: left;
        width: 200px;
        height: 100px;
        background-color: pink;
      }
  </style>
</head>
<body>
  <span>我是span</span>
</body>
</html>

```

## 9.2浮动和标准流父级元素搭配使用

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292121417.png)

> 为了约束元素位置，一般采取，先用标准流父元素上下排列位置，之后内部子元素采取浮动排列左右位置，符合网页布局第一准则。

## 9.3常见网页布局

> 浮动和标准流的父盒子搭配
>
> 先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列左右位置。
>
> 一个元素浮动了，理论上其余兄弟元素也要浮动
>
> 一个盒子里有多个盒子，其中一个盒子浮动，其他兄弟也应该浮动，防止引起问题。
>
> 浮动的盒子只会影响浮动盒子后面的标准流，不会引起前面的标准流。

## 9.4练习

### 9.4.1练习1

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292219559.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    .box{
      width: 1226px;
      height: 460px;
      background-color: pink;
      margin: 100px auto;
    }
    .box .left{
      float: left;
      width: 350px;
      height: 460px;
      background-color: rgb(159, 156, 156);
    }
    .box .right{
      float: right;
      width: 876px;
      height: 460px;
      background-color: pink;
    }

  </style>
</head>
<body>
    <div class="box">
      <div class="left">
      </div>
      <div class="right"></div>
    </div>
</body>
</html>

```

### 9.4.2练习2

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408292219576.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408300923226.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    li{
      list-style: none;
    }
    .box{
      width: 1226px;
      height: 285px;
      background-color: pink;
      margin: 100px auto;
    }
    .box li{
      float: left;
      margin-right: 14px;
      width: 296px;
      height: 285px;
      background-color: skyblue;
    }
    .box .last{
      margin: 0;
    }
  </style>
</head>
<body>
    <ul class="box">
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li class="last">4</li>
    </ul>
</body>
</html>
```

### 9.4.3练习3

> 思路
>
> 一个大的div包着左边一个div和右边一个div
>
> 右边的div又包着8个小的div
>
> 先设置盒子大小，之后设置盒子的位置

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408300926782.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    .box{
      width: 1226px;
      height: 615px;
      background-color: pink;
      margin: 0 auto;
    }
    .box .left{
      float: left;
      width: 234px;
      height: 615px;
      background-color: skyblue;
    }
    .box .right{
      float: right;
      width: 992px;
      height: 615px;
      background-color: green;
    }
    .box .left img{
      width: 100%;
      height: 100%
    }
    .right > div{
      float: left;
      width: 234px;
      height: 300px;
      background-color: pink;
      margin-left: 10px;
      margin-bottom: 14px;
    }

  </style>
</head>
<body>
    <div class="box">
      <div class="left">
        <img src="./src/assets/images/fresh_left.png" alt="">
      </div>
      <div class="right">
        <div class="one">1</div>
        <div class="two">1</div>
        <div class="three">1</div>
        <div class="four">1</div>
        <div class="five">1</div>
        <div class="six">1</div>
        <div class="seven">1</div>
        <div class="eight">1</div>
      </div>
    </div>
</body>
</html>

```

## 9.5常见的网页布局

> 只要和浏览器一样宽的距离就不需要指定宽度

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408300954131.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408300953844.png)



![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301007403.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    .top{
      height: 50px;
      background-color: grey;
    }
    .banner{
      width: 980px;
      height: 150px;
      background-color: grey;
      margin: 10px auto;
    }
    .box{
      width: 980px;
      height: 300px;
      background-color: pink;
      margin: 0 auto;
    }

    li{
      list-style: none;
    }
    .box li{
      float: left;
      width: 237px;
      height: 300px;
      margin-right: 10px;
      background-color: grey;
    }
    .box .last{
      margin-right: 0;
    }
    .footer{
      height: 200px;
      margin-top: 10px;
      background-color: grey;
    }
  </style>
</head>
<body>
    <div class="top"></div>
    <div class="banner"></div>
    <div class="box">
      <ul>
        <li></li>
        <li></li>
        <li></li>
        <li class="last"></li>
      </ul>
    </div>
    <div class="footer"></div>
</body>
</html>

```

## 9.6清除浮动

> 由于父级盒子很多情况下，不方便给高度，当时盒子浮动又不占有位置，最后父级盒子高度为 0 时，就会影响下面的盒子，对后面元素排版产生影响。

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301014393.png)



![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301019273.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    .box{
      width: 800px;
      border: 1px solid blue;
      margin: 0 auto;
    }
    .damao{
      width: 300px;
      height: 200px;
      background-color: purple;
    }
    .ermao{
      width: 200px;
      height: 200px;
      background-color: pink;
    }
  </style>
</head>
<body>

    <div class="box">
      <div class="damao">大毛</div>
      <div class="ermao">二毛</div>
    </div>

</body>
</html>

```

### 9.6.1 清除浮动的本质

> 由于父级盒子很多情况下，不方便给高度，当时盒子浮动又不占有位置，最后父级盒子高度为 0 时，就会影响下面的盒子，对后面元素排版产生影响。
>
> 因为浮动不占有高度，如果是父元素没有设置高度，子盒子又设置浮动，那么前面都设置浮动的话，那么父元素高度就是0，就会影响下面的盒子
>
> 清除浮动的本质是清除浮动元素造成的影响
>
> 如果父盒子本身具有高度，则不需要清除浮动
>
> 清除浮动之后，父级会根据浮动的子盒子自动检测高度，父级有了高度，就不会影响下面的标准流了。

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301022624.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301032034.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    .box {
      width: 800px;
      border: 1px solid blue;
      margin: 0 auto;
    }

    .damao {
      float: left;
      width: 300px;
      height: 200px;
      background-color: purple;
    }

    .ermao {
      float: left;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

    .footer {
      height: 200px;
      background-color: skyblue;
    }
   
  </style>
</head>
<body>

<div class="box">
  <div class="damao">大毛</div>
  <div class="ermao">二毛</div>
</div>
<div class="footer"></div>

</body>
</html>

```

### 9.6.2 清除浮动

> 1.**额外标签法（隔墙法）**，是 W3C 推荐的方法
>
> 2.父级添加 overflow 属性
>
> 3.父级添加 after 伪元素
>
> 4.父级添加双伪元素
>
> 清除浮动策略：闭合浮动

```css
选择器: {
  clear: 属性值;
}
```

| 属性值 | 描述                 |
| ------ | -------------------- |
| left   | 不允许左侧有浮动元素 |
| right  | 不允许右侧有浮动元素 |
| both   | 同时清除左右两侧浮动 |

#### 9.6.2.1额外标签法

> 也成为隔墙法，是 W3C 推荐的方法。
>
> 额外标签法是在最后一个浮动元素末尾添加一个 **空块级元素**，给其赋以属性  clear:both; 。

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301110784.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    .box {
      width: 800px;
      border: 1px solid blue;
      margin: 0 auto;
    }

    .damao {
      float: left;
      width: 300px;
      height: 200px;
      background-color: purple;
    }

    .ermao {
      float: left;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

    .footer {
      height: 200px;
      background-color: skyblue;
    }
    .clear{
      clear: both;
    }
  </style>
</head>
<body>

<div class="box">
  <div class="damao">大毛</div>
  <div class="ermao">二毛</div>
  <div class="clear"></div>
</div>
<div class="footer"></div>

</body>
</html>

```

#### 9.6.2.2父级添加 overflow

> 可以给父级添加  overflow  属性，将其属性设置为  hidden 、 auto 或 scroll 。

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301110784.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    .box {
      overflow: hidden;
      width: 800px;
      border: 1px solid blue;
      margin: 0 auto;
    }

    .damao {
      float: left;
      width: 300px;
      height: 200px;
      background-color: purple;
    }

    .ermao {
      float: left;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

    .footer {
      height: 200px;
      background-color: skyblue;
    }

  </style>
</head>
<body>

<div class="box">
  <div class="damao">大毛</div>
  <div class="ermao">二毛</div>
</div>
<div class="footer"></div>

</body>
</html>

```

#### 9.6.2.3after 伪元素法

> 实际上也是额外标签法的一种，给父元素添加

```css
.clearfix:after {
  content: "";
  display: block;
  height: 0;
  clear: both;
  visibility: hidden;
}
.clearfix {
  /*IE6、7专有*/
  *zoom: 1;
}
```

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }
    .clearfix:after {
      content: "";
      display: block;
      height: 0;
      clear: both;
      visibility: hidden;
    }
    .clearfix {
      /*IE6、7专有*/
      *zoom: 1;
    }
    .box {
      width: 800px;
      border: 1px solid blue;
      margin: 0 auto;
    }

    .damao {
      float: left;
      width: 300px;
      height: 200px;
      background-color: purple;
    }

    .ermao {
      float: left;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

    .footer {
      height: 200px;
      background-color: skyblue;
    }

  </style>
</head>
<body>

<div class="box clearfix">
  <div class="damao">大毛</div>
  <div class="ermao">二毛</div>
</div>
<div class="footer"></div>

</body>
</html>

```

#### 9.6.2.4双伪元素法

```css
.clearfix::before,
.clearfix::after {
  content: "";
  display: table;
}
.clearfix::after {
  clear: both;
}
.clearfix {
  *zoom: 1;
}
```

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }
    .clearfix::before,
    .clearfix::after {
      content: "";
      display: table;
    }
    .clearfix::after {
      clear: both;
    }
    .clearfix {
      *zoom: 1;
    }
    .box {
      width: 800px;
      border: 1px solid blue;
      margin: 0 auto;
    }

    .damao {
      float: left;
      width: 300px;
      height: 200px;
      background-color: purple;
    }

    .ermao {
      float: left;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

    .footer {
      height: 200px;
      background-color: skyblue;
    }

  </style>
</head>
<body>

<div class="box clearfix">
  <div class="damao">大毛</div>
  <div class="ermao">二毛</div>
</div>
<div class="footer"></div>

</body>
</html>

```

# 10.0css编写顺序

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301121995.png)

```css
.jdc { 
display: block; 
position: relative; 
float: left; 
width: 100px; 
height: 100px; 
margin: 0 10px; 
padding: 20px 0; 
color: #333; 
font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif; 
background: rgba(0,0,0,.5); 
border-radius: 10px;
}  
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301122063.png)

# 11.0布局分析

> 为了提高网页制作的效率，布局时通常有以下的布局流程：  
>
> 1.必须确定页面的版心就是打开网页第一眼的屏幕的可视区，我们测量可得知。 
>
> 2.分析页面中的行模块，以及每个行模块中的列模块。其实页面布局，就是一行行罗列而成的。
>
> 3.制作 HTML 结构。我们还是遵循，先有结构，后有样式的原则。结构永远最重要。
>
> 4.开始运用盒子模型的原理，通过 DIV+CSS 布局来控制网页的各个模块。

## 11.1版心

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301128376.png)

# 12.0学成在线

## 12.1.定版心

> 这个页面的版心是 1200 像素，每个版心都要水平居中对齐，可以定义版心为公共类：

```css
.w {
  margin: 1200px auto;
}
```

## 12.2导航栏

> 实际开发中，不会直接用链接 a 而是用 li 包含链接（li+a）的做法。
>
> 1. li+a 语义更清晰，一看就是有条理的列表型内容。
> 2. 如果直接用 a，搜索引擎容易辨别为有堆砌关键字嫌疑（故意堆砌关键字容易被搜索引擎有降权的风险），从而影响网站排名。
>
> 3. 让导航栏一行显示，给  li  加浮动，因为 li 是块级元素，需要一行显示。
> 4. 这个 nav 导航栏可以不给宽度，将来可以继续添加其余文字。
> 5. 因为导航栏里面文字不一样多，所以最好给链接 a 左右 padding 撑开盒子，而不是指定宽度。
> 6. 浮动的盒子不会有外边距合并的问题.

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301456848.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301135805.png)



![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301144651.png)

```css
*{
    margin: 0;
    padding: 0;
}
.w{
    width: 1200px;
    margin: auto;
}
.header{
    height: 42px;
    background-color: pink;
    margin: 30px auto;
}
<body>

  <div class="header w">
    头部盒子
  </div>

</body>
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301149432.png)

```css
*{
    margin: 0;
    padding: 0;
}
.w{
    width: 1200px;
    margin: auto;
}
.header{
    height: 42px;
    background-color: pink;
    margin: 30px auto;
}
.logo{
    width: 198px;
    height: 42px;
    background-color: skyblue;
}
.logo img{
    width: 100%;
    height: 100%;
}  
<div class="header w">
<!--    logo部分-->
    <div class="logo">
      <img src="./image/01.jpg" alt="">
    </div>
</div>
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301446716.png)

```css
*{
    margin: 0;
    padding: 0;
}
.w{
    width: 1200px;
    margin: auto;
}
.header{
    height: 42px;
    background-color: pink;
    margin: 30px auto;
}
.logo{
    float: left;
    width: 198px;
    height: 42px;
    background-color: skyblue;
}
.logo img{
    width: 100%;
    height: 100%;
}
li{
    list-style: none;
}
.nav{
    float: left;
    margin-left: 60px;
}
.nav ul li a{
    text-decoration: none;
}


  <div class="header w">
<!--    logo部分-->
    <div class="logo">
      <img src="./image/01.jpg" alt="">
    </div>
<!--    导航栏-->
      <div class="nav">
        <ul>
          <li><a href="#">首页</a></li>
          <li><a href="#">课程</a></li>
          <li><a href="#">职业规划</a></li>
        </ul>
      </div>
  </div>

```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301459128.png)

```css
*{
    margin: 0;
    padding: 0;
}
.w{
    width: 1200px;
    margin: auto;
}
.header{
    height: 42px;
    background-color: pink;
    margin: 30px auto;
}
.logo{
    float: left;
    width: 198px;
    height: 42px;
    background-color: skyblue;
}
a{
    text-decoration: none;
}
.logo img{
    width: 100%;
    height: 100%;
}
li{
    list-style: none;
}
.nav{
    float: left;
    margin-left: 60px;
}
.nav ul li a{
    display: block;
    height: 42px;
    line-height: 42px;
    font-size: 18px;
    padding: 0 10px;
    color: #050505;
}
.nav ul li{
    float: left;
    margin: 0 15px;
}
.nav ul li a:hover{
    border-bottom: 2px solid #00a4ff;
}


  <div class="header w">
<!--    logo部分-->
    <div class="logo">
      <img src="./image/01.jpg" alt="">
    </div>
<!--    导航栏-->
      <div class="nav">
        <ul>
          <li><a href="#">首页</a></li>
          <li><a href="#">课程</a></li>
          <li><a href="#">职业规划</a></li>
        </ul>
      </div>
  </div>

```

### 12.2.1seacher框

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301502434.png)



## 12.3banner

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301136717.png)

## 12.4小模块

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301136748.png)

## 12.5大模块

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301136899.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301137932.png)

## 12.6底部模块

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301137211.png)

# 13.0定位

## 13.1为什么需要定位

> 一些固定盒子的效果，标准流或浮动都无法快速实现，此时需要定位来实现。所以：
>
> 1.浮动可以让多个块级盒子一行没有缝隙排列显示，经常用于横向排列盒子
>
> 2.定位则是可以让盒子自由的在某个盒子内移动位置或者固定屏幕中某个位置，并且可以压住其他盒子。

## 13.2 定位组成

> 定位：将盒子定在某一个位置，所以定位也是在摆放盒子，按照定位的方式移动盒子。
>
> 定位=定位模式+边偏移。
>
> 定位模式用于指定一个元素在文档中的定位方式。边偏移则决定了该元素的最终位置。

## 13.3定位模式

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301522844.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301523425.png)

## 13.4相对定位 relative

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301528099.png)

> 相对定位是元素在移动位置的时候，是相对于它==原来的位置==来说的。
>
> 继续==占有原来的位置==

```css
选择器 {
  position: relative;
}
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301532669.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    .box1{
      position: relative;
      top: 100px;
      left: 100px;
      width: 200px;
      height: 200px;
      background-color: pink;
    }
    .box2{
      width: 200px;
      height: 200px;
      background-color: purple;
    }
  </style>
</head>
<body>

  <div class="box1"></div>
  <div class="box2"></div>
</body>
</html>
```

## 13.5 绝对定位 absolute

> 绝对定位是元素在移动位置的时候，是相对于它祖先元素来说的。
>
> 如果 **没有祖先元素** 或者 **祖先元素没有定位**，则以 **浏览器** 为准定位
>
> 如果祖先元素有定位（相对、绝对、固定定位） ，则以最近一级的有定位祖先元素为参考点移动位置。
>
> 绝对定位==不再占有原先==的位置。

```css
选择器 {
  position: absolute;
}
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301538932.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    .father{
      width: 500px;
      height: 500px;
      background-color: skyblue;
    }
    .son {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

  </style>
</head>
<body>
<div class="father">
  <div class="son"></div>
</div>

</body>
</html>
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301541283.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    .father{
      position: absolute;
      width: 500px;
      height: 500px;
      background-color: skyblue;
    }
    .son {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

  </style>
</head>
<body>
<div class="father">
  <div class="son"></div>
</div>

</body>
</html>
```

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301545383.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    .yeye{
      position: absolute;
      width: 700px;
      height: 700px;
      background-color: hotpink;
    }
    .father{
      width: 500px;
      height: 500px;
      background-color: skyblue;
    }
    .son {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 200px;
      height: 200px;
      background-color: pink;
    }

  </style>
</head>
<body>
    <div class="yeye">
      <div class="father">
        <div class="son"></div>
      </div>
    </div>

</body>
</html>
<script setup>
</script>
```

## 13.6静态定位 static

> 静态定位是元素的默认定位方式，无定位的意思。就是标准流。
>
> 静态定位按照标准流特性摆放位置，它没有边偏移静态定位在布局时很少用到。

```css
选择器 {
  position: static;
}
```

## 13.7子绝父相的由来

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301550673.png)

> 子绝父相：子级是绝对定位的话，父级要用相对定位
>
> 子级绝对定位，不会占有位置，可以放到父盒子里面的任何一个地方，不会影响其他的兄弟盒子。
>
> 父盒子需要加定位限制子盒子在父盒子内显示。
>
> 父盒子布局时，需要占有位置，因此父亲只能是相对定位。
>
> 这就是子绝父相的由来，所以相对定位经常用来作为绝对定位的父级。
> 总结：因为父级需要占有位置，因此是相对定位，子盒子不需要占有位置，则是绝对定位

## 13.8 固定定位 fixed

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301555578.png)

> 固定定位是元素固定于浏览器可视区的位置。主要使用场景：可以在浏览器页面滚动时元素的位置不会改变。
>
> 以浏览器的可视窗口为参照点移动元素。
>
> 跟父元素没有任何关系
>
> 不随滚动条滚动

```css
选择器 {
  position: fixed;
}
```

### 13.8.1固定定位小技巧

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301603191.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301611703.png)

```css
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <style>
    *{
      margin: 0;
      padding: 0;
    }
    .fixed{
      position: fixed;
      left: 50%;
      margin-left: 400px;
      width: 50px;
      height: 150px;
      background-color: skyblue;
    }
    .w{
      width: 800px;
      height: 1400px;
      background-color: pink;
      margin: 0 auto;
    }



  </style>
</head>
<body>

    <div class="fixed"></div>
    <div class="w">版心盒子 800像素</div>

</body>
</html>

```

## 13.9总结

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301613282.png)

## 13.10定位叠放次序

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301614064.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301620577.png)

## 13.11绝对定位的盒子居中

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301624284.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301627023.png)

```css
<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport"
        content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
  <style>
    .box{
      position: absolute;
      top: 50%;
      margin-top: -100px;
      left: 50%;
      margin-left: -100px;
      width: 200px;
      height: 200px;
      background-color: pink;
    }
  </style>
</head>
<body>
    <div class="box"></div>
</body>
</html>
```

## 13.12 定位特殊特性

> 绝对定位和固定定位也和浮动类似。
>
> 1.行内元素添加绝对或者固定定位，可以直接设置高度和完度。
>
> 2.块级元素添加绝对或者固定定位，如果不给宽度或者高度，默认大小是内容的大小。

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301631458.png)

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301632907.png)

## 13.13脱标的盒子不会触发外边距塌陷

> 浮动元素、绝对定位（固定定位）元素的都不会触发外边距合并的问题。

## 13.14 绝对定位（固定定位）会完全压住盒子

> 浮动元素不同，只会压住它下面标准流的盒子，但是不会压住下面标准流盒子里面的文字（图片）但是绝对定位（固定定位）会压住下面标准流所有的内容。
>
> 浮动之所以不会压住文字，因为浮动产生的目的最初是为了做文字环绕效果的。文字会围绕浮动元素

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301636549.png)

```css
<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport"
        content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
  <style>
    .box{
      //float: left;
      position: absolute;
      width: 200px;
      height: 200px;
      background-color: pink;
    }
  </style>
</head>
<body>
    <div class="box"></div>
    <p>阁下何不同风起，扶摇直上九万里</p>
</body>
</html>
```

## 11. 网页布局总结

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301640393.png)

# 14.0元素的显示与隐藏

> 类似网站广告，当我们点击关闭就不见了，但是我们重新刷新页面，会重新出现！本质：让一个元素在页面中隐藏或者显示出来。

## 14.1display 属性

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301645940.png)

> display  属性用于设置一个元素应如何显示。
>
> display： none;  隐藏对象
>
> display ： block;  除了转换为块级元素之外，同时还有显示元素的意思 display 隐藏元素后，不再占有原来的位置。
>
> 后面应用及其广泛，搭配 JS 可以做很多的网页特效。

## 14.2 visibility 可见性

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301645940.png)

> visibility 属性用于指定一个元素应可见还是隐藏。- - visibility : visible;元素可视
>
> visibility : hidden;元素隐藏
>
> visibility 隐藏元素后，继续占有原来的位置
>
> 如果隐藏元素想要原来位置，就用  visibility ： hidden 
> 如果隐藏元素不想要原来位置，就用  display ： none  （用处更多重点）

### 14.3 overflow 溢出

![](https://raw.githubusercontent.com/fightingwithmee/css/main/img/202408301646468.png)

> overflow 属性指定了如果内容溢出一个元素的框（超过其指定高度及宽度）时，会发生什么。

| 属性值  | 描述                                           |
| ------- | ---------------------------------------------- |
| visible | 不剪切内容也不添加滚动条                       |
| hidden  | 不显示超过对象尺寸的内容                       |
| scroll  | 超出的部分隐藏掉不管超出内容否，总是显示滚动条 |
| auto    | 超出自动显示滚动条，不超出不显示滚动条         |

