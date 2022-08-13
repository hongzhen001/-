## CSS

### 1. 元素模式/特性

1. 元素模式

> 元素嵌套规则：
>
> a. 块级元素可做容器嵌套任意标签（p 除外，p 不能嵌套块级元素）
>
> b. a 可嵌套任意标签（除自身，a 不能嵌套 a）

- 块级元素

> 独占一行，可设置宽高
>
> 如：div，h1，p，ul，li 等

- 行内元素

>一行显示多个，不可设置宽高
>
> 如 span，a，i，em 等

- 行内块元素

> 一行显示多个，可设置宽高
>
> 如 img，input 等


- 元素转换方式

  ```css
  display: block // 块级
  display: inline-block // 行内块
  display: inline  // 行内
  ```

2. 元素特性

> a. 继承性
>
> 子级继承父级元素的文字样式，如自身存在相应样式则不会继承（继承优先级最低）
>
> 特例：a不能继承color属性，h1不能继承font-size属性
>
> b. 层叠行
>
> 父子级中不同样式可叠加，相同样式优先级高的会覆盖优先级低的样式（优先级按CSS选择器进行计算）

### 2. CSS 选择器

> a. 选择器优先级
>
>继承<通配符<标签<类<id<行内式<!important(提高优先级至最高，书写于需要提高的属性值后，分号前；继承属性无法提升)
>
> b. 选择器的叠加计算
>
>（行内个数，id个数，类个数，标签个数）；个数相同比较下一个，哪一个多优先生效哪一个选择器
>
> i. 行内1，id1，类0，标签1 与 行内0，id1，类0，标签1 ；优先生效前面的
>
> ii. 行内0，id1，类0，标签1 与 行内0，id1，类1，标签1 ；优先生效后面的

1. 标签选择器（选择整类标签）

   ```css
   div {css属性+取值}
   ```

2. 类选择器（一个标签可有多个类名，用空格隔开；不能以数字中划线开头）

   ```css
   <div class="IU"> </div>

   .IU {CSS属性+取值}
   ```

3. id 选择器（id 名不能重复使用，故只能选中一个标签，超链接的链接可使用 id 名跳转本页面的位置）

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

10. hover 伪类选择器（改变光标悬停时的元素样式）

    ```css
    <div>
    	<p class="IU"></p>
    </div>

    .IU:hover {CSS属性+取值}
    ```

### 3. 盒子样式

>     盒子样式分为：内容区域，边框，内边距，外边距；设置盒子样式默认会撑大盒子本身

1. 内容区域 content（由盒子宽高组成）

   ```css
   width //盒子宽
   height //盒子高
   ```

2. 边框

   ```css
   border: '边框线大小（数字+px） 边框样式 颜色' 边框样式：solid实线；
     dashed虚线； dotted点线； // 可通过方位词设置单个方向的边框样式
     border-top上； border-right右； border-bottom下； border-left左；;
   ```

- 边框圆角

  ```css
  border-radius: '数字+px/百分比（圆角半径）'
    // 最多可取四个值，按顺时间：左上-右上-右下-左下
    // 如有一角无取值，则看对角设置的值;; ; ; ; ; ; ; ; ; ; ;
  ```

3. 内边距（与边框一致，可通过方位词设置单个方位）

   ```css
   padding: '数字+px' // 最多可取四个值，按顺时间：上右下左
     // 取三个值，按上，左右，下设置
     // 取两个值，按上下，左右设置;; ; ; ; ; ; ; ; ; ; ;
   ```

4. 外边距（与边框一致，可通过方位词设置单个方位）

   ```css
   margin: '数字+px' // 最多可取四个值，按顺时间：上右下左
     // 取三个值，按上，左右，下设置
     // 取两个值，按上下，左右；左右可去auto（居中）;; ; ; ; ; ; ; ; ; ; ;
   ```

