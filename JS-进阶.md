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

1. DOM树

   > 文档：一个页面就是一个文档，DOM中使用document表示
   >
   > 元素：页面中所有的标签都是元素，DOM中使用element表示
   >
   > 节点：网页中所有内容都是节点（标签/属性/文本/注释等），DOM使用node表示
   >
   > DOM把上述内容都看作是对象

2. 获取元素

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

3. 事件基础

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

4. 常见鼠标事件

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

5. 操作元素

   1. 改变元素内容

      ```javascript
      a. element.innerText，不识别HTML标签，获取元素内容时会去除空格和换行
      b. element.innerHTML，可识别HTML标签，获取元素内容时不会去除空格和换行
      
      // 点击按钮，div内文字发生变化
      <button></button>
      <div></div>
      var btn = doucment.querySelector('button'); // 获取按钮元素
      var div = doucment.querySelectoe('div'); // 获取div元素
      btn.onclick = function(){
        div.element.innerText = '需要显示文字内容'
      }
      
      // 不添加事件，直接显示
      var div = doucment.querySelectoe('div'); // 获取div元素
      div.element.innerText = '需要显示文字内容'
      
      // Text与HTML的区别
      var div = doucment.querySelectoe('div');
      div.innerText = '<strong>IU</strong>' // 不识别加粗标签
      div.innerHTML = '<strong>IU</strong>' // 可识别加粗标签
      ```

   2. 改变元素属性

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

   3. 改变表单属性

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

   4. 改变CSS样式属性

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
        </script>
      ```