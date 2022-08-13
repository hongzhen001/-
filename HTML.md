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
    <meta charset="UTF-8" />
    // 适配IE浏览器
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    // 配备移动端代码
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    // 引入网页logo
    <link rel="shortcut icon" href="favicon.ico(ico地址)" type="image/x-icon" />
    // 引入CSS
    <link rel="stylesheet" href="css地址" />

    // 网页SEO：提升网页在搜索时的优先级 // 网页标题
    <title>标题内容</title>
    // 网页描述
    <meta name="description" content="描述内容" />
    // 网页关键词
    <meta name="keywords" content="关键词内容" />
  </head>

  // 网页内容
  <body>
    网页内容区域 // body引入js，需写在末尾位置
    <script src="js地址"></script>
  </body>
</html>

扩展：CSS写入方式
   a. 内嵌式：在<head>中添加:<style>CSS属性+取值</style>
   c. 外链式：在<head>中用<link rel="stylesheet" href="css地址">
   d. 引入行内式：在<body>内写的标签中添加 style="CSS属性+取值"
```

### 3. 网页基础标签

```html
标题： <h1></h1> //分为一到六级 

段落： <p></p>

换行： <br>

分割线：<hr>

块级容器：<div></div> //一行只能排一个 

行内容器： <span></span> //一行可排多个 

加粗：<strong></strong> //具有强调意义 <b></b>

下划线： <ins></ins> //具有强调意义 <u></u>

倾斜： <em></em> //具有强调意义 <i></i>

删除线： <del></del> //具有强调意义 <s></s>

插入图片：<img src="图片路径位置" alt="图片加载失败后显示的文本内容" title="光标悬停时显示的文本内容">

音频标签：<audio src="音频位置" controls autoplay loop></audio>
//controls:插入播放器 loop:循环播放 autoplay:自动播放 

视频标签：<video src="视频位置" controls autoplay loop muted></video>
// 自动播放音频无法实现，视频配合muted静音可实现 

超链接：<a herf="跳转地址" target="窗口打开方式"></a>
// _blank 新窗口打开，跳转地址可用id名进行页面内跳转（书写：#id名）
```

### 4. 移动端语义化标签

```html
头部：<header></header>

导航：<nav></nav>

内容：<article></article>

文档某个区域：<section></section>

侧边栏：<aside></aside>

尾部：<footer></footer>

页面主页：<main></main>
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

// 清除列表自带样式： list-style：none（CSS） 

// 表格：
<table border="边框大小属性：数字+px">
  <caption>
    表格标题，默认加粗
  </caption>
  <tr>
    表格的行
    <th>表格第一行中的单元格，默认加粗居中</th>
  </tr>
  <tr>
    <td>表格每行中的单元格</td>
  </tr>
</table>

// 表格结构：thead头部；tbody主体；tfoot尾部；结构书写于<table>内 
// 单元格合并：colspan：水平单元格合并；rowspan：垂直单元格合并；如有书写表格结构，不能跨结构合并单元格
</table>
```

### 6. 表单

```html
// 表单验证时，须添加form表单域，才可上传
<form action="表单上传地址">
  文本框：<input type="text" placeholder="“预显示文字内容”" />

  密码框：<input type="password" placeholder="“预显示文字内容”" />

  单选：<input type="radio" name=“单选需添加相同名才可生效” checked"默认选中">
  
  多选：<input type="checkbox" checked"默认选中"> 文件：<input type="file"
  multiple"选择多个文件"> 
  
  下拉：<select name="" id=""><option value="" selected默认选中>下拉显示的内容，有几个写几个</option></select>

  邮箱: <input type="email" />

  网址: <input type="url" />

  日期: <input type="date" />

  时间: <input type="time" />

  数量: <input type="number" />

  手机号码: <input type="tel" />

  搜索: <input type="search" />

  颜色: <input type="color" />

  提交按钮：<input type="submit" value="按钮显示内容" />

  重置按钮：<input type="rest" value="按钮显示内容" />

  无意义按钮：<input type="button" value="按钮显示内容" />
</form>

按钮另一种形式：
<button type="button">按钮显示内容</button> // 默认提交效果
<button type="submit/rest">按钮显示内容</button>

单选/多选时点文字也可选择：
<label for="">
  // for属性需删除
  <input type="radio" />
</label>
```

### 7. 字符

```html
&copy 版权©️ &nbsp 一个字符的空格； &emsp 两个字符的空格
```
