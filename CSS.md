## 提示框
- **为什么不能使用`<p>`**
- 提示文本放在内联元素上(如 <span>) 并使用class="tooltiptext"。
- 文本下划线  border-bottom: 1px dotted black;
-  让下划线与字对齐不溢出 display: inline-block;
- position: relative;

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200511211347799.png)
 
- 隐藏文本 visibility: hidden;

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200511213710842.png)

- 设置元素堆叠顺序
 position: absolute;
 z-index: **1**;
- 设置动作鼠标放上去显示文本提示框
div.tooltip:hover .tooltiptext{
	visibility: visible;
}
- 设置提示框格式
  width: 120px;
	background-color: black;
	color: #fff;
	text-align: center;
	border-radius: 6px;
	padding: 5px 0;

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200511214247611.png)

- 对提示文本定位
left: 120%;
top:-5px;[与padding对应]

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200511215212662.png)

- 头部提示：移到上方
position: absolute;
**bottom**:120%; （底部为top）

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512061525311.png)

- 调整位置移到正上方
left:50%;
margin-**left**: -60px;（一半宽度）

![在这里插入图片描述](https://img-blog.csdnimg.cn/202005120616444.png)

- 加上箭头
.tooltip_arrowtext::after{
content:"";
	position: absolute;
	bottom: 100%;（将箭头显示在顶部）
	left: 50%;（把箭头在中间对准）
	margin-left: -5px;（对准箭头位置，与bor-wid大小一致）
	border-width: 5px;（指定箭头大小）
	border-style: solid;
	border-color:  transparent transparent **black** transparent;
  
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020051206595321.png)

- 上箭头变右箭头
bottom→left；
调箭头到中心：（如果是top都改成top；是bottom都改成bottom）
left→top；
margin-left；→margin-top；

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512071130641.png)

border-color:  transparent transparent  transparent **black**;

- 设置淡入
opacity: 0;
	transition: opacity 2s;
:hover{opacity: 1;}
从原本到鼠标放上去（0→1，用时2s）

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020051207314156.png)

## 图片廊
-  `<div> <a> <img>` 图片
`<div>` 描述
- 设置整体
margin:5px;(间距)
border:1px solid #ccc;
float:left;(向左浮动)
width:180px;(设置宽度)
- 设置鼠标放置时的边框
:hover{border;}
- 设置图片适应
width:100%;(完全填充)
height:auto;(跟着宽度自动)
- 设置描述格式
padding:15px;(描述的宽度)
text-align:center;(居中)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512083305915.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

- 响应式
div.img_veranda_respon{
	padding: 0 6px;(设置整体间距)
	float: left;
	width: 29.99999%;(设置整体宽度)
}

