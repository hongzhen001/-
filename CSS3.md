## CSS3

### 1. 字体图标

> a. 本质：展示的为图标，实质为文字，可修改大小/颜色等
>
> b. 使用方法：
>
> i. 下载字体包：[字体图标网](https://www.iconfont.cn/)
>
> ii. 引入字体图标： `<link rel="stylesheet" href="下载字体包中的 iconfont.css 文件">`
>
> iii. 调用图标对应的类名，必须调用两个类名：`<div class="iconfont icon-xxx"></div>`


### 2. 转换效果

1.  位移

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

2.  旋转

    > a. XY 轴旋转需配合 perspective 实现效果
    >
    > b. 左手法则：
    >
    >     i. 用左手握住旋转轴，大拇指指向平面正数方向，手指弯曲方向为正数
    >
    >     ii. Y轴往下为正，X轴往右为正
    >
    > c. 同时存在多个转换效果：
    >
    >     transform: translate() rotate() ;
    >
    >     // 多重转换涉及旋转的情况，旋转属性最后书写；

    a. 平面旋转

    ```css
    transform: rotate(角度 + deg); // deg为单位; 正数为顺时间，负数为逆时针
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

3.  缩放

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

4.  立方体

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
   animation-play-state: paused 暂停动画 // 配合hover使用，书写于hover内;; ; ; ; ; ; ; ; ; ; ;
   ```

### 4. 移动端

> a. 移动端一般使用 iphone6/7/8 （375\*667）的尺寸进行设计
>
> b. 视口宽=手机宽

1. 利用媒体查询检测视口宽度

   > [flexible.js](视口/flexible.js) 引入该 js 文件后可省略媒体查询，自动适配

   ```css
   @media（媒体属性）{                     @media（width：设备宽度）{
       选择器{CSS属性}                         html {font-size:需要设置的字号;}
   ```

2. rem

   > i. rem 单位：相对单位；依据 HTML 标签的字号计算尺寸；
   >
   > ii. 1rem=1HTML 字号大小=1/10 /视口宽度； 375宽的设备为 1rem=37.5

3. vw/vh

   > i. vw:viewport width; vh:viewport hight;
   >
   > ii. 1vw=1/100 视口宽度； 1vh=1/100 视口高度； 375宽的设备为 1vw=3.75
   >
   > iii. vw/vh 不同时设置，取其一即可

### 5. Flex 布局

> a. 弹性容器，移动端常用的布局方式，可避免浮动脱标的情况
>
> b. [搜索代码兼容性网站](https://www.caniuse.com)

1. 启用 Flex 布局

   ```css
   display: flex // 给父级添加，子元素会自动拉伸或挤压； 默认主轴：水平；;; ; ; ; ; ; ; ; ; ; ;
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
   flex: 数字（正数）; // 扣除父级已用的范围，剩余尺寸的份数，书写于需要伸缩的子级内
   // flex属性可以修改弹性盒子伸缩比

   <div class=flex > <div > </div > <p > </p > </div > .flex {
     width: 200px;
     display: flex;
   }
   .flex div {
     width: 100px;
   }
   .flex p {
     flex: 1;
   } // flex盒子扣除子级div后剩下的100px尺寸都给p标签
   ```

5. 改变主轴方向

   ```css
   flex-direction: column; // 修改主轴方向为垂直
   // row默认水平（忽略不写即可）
   ```

6. 换行排列

   ```css
   flex-wrap: wrap; // 换行排列，不挤压弹性盒子
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

### 6. Less 语法

> a. CSS 的预处理器，可扩充 CSS 语言，使 CSS 具备一定的逻辑性、计算能力，更加方便的书写 CSS
>
> b. vscode 中插件：Easy less；文件后缀（.less)
>
> c. 浏览器不识别 less，less 文件保存后会自动生成 CSS 文件，引入 CSS 文件即可
>
> d. 加、减、乘可直接书写，除需添加括号 // 如 width{100/10rem} 100 除以 10rem 的宽

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

3. less 导入

   ```css
   @import '文件路径'; //  如果导入是less文件可省略后缀.less
   ```

4. less 导出

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

> a. BootStrap 是一种前端 UI 框架，能够快速完善网页与交互效果 [BootStrap 网站](https://www.bootcss.com)
>
> b. 先引入 Bootstrap 在引入自己的 css 文件，如此不满意的样式可用自己的样式覆盖
>
> c. 使用步骤：
>
> i. 下载官网中的：bootstrap3文档
>
> ii. 引入bootstrap中的CSS代码：bootstrap.css / bootstrap.min.css两者都可
>
> iii. 调用类名

1. 栅格系统

   > 将网页等分为 12 份，通过设置份额来排列容器

   ```css
   // 下列*代表盒子占12分中的几份则为几，无单位
   超小屏<768 : 类名前缀col-xs-*；
   小屏幕>=768: 类名前缀col-sm-*；
   中屏幕>=992: 类名前缀col-md-*；
   大屏幕>1200: 类名前缀col-lg-*；
   ```

2. BootStrap 类名

   ```css
   container：版心样式，自带左右15px的padding；
   row：自带间距-15px的padding;  // 在container里新加一个子级类名为row
   container-fluid：宽度100%，自带左右15px的padding；
   ```

3. BootStrap 样式使用

   > a. [bootstrap CSS 样式](https://v3.bootcss.com/css/)
   >
   > b. [bootstrap 组件样式](https://v3.bootcss.com/components/)
   >
   > c. [bootstrap js 插件](https://v3.bootcss.com/javascript/)
   >
   > d. [bootstrap 个人定制](https://v3.bootcss.com/customize/)

   ```css
   Bootstrpa插件使用步骤：// CSS/js文件可用bootstrap/bootstrap.min 两者内容相同

   a.引入样式表  <link rel="stylesheet" href="bootstrap.css">

   b. 引入js文件  // 按顺序引入，js文件引入写body最后
   <script src="./js/jquery.js"></script>
   <script src="./bootstrap-3.4.1-dist/js/bootstrap.js"></script>
   ```
