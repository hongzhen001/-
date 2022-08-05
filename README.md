# 前端学习

## Git

### 1. Git基础配置
1. 设置用户名、邮箱
```C++
git config --global user.name "输入设置的用户名"
git config --global user.email "输入设置的邮箱"
git config --global --list
```
2. 初始化仓库
```C++
git init
```
3. 连接github
```C++
git remote add origin 远程仓库地址
```

### 2. 远程仓库覆盖本地文件
```C++
git fetch --all
git reset --hard origin/master
git pull
```


## HTML

### 1. 类名

| ClassName |  含义  | ClassName | 含义 | ClassName |   含义   | ClassName |   含义   |
| :-------: | :----: | :-------: | :--: | :-------: | :------: | :-------: | :------: |
|  account  |  关于  |   arrow   | 箭头 |  article  |   文章   |   aside   |   边栏   |
|  avatar   |  头像  |    bar    |  栏  |    btn    |   按钮   |  caption  |   标题   |
| category  |  分类  |   chart   | 图表 | clearficx | 清除浮动 |  comment  |   评论   |
| community |  社区  | container | 容器 |  content  |   内容   |   copy    |   版权   |
|  current  |  当前  |  footed   | 页脚 |   forum   |   论坛   |  header   |   页头   |
|   home    |  主页  |   icon    | 图标 |   more    |   更多   |   next    |  下一个  |
|    off    |  离开  |    on     | 移过 |  output   |   输出   |    pop    |   弹窗   |
|   prev    | 上一个 |  search   | 搜索 |  wrapper  |   版心   | shortcut  | 快捷导航 |
|  banner   | 轮播图 |   goods   | 好物 | bd/boder  |   内容   |   mask    |   遮罩   |
|  module   |  模块  |   info    | 信息 |   last    |   最后   |   login   |   登录   |
|  logout   |  退出  |   logo    | 标志 |   menu    |   菜单   |   meta    |   作者   |

### 2. 网页框架

```html
// 网页类型声明
<!DOCTYPE html>

// 网页语言；中文zh-CN，en-英文
<html lang="en">
  
// 文档头部，添加CSS/js/网页关键词等地方
<head>
  
  // 网页字符编码
  <meta charset="UTF-8">
  // 适配IE浏览器
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  // 配备移动端代码
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  // 引入网页logo
  <link rel="shortcut icon" href="favicon.ico(ico地址)" type="image/x-icon">
  // 引入CSS
  <link rel="stylesheet" href="css地址">
  
  // 网页SEO：提升网页在搜索时的优先级
  // 网页标题
  <title>标题内容</title>
  // 网页描述
  <meta name="description" content="描述内容">
  // 网页关键词
  <meta name="keywords" content="关键词内容">
  
</head>

// 网页内容
<body>
	网页内容区域
	// body引入js，需写在末尾位置
	<script src="js地址"></script>
</body>

</html>

扩展：CSS写入方式
内嵌式：在<head>中添加<style>CSS属性+取值</style>
外链式：在<head>中用<link rel="stylesheet" href="css地址">引入
行内式：在<body>内写的标签中添加 style="CSS属性+取值"
```

### 3. 网页基础标签

```html
标题： <h1></h1>   //分为一到六级

段落： <p></p>

换行： <br>

分割线 <hr>

块级容器： <div></div>  //一行只能排一个

行内容器： <span></span>  //一行可排多个

加粗： <strong></strong> //具有强调意义    <b></b>

下划线： <ins></ins>  //具有强调意义    <u></u>

倾斜： <em></em>  //具有强调意义    <i></i>

删除线： <del></del>  //具有强调意义   <s></s>

插入图片： <img src="图片路径位置" alt="图片加载失败后显示的文本内容" title="光标悬停时显示的文本内容" >

音频标签：<audio src="音频位置" controls autoplay loop></audio> //controls:插入播放器 loop:循环播放 autoplay:自动播放

视频标签：<video src="视频位置" controls autoplay loop muted></video>  // 自动播放音频无法实现，视频配合muted静音可实现

超链接：<a herf="跳转地址" target="窗口打开方式"></a>  // _blank 新窗口打开，跳转地址可用id名进行页面内跳转（书写：#id名）
```

### 4. 移动端语义化标签

```html
头部： <header></header>

导航： <nav></nav>

内容： <article></article>

文档某个区域： <section></section>

侧边栏： <aside></aside>

尾部： <footer></footer>

页面主页： <main></main>
```

### 5. 列表/表格

```html
// 无序列表：
<ul>
	<li>可嵌套任意标签</li>  
</ul>

// 有序列表：
<ol>
	<li>可嵌套任意标签</li>
</ol>

// 自定义列表：
<dl>
  	<dt>列表主题，可嵌套任意标签</dt>
   <dd>主题介绍，可嵌套任意标签</dd>
</dl>

// 清除列表自带形式： list-style：none（CSS）

// 表格：
<table border="边框大小属性：数字+px">
   <caption>表格标题，默认加粗</caption>
   <tr> 表格的行
    	<th>表格第一行中的单元格，默认加粗居中</th>
   </tr>
   <tr>
    	<td>表格每行中的单元格</td>
   	</tr>
</table>

// 表格结构：thead头部；tbody主体；tfoot尾部；结构书写于<table>内
// 单元格合并：colspan：水平单元格合并；rowspan：垂直单元格合并；如有书写表格结构，不能跨结构合并单元格
```

### 6. 表单

```html
// 表单验证时，须添加form表单域，才可上传
<form action="表单上传地址">
    	
	文本框：<input type="text" placeholder=“预显示文字内容”>
    
	密码框：<input type="password" placeholder=“预显示文字内容”>
    
	单选：<input type="radio" name=“单选需添加相同名才可生效” checked"默认选中">
    
	多选：<input type="checkbox" checked"默认选中">
    
	文件：<input type="file" multiple"选择多个文件">
    
	下拉：<select name="" id="">
      <option value="" selected默认选中>下拉显示的内容，有几个写几个</option>
      </select>
    
	邮箱: <input type="email">
    
	网址: <input type="url" >
    
	日期: <input type="date" >
    
	时间: <input type="time">
    
	数量: <input type="number">
    
	手机号码: <input type="tel">
    
	搜索: <input type="search">
    
	颜色: <input type="color">
    
	提交按钮：<input type="submit" value="按钮显示内容">
    
	重置按钮：<input type="rest" value="按钮显示内容">
    
	无意义按钮：<input type="button" value="按钮显示内容">
    
</form>


按钮另一种形式：
<button type="button">按钮显示内容</button>  // 默认提交效果
<button type="submit/rest">按钮显示内容</button>

单选/多选时点文字也可选择：
<label for="">  // for属性需删除
	<input type="radio">
</label>
```