```javascript
@media only screen and (max-width:700px){
	div.img_veranda_respon{
		width: 49.9999%;
		margin: 6px 0;
	}
}

@media only screen and (max-width:500px){
	div.img_veranda_respon{
		width: 100%;
	}
}

div.clearfix:after{
	content:"";
	display: table;
	clear: both;
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512085319523.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

## 图片透明化
- opacity: 0.3;
	filter:alpha(opacity=40); /* IE8 及其更早版本 */
	![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512091036663.png)
- 悬停效果
img:hover{opacity: 1.0;}
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512091208685.png)
## 透明盒子中的文字
- 设置背景图片
div.trans_background{background: url(EDG01.png) repeat;}
- 设置透明框
div.transbox{opacity: 0.6;}
- 设置文字格式
div.transbox p{margin等}

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512163856767.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

## *图像拼合
- 插入透明图（暂时无素材）


```css
<img class="home" src="1">
```

- 设置背景图 定位到相应位置

```css
div.img_splitgather img.next{
	width: 43px;
	height: 44px;
	background: url(img_navgather01.png) -91px 0;
```

}

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512170536653.png)![在这里插入图片描述](https://img-blog.csdnimg.cn/20200512170553888.png)

## @media:在相同样式表为不同媒体设置不同的样式
- 设置打印与屏幕上不同的格式

```css
@media screen{
	div.media p.media_test{font-family: verdana,sans-serif;font-size: 14px;}
}
@media print{
	div.media p.media_test{font-family: times,serif;font-size: 10px;}
}
@media screen,print{p.test{font-weight: bold;}}
```
### 其他媒体类型
`all` 用于所有的媒体设备。
`aural` 用于语音和音频合成器。
`braille`	用于盲人用点字法触觉回馈设备。
`embossed`	用于分页的盲人用点字法打印机。
`handheld`	用于小的手持的设备。
`print`	用于打印机。
`projection`	用于方案展示，比如幻灯片。
`screen`	用于电脑显示器。
`tty`	用于使用固定密度字母栅格的媒体，比如电传打字机和终端。
`tv`	用于电视机类型的设备。

## 属性选择器 
- title

```css
[title]{
	color:#FFAECF;
}
[title=BLEACH text01]{
	color:#FF4F81;
}
[title~=BLEACH]{
	color:#FF4F81;
}

<p title="BLEACH text01">“大家都把最重要的东西托付给我之后就走了，其实我很不擅长面对如此沉重的事情。”</p>
<p title="BLEACH text02">THE DEATH AND THE STRAWBERY.</p>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513115952811.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513120047420.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513120108830.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

- lang

```css
[lang|=BLEACH]{
	color: #FF4F81;
}

<p lang="BLEACH-text03">前往虚圈前最后的告白。</p>
<p lang="BLEACH-text04">“为什么你…当初不带我一起走呢。”</p>
```


## 表单

```css
input[type=submit]{
	width:100%;
	padding: 12px 20px;
	margin: 8px 0;
	display: inline-block;
	cursor: pointer;
/*	光标：指针*/
}

<label for="fname">First Name</label>
<input type="text" id="fname" name="firstname" placeholder="Shizukuu">

	
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513120401233.png)

- 设置点击时的格式

```css
input[type=text]:focus{
	background-color: #f7c8d0;
	border: 1px solid black;
/*	点击时的格式设置*/
}
input[type=text]{
	-webkit-transition:0.5s;
	transition: 0.5s;
/*	0.5s内进行边框变换*/
	outline: none;
/*	删除点击时的蓝色边框*/
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513152246488.png)

## 搜索框

```css
div.search_01 input.search{
	background-image: url(图标/searchicon.png);
	background-position: 10px 10px;
	background-repeat: no-repeat;}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513154044675.png)

- 搜索框动画

```css
div.search_01 input.search{
	width:130px;
	-wabkit-transition:width 0.4s ease-in-out;
	transition: width 0.4s ease-in-out;}
/*	设置0.4s内的具体变化*/

div.search_01 input.search:focus{
	width: 100%}
/*设置鼠标点击时的样式*/
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513162845237.png)

## 文本框
- 禁止重新设置大小

```css
div.textarea_01 textarea{
resize:none;
/*	禁止重新设置大小*/}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513162905898.png)

## 计数器

- `content`	使用 ::before 和 ::after 伪元素来插入自动生成的内容
`counter-increment`	递增一个或多个值
`counter-reset`	创建或重置一个或多个计数器

```css
div.counting_01{
	counter-reset: section;
}

