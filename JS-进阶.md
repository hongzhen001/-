## JS进阶

### 1. API与Web API

> a. API：应用程序接口，是一些预先定义的函数，以便能更轻松的实现某些功能
>
> b. Web API：是浏览器提供的一套操作浏览器功能和页面元素的API（BOM与DOM），如alert(弹窗)
>
> c. MDN详细API：[API](https://developer.mozilla.org/zh-CN/docs/Web/API)
>
> d. Web API一般都有输入与输出（函数的传参与返回值），Web API很多都是方法（函数）

### 2. DOM

> a. DOM是文档对象模型，是W3C组织推荐的HTML的标准编程接口
>
> b. 通过DOM可以改变内容/样式/结构

#### 1. DOM树

> 文档：一个页面就是一个文档，DOM中使用document表示
>
> 元素：页面中所有的标签都是元素，DOM中使用element表示
>
> 节点：网页中所有内容都是节点（标签/属性/文本/注释等），DOM使用node表示
>
> DOM把上述内容都看作是对象

#### 2. 获取元素

```javascript
1. 根据ID获取，使用getElementById('id名')，返回的是一个对象
<div id="time"></div>
<script>
  var timer = document.getElementById('time'); // 这里参数需为字符串，否则返回null，这里返回的是一个对象
  console.dir(timer);  // 打印返回的元素对象，可以更好的查看里面的属性与方法
</script>  
// 先写标签，后写js，这里的js写在body中

2. 根据标签名获取，使用getElementsByTagName('标签名'),返回的是对象的集合
<ul>
  <li></li>
  <li></li>
</ul>
var lis = document.getElementsByTagName('li'); // 返回的是一个伪数组，可用索引号提取其中的几个，若无li标签，返回的是一个空的伪数组
console.log(lis[0]); // 获取第一个li
// 若存在其他的li，如ol中的li，只提取ol中的li
var ol = document.getElementsByTagName('ol'); // 先将需要提取的父元素设为一个伪数组
var lis = ol[0].getElementsByTagName('li'); // 在从伪数组中提取相应的对象，这里索引号不能漏
// 也可将ol设一个id，在提取li

3. 根据类名获取，使用getElementsByClassName('类名')，返回的是对象的集合
<div class="box"></div>
<div class="box"></div>
<div class="box1"></div>
var boxs = document.getElementsByClassName('box'); // 返回所有class为box的盒子

4. 通过选择器获取
a. 使用querySelector('选择器')，返回第一个元素对象（选择器需要加符号）
var firstBox = doucment.querySelector('.box'); //  返回第一个class为box的盒子
b. 使用querySelectorAll('选择器')，返回选择器所有元素对象集合
var boxs = doucment.querySelectorAll('.box'); // 返回所有class为box的盒子

5. 获取body元素
var bodyEle = doucment.body;
6. 获取html元素
var htmlEle = doucment.doucmentElement;
```

#### 3. 事件基础

```javascript
事件是可以被js检测到的行为
事件分为三部分：事件源/事件类型/事件处理程序（事件三要素）

a. 事件源（事件被触发的对象）
b. 事件类型（如何触发，如点击：onclick）
c. 事件处理程序（通过一个函数赋值的方式完成）

<button id="btn">IU</button>
var btn = doucment.getElementById('btn'); // 先获取按钮元素（事件源）
btn.onclick = function(){  // btn.onclick 点击按钮（事件类型）
  alert('IU') // 事件处理程序，用函数赋值方法
}；
```

#### 4. 常见鼠标事件

|  鼠标事件   |     触发条件     |
| :---------: | :--------------: |
|   onclick   | 鼠标点击左键触发 |
| onmouseover |   鼠标经过触发   |
| onmouseout  |   鼠标离开触发   |
|   onfocus   | 获得鼠标焦点触发 |
|   onblur    | 失去鼠标焦点触发 |
| onmousemove |   鼠标移动触发   |
|  onmouseup  |   鼠标弹起触发   |
| onmousedown |   鼠标按下触发   |

### 3. 改变文本内容/元素属性

#### 1. 改变文本内容

```javascript
a. element.innerText，不识别HTML标签，获取元素内容时会去除空格和换行
b. element.innerHTML，可识别HTML标签，获取元素内容时不会去除空格和换行

// 点击按钮，div内文字发生变化
<button></button>
<div></div>
var btn = doucment.querySelector('button'); // 获取按钮元素
var div = doucment.querySelectoe('div'); // 获取div元素
btn.onclick = function(){
  div.innerText = '需要显示文字内容'
}

// 不添加事件，直接显示
var div = doucment.querySelectoe('div'); // 获取div元素
div.innerText = '需要显示文字内容'

// Text与HTML的区别
var div = doucment.querySelectoe('div');
div.innerText = '<strong>IU</strong>' // 不识别加粗标签
div.innerHTML = '<strong>IU</strong>' // 可识别加粗标签
```

#### 2. 改变元素属性

```javascript
<button id="1">1</button>
<button id="2">2</button>
<img src="xx图片路径" alt="" title="1">

// 通过按钮改变图片
var btn1 = doucment.getElementById('1');
var btn2 = doucment.getElementById('2');
var img = doucment.querySelector('img');
btn2.onclick = function(){
  img.src = "xx图片2路径";
  img.title = "2";
}
btn1.onclick = function(){
  img.src = "xx图片1路径";
  img.title = "1";
}

❤️案例：通过当前时间显示不同图片内容
<img src="./images/s.gif" alt="">
<div>上午好</div>
<script>
  var img = document.querySelector('img');
  var div = document.querySelector('div');
  var date = new Date();
  var h = date.getHours();  // 获取当前小时数
  if (h < 12){
    img.src = './imamges/s.gif';
	  div.innerHTML = '上午好';
  } else if(h <18){
	  img.src = './images/x.gif';
	  div.innerHTML = '下午好';
  } else {
	  img.src = './images/w.gif';
	  div.innerHTML = '晚上好';
  }
</script>
```

### 4. 改变表单属性

```javascript
// 点击按钮，修改文本框中的内容
<button></button>
<input type="text" value="请输入内容">
<script>
  var btn = doucment.querySelector('button');
  var text = doucment.querySelector('input');
  btn.onclick = function(){
    text.value = '被点击了';
    this.disabled = true; // 点击按钮后禁用此按钮，用disabled = true
  }
</script>

❤️案例：密码框显示内容与不显示内容切换
var password = document.querySelector('#password');
var img = document.querySelector('img');
var flag = 0; // 设置一个flag变量，0的时候为密码隐藏，1的时候为密码显示，以此可以无限显示隐藏功能
img.onclick = function(){
  if (flag == 0){
	  password.type = 'text';
	  img.src = './images/open.png';
	  flag = 1; // 点击后flag修改为1
  } else {
    password.type = 'password';
    img.src = './images/close.png';
    flag = 0; // 再次点击后flag修改为0，无限循环操作
  }
}
```

### 5. 改变CSS样式属性

```javascript
element.style // 行内样式操作，js写的样式会加入到行内样式中，权重高优先显示（修改样式较少的情况下使用）
element.className // 类名样式操作 （修改样式较多时使用）

// 点击修改CSS中的样式
<div></div>
var div = document.querySelector('div');
div.onclick = function(){
  this.style.backgroundColor = 'purple'; // 修改div中的背景颜色，这里样式名不用-
}

// 利用className修改样式
1. 先在style中书写改变后的样式（新起一个类名）
2. 再在js中使用
  this.className = '上面新起的类名' // 这里直接写类名即可，不需要加符号
  this.className = '原先的类名 新起的类名' // 这样书写可保留原先的类名在加上新起的类名

❤️案例：隐藏某一元素
var div = document.querySelector('.box');
var btn = document.querySelector('.close-btn');
btn.onclick = function(){
  div.style.display = 'none';
}

❤️案例：利用循环一次性制作精灵图（精灵图必须有规律，竖排或横排）
var lis = document.querySelectorAll('li');
for(var i = 0; i < lis.length; i++){
  // 让索引号x精灵图之间的距离就是背景图y的坐标
  var index = i * 精灵图之间的距离;
  lis[i].style.backgroundPosition = '0 -' + index + 'px'; // 负号不能漏
}

❤️案例：显示隐藏文本框内容
var texts = document.querySelector('input');
texts.onfocus = function(){
  if(texts.value == '手机'){  // 提取用户输入的值做判断
    this.value = '';
  }
  this.style.color = '#333'; // 获得焦点后文字颜色变深
}
texts.onblur = function(){
  if(texts.value == ''){
    this.value = '手机';
  	this.style.color = '#999'; // 失去焦点后文字如果为默认值则颜色变浅，否则保持深色
  }
}

❤️案例：密码条件
<div class="box">
  <input type="password" style="outline: none;">
  <img src="./images/mess.png" alt="">
  <span>请输入6~16位密码</span>
</div>
<script>
  var password = document.querySelector('input');
  var img = document.querySelector('img');
  var text = document.querySelector('span')
  password.onblur = function () {
    if(password.value.length < 6 || password.value.length >16){
      img.src = './images/wrong.png';
      text.innerHTML = '密码不符合标准';
      password.value='';  // 密码不符合标准时清空输入内容
    } else {
      img.src = './images/right.png';
      text.innerHTML = '密码可用';
    }
  }
```

### 6. 排他思想（算法）

```javascript
// 多个按钮点击效果相同，可利用for循环，不需要一个个添加事件
<button>1</button>
<button>2</button>
<button>3</button>
var btn = document.getElementsByName('button');
for(var i = 0; i < btn.length; i++){
  btn[i].onclick = function(){
    // 先清空所有按钮的背景色
    for (var i = 0; i < btn.length; i++){
      btn[i].style.backgroundColor = '';
    }
    // 再给点击的按钮添加背景色
    this.style.backgroundColor = 'pink';
  }
}

❤️案例：点击图片更换网页背景
<ul class="baidu">
  <li><img src="images/1.jpg"></li>
  <li><img src="images/2.jpg"></li>
  <li><img src="images/3.jpg"></li>
  <li><img src="images/4.jpg"></li>
</ul>
<script>
	var imgs = document.querySelector('.baidu').querySelectorAll('img'); // 获取baidu中所有的img
	for (var i = 0; i < imgs.length; i++){
    imgs[i].onclick = function(){
      // 更改body中的背景图片，this.src为点击图片后获取的图片地址，用字符串相加的书写形式
      document.body.style.backgroundImage = 'url('+ this.src +')';
    }
  }

❤️案例：复选框全选反选
var j_cbAll = document.querySelector('#j_cbAll'); // 全选复选框
var j_tbs = document.querySelector('tbody').getElementsByTagName('input'); // 小复选框
// 全选复选框选中小复选框都跟着全部选中
j_cbAll.onclick = function(){
	// this.checked; // 这个可得到复选框是否选中，选中为ture，未选中为fasle
  for (var i = 0; i < j_tbs.length; i++){
	  j_tbs[i].checked = this.checked;
  }
}
// 小复选框全部选中，全选复选框跟着选中
for (var i = 0; i < j_tbs.length; i++){ // 循环小复选框点击事件
  j_tbs[i].onclick = function(){
    var flag = true; // 设置一个变量检测小复选框是否都选中
    for(var j =0;j<j_tbs.length;j++){ // 循环检测小复选框
      if(!j_tbs[j].checked){  // 如果有一个小复选框未选中，则flag为fasle，全选复选框则不会选中（这里使用反选，!j_tbs[i].checked)
        flag = false;
        break; // 退出for循环，可提高执行效率，只要有一个小复选框未选中则退出循环
      }
    }
    j_cbAll.checked = flag;
  }  
}
```

### 7. 获取/修改/删除属性内容

#### 1. 获取属性的值

```javascript
<div id="IU" index="1"></div>
var div = document.querySelector('div')

a. 通过element.属性，获取内置属性值（元素自带的属性）
console.log(div.id); // 输出id属性 IU

b. 通过element.getAttribute('属性')，获取自定义属性值，如index（自定义属性为自己添加的属性）
console.lig(div.getAttribute('id')); // 输出id属性 IU
```

#### 2. 设置属性的值

```javascript
<div id="IU" index="1" class='IU'></div>
var div = document.querySelector('div')

a. 通过element.属性 ='值'，修改内置属性值
div.id = 'hz'; // 修改id为hz
div.className = 'hz'; // 修改class为hz，这里需要书写为className；

b. 通过element.setAttribute('属性','值')，修改自定义属性值
div.setAttribute('index','2'); // 修改index为2
div.setAttribute('class','hz'); // 修改class为hz，这里需要书写为class（与上面的不同，比较特殊）
```

#### 3. 移除属性

```javascript
<div id="IU" index="1" class='IU'></div>
var div = document.querySelector('div')

通过element.removeAttribute('属性')
div.removeAttribute('index'); // 移除index属性
```

❤️案例

```javascript
// tab栏切换，点击相应的模块展示相应的内容，隐藏其余内容
<div class="tab">
  <div class="tab_list"> // tab栏
    <ul>
      <li class="current">商品介绍</li>
      <li>规格与包装</li>
      <li>售后保障</li>
      <li>商品评价（50000）</li>
      <li>手机社区</li>
    </ul>
  </div>
  <div class="tab_con"> // 详情页
    <div class="item" style="display: block;">商品介绍模块内容</div>
    <div class="item">规格与包装模块内容</div>
    <div class="item">售后保障模块内容</div>
    <div class="item">商品评价（50000）模块内容</div>
    <div class="item">手机社区模块内容</div>
  </div>
</div>

// 获取元素
var tab_list = document.querySelector('.tab_list');
var lis = tab_list.querySelectorAll('li');
var items = document.querySelectorAll('.item');
// for循环绑定点击事件
for (var i = 0; i < lis.length; i++) {
  // 开始给5个小li 设置索引号
  lis[i].setAttribute('index', i);
  lis[i].onclick = function() {
    // 1. 上的模块选项卡，点击某一个，当前这一个底色会是红色，其余不变（排他思想） 修改类名的方式
    // 干掉所有人 其余的li清除 class 这个类
    for (var i = 0; i < lis.length; i++) {
      lis[i].className = '';
    }
    // 留下我自己
    this.className = 'current';
    // 2. 下面的显示内容模块
    var index = this.getAttribute('index');
    // 干掉所有人 让其余的item 这些div 隐藏
    for (var i = 0; i < items.length; i++) {
      items[i].style.display = 'none';
    }
    // 留下我自己 让对应的item 显示出来
    items[index].style.display = 'block';
  }
}
```

### 8. H5自定义属性

```javascript
// H5新增的获取属性只能提取 “data-” 开头的自定义属性
<div id="IU" data-index="1" data-lis-name="IU"></div>
var div = document.querySelector('div')

a. 书写：统一使用data-开头，如：data-index="1";

b. 添加属性：使用element.setAttribute('属性名',属性值)
div.setAttribute('data-index',2); // 添加一个data-index="2"的属性

c. 获取属性:
1. 使用element.getAttribute('属性名')
div..getAttribute('data-index'); // 获取data-index的属性值，输出为1

2. 使用element.dataset.属性名
div.dataset.index  // 输出为1
div.dataset // dataset是一个集合，存放了所有data开头的自定义属性
div.dataset.lisName // 自定义属性中有多个用“-”连接的单词，获取时采用驼峰命名法

3. 使用eltment.dataset['属性名']
div.dataset['index'] 
div.dataset['lisName'] 
```

### 9. 节点操作

> a. 节点操作是获取元素的方式
>
> b. 获取元素的方式分为两种：
>
> 1. 利用DOM提供的方式获取（如：getElementByID；querySeletor等），这种获取方式较为繁琐/逻辑性不强
> 2. 利用父子兄弟节点层级关系获取，逻辑性更强，兼容性较差
>
> c. 页面中所内容都是节点（标签，属性，文本等）
>
> d. 节点至少拥有三个基本属性：nodeType（节点类型）；nodeName（节点名称）；nodeValue（节点值）
>
> 1. 元素节点：nodeType为1
> 2. 属性节点：nodeType为2
> 3. 文本节点：nodeType为3
>
> e. 节点操作主要操作的是元素节点

##### 1. 父子节点

```javascript
a. 父节点，使用 node.parentNode // 得到的是离元素最近的父节点（亲爸爸），若找不到父节点则返回null；
<div>
  <span></span>
</div>
var span = document.querySelector('span');
span.parentNode; // 输出为父节点div

b. 子节点，使用 parentNode.childNodes（不常用） / parentNode.children（常用）
<ul>
  <li></li>
</ul>
var ul = document.querySelector('ul');
ul.childNodes; // 输出为ul中的li，输出内容包含元素节点，文本节点等（换行=文本节点）
ul.children; // 输出为ul中li，只返回元素节点，文本/属性节点部返回

c. 第一个元素与最后一个元素
<ul>
  <li></li>
  <li></li>
</ul>
var ul = document.querySelector('ul');

1. 第一个子节点：firstChild
ul.firstchild; // 获取ul中的第一个子节点，为：text（换行）
2. 最后一个子节点：lastChild
ul.lastchild; // 获取ul中的最后一个子节点，为：text（换行）
3. 第一个子元素:firstElementChild
ul.firstElementChild; // 获取ul中第一个元素节点li
4. 最后一个子元素:lastElementChild
ul.lastElementChild; // 获取ul中最后一个元素节点li

⚠️ 实际开发的书写形式
ul.children[0]; // 获取ul中第一个元素节点li
ul.children[ul.children.length - 1]; // 获取ul中最后一个元素节点li(最后一个子元素为子级个数-1，所以先获取子元素的个数)

❤️案例：新浪下拉框，鼠标经过显示（结构ul嵌套li（导航栏）再嵌套a（导航栏的文字）与ul（下拉框）
// 1. 获取元素
var nav = document.querySelector('.nav');
var lis = nav.children; // 得到4个小li
// 2.循环注册事件
for (var i = 0; i < lis.length; i++) {
  lis[i].onmouseover = function() {
    this.children[1].style.display = 'block';
  }
  lis[i].onmouseout = function() {
    this.children[1].style.display = 'none';
  }
}
```

##### 2. 兄弟节点

```javascript
<div></div>
<span></span>
var div = document.querySelector('div');

a. 使用 node.nextSibling // 得到的是下一个兄弟节点（包含元素节点，文本节点等），若无则返回null
div.nextSibling; // 输出为text（换行）

b. 使用 node.previousSibling // 得到的是上一个兄弟节点（包含元素节点，文本节点等），若无则返回null
div.previousSibling; // 输出为text（换行）

c. 使用 node.nextElementSibling
div.nextElementSiling; // 得到的是下一个兄弟元素节点，若无返回null

d. 使用 node.previousElementSibling
div.previousElementSiling; // 得到的是上一个兄弟元素节点，若无返回null

⚠️ c/d存在兼容性问题，老版本浏览器需封装函数
function getNextElementSibling(element){
  var el = element;
  while(el = el.nextElementSibling){
    if(el.nodeType === 1){
      return el;
    }
  }
  return null;
}
```

##### 3. 创建/添加节点

```javascript
a. 创建节点：通过tagName指定HTML元素，这些元素原本是不存在的，通过需求动态生成，也称为动态创建元素节点
使用 document.createElement('tagName') 创建节点
b. 添加节点：将一个节点添加至指定父节点的子节点列表末尾（类似于css中的after伪元素）
使用 node.appendChild(child) 在子节点末尾添加节点 // 这里添加元素不需要加引号
使用 node.insertBefore(child,指定元素) 在子节点指定位置添加新节点

<ul>
  <li></li>  
</ul>
var lis = document.createElement('li'); // 创建li元素节点
var uls = document.querySelector('ul');
uls.appendChild(lis); // 给ul中第一个li后面添加一个新的li元素节点
uls.insertBefore(lis,uls.children[0]); // 给ul中的第一个li前面添加一个新的li元素节点
uls.insertBefore(lis,uls.children[2]); // 在ul中的子元素第二个li前面添加li（这里数字代表索引号）

❤️案例：评论发布
<textarea name="" id="" cols="30" rows="10"></textarea>
<input type="button" value="发布">
<ul></ul>
<script>
  var text = document.querySelector('textarea');
  var btn = document.querySelector('input');
  var ul = document.querySelector('ul');
  btn.onclick = function (){
    if(text.value == ''){
      alert('请输入内容');
      return false;  // 如果输入为空则弹窗提示，直接输出false
    }else {
      var lis = document.createElement('li');
      lis.innerHTML = text.value;
      ul.insertBefore(lis,ul.children[0]); // 最新提交的永远放在第一个位置
      text.value = ''; // 提交后文本框清空
    }
  }
</script>
```

##### 4. 删除节点

```javascript
使用 node.removeChild(child) 删除父节点中某一个子节点
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
var ul = document.querySelector('ul');
ul.removeChild(ul.children[1]); // 删除ul中第二个子节点

❤️案例：删除留言
var text = document.querySelector('textarea');
var btn = document.querySelector('input');
var ul = document.querySelector('ul');
btn.onclick = function (){
  if(text.value == ''){
    alert('请输入内容');
    return false;  // 如果输入为空则弹窗提示，直接输出false
  }else {
    var lis = document.createElement('li');
    lis.innerHTML = text.value + "<a href='javascript:;'>删除</a>"; // 添加li内容的同时添加一个a进行删除操作，这里可以使用javasrcipt:;阻止超链接跳转
    ul.insertBefore(lis,ul.children[0]); // 最新提交的永远放在第一个位置
    text.value = ''; // 提交后文本框清空
  }
  var del = document.querySelectorAll('a'); // 获取所有的a元素
  for (var i =0;i<del.length;i++){ // 添加点击事件
    del[i].onclick =function(){
      ul.removeChild(this.parentNode); // 删除当前a所在的父级li元素
    }
  }
}
```

##### 5. 复制节点

```javascript
使用 node.cloneNode() 复制一个节点，若括号内为空或false，则为浅拷贝，只拷贝标签，不克隆里面的内容。若括号内为true，则为深拷贝，拷贝标签与内容
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
var ul = document.querySelector('ul');
var li = ul.children[0].cloneNode(); // 复制第一个li标签
ul.appendChild(li); // 添加复制的li到最后一个

❤️案例：通过js设置对象数组，自动生成表格
// 1.先去准备好学生的数据
var datas = [{
    name: '魏璎珞',
    subject: 'JavaScript',
    score: 100
}, {
    name: '弘历',
    subject: 'JavaScript',
    score: 98
}];
// 2. 往tbody 里面创建行： 有几个人（通过数组的长度）我们就创建几行
var tbody = document.querySelector('tbody');
for (var i = 0; i < datas.length; i++) { // 外面的for循环管行 tr
  // 1. 创建 tr行
  var tr = document.createElement('tr');
  tbody.appendChild(tr);
  // 2. 行里面创建单元格(跟数据有关系的3个单元格) td 单元格的数量取决于每个对象里面的属性个数  for循环遍历对象 datas[i]
  for (var k in datas[i]) { // 里面的for循环管列 td
    // 创建单元格 
    var td = document.createElement('td');
    // 把对象里面的属性值 datas[i][k] 给 td 
    td.innerHTML = datas[i][k];
    tr.appendChild(td);
  }
  // 3. 创建有删除2个字的单元格 
  var td = document.createElement('td');
  td.innerHTML = '<a href="javascript:;">删除 </a>';
  tr.appendChild(td);
}
// 4. 删除操作
var as = document.querySelectorAll('a');
for (var i = 0; i < as.length; i++) {
  as[i].onclick = function() {
    // 点击a 删除 当前a 所在的行(链接的爸爸的爸爸) ，a的父级为单元格td，单元格的父级为行tr
    tbody.removeChild(this.parentNode.parentNode);
  }
}
```

##### 6. 创建元素

```javascript
<div><div>
var div = document.querySelector('div');

a. 使用 document.write()；会导致页面重绘（原页面内容全部消除，只存在这个创建的元素内容）
document.write('<div></div>')

b. 使用 element.innerHTML；若采取拼接字符串的形式效率较低，使用数组形式效率最高
拼接字符串形式：div.innerHTML = '<a href="javasrcipt:;"></a>'
数组形式：
var arr =[];
for(var i =0;i <=100,i++){
  arr.push('<a href="javasrcipt:;"></a>')
}
div.innerHTML = arr.join('');

c. 使用 document.createElement()，效率比innerHTML拼接字符串形式高，比innerHTML数组形式低
var a = document.createElement('a');
div.appendChild(a);
```

### 10. DOM重点核心

> 1. 创建元素/节点：document.write();innerHTML;createElememt
>
> 2. 增加元素/节点：appendChild;insertBefore
>
> 3. 删除元素/节点：removeChild
>
> 4. 修改元素/节点：
>    1. 修改元素属性：元素.src/href/title
>    2. 修改元素内容：innerHTML/innerText
>    3. 修改表单元素：元素.value/type/disabled(禁用按钮，值为true)
>    4. 修改元素样式：元素.style.需要修改的样式属性='修改样式的值'； 元素.className = '修改的样式类名'
> 5. 查询元素/节点：
>    1. API提供的方法：getElementById;getElementsByTagName;
>    2. H5新增的方法：querySelector;querySelectorAll
>    3. 利用节点获取：父（parentNode）;子（children）;兄（previousElementSibling\nextElementSibling）
> 6. 属性操作：（针对自定义属性，自定义属性都用data-开头）
>    1. setAttribute 设置属性值（这里获取类名直接写class，不需要写className）
>    2. getAttribute/dataset（H5专用） 获取属性值
>    3. removeAttribute 删除属性值
> 7. 事件操作：鼠标事件

### 11. 事件高级

#### 1. 注册事件

> 1. 给元素添加事件称为注册事件，也称作绑定事件
> 2. 注册事件有两种方式：传统方式与方法监听注册方式
>    1. 传统注册：利用on开头的事件（如onclick），特点是唯一性，同一个元素同一个事件只能设置一个处理函数，最后注册的会覆盖前面注册的
>    2. 方法监听注册：使用addEventListener();IE9不支持此方法，同一个元素同一个事件可以注册多个侦听器，按注册依次执行
>    3. 方法监听注册：IE9之前使用attachEvent；（基本不使用）

##### addEventListener事件监听方式

```javascript
a. eventTarget.addEventListener(type,listener[,useCaptrue])
// 将指定的监听器注册到eventTarget（目标对象），当该对象触发指定事件时，则会执行事件处理函数
type：事件类型字符串，如click，mouseover（这里不要带on）
listener：事件处理函数
useCapture：可选参数，是一个布尔值，默认为false

<button></button>
var btn = document.querySelector('button');
btn.addEventListener('click(点击)',function(){ // 这里点击不要加on
  alert('IU')
})

b. eventTarget.attachEvent(eventNameWithOn,callback)
eventNameWithOn：事件类型字符串，如onclick，onmouseover（这里需要加on）
callback：事件处理函数

<button></button>
var btn = document.querySelector('button');
btn.attachEvent('onclick',function(){ // 这里点击不要加on
  alert('IU')
})
```

#### 2. 删除事件

```javascript
<div></div>
var div =document.querySelector('div');

a. 传统方式删除事件：eventTarget.onclick=null;
div.onclick = function(){
  alert('IU');
  div.onclick=null; // 点击一次弹框后无法再次点击
}

b. 方法监听删除事件：eventTarget.removeEventListener(type,listener[,useCaptrue]) // 此类删除事件需将函数分开写
div.addEventListener('click',fn) // 这里直接写函数名，这里不需要调用加小括号
function fn(){ // 另外注册函数
  alert('IU')；
  div.removeEventListener('click',fn)
}

c. IE9以下版本的方法监听删除：eventTarget.datachEvent(eventNameWithOn,callback)
div.attachEvent('onclick',fn)
function fn(){
  alert('IU');
  div.datachEvent('onclick',fn)
}
```

#### 3. DOM事件流

> 1. 事件流描述是从页面中接受事件的顺序
> 2. 事件发生时会在元素节点之间按照特定的顺序传播，此过程称为DOM事件流
> 3. 给一个div注册点击事件：从Document-HTML-body-div-body-HTML-Document；
> 4. DOM事件流分为三个阶段：捕获阶段（从document-div）/当前目标阶段（div）/冒泡阶段（从div-document）
> 5. js只能执行捕获或冒泡其中一个阶段
> 6. onclick和attachEvent只能得到冒泡阶段
> 7. addEventListener(type,listener[,useCaptrue])中第三个参数，如果是true则为捕获阶段调用事件处理程序，如果为false则为冒泡阶段调用事件处理程序
> 8. 有些事件没有冒泡，如：onblur/onfocus/onmouseenter/onmouseleave
> 9. 实际开发中常使用冒泡，很少使用捕获

#### 4. 事件对象

```javascript
<div></div>
var div = querySelector('div');
div.onlick = function(event){} 
1. 这里的event就是一个事件对象，写在侦听函数的小括号内，当形参来看
2. 事件对象有了事件才会存在，是系统自动创建的，不需要认为传递参数
3. 事件对象是事件的一系列相关数据的集合，跟事件相关，比如鼠标事件就有鼠标相关信息（如鼠标坐标等），如果是键盘事件就有键盘信息（如按下了哪个键）
4. 事件对象名可自定义 e / evt / event
5. 存在兼容性问题，IE9以下通过 window.event(固定写法)，兼容性写法 e = e || window.event（设一个变量等于两个）
```