### 7. 字符

```html
&copy 版权©️

&nbsp 一个字符的空格； &emsp 两个字符的空格
```

## CSS

### 1. 元素模式/特性

1. 元素模式

> 元素嵌套规则：
>
>  a. 块级元素可做容器嵌套任意标签（p除外，p不能嵌套块级元素）
>
>  b. a可嵌套任意标签（除自身，a不能嵌套a）

- 块级元素

  - 独占一行，可设置宽高
  - 如：div，h1，p，ul，li等

- 行内元素

  - 一行显示多个，不可设置宽高
  - 如span，a，i，em等

- 行内块元素

  - 一行显示多个，可设置宽高
  - 如img，input等

- 元素转换方式

  ```css
  display:block //块级
  display:inline-block //行内块
  display:inline  //行内
  ```

2. 元素特性

> a. 继承性
>
>	子级继承父级元素的文字样式，如自身存在相应样式则不会继承（继承优先级最低）
>
>	特例：a不能继承color属性，h1不能继承font-size属性
>
> b. 层叠行
>
>	父子级中不同样式可叠加，相同样式优先级高的会覆盖优先级低的样式（优先级按CSS选择器进行计算）

### 2. CSS选择器

> a. 选择器优先级
>
>	继承<通配符<标签<类<id<行内式<!important(提高优先级至最高，书写于需要提高的属性值后，分号前；继承属性无法提升)
>
> b. 选择器的叠加计算
>
>	（行内个数，id个数，类个数，标签个数）；个数相同比较下一个，哪一个多优先生效哪一个选择器
>
>	i. 行内1，id1，类0，标签1 与 行内0，id1，类0，标签1 ；优先生效前面的
>
>	ii. 行内0，id1，类0，标签1 与 行内0，id1，类1，标签1 ；优先生效后面的

1. 标签选择器（选择整类标签）

   ```css
   div {css属性+取值}
   ```

2. 类选择器（一个标签可有多个类名，用空格隔开；不能以数字中划线开头）

   ```css
   <div class="IU"> </div>
   
   .IU {CSS属性+取值}
   ```

3. id选择器（id名不能重复使用，故只能选中一个标签，超链接的链接可使用id名跳转本页面的位置）

   ```css
   <div class="IU"> </div>
   
   #IU {CSS属性+取值}
   
   <a href="#IU"></a> //跳转到id为IU的div位置
   ```

4. 通配符选择器（选中所有<body>内的内容）

   ```css
   * {CSS属性+取值}
   ```

5. 后代选择器（选择父级内所有的相关标签，中间用空格隔开，不限于用标签或类名）

   ```css
   <div>
   	<p class="IU">
   		<div class="IU2"></div>
   	</p>
   </div>
   
   div IU {CSS属性+取值} //div中的IU设置样式
   div IU2 {CSS属性+取值} //div中的IU2设置样式
   ```

6. 子代选择器（选择父级中的子级标签，中间用>隔开，只能选择子级，孙子级无法生效）

   ```css
   <div>
   	<p class="IU">
   		<div class="IU2"></div>
   	</p>
   </div>
   
   div>IU {CSS属性+取值} //可生效
   div>IU2 //无法生效
   ```

7. 并集选择器（选择多组不同标签，用，隔开）

   ```css
   <div></div>
   <p></p>
   
   div,p {CSS属性+取值}
   ```

8. 交集选择器（选择同时满足多个元素的标签，中间不隔开）

   ```css
   <div>
   	<p class="IU">
   		<div class="IU2"></div>
   	</p>
   </div>
   
   divIU2 {CSS属性+取值} //需同时满足存在div且div中有IU2才可生效
   ```

9. 结构伪类选择器（通过计算找相应的元素）

   ```css
   <ul>
   	<li></li>
   	<li></li>
   <ul>
   
   li:first-child {CSS属性+取值}  // ul中第一个li
   li:last-child {CSS属性+取值}  // ul中最后一个li
   li:nth-child(n) {CSS属性+取值}  // ul中第n个li
   li:nth-last-child(n) {CSS属性+取值}  // ul中倒数第n个li
   
   <ul>
   	<li><a></a></li>
   	<li><a></a></li>
   <ul>
   li:first-child a {CSS属性+取值}  //ul中第一个li中的a
   
   //n可使用公式进行计算
   	a. 数字+n：数字与数字的倍数都会被选中（如5n：第5/第10元素会被选中）
   	b. 数字n+1:数字与数字的倍数+1都会被选中（如5n：第6/第11元素会被选中）
   	c. -n+数字：找到数字前的几个元素（如-n+5:前5个元素会被选中，包含第5个）
   	d. n+数字：数字后的几个元素（如n+5:第5个后的元素会被选中，不包含第5个）
   ```

10. hover伪类选择器（改变光标悬停时的元素样式）

    ```css
    <div>
    	<p class="IU"></p>
    </div>
    
    .IU:hover {CSS属性+取值}
    ```

### 3. 盒子样式

>	盒子样式分为：内容区域，边框，内边距，外边距；设置盒子样式默认会撑大盒子本身

1. 内容区域content（由盒子宽高组成）

   ```css
   width //盒子宽
   height //盒子高
   ```

2. 边框

   ```css
   border:"边框线大小（数字+px） 边框样式 颜色"
   	边框样式：solid实线； dashed虚线； dotted点线；
   
   // 可通过方位词设置单个方向的边框样式
   	border-top上； border-right右； border-bottom下； border-left左；
   ```

- 边框圆角

  ```css
   border-radius:"数字+px/百分比（圆角半径）"
   // 最多可取四个值，按顺时间：左上-右上-右下-左下
   // 如有一角无取值，则看对角设置的值
  ```

3. 内边距（与边框一致，可通过方位词设置单个方位）

   ```css
   padding:"数字+px"
   	// 最多可取四个值，按顺时间：上右下左
   	// 取三个值，按上，左右，下设置
   	// 取两个值，按上下，左右设置
   ```

4. 外边距（与边框一致，可通过方位词设置单个方位）

   ```css
   margin:"数字+px"
      // 最多可取四个值，按顺时间：上右下左
   	// 取三个值，按上，左右，下设置
   	// 取两个值，按上下，左右；左右可去auto（居中）
   ```