div.counting_01 p.content::before {
	counter-increment: section;
	content: "202005 " counter(section)":";
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200513162630779.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

- 嵌套计数器

```css
div.counting2{
	counter-reset: section;
}

div.counting2 p.title{
	counter-reset: subsection;
	color: #ffaecf;
}

div.counting2 p.title::before{
	counter-increment: section;
	content: "Section " counter(section)". ";
}

div.counting2 p::before{
	counter-increment: subsection;
	content: counter(section)"." counter(subsection)" ";
	color: #ffaecf;
}
```

```css
<div class="counting2">
		<p class="title">202005</p>
		<p>撒野</p>
		<p>TOP</p>
		<p>Rooftop</p>
		
		<p class="title">202004</p>
		<p>無限大</p>
		<p>SUMMER!</p>
		<p>BOKE</p>
		
		<p class="title">202003</p>
		<p>追</p>
		<p>心似烟火</p>
	</div>
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200514084157514.png)

- 列表使用计数器

```css
div.counting3 ol{
	counter-reset: section;
	list-style-type: none;
}

div.counting3 li::before{
	counter-increment: section;
	content: counters(section,".")" ";
	color: #ff4f81;
}
```

```css
<ol>
			<li>佐々木琲世</li>
			<li>佐々木琲世
				<ol>
					<li>佐々木琲世</li>
					<li>佐々木琲世</li>
					<li>佐々木琲世
						<ol>
							<li>佐々木琲世</li>
							<li>佐々木琲世</li>
						</ol>
					</li>
				</ol>
			</li>
			<li>佐々木琲世</li>
		</ol>
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200514085303468.png)

##  布局
- 头部

```css
/*头部样式*/
.header{
	background-color: #EDECEC;
	padding: 20px;
	text-align: center;
}
```

```css
	<div class="header">
		<p style="color: pink;font-size: 36px;">班德尔城</p>
	</div>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200514162335140.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

- 导航栏

```css
/*导航条*/
.topnav{
	overflow:hidden;
	background-color: #ffaecf;
}

/*导航链接*/
.topnav a{
	padding: 14px 16px;
	text-align: center;
	color: white;
	text-decoration: none;
	float: left;
	display: block;
/*	向左浮动、块状显示*/
}

/*链接修改颜色*/
.topnav a:hover{
	background-color: white;
	color: #ff4f81;
}
```

```css
	<div class="topnav">
		<a href="#">漫画</a>
		<a href="#">动画</a>
		<a href="#">小说</a>
		<a href="#" style="float: right">时间线</a>
	</div>
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200514162510817.png)

- 分栏
- 三列

```css
/*创建三个相等的列*/
.column{
	float: left;
	width: 33.3%;
}
```

```css
/*创建三个不相等的列*/
.column{
	float: left;
	padding: 10px;
}
*/

/*左右两侧宽度*/
/*
.column.side{
	width: 25%;
}
*/

/*中间区域宽度*/
/*
.column.middle{
	width: 50%;
}
```
	

```css
<div class="row">
		<div class="column side">
		<div class="column middle">
		<div class="column side">
		......
```


- 两列+卡片化

```css
/*创建两列*/
/*left column*/
.leftcolumn{
	float: left;
	width: 75%;
}

/*右侧栏*/
.rightcolumn{
	float: left;
	width: 25%;
	background-color: #f1f1f1;
	padding-left: 20px;
}

/*图像部分*/
.BLEACH_img1{
	background-color: #ffffff;
	width: 100%;
	padding: 20px;
	align-content: center;
}

/*文章卡片效果*/
.card{
	background-color: white;
	padding: 20px;
	margin-top: 20px;
}

/*列后清除浮动*/
.row:after{
	content: "";
	display: table;
	clear: both;
}
```


```css
<div class="row">
		<div class="leftcolumn">
			<div class="card">
		<div class="rightcolumn">
			 <div class="card">
......
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200514163350946.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

- 响应式布局

```css
/*响应式布局* - 小于800px时改为上下布局*/
@media screen and (max-width:800px){
	.column .leftcolumn .rightcolumn{
		width: 100%;
		padding: 0;
	}
}

/*响应式布局 - 屏幕尺寸小于400px时，导航等布局改为上下布局 */
@media screen and (max-width:400px){
	.topnav a{
		float: none;
		width: 100%;
	}
}
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020051416372216.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)

- 底部样式

```css
/*底部样式*/
.footer{
	background-color: #F1EFEF;
	padding: 10px;
	text-align: center;
	color: #ff4f81;
}
```

```css
	<div class="footer">
		<p>THE DEATH AND THE STRAWBERRY.</p>
	</div>
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200514163916517.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)
### 出现的问题
- 图片没能适应div块
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200514164018947.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0MTk5Njc0,size_16,color_FFFFFF,t_70)