5. 盒子阴影

   ```css
   box-shadow: '数字+px 数字+px 数字+px 数字+px 颜色 阴影位置'
     // 第一个值为：水平偏移量（必写）
     // 第二个值为：垂直偏移量（必写）
     // 第三个值为：模糊度（可不写）
     // 第四个值为：阴影扩大（可不写）
     // 第五个值为：颜色（可不写）
     // 第六个值为：阴影位置（可不写，默认外阴影，inset为内阴影）;; ; ; ; ; ; ; ; ; ; ;
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

> font 可作为复合属性:
>
> font：italic 700 数字+px 类型（顺序不能更改，前两个值可不写为默认值）
>
> 行高可写在size后面，用“/”隔开

1. 字体大小

   ```css
   font-size: '数字+px' // 浏览器默认字体大小为16px;; ; ; ; ; ; ; ; ; ; ;
   ```

2. 字体粗细

   ```css
   font-weight: '400（正常）/700（加粗）' //h1自动加粗的字体可用此取消加粗;; ; ; ; ; ; ; ; ; ; ;
   ```

3. 字体样式

   ```css
   font-style: 'italic（倾斜）/normad（不倾斜）' // 样式自带倾斜用此清除;; ; ; ; ; ; ; ; ; ; ;
   ```

4. 字体类型

   ```css
   font-family: '字体类型' // 多个类型中间用空格隔开，需最后添加“sans-serif”;; ; ; ; ; ; ; ; ; ; ;
   ```

5. 字体颜色

   ```css
   font-color: ''
     // 颜色名（red）；rgb；rgba（a为透明度，范围0-1之间）；16进制表示法
     // rgb的表述形式为：rgb(0,0,0)【0,0,0为纯白，255,255,255为纯黑】;; ; ; ; ; ; ; ; ; ; ;
   ```

6. 行高

   ```css
   line-height: '数字+px/数字' // 单独的数字代表当前文字大小的倍数;; ; ; ; ; ; ; ; ; ; ;
   ```

7. 文字水平对齐

   ```css
   text-aligntext: 'left左/center居中/right右' // 给父级添加;; ; ; ; ; ; ; ; ; ; ;
   ```

8. 文本缩进

   ```css
   text-indent: '数字+px/数字+em'
     // em为当前文字大小，如2em：当前2个文字大小缩进;; ; ; ; ; ; ; ; ; ; ;
   ```

9. 字体修饰线

   ```css
   text-decoration: ''
     underline下划线；line-through删除线；overline上划线；none无修饰
     // none可清除自带修饰线的格式，如a的下划线等;; ; ; ; ; ; ; ; ; ; ;
   ```

### 5. 背景样式

> background 可作为复合标签使用
>
> background：color image repeat position（空格隔开每个取值）

1. 背景颜色

   ```css
   background-color: '' // transparent无背景色;; ; ; ; ; ; ; ; ; ; ;
   ```

2. 背景图片

   ```css
   background-image: url= '图片地址';
   ```

3. 背景图样式

   ```css
   background-repeat: '' no-repeat不平铺；repeat-x，repeat-y：沿x或y轴平铺;
   ```

4. 背景图位置

   ```css
   background-position: '水平位置 垂直位置' // 两个取值用空格隔开
     取值：数字 + px/方位名词（left左，center中，right右，top上，center中，bottom下）
     // center可只写一个，会水平垂直居中显示
     // 取值为数字时：往左为正数，往下为正数 ;
   ```

5. 背景图大小

   ```css
   background-size: '宽 高' // 两个取值用空格隔开
     取值：数字 + px；百分比；contain等比例缩放（包含，宽高其中一个充满盒子则停止缩放）；cover等比例缩放（覆盖，不留空白）
     // 背景图的包装标签常设置与图片同等宽高，基本使用contain/cover即可;; ; ; ; ; ; ; ; ; ; ;
   ```

6. 精灵图

   > a. 设置一个盒子与图片大小相同（宽高）
   >
   > b. 将精灵图设置为背景图
   >
   > c. 使用 background-position 调整图片位置（用数字+px 取值)

7. 渐变背景

   ```css
   background-image: linear-gradient(颜色1, 颜色2, ...);

   background-image: linear-gradient(
     transparent,
     rgba(0, 0, 0, 0.5)
   ); // 半透明效果（常用）
   ```

### 6. 伪元素

> 使用 CSS 模拟出的:行内元素效果
>
> ⚠️伪元素必须添加content""；否则无法生效，无文本内容引号内可留空

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

> a. 定位需配合：方位+数字 px 移动使用
>
> b. 一般定位采用：子绝父相
>
> c. 元素层级关系：标准流<浮动<定位（标准流：浏览器默认的排列方式）
>
> d. 同层级关系：后面的内容会压住前面的内容（定位情况下）
>
> e. 可用 z-index:数字 提升显示优先级，数字越大越优先（需配合定位才能生效）

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
   <div > <div class=center > </div > </div > div {
     position: relativ;
   } //子绝父相
   .center {
     position: absolute;
     left: 50%;
     top: 50%;
     transform: translate(-50%, -50%);
   }
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
   opacity: 0-1（0为透明，1为不透明） // 可使用hover进行效果制作;; ; ; ; ; ; ; ; ; ; ;
   ```

2. 元素隐藏

   ```css
   display:none（不占用标准流）
   	// 配合hover实现光标悬停显示；hover中设置display：black
   visibility:hidden（占用标准流，不常用）
   ```

### 11. 过渡效果

> 配合 CSS3 的位移/旋转等使用

```css
transition: all 数字 + s // 过渡写在需要过渡效果的选择器内
  // all表示所有可以过渡的属性都有过渡效果，也可单独设置需要过渡效果的属性名（如width等）
  // 数字+s为过渡的时间;; ; ; ; ; ; ; ; ; ; ;
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