5. 盒子阴影

   ```css
   box-shadow:"数字+px 数字+px 数字+px 数字+px 颜色 阴影位置"
      // 第一个值为：水平偏移量（必写）
      // 第二个值为：垂直偏移量（必写）
      // 第三个值为：模糊度（可不写）
      // 第四个值为：阴影扩大（可不写）
      // 第五个值为：颜色（可不写）
      // 第六个值为：阴影位置（可不写，默认外阴影，inset为内阴影）
   ```

6. BUG

   ```css
   a. 盒子撑大解决方式：
   	box-sizing:"border-box"
   b. 清除浏览器自带内外边距：
   	*{margin:0,padding:0}
   c. 父子级中，子级设置margin-top会作用于父级，子级无法生效:
      i. 给父级添加 overflow-hidden；
      ii. 设置浮动
   ```


### 4. 字体样式

> font可作为复合属性:
>
>	font：italic 700 数字+px 类型（顺序不能更改，前两个值可不写为默认值）
>
>	行高可写在size后面，用“/”隔开

1. 字体大小

   ```css
   font-size:"数字+px" // 浏览器默认字体大小为16px
   ```

2. 字体粗细

   ```css
   font-weight:"400（正常）/700（加粗）"  //h1自动加粗的字体可用此取消加粗
   ```

3. 字体样式

   ```css
   font-style:"italic（倾斜）/normad（不倾斜）" // 样式自带倾斜用此清除
   ```

4. 字体类型

   ```css
   font-family:"字体类型"  // 多个类型中间用空格隔开，需最后添加“sans-serif”
   ```

5. 字体颜色

   ```css
   font-color:""
      // 颜色名（red）；rgb；rgba（a为透明度，范围0-1之间）；16进制表示法
      // rgb的表述形式为：rgb(0,0,0)【0,0,0为纯白，255,255,255为纯黑】
   ```

6. 行高

   ```css
   line-height:"数字+px/数字"  // 单独的数字代表当前文字大小的倍数
   ```

7. 文字水平对齐

   ```css
   text-aligntext:"left左/center居中/right右"  // 给父级添加
   ```

8. 文本缩进

   ```css
   text-indent:"数字+px/数字+em"  // em为当前文字大小，如2em：当前2个文字大小缩进
   ```

9. 字体修饰线

   ```css
   text-decoration:""
   	underline下划线；line-through删除线；overline上划线；none无修饰
   	// none可清除自带修饰线的格式，如a的下划线等
   ```

### 5. 背景样式

> background可作为复合标签使用
>
> background：color image repeat position（空格隔开每个取值）

1. 背景颜色

   ```css
   background-color:""  // transparent无背景色
   ```

2. 背景图片

   ```css
   background-image:url="图片地址"
   ```

3. 背景图样式

   ```css
   background-repeat:""
   	no-repeat不平铺；repeat-x，repeat-y：沿x或y轴平铺
   ```

4. 背景图位置

   ```css
   background-position:"水平位置 垂直位置"  // 两个取值用空格隔开
       取值：数字+px/方位名词（left左，center中，right右，top上，center中，bottom下）
    	  // center可只写一个，会水平垂直居中显示 
   	  // 取值为数字时：往左为正数，往下为正数 
   ```

5. 背景图大小

   ```css
   background-size:"宽 高" // 两个取值用空格隔开
   	取值：数字+px；百分比；contain等比例缩放（包含，宽高其中一个充满盒子则停止缩放）；cover等比例缩放（覆盖，不留空白）
       // 背景图的包装标签常设置与图片同等宽高，基本使用contain/cover即可
   ```

6. 精灵图

   >a. 设置一个盒子与图片大小相同（宽高）
   >
   >b. 将精灵图设置为背景图
   >
   >c. 使用background-position调整图片位置（用数字+px取值)

7. 渐变背景

   ```css
   background-image:linear-gradient(颜色1,颜色2,...) ;
   
   background-image:linear-gradient(transparent,rgba(0,0,0,0.5));  // 半透明效果（常用）
   ```

### 6. 伪元素

> 使用CSS模拟出的:行内元素效果
>
>	⚠️伪元素必须添加content""；否则无法生效，无文本内容引号内可留空

```css 
<div>
	<p></p>
</div>

p::after {content"",CSS属性+取值}  //在p标签最后添加一个伪元素
p::befor {content"",CSS属性+取值}  //在p标签最前添加一个伪元素
```

### 7. 浮动

> 网页中最长用的布局方式

```css
<div class=clearfix>
	<div class=left></div>
	<div class=right></div>
</div>

.left {float:left}  // 浮动到父级的左边
.right {float:right}  // 浮动到父级的右边

⚠️ 上例中，若div父级不设置高度，浮动无法生效，需清除浮动效果
	.clearfix::befor,
	.clearfix::after {content"";display:block;}
	.clearfix::after {clear:both;}
```

### 8. 定位

> a. 定位需配合：方位+数字px 移动使用
>
> b. 一般定位采用：子绝父相
>
> c. 元素层级关系：标准流<浮动<定位（标准流：浏览器默认的排列方式）
>
> d. 同层级关系：后面的内容会压住前面的内容（定位情况下）
>
> e. 可用z-index:数字 提升显示优先级，数字越大越优先（需配合定位才能生效）

1. 相对定位

   ```css
   position:relativ  //会占用标准流位置，根据原有位置进行移动
   left/right:
   top/bottom:
   ```

2. 绝对定位

   ```css
   position:absolute  //不会占用标准流位置，根据已定位的父元素进行移动，会改变元素模型为：行内块
   left/right:
   top/bottom:
   ```

3. 固定定位

   ```css
   position:fixed  //不会占用标准流位置，固定于页面某一位置
   left/right:
   top/bottom:
   ```

4. 绝对定位居中

   ```css
   <div>
   	<div class=center></div>
   </div>
   
   div {position:relativ}  //子绝父相
   .center {
      position:absolute;
      left:50%;
      top:50%;
      transform:translate(-50%,-50%);}
   ```

### 9. 溢出效果

```css
overflow:hidden溢出部分隐藏  // 也可使用该形式解决浮动/内外边距问题
overflow:scroll无论是否溢出都显示滚动条
overflow:auto自动显示滚动条
```

### 10. 元素效果

1. 元素透明

   ```css
   opacity:0-1（0为透明，1为不透明）
   	// 可使用hover进行效果制作
   ```

2. 元素隐藏

   ```css
   display:none（不占用标准流）
   	// 配合hover实现光标悬停显示；hover中设置display：black
   visibility:hidden（占用标准流，不常用）
   ```

### 11. 过渡效果

> 配合CSS3的位移/旋转等使用

```css
transition:all 数字+s  // 过渡写在需要过渡效果的选择器内
    // all表示所有可以过渡的属性都有过渡效果，也可单独设置需要过渡效果的属性名（如width等）
    // 数字+s为过渡的时间
```

### 12. 光标效果

```css
cursor:pointer（小手，可跳转，与超链接自带效果相同）
cursor:text（工字，可复制文本）
cursor:move（十字，可移动图片）
```

### 13. 基线

> 作用于头像与文字不在同一水平的情况

```css
vertical-align:top // 顶部对齐
vertical-align:middle // 中对齐
vertical-align:bottom // 底部对齐
```

## CSS3

### 1. 字体图标

> a. 本质：展示的为图标，实质为文字，可修改大小/颜色等
>
> b. 使用方法：
>
>	i. 下载字体包：[字体图标网](https://www.iconfont.cn/)
>
>	ii. 引入字体图标：<link rel="stylesheet" href="下载字体包中的 iconfont.css 文件">
>
>	iii. 调用图标对应的类名，必须调用两个类名：<div class="iconfont icon-xxx"></div>

![字体图标类名](./image/iconfont.png)

### 2. 转换效果

1. 位移

   a. 平面转换

   ```css
   transform: translate(X,Y);  // 取值：数字+px/百分比
   	X：往右正数 Y：往下正数
   	// 如果只写一个值，表示x轴方向移动
   
   transform: translateX() x轴移动
   transform: translateY() y轴移动
   transform: translateZ() Z轴移动
   ```

   b. 空间转换

   ```css
   transform: translate3d(X,Y,Z);
   	Z：正数,内容变大
   
   perspective: 取值范围800-1200px;  // 空间转换需配合:perspective属性实现透视效果（近大远小）
   	// 属性添加给父级
   ```

2. 旋转

   > a. XY轴旋转需配合perspective实现效果
   >
   > b. 左手法则：
   >
   >	i. 用左手握住旋转轴，大拇指指向平面正数方向，手指弯曲方向为正数
   >
   >	ii. Y轴往下为正，X轴往右为正
   >
   > c. 同时存在多个转换效果：
   >
   >	transform: translate() rotate() ;
   >
   >	// 多重转换涉及旋转的情况，旋转属性最后书写；

   a. 平面旋转

   ```css
   transform: rotate(角度+deg);  // deg为单位; 正数为顺时间，负数为逆时针
   	// 须配合过渡属性才能实现旋转
   ```

   b. 空间旋转

   ```css
   transform: rotateZ(角度+deg); Z轴旋转  // 与平面旋转效果相同
   transform: rotateX(角度+deg); X轴旋转
   transform: rotateY(角度+deg); Y轴旋转
   
   transform: rotate3d(X,Y,Z+deg);  //设置自定义旋转轴的位置和角度
   	// X,Y,Z取值为0-1
   ```

   c. 改变转换原点

   ```css
   transform-origin:原点水平位置 原点垂直位置;  // 两个取值空格隔开
   	取值：方位名词（常用）/数字+px/百分比
   	// 书写在标签本身，不写在hover中
   ```

3. 缩放

   >  [平面效果.html](案例/平面效果.html) 

   a. 平面缩放

   ```css
   transform: scale(缩放倍数：数字 不需要单位);
   	// 取值大于1为放大，取值小于1为缩小
   ```

   b. 空间缩放

   ```css
   transform: scaleX(倍数)
   transform: scaleY(倍数)
   transform: scaleZ(倍数)
   transform: scale3d（x,y,z）
   ```

4. 立方体

   > [3D导航案例.html](案例/3D导航案例.html) 

   ```css
   transform-style: preserve-3d;  // 给父级添加
   
   呈现立体图形步骤:
   	a. 给父级添加：transform-style: preserve-3d;
   	b. 将内容定位到相对位置
   	c. 给前面的内容添加： transform: translateZ();让前面内容显示在页面
   	d. 添加：hover-transform: rotateX/Y()，光标悬停旋转
   ```

### 3. 动画

> a. 多组动画的情况下，在第一个动画属性值后用逗号隔开再添加属性值即可
>
> b. 配合过渡效果使用

![动画属性与取值](./image/ani.png)

1. 定义动画

   ```css
   @keyfoames 动画名称（自定义）{
   	form {开始的CSS样式}
   	to {结束的CSS样式}
   }   // 两个动画的效果
   
   @keyframes 动画名称（自定义）{
      0% {}
      10% {}
      15% {}
      100% {}
   }   // 多个动画的效果; 百分比数值可以自定义（动画总时长的占比）
   ```

2. 使用动画

   ```css
   animation:动画名称 动画时长 速度曲线 延迟时间 重复次数 动画方向 执行完毕时状态;
       // 动画名称和动画时长必须赋值；取值不分先后顺序；
       // 存在两个时间值的情况下，第一个为动画时长，第二个为延迟时间
   
   	速度曲线：linear匀速；steps(数字)按数字分步实现动画；
   	延迟时间：数字+s；
   	重复次数：数字/infinite（无限循环）
   	动画方向：alternate（反向，使动画均匀变化）
   	执行完毕时状态：forwards（停留在最终状态）；backwards（默认，回到最初状态）
	// 尽量不与重复次数和动画方向同时书写
   ```

3. 暂停动画

   ```css
   animation-play-state:paused 暂停动画   // 配合hover使用，书写于hover内
   ```

### 4. 移动端

> a. 移动端一般使用iphone6/7/8 （375*667）的尺寸进行设计
>
> b. 视口宽=手机宽

1. 利用媒体查询检测视口宽度

   >  [flexible.js](视口/flexible.js)  引入该js文件后可省略媒体查询，自动适配

   ```css
   @media（媒体属性）{                     @media（width：设备宽度）{
       选择器{CSS属性}                         html {font-size:需要设置的字号;}
   ```

2. rem

   > i. rem单位：相对单位；依据HTML标签的字号计算尺寸；
   >
   > ii. 1rem=1HTML字号大小=1/10视口宽度   /* 375宽的设备为1rem=37.5 */

3. vw/vh

   > i. vw:viewport width;   vh:viewport hight;
   >
   > ii. 1vw=1/100视口宽度；  1vh=1/100视口高度；  /* 375宽的设备为1vw=3.75 */
   >
   > iii. vw/vh不同时设置，取其一即可 

### 5. Flex布局

> a. 弹性容器，移动端常用的布局方式，可避免浮动脱标的情况
>
> b. [搜索代码兼容性网站](https://www.caniuse.com)

1. 启用Flex布局

   ```css
   display:flex  // 给父级添加，子元素会自动拉伸或挤压； 默认主轴：水平；
   ```

2. 主轴对齐方式

   ```css
   主轴对齐方式：justify-content: ;   // 给父级添加 
       centent居中；space-around子级之间的距离是父级两头距离的2倍；
       space-between间距在弹性盒子(子级)之间；space-evenly所有地方的间距都相等
   ```

3. 侧轴对齐方式

   ```css
   align-itmes:;  // 都给父级添加
       centent居中；stretch默认值，子级不设置高度的情况下会拉伸子级盒子高度至父级高度
   
   align-self:;  // 单独控制某一个子级在侧轴的对齐方式,给需要控制的子级添加；取值与上相同
   ```

4. 弹性盒子占比

   ```css
   flex:数字（正数）;   // 扣除父级已用的范围，剩余尺寸的份数，书写于需要伸缩的子级内
       // flex属性可以修改弹性盒子伸缩比
   
   <div class=flex>
   	<div></div>
   	<p></p>
   </div>
   
   .flex {width:200px;display:flex;}
   .flex div {width:100px}
   .flex p {flex:1}  // flex盒子扣除子级div后剩下的100px尺寸都给p标签
   ```

5. 改变主轴方向

   ```css
   flex-direction:column;   // 修改主轴方向为垂直
   	 // row默认水平（忽略不写即可）
   ```

6. 换行排列

   ```css
   flex-wrap:wrap;  // 换行排列，不挤压弹性盒子
      // nowrap默认不换行；
   ```

7. 调节行的对齐方式

   ```css
   align-content:;  // 与wrap配合使用
       centent居中；space-around子级之间的距离是父级两头距离的2倍；
       space-between间距在弹性盒子(子级)之间；
   ```

8. 溢出文本内容省略号显示

   ```css
   a. 一行显示，超出显示省略号
   	text-overflow:ellipsis;
   	white-space:nowrap;
   	overflow:hidden;
   	// 再给父级添加 flex:1; widht:0;
   
   b. 两行显示，超过显示省略号
       overflow: hidden;  // 超出的文本隐藏
       text-overflow: ellipsis; // 溢出用省略号显示
       white-space: nowrap; // 溢出不换行
       display: -webkit-box; // 将对象作为弹性伸缩盒子模型显示。
       -webkit-line-clamp: 2; // 这个属性不是css的规范属性，需要组合上面两个属性，表示显示的行数。
       -webkit-box-orient: vertical;  // 从上到下垂直排列子元素（设置伸缩盒子的子元素排列方式）
   ```

### 6. Less语法

> a. CSS的预处理器，可扩充CSS语言，使CSS具备一定的逻辑性、计算能力，更加方便的书写CSS
>
> b. vscode中插件：Easy less；文件后缀（.less)
>
> c. 浏览器不识别less，less文件保存后会自动生成CSS文件，引入CSS文件即可
>
> d. 加、减、乘可直接书写，除需添加括号  // 如width{100/10rem} 100除以10rem的宽

1. 嵌套书写

   ```css
   // 可快速书写后代选择器
   .father {color:red;
     .son {color:pink;
     	&:hover {color:blue}.  // &表示当前选择器，例子中hover为 .son的hover
     }  // 在父级中添加子级，less会自动生成 
   }
   ```

2. 设置变量

   ```css
   <div></div>
   
   定义变量：
   	@color:red;
   使用变量:
   	div {color:@color} // 颜色即可变成定义变量中的颜色
   ```

3. less导入

   ```css
   @import "文件路径";    //  如果导入是less文件可省略后缀.less
   ```

4. less导出

   ```css
   方法一：
   vscood设置-搜索：easy-在json中打开加上下列代码
        "less.compile": {
         "out": "CSS文件夹路径"  // 注意结尾加/表示文件夹
       }
   
   方法二：
   less文件第一行中书写：
       // out: 需要导出的文件夹路径
       // out:xx文件夹/xx.css  // 将less文件导出到xx文件夹中生成xx.css文件
   
   less禁止导出：文件第一行中书写：// out:false 
   ```

### 7. 媒体查询

> 用于检测视口宽度，响应式网页常用的一种方式

```css
@media（媒体特性）{  //媒体特性常用写法：max-width（<=）；min-width（>=）
   选择器{CSS属性}
}  //  min-width从小到大按顺序书写；max-width从大到小按顺序写 

媒体查询的完整写法：（了解即可）
    @media 关键词 媒体类型 and （媒体特性） {CSS代码}
    关键词：and（两个条件）；only（一个条件）；not（非这个条件外的其他条件）
    媒体类型：screen（屏幕）；print（打印预览）；speech（阅读器）；all（不区分类型）
    媒体特性：max-width；min-width；orientation（屏幕方向）
        		portrait（竖屏）；landscape（横屏）

引入CSS文件时设置媒体查询即仅让该CSS文件生效：
    <link rel="stylesheet" href="./two.css" media="(min-width: 1200px)">   // 仅让two样式表生效

响应式网页隐藏元素方式：
    @media (媒体特性) {
    	xx选择器 {display: none;}
    }
```

### 8. BootStrap

> a. BootStrap是一种前端UI框架，能够快速完善网页与交互效果 [BootStrap网站](https://www.bootcss.com)
>
> b. 先引入Bootstrap在引入自己的css文件，如此不满意的样式可用自己的样式覆盖
>
> c. 使用步骤：
>
>	i. 下载官网中的：bootstrap3文档
>
>	ii. 引入bootstrap中的CSS代码：bootstrap.css / bootstrap.min.css两者都可
>
>	iii. 调用类名

1. 栅格系统

   > 将网页等分为12份，通过设置份额来排列容器

   ```css
   // 下列*代表盒子占12分中的几份则为几，无单位
   超小屏<768 : 类名前缀col-xs-*；
   小屏幕>=768: 类名前缀col-sm-*；
   中屏幕>=992: 类名前缀col-md-*；
   大屏幕>1200: 类名前缀col-lg-*；
   ```

2. BootStrap类名

   ```css
   container：版心样式，自带左右15px的padding；
   row：自带间距-15px的padding;  // 在container里新加一个子级类名为row
   container-fluid：宽度100%，自带左右15px的padding；
   ```

3. BootStrap样式使用

   >a. [bootstrap CSS样式](https://v3.bootcss.com/css/)
   >
   >b. [bootstrap 组件样式](https://v3.bootcss.com/components/)
   >
   >c. [bootstrap js插件](https://v3.bootcss.com/javascript/)
   >
   >d. [bootstrap 个人定制](https://v3.bootcss.com/customize/)

   ```css
   Bootstrpa插件使用步骤：// CSS/js文件可用bootstrap/bootstrap.min 两者内容相同
   
   a.引入样式表  <link rel="stylesheet" href="bootstrap.css">
   
   b. 引入js文件  // 按顺序引入，js文件引入写body最后
   <script src="./js/jquery.js"></script>
   <script src="./bootstrap-3.4.1-dist/js/bootstrap.js"></script>
   ```

## JS

> a. JS是一门高级编程语言（也可称为脚本语言），通过js引擎转变成机器语言进行执行。
>
> b. JS的组成
>
>	i. JS语法
>
>	ii. DOM-页面文档对象模型
>
>	iii. BOM-浏览器对象模型

### 1. JS书写形式

> JS中使用单引号书写

1. 行内式

   ```html
   <input type="button" value="按钮显示的文字" 	onclick="alert('弹框显示的内容')"
   	// onclick：点击  alert：弹框
   ```

2. 内嵌式

   ```javascript
   // 写在<head>中
   <script>
     alert('弹框显示的内容')
   </script>
   ```

3. 引入式

   ```javascript
   // 写在<head>中
   a. 创建一个js文件
   b. 引入 <script scr="js文件地址"></script>
   ```

### 2. 注释

> a. 单行注释 //xxx  
>
>	快捷键：“ctrl+/”
>
> b. 多行注释 /* xxx */
>
>	快捷键：“shift+alt+a” 【VScode中可以自定义快捷键】

### 3. 输入输出语言

|      代码形式      |                    说明                    |
| :----------------: | :----------------------------------------: |
|    alert（msg）    |              浏览器弹出警示框              |
| console.log（msg） | 浏览器控制台打印输出信息(浏览器检查中可看) |
|   prompt（info）   |        浏览器弹出输入框，用户可输入        |

```javascript
prompt('弹出输入框显示的标题内容')
alert('弹出警示框显示的内容')
console.log('检查元素中显示的内容')
```

### 4. 变量

> 用于存放数据的容器，通过变量名获取数据

1. 变量的使用

   >a. 声明变量
   >
   >	var age; // 声明一个名称为age的变量，变量名可自行设置  
   >
   >b. 赋值（把值存入变量中）
   >
   >	age = 18; // 给age变量赋值为18
   >
   >c. 变量初始化（将声明变量与赋值同时书写）
   >
   >	var age = 18;  //声明变量同时赋值18
   >
   >// 可通过console.log(age);检查是否赋值成功
   >
   >// 除数字外，其他内容用''包裹，如：var name = ’知恩‘；

   ```javascript
   <script>
   	var myname = prompy('输入用户名') // 用户输入后存储到myname变量中
   	alert(myname) // 弹出用户输入的信息内容
   </script>
   ```

2. 变量语法扩展

   1. 变量更新

      ```javascript
      var name = '知恩'；
      name = 'IU'   // 后面的IU会覆盖前面的知恩
      ```

   2. 声明多个变量

      ```javascript
      var age = 18 ,  // 多个变量中间用逗号隔开
          address = '地址名',
          name = '用户名';  // 最后用分号结尾
      ```

   3. 声明变量的特殊情况

      ```javascript
      a. 只声明，不赋值
      	var name；  // 输出后结果为 undefined（未定义）
      b. 不声明，不赋值
      	// 输出后会报错
      c. 不声明，只赋值
      	// 可以输出相应结果，但会变成全局变量，不如此使用
      ```

3. 变量命名规范

> a. 由字母、数字、下划线、美元符号（$）组成，如：num_01。//不能以数字开头，会报错
>
> b. 严格区分大小写,var app/var App 是两个变量
>
> c. 不能是关键字、保留字，如：var for while
>
> d. 变量名必须有意义，如：nl（年龄） // 不如此设置变量名
>
> e. 遵守驼峰命名法；首字母小写，后面的首字母需要大写，如myFirstName
>
> f. 翻译网站：[有道](https://fanyi.youdao.com/) [爱词霸](http://www.iciba.com/)
>
> g. name有特殊含义，不使用name作为变量名

```javascript
交换两个变量值
设置一个场景：apple1为青苹果，apple2为红苹果，将红苹果给apple1，青苹果给apple2

a. 设置一个临时变量
   var temp；  // 声明一个临时变量赋值为空
   var apple1 = '青苹果'；
   var apple2 = '红苹果'；
b. 将青苹果放入临时变量
	temp = apple1；
c. 将红苹果给apple1
	apple1 = apple2；
d. 把临时变量中的青苹果给apple2
	apple2 = temp；
```

### 5. 数据类型

> a. JS的变量数据类型是只有程序在运行过程中，根据等号后面的值来确定
>
> b. JS是动态语言，变量的数据类型是可变化的
>
> c. var x = 10；x为数字型 ； var x = 'IU' x为字符串型

1. 简单数据类型

   | 数据类型  |                     说明                     |   默认值   |
   | :-------: | :------------------------------------------: | :--------: |
   |  Number   |    数字型，包含整型值与浮点型值，如5，0.5    |     0      |
   |  Boolean  |        布尔值类型，如true=1，false=0         | false（0） |
   |  string   |     字符串类型，如"知恩"，字符串都带引号     |     ""     |
   | Undefined | var a;声明了变量a但没有赋值，此时a=undefined | Undefined  |
   |   Null    |       var a = null; 声明了变量a为空值        |    null    |

   1. 数字型（Number）

      > a. 八进制（范围0～7）
      >
      > var num = 010 // 输出为8
      >
      > b. 十六进制（范围0～9；A～F）
      >
      >var num =0xA // 输出为10
      >
      > c. JS中八进制前面加0，十六进制前面加0x；

      1. 数字范围

         ```javascript
         Number.MAX_VALUE;  // 最大值
         Number.MIN_VALUE;  // 最小值
         ```

      2. 三个特殊值

         ```javascript
         Infinity；  // 无穷大（Number.MAX_VALUE * 2）
         -Infinity；   //无穷小（-Number.MAX_VALUE * 2）
         NaN；  // 非数字
         ```

      3. isNAN

         ```javascript
         用来判断一个变量是否为非数字类型；输出false则为数字；输出true则为非数字；
         
         var IU = 12;
         var isok = isNAN(IU);
         console.log (IU);   // 输出为false
         
         var IU ='IU';
         console.log (isNAN(IU));   // 输出为true
         ```


   2. 字符串型（string）

      > a. 字符串型可以是引号中的任意文本，只要是单引导/双引号中的文本内容都为字符串
      >
      > b. 引号嵌套：单引号嵌套双引号 or 双引号嵌套单引号（外双内单/外单内双）

      1. 字符串转义符(转义符都需加`\`)

         | 转义符 | 解释说明 |
         | :----: | :------: |
         |  `\n`  |  换行符  |
         |  `\\`  |  斜杠\   |
         |  `\'`  | 单引号'  |
         |  `\"`  | 双引号"  |
         |  `\t`  | tab缩进  |
         |  `\b`  |   空格   |

      2. 字符串长度

         ```javascript
         通过length属性获取整个字符串长度
         
         var str = 'my name is IU';
         console.log(str.length);   // 显示为15个字符，每个空格也算1个字符，如有标点符号也算一个字符
         ```

      3. 字符串拼接

         ```javascript
         多个字符串可用+进行拼接；如：字符串+任何类型=拼接后的新字符串
         
         console.log('沙漠'+'骆驼');  // 输出为 沙漠骆驼
         console.log('IU'+ 18);   // 输出为 IU18
         console.log(12 + 12);   // 输出为24 前面为数字型则为加法算数
         console.log('12' + 12);  // 输出为1212 前面加单引号则为字符串，相加则为新的字符串
         
         var age =18;
         console.log('IU' + age + '岁');  // 输出为IU18岁；变量不能直接写在字符串内（变量不能加引号），否则会报错
         ```

   3. 布尔型（Boolean）

      ```javascript
      a. ture表示真的，在加法运算中当1计算；
      console.log(true + 1);  // 输出为2
      
      b. false表示假的，在加法运算中当0计算；
      console.log(false + 1);  // 输出为1

   4. 未定义数据类型（undefined）

      ```javascript
      // 声明变量后没有赋值的情况会有一个默认值：undefined
      
      a. console.log(undefined + 'IU');  // 输出为undefinedIU
      
      b. console.log(undefined + 1);  // 输出为NaN（非数字型）
      ```

   5. 空值（Null）

      ```javascript
      // 声明变量给null值，里面存储的值为空值
      
      a. console.log(Null + 'IU');  // 输出为NullIU
      
      b. console.log(Null + 1);  // 输出为1
      ```

2. 获取变量数据类型

   > a. 利用typeof进行获取数据类型
   >
   > b. 可通过浏览器检测面板进行判读
   >
   >	i. 浅蓝色为数字型
   >
   >	ii. 黑色为字符串型
   >
   >	iii. 深蓝色为布尔型
   >
   >	iv. 灰色为空值/为定义数据类型
   >
   > c. 通过表单/prompt获取的数据默认是字符串型

   ```javascript
   var num =10;
   console.log(typeof num);  // 输出为number数字型
   
   var str ='IU';
   console.log(typeof str);  // 输出为string字符串型
   
   var str = prompt('请输入你的信息')； // 不论用户输入的内容是什么都为字符串型
   ```

3. 数据类型转换

   1. 转换为字符串类型

      ```javascript
      a. .toString()
         var num = 1；
         console.log(num.toString());  // 输出为1字符串型；toString括号内可为空
        
      b. String()  // 强制转换
         var num = 1；
         console.log(String(num));  // 输出为1字符串型
        
      c. 加号拼接字符串（隐式转换）【常用】
         var num = 1；
         console.log(num + '');  // 输出为1字符串型
      ```

   2. 转换为数字型

      ```javascript
      a. parseIut(string)  // 可以把字符串转换为数字型（只能为整数）
         console.log(parseInt('19'));  // 输出为19
         console.log(parseInt('3.94'));  // 输出为3，小数会自动舍去小数点后的内容取前面的整数
         console.log(parseInt('120px'));  // 输出为120，120px会自动去掉px单位
         console.log(parseInt('rem120px'));  // 输出为NaN，因为前面为rem，120px会自动去掉
      
      b. parseFloat(string)  // 可以吧字符串转变成数字型（可以为小数）
         console.log(parseFloat('3.14'));  // 输出为3.14
         console.log(parseInt('120px'));  // 输出为120，120px会自动去掉px单位
         console.log(parseInt('rem120px'));  // 输出为NaN，因为前面为rem，120px会自动去掉
      
      c. Number()
         console.log(Number('3.14'));  // 输出为3.14
      
      d. js隐式转换（- * /）【算数运算】
         console.log(parseFloat('3.14' - 0));  // 输出为3.14
         console.log(parseFloat('123' - '120'));  // 输出为3
      ```

   3. 转换为布尔型

      ```javascript
      Boolean()  // 空/否定的值会转换成false，如：0、NaN、null、undefined，其他值都会转换成true；
      
      Boolean(''); // 输出为false
      Boolean('0'); // 输出为false
      Boolean(12); // 输出为ture
      Boolean(IU); // 输出为ture
      ```

4. 编译型语言与解释型语言

   > a. 编译型语言是整体代码编译完成后在进行翻译再执行
   >
   > b. 解释型语言是边输入代码边翻译边执行

5. 标识符/关键字/保留字

   > a. 标识符是指开发人员为变量、属性、函数、参数取的名字，标识符不能是关键字或保留字
   >
   > b. 关键字是指JS本身已经使用过的字，不能再用她们充当变量名、方法名，如：break、case、else、do、delete等
   >
   > c. 保留字实际上为预留的”关键字“，同样不能使用它们当变量名、方法名，如：class、byte、const、float、fimal、int等

### 6. 运算符

> a. 也被称为操作符，用于实现赋值、比较、执行算数运算等功能的符号
>
> b. 可用双等号进行验算
>
> ​var num = 1 + 1;
>
> ​console.log(num == 2); // 输出为true为正确，输出false为错误

1. 算数运算符

   ```javascript
   a. 加号（+）
      console.log(1 + 1); // 输出为2
   
   b. 减号（-）
      console.log(1 - 1); // 输出为0
   
   c. 乘号（*）
      console.log(1 * 1); // 输出为1
   
   d. 除号（/）
      console.log(1 / 1); // 输出为1
   
   e. 取余（%）
      console.log(5 % 3); // 输出为2
      console.log(3 % 5); // 输出为3
   
   // 浮点数在算数运算中会出现问题，尽量避免浮点数计算
   console.log(0.1 + 0.2); // 输出为0.30000000000000004
   
   // 表达式：由数字、运算符、变量组成的式子
   // 返回值：由表达式返回的值
   console.log(1 + 1);  表达式
   ==>2  返回值
   // 在程序中 2 = 1 + 1； 将程序中右边表达式计算完毕后把返回值给左边
   ```

2. 递增与递减运算符

   > 递增（++）与递减（--）必须配合变量使用，可放在变量前（前置递增/递减）；也可放在变量后（后置递增/递减）

   1. 前置递增/递减（先自加/自减，后运算）

      ```javascript
      var num = 1;
      //递增
      ++num； // 等价于num = num + 1；输出为2
      console.log(num); // 输出为2 
      console.log(++num + 10); // 输出为12，先加1后返回值，先计算++num
      
      //递减
      --num； // 等价于num = num - 1；输出为0
      console.log(num); // 输出为0
      console.log(--num + 10); // 输出为10，先减1后返回值
      ```

   2. 后置递增（先返回原值，后自加）

      ```javascript
      var num = 1;
      //递增
      num++； // 输出为2
      console.log(num); // 输出为2
      console.log(num++ + 10); // 输出为11，先返回原值后自加1
      console.log(num); // 输出为2
      
      //递减
      num--； // 输出为0
      console.log(num); // 输出为0
      console.log(num-- + 10); // 输出为11，先返回原值后自减1
      console.log(num); // 输出为0
      ```

   ❤️ 案例

   ```javascript
   ⚠️ ++a/a++单独书写时结果相同，与其他代码连用时结果不同
   
   var a =10;
   ++a; // ++a = 11 ; a = 11
   var b = ++a + 2; // ++a = 12 ; a = 12 ; b = 14
   console.log(b);  // 14
   
   var c =10;
   c++; // C++ = 11 ; c = 11; 
   var d = c++ + 2;  // c++ = 11, c = 12 , d = 13
   console.log(d); // 13
   
   var e =10;
   var f = e++ + ++e; 
      // 1. e++ = 10 ; e = 11 ; 先计算e++，后置先返回原值为10，后自加1得到e为11
      // 2. e = 12 ; ++e = 12 ; 前置先自加1得到e为12，后返回值为12
      // f = 22
   console.log(f); // 22
   
   var g = 10;
   --g; // --g = 9 ; g = 9
   var h = --g + 2; // --g = 8 ; g = 8 ; h = 10;
   console.log(h); // 10
   
   var c =10;
   c--; // c-- = 9 ; c = 9; 
   var d = c-- + 2;  // c-- = 9, c = 8 , d = 11
   console.log(d); // 11
   
   var e =10;
   var f = e-- + --e;
   	// 1. e-- = 10 ; e = 9;
   	// 2. e = 8 ; --e = 8;
   	// 18
   console.log(f); //18 
   ```

3. 比较运算符

   > a. “=”作用为赋值，把后边给左边
   >
   > b. “==”判断，判断两边值是否相等（注意这里会默认转换数据类型）
   >
   > c. “===”全等，判断两边的值和数据类型是否完全相同

   | 运算符 |            说明            |    案例     | 结果  |
   | :----: | :------------------------: | :---------: | :---: |
   |   <    |           小于号           |     1<2     | true  |
   |   >    |           大于号           |     1>2     | false |
   |   >=   |         大于等于号         |    2>=2     | true  |
   |   <=   |         小于等于号         |    3<=2     | false |
   |   ==   | 判等号（默认转换数据类型） |  37=='37'   | true  |
   |   !=   |           不等号           |  37 != 37   | false |
   |  ===   | 全等要求值和数据类型都一致 | 37 === '37' | false |
   |  !==   |           不全等           |  37 !== 37  | fasle |

4. 逻辑运算符

   | 运算符 |   说明   |     案例      |
   | :----: | :------: | :-----------: |
   |   &&   | “与”/and |  true&&false  |
   |  \|\|  | “或”/or  | true\|\|false |
   |   !    | “非”/not |     !true     |

   1. 逻辑与（并且）

      ```javascript
      console.log(3 > 5 && 3 > 2);  // 输出false
      console.log(3 > 2 && 3 < 5);  // 输出true
      // 条件同时满足则为true，只要有一个不满足则为false
      ```

   2. 逻辑或

      ```javascript
      console.log(3 > 5 || 3 > 2);  // 输出true
      console.log(3 > 5 || 3 < 2);  // 输出false
      // 只要有一个条件满足则为true，都不满足则为false
      ```

   3. 逻辑非（取反符）

      ```javascript
      console.log(!true);   // 输出false
      console.log(!false);  // 输出true
      ```

   4. 短路运算

      ```javascript
      // 当有多个表达式（值）的情况，左边的表达式（值）可以确定结果时，不在运算右边的表达式（值）
      
      a. 逻辑与（表达式1&&表达式2）
         i. 如果表达式1为真，则返回表达式2
      	console.log(123 && 456); // 输出结果为456
      	console.log(123 && 456 && 789); // 输出结果为789
      
         ii. 如果表达式1为假，则返回表达式1
      	console.log(0 && 456);  // 输出结果为0
      	// 0、''、null、undefined、NaN都为假
      
      b. 逻辑或
         i. 如果表达式1为真，则返回表达式1
      	console.log(123 || 456); // 输出结果为123
      
         ii. 如果表达式1为假，则返回表达式2
      	console.log(0 || 456); // 输出结果为456
      	console.log(0 || 456 || 789); // 输出结果为456
      
      案例
      var a = 0;
      console.log(123 || a++);  // 输出为123
      console.log(a);  // 输出为0
      
      var a = 1;
      console.log(0 || a++);  // 输出为1，若是++a则输出为2
      console.log(a);  // 输出为2
      ```

5. 赋值运算符

   |   运算符   |         说明         |             案例              |
   | :--------: | :------------------: | :---------------------------: |
   |     =      |       直接赋值       |         var age = 10;         |
   |   +=/-=    | 加/减一个数后在赋值  | var age = 10; age += 5; //15  |
   | *=、/=、%= | 乘、除、取余后在赋值 | var age = 10; age *= 5;  //50 |

6. 运算符优先级

   | 优先级 |   运算符   |    先后顺序     |
   | :----: | :--------: | :-------------: |
   |   1    |   小括号   |      （）       |
   |   2    | 一元运算符 |    ++ -- ！     |
   |   3    | 算数运算符 |  先乘除后加减   |
   |   4    | 关系运算符 |    > >= < <=    |
   |   5    | 相等运算符 | == != === `!==` |
   |   6    | 逻辑运算符 |  先 && 后 \|\|  |
   |   7    | 赋值运算符 |        =        |
   |   8    | 逗号运算符 |        ,        |





