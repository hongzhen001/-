## JS

> a. JS 是一门高级编程语言（也可称为脚本语言），通过 js 引擎转变成机器语言进行执行。
>
> b. JS 的组成
>
> i. JS语法
>
> ii. DOM-页面文档对象模型
>
> iii. BOM-浏览器对象模型

### 1. JS 书写形式

> JS 中使用单引号书写

1. 行内式

   ```html
   <input type="button" value="按钮显示的文字" onclick="alert('弹框显示的内容')"
   // onclick：点击 alert：弹框
   ```

2. 内嵌式

   ```javascript
   // 写在<head>中
   <script>alert('弹框显示的内容')</script>
   ```

3. 引入式

   ```javascript
   // 写在<head>中
   a. 创建一个js文件
   b. 引入 <script scr="js文件地址"></script>
   ```

### 2. 注释

> a. 单行注释 //xxx   快捷键：“ctrl+/”
>
> b. 多行注释 /_ xxx _/    快捷键：“shift+alt+a” 【VScode中可以自定义快捷键】
>

### 3. 输入输出语言

|      代码形式      |                    说明                    |
| :----------------: | :----------------------------------------: |
|    alert（msg）    |              浏览器弹出警示框              |
| console.log（msg） | 浏览器控制台打印输出信息(浏览器检查中可看) |
|   prompt（info）   |        浏览器弹出输入框，用户可输入        |

```javascript
prompt('弹出输入框显示的标题内容');
alert('弹出警示框显示的内容');
console.log('检查元素中显示的内容');
```

### 4. 变量

> 用于存放数据的容器，通过变量名获取数据

1.  变量的使用

    > a. 声明变量
    >
    > var age; // 声明一个名称为age的变量，变量名可自行设置
    >
    > b. 赋值（把值存入变量中）
    >
    > age = 18; // 给age变量赋值为18
    >
    > c. 变量初始化（将声明变量与赋值同时书写）
    >
    > var age = 18;  //声明变量同时赋值18
    >
    > // 可通过 console.log(age);检查是否赋值成功
    >
    > // 除数字外，其他内容用''包裹，如：var name = ’知恩‘；

    ```javascript
    <script>
      var myname = prompy('输入用户名') // 用户输入后存储到myname变量中
      alert(myname) // 弹出用户输入的信息内容
    </script>
    ```

2.  变量语法扩展

    1. 变量更新

       ```javascript
       var name = '知恩'；
       name = 'IU'   // 后面的IU会覆盖前面的知恩
       ```

    2. 声明多个变量

       ```javascript
       var age = 18, // 多个变量中间用逗号隔开
         address = '地址名',
         name = '用户名'; // 最后用分号结尾
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

3.  变量命名规范

> a. 由字母、数字、下划线、美元符号（$）组成，如：num_01。//不能以数字开头，会报错
>
> b. 严格区分大小写,var app/var App 是两个变量
>
> c. 不能是关键字、保留字，如：var for while
>
> d. 变量名必须有意义，如：nl（年龄） // 不如此设置变量名
>
> e. 遵守驼峰命名法；首字母小写，后面的首字母需要大写，如 myFirstName
>
> f. 翻译网站：[有道](https://fanyi.youdao.com/) [爱词霸](http://www.iciba.com/)
>
> g. name 有特殊含义，不使用 name 作为变量名

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

> a. JS 的变量数据类型是只有程序在运行过程中，根据等号后面的值来确定
>
> b. JS 是动态语言，变量的数据类型是可变化的
>
> c. var x = 10；x 为数字型 ； var x = 'IU' x 为字符串型

1.  简单数据类型

    | 数据类型  |                      说明                       |   默认值   |
    | :-------: | :---------------------------------------------: | :--------: |
    |  Number   |     数字型，包含整型值与浮点型值，如 5，0.5     |     0      |
    |  Boolean  |         布尔值类型，如 true=1，false=0          | false（0） |
    |  string   |      字符串类型，如"知恩"，字符串都带引号       |     ""     |
    | Undefined | var a;声明了变量 a 但没有赋值，此时 a=undefined | Undefined  |
    |   Null    |        var a = null; 声明了变量 a 为空值        |    null    |

    1. 数字型（Number）

       > a. 八进制（范围 0 ～ 7）
       >
       > var num = 010 // 输出为 8
       >
       > b. 十六进制（范围 0 ～ 9；A ～ F）
       >
       > var num =0xA // 输出为 10
       >
       > c. JS 中八进制前面加 0，十六进制前面加 0x；

       1. 数字范围

          ```javascript
          Number.MAX_VALUE; // 最大值
          Number.MIN_VALUE; // 最小值
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
          |  `\t`  | tab 缩进 |
          |  `\b`  |   空格   |

       2. 字符串长度

          ```javascript
          通过length属性获取整个字符串长度;

          var str = 'my name is IU';
          console.log(str.length); // 显示为15个字符，每个空格也算1个字符，如有标点符号也算一个字符
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

       ```

    4. 未定义数据类型（undefined）

       ```javascript
       // 声明变量后没有赋值的情况会有一个默认值：undefined

       a.console.log(undefined + 'IU'); // 输出为undefinedIU

       b.console.log(undefined + 1); // 输出为NaN（非数字型）
       ```

    5. 空值（Null）

       ```javascript
       // 声明变量给null值，里面存储的值为空值

       a.console.log(Null + 'IU'); // 输出为NullIU

       b.console.log(Null + 1); // 输出为1
       ```

2.  获取变量数据类型

    > a. 利用 typeof 进行获取数据类型
    >
    > b. 可通过浏览器检测面板进行判读
    >
    >     i. 浅蓝色为数字型
    >
    >     ii. 黑色为字符串型
    >
    >     iii. 深蓝色为布尔型
    >
    >     iv. 灰色为空值/为定义数据类型
    >
    > c. 通过表单/prompt 获取的数据默认是字符串型

    ```javascript
    var num =10;
    console.log(typeof num);  // 输出为number数字型

    var str ='IU';
    console.log(typeof str);  // 输出为string字符串型

    var str = prompt('请输入你的信息')； // 不论用户输入的内容是什么都为字符串型
    ```

3.  数据类型转换

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
    Boolean(); // 空/否定的值会转换成false，如：0、NaN、null、undefined，其他值都会转换成true；
    Boolean(''); // 输出为false
    Boolean('0'); // 输出为false
    Boolean(12); // 输出为ture
    Boolean(IU); // 输出为ture
    ```

4.  编译型语言与解释型语言

    > a. 编译型语言是整体代码编译完成后在进行翻译再执行
    >
    > b. 解释型语言是边输入代码边翻译边执行

5.  标识符/关键字/保留字

    > a. 标识符是指开发人员为变量、属性、函数、参数取的名字，标识符不能是关键字或保留字
    >
    > b. 关键字是指 JS 本身已经使用过的字，不能再用她们充当变量名、方法名，如：break、case、else、do、delete 等
    >
    > c. 保留字实际上为预留的”关键字“，同样不能使用它们当变量名、方法名，如：class、byte、const、float、fimal、int 等

### 6. 运算符

> a. 也被称为操作符，用于实现赋值、比较、执行算数运算等功能的符号
>
> b. 可用双等号进行验算
>
> ​var num = 1 + 1;
>
> ​console.log(num == 2); // 输出为 true 为正确，输出 false 为错误

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
      console.log(3 > 5 && 3 > 2); // 输出false
      console.log(3 > 2 && 3 < 5); // 输出true
      // 条件同时满足则为true，只要有一个不满足则为false
      ```

   2. 逻辑或

      ```javascript
      console.log(3 > 5 || 3 > 2); // 输出true
      console.log(3 > 5 || 3 < 2); // 输出false
      // 只要有一个条件满足则为true，都不满足则为false
      ```

   3. 逻辑非（取反符）

      ```javascript
      console.log(!true); // 输出false
      console.log(!false); // 输出true
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

   |   运算符    |         说明         |             案例              |
   | :---------: | :------------------: | :---------------------------: |
   |      =      |       直接赋值       |         var age = 10;         |
   |    +=/-=    | 加/减一个数后在赋值  | var age = 10; age += 5; //15  |
   | \*=、/=、%= | 乘、除、取余后在赋值 | var age = 10; age \*= 5; //50 |

6. 运算符优先级

   | 优先级 |   运算符   |   先后顺序    |
   | :----: | :--------: | :-----------: |
   |   1    |   小括号   |     （）      |
   |   2    | 一元运算符 |   ++ -- ！    |
   |   3    | 算数运算符 | 先乘除后加减  |
   |   4    | 关系运算符 |   > >= < <=   |
   |   5    | 相等运算符 | == != === !== |
   |   6    | 逻辑运算符 | 先 && 后 \|\| |
   |   7    | 赋值运算符 |       =       |
   |   8    | 逗号运算符 |       ,       |

### 7. 流程控制-分支

1. 流程控制

   1. 顺序流程控制

      > 按照代码的先后顺序，依次执行

   2. 分支流程控制

      > 根据不同的条件，执行不同的路径代码，从而得到不同的结果

      1. if 语法

         ```javascript
         if(条件表达式){
            执行语句
         }
         // 执行思路
         a. 如果条件表达式为true，则执行if中的语句
         b. 如果条件表达式为false，则不执行if中的语句，跳过当前if执行下一个代码

         ❤️案例：
         var age = prompt('请输入您的年龄');
         if (age >= 18){
            alert('IU');
         }
         if (age < 18){
            alert('iu')
         }  // 用户输入年龄大于等于18则弹出IU；若小于18则弹出iu；
         ```

      2. if else（双分支语句）

         ```javascript
         if (条件表达式){
            执行语句1
         } else {
            执行语句2
         }
         // 执行思路
         a. 如果条件表达式为true，则执行语句1
         b. 如果条件表达式为flase，则执行语句2
         c. if中的语句1与语句2，最终只执行其中一个

         ❤️案例：
         var age = prompt('请输入想要查询的年份');

         // 能被400整除（余为0）或 能被4整数且不能被100整除
         if (age % 400 == 0 || age % 4 == 0 && age % 100 != 0 ){
         	alert(age + '是闰年');
         } else {
            alert(age + '是平年');
         }
         ```

      3. if else if（多分支语句）

         ```javascript
         if (条件表达式1){
            执行语句1
         } else if (条件表达式2) {
            执行语句2
         } else if (有几个条件写几个){
            执行语句3
         } else {} // 最后用else结尾输入不满足上诉所有条件的结果
         // 执行思路
         a. 如果条件表达式1为true，则执行语句1
         b. 如果条件表达式1为flase，则判断条件表达式2
         c. 若条件表达式都不满足则执行else
         d. 最终只能执行其中的一个语句

         ❤️案例：
         var age = prompt('请输入分数');
         if (age >= 90){
            alert('A'); // 90以上（含90），则为A
         } else if (age >= 80){
            alert('B'); // 80（含）～90（不含）；则为B
         } else if (age >= 70){
            alert('C'); // 70（含）～80（不含）；则为C
         } else {
            alert('D'); // 小于70；则为D
         }
         ```

      4. switch 语句（多分支语句）

         ```javascript
         // switch 是针对变量设置的特定值进行判断，若为范围值则使用if/if else
         // 利用变量时，变量与case里面的值是全等的关系，必须值与数据类型相同（===）
         // 若当前case中无break 则不会退出switch，继续执行下一个case且不区分是否匹配直接输出，直到全部case执行完或出现break结束
         switch(表达式){
            case value1:
               执行语句1；
               break；
            case value2:
               执行语句2;
               break；
            ...有多写多少
            default: // 若上面都不满足则执行最后的语句
               执行最后的语句
         }

         // 执行思路
         a. 利用表达式的值和case后面的选项值相匹配
         b. 匹配上则执行该case里面的语句
         c. 匹配不上则执行最后的语句

         ❤️案例1：
         var num = 2;
         switch(num) {
         	case 1:
         		console.log('这是1');
         		break;
         	case 2:
         		console.log('这是2');
         		break;
         	case 3:
         	   console.log('这是3');
            break;
            default:
         	   console.log('没有匹配结果');
         }  // 最终输出'这是2'

         ❤️案例2：
         var name = prompt('请输入一个水果');
         switch(name) {
         	case '苹果':
         		alert('100元');
         		break;
         	case '香蕉':
         		alert('50元');
         		break;
         	case '西瓜':
         		alert('30元');
         		break;
            default:
         	   alert('没有此水果');
         }  // 用户输入的水果名在case中则出现相应的价格，若没有在case中则出现'无此水果'
         ```

      5. switch 与 if else 的区别

         > a. switch 通常处理比较确定值的情况；if else 更灵活，常用于范围判断；
         >
         > b. switch 执行效果更高，通过确定值直接跳到相应的执行语句；if else 中条件有多少就需要判断多少次，执行效率会较低些；
         >
         > c. 当分支较少的情况下，if else 执行效率比 switch 高；
         >
         > d. 当分支较多的情况下，if else 执行效率比 switch 低；

   3. 三元表达式（三元运算符）

      ```javascript
      条件表达式 ? 表示1 : 表达式2
      // 执行思路
      a. 若条件表达式为true 则返回表达式1
      b. 若条件表达式为false 则返回表达式2

      ❤️案例：
      var age = prompt('请输入一个数字');
      var result = age < 10 ? '0'+ age : age;
      alert(result);  // 用户输入数小于10则补0（如09）；若大于等于10则输出输入的原值
      ```

### 8. 流程控制-循环

> a. 重复执行某些语句/代码
>
> b. 一组被重复循环的语句称为循环体，是否继续重复循环，取决于终止条件
>
> c. 循环体与循环的终止条件组成的语句，称为循环语句

1. for 循环

   ```javascript
   // 重复执行某些代码，通常与计数有关（一个代码重复多少次）
   for (初始化变量;条件表达式;操作表达式){
     循环体
   }
   初始化变量：用var声明的一个普通变量，用于作为计数器使用
   条件表达式：用于决定每一次循环是否继续执行（终止的条件）
   操作表达式：每次循环最后执行的代码，常用于计数器变量进行更新（递增或递减）

   ❤️案例：
   for(var i = 1; i <= 100; i++){
      console.log('你好');
   }
   // 执行思路
   a. 先设置一个变量i为1
   b. 判断i变量是否小于等于100，满足条件则执行语句console.log
   c. 执行完语句后继续执行i++(递增)；
   d. i++后，变量i的值更新，继续重复上述流程，直到i的值不满足条件（<=100）终止循环

   ❤️案例：
   var num = prompt('请输入一个数');
   for (var i =1; i <= num; i++){
      console.log('你好！');
   } // 用户输入多少则执行多少次

   ❤️案例：
   for （var i = 1；i <= 100; i++){
      if (i == 1){
         console.log('今天你出生啦')；
      } else if (i == 100){
         console.log('今天是你去世的日子')；
      } else {
         console.log('你今年'+i+'岁');
      }
   }  // 循环输出你今天1-100岁,1与100显示单独语句

   ❤️案例：计算1~100的总和
   var sum =0;
   for (var i = 1;i <= 100;i++){
      sum += i;
   }
   ```

   断点调试

   > a. 浏览器 F12-->sources-->找到需要调试的文件-->在程序的某一行设置断点（单机+刷新）
   >
   > b. Watch 可以进行程序监视
   >
   > c. F11 进行程序单步执行

❤️ 实际案例：

```javascript
// 通过用户输入的人数弹出相应的输入框且计算总成绩与总成绩的平均值
var age = prompt('请输入班级总人数');
var sum = 0; // 求和
var aver = 0; // 求平均值
for (var i = 1; i <= age; i++) {
  var grade = prompt('请输入第' + i + '学生的成绩');
  sum += parseFloat(grade); // 用户输入框的值都为字符串型，需转换为数值型
} // 设置用户输入数为多少则弹框多少次
aver = sum / age;
alert('班级总成绩为：' + sum);
alert('班级总成绩的平均分为：' + aver);

// 一行打印5个❤️
var str = ''; // 设置一个变量为空
for (var i = 1; i <= 5; i++) {
  str += '❤️'; // 空值与❤️相加=❤️
}
```

2. 双重 for 循环

   ```javascript
   for(外层的初始化变量;外层的条件表达式;外层的操作表达式){
      for(里层的初始化变量;里层的条件表达式;里层的操作表达式){
         执行语句
      }
   }  // 里层的循环是外层循环的语句；外层循环一次，里层循环执行全部

   ❤️案例：
   for (var i = 1; i<=3; i++){
      console.log('这是外层循环第'+i+'次');
      for (var j = 1; j<=3; j++){
         console.log('这是里层循环第'+j+'次');
      }
   }
   // 执行思路
   a. 先执行外层的for，i满足条件打印第一次外层循环的执行语句
   b. 打印完第一次外层循环语句后执行里层循环，直到不满足里层循环条件，则停止里层循环
   c. 里层循环停止则回到外层循环继续判断i是否满足条件，满足条件则继续打印第二次外层循环语句
   d. 打印完第二次外层循环语句后再次执行里层循环（重新开始里层循环的判断条件，从0开始）
   f. 直到打印完第三次外层语句与第三次外层中第三次里层的语句，才停止全部循环

   ❤️案例：一行打印五个❤️，总共打印五行
   var str = '';
   for (var i = 1; i <= 5; i++) {
      // 外层循环负责打印五行
      for (var j = 1; j <= 5; j++) {
      // 里层循环负责一行打印五个❤️
         str += '❤️';
      }
      // 一行打印完五个后换行
      str += '\n';
   }
   console.log(str);

   ❤️案例：打印三角型，从一行10个到一行1个
   var str = '';
   for (var i = 1; i <= 10; i++) {
     // 外层循环负责打印10行
      for (var j = i; j <= 10; j++) {
       // 里层循环负责一行打印10-i个
         str += '❤️';
      }
      str += '\n';
   }

   ❤️案例：九九乘法表
   var str = '';
   for (var i = 1; i <= 9; i++) {
      for (var j = 1; j <= i; j++) {
         str += j + 'x' + i + '=' + i * j + '\t';
      }
      str += '\n';
   }
   ```

3. while 循环

   ```javascript
   while(条件表达式){
     // 循环体
   } // 当条件表达式结果为true则执行循环，若为false则退出循环

   var num = 1;
   while(num <= 100){
      console.log('你好')
      num++；  // 操作表达式不能漏，否则会进入死循环，无法结束循环
   }

   ❤️案例：1～100总和
   var num = 1；
   var sum = 0;
   while(num <= 100){
      sum += num;
      num++;
   }
   ❤️案例：弹出一个提示框”喜欢IU吗“，如果输入喜欢则结果，否则一直循环
   var IU = prompt('喜欢IU吗？');
   while (IU != '喜欢'){
      IU = prompt('喜欢IU吗');
   }
   ```

4. do..while 循环

   ```javascript
   do {
     //循环体
   } while (条件表达式)
   // 执行思路
      a. 先执行一次循环体（至少执行一次循环体）
      b. 在判断调教，如果条件表达式结果为true则继续执行循环体，若为false则退出循环
   var num = 1;
   do {
      console.log('你好');
      num++;
   } while (num <= 10)  // 当num大于10则退出循环

   ❤️案例：弹出一个提示框”喜欢IU吗“，如果输入喜欢则结果，否则一直循环
   do {
      var IU = prompt('喜欢IU吗');
   } while (IU != '喜欢')
   ```

> 循环总结：
>
> a. 用来计数的情况通常用 for 循环
>
> b. while 与 do..while 通常用于做更复杂的判断，比 for 更灵活
>
> c. while 与 do..while 执行顺序不一样，while 先判断后执行，do..while 先执行一次后判断（至少执行一次）
>
> d. for 的写法更简洁直观

5. continue break

   1. continue 关键字

      ```javascript
      continue 关键字用于立即跳出本次循环，继续下一次循环

      for(var i = 1; i <= 5; i++){
         if(i == 3){
            continue;
         }
         console.log('我正在吃第'+ i +'个包子');
      } // 最终执行4次循环，当i=3时退出本次循环继续下一次（i=4）的循环
      ```

   2. break 关键字

      ```javascript
      break 关键字用于立即跳出整个循环（直接结束循环）

      for(var i = 1; i <= 5; i++){
         if(i == 3){
          break;
        }
         console.log('我正在吃第'+ i +'个包子');
      } // 最终执行2次循环，当i=3时直接结束整个循环
      ```

简易 ATM 案例：

```javascript
var sum = 100; // 整体设置余额数为sum，存取多次后余额都能统一，退出后余额重置
while (true) {
  // 设置一个初始弹窗
  var oper = prompt(
    '请输入您要的操作：\n 1.存钱 \n 2.取钱 \n 3.显示余额 \n 4.退出'
  );
  // 利用if将则进入一个步骤
  if (oper == '1') {
    var saver = parseFloat(prompt('请输入存钱金额'));
    var sum = saver + sum;
    alert('目前余额为：' + sum);
  }
  // 结束后回到第一个弹窗，继续下一步
  if (oper == '2') {
    var get = parseFloat(prompt('请输入取钱金额'));
    var sum = sum - get;
    alert('目前余额为：' + sum);
  }
  if (oper == '3') {
    alert('目前余额为：' + sum);
  }
  // 设置用户输入为4 则退出循环
  if (oper == '4') {
    break;
  }
}
```

### 9. 数组

> 一组数据的集合，将一组数据存在一个变量内
>
> var num = [1,2,3,4,5]; // num 变量内存储 5 个值

1. 创建数组

   ```javascript
   a.new创建;
   var 数组名 = new Array();
   var arr = new Array(); // 创建一个新的空数组

   b.数组字面量创建;
   var 数组名 = [];
   var arr = [1, 2, 'IU', true]; // 数组中可放任意的值，数组里面的值用逗号隔开，数组中的值称为数组元素
   ```

2. 获取数组中的元素（提取数组元素中的某一项）

   ```javascript
   索引（下标）：用来访问数组元素的序号（数组下标从0开始）
   表达形式：数组名[索引号]

   var arr = ['小白','小黑','小黄','小红'];
        索性号      0      1     2     3
   console.log(arr[3]);  // 输出为小红
   ```

3. 遍历数组（提取数组中的全部元素）

   ```javascript
   将数组中的每个元素访问一次；利用循环，可一次性将数组中的元素全部提取出来

   var arr = ['小白','小黑','小黄','小红'];
   for (var i = 0; i < 4; i++){
      console.log(arr[i]);
   }  // 因为数组索引号从0开始，所以i=0；且索引号到3结束，所以i<4；
   ```

4. 数组长度

   ```javascript
   a. 使用“数组名.length“可以访问数组元素的数量
   b. 数组的长度是元素的个数，不能加等于号

   var arr = ['小白','小黑','小黄','小红'];
   for (var i = 0; i < arr.length; i++){
      console.log(arr[i]);
   }

   ❤️案例：求[2,6,1,7,4]里面所有元素的和以及平均值
   var sum = 0;
   var aver = 0;
   var arr = [2, 6, 1, 7, 4];
   for (var i = 0; i < arr.length; i++) {
      sum = sum + arr[i];  // i是计数器，这里需要的是数组元素相加，所以应该为sum+arr[i];
   }
   aver = sum / arr.length; // 用sum/数组元素个数即可得出平均值；
   console.log(sum,aver);  // 输出多个变量用逗号隔开

   ❤️案例：求[2, 6, 1, 77, 52, 25, 7]中的最大值
   var arr = [2, 6, 1, 77, 52, 25, 7];
   var max = arr[0];  // 设置一个存储最大值的变量为数组元素中的第一个数
   for (var i =1; i < arr.length; i++){  // 因为已经将数组元素中的第一个数赋值给max，所以i可以从索引号1开始比较
      if (arr[i] > max){
         max = arr[i];  // 设置if条件：当数组元素大于max的值时，替换掉max中的原值，即可得出最大值
      }
   }

   ❤️案例：将数组['red', 'blue', 'green']输出为：red|blue|green|
   var arr = ['red', 'blue', 'green'];
   var str = '';
   var sep = '|';
   for (var i = 0; i < arr.length; i++) {
      str += arr[i] + sep;
   }
   ```

5. 数组中新增元素

   ```javascript
   a. 通过修改length长度新增数组元素
   var arr = ['red', 'blue', 'green'];
   arr.length = 5; // 把数组长度修改为5，数组中应该有5个元素，后面增加的值为默认值：undefined;

   b. 通过修改数组索引新增数组元素
   var arr = ['red', 'blue', 'green'];
   arr[3] = 'IU'; // 输出arr数组元素为4个，新增一组元素：IU；
   arr[0] = 'yellow'  // 输出第一个数组元素被替换为yellow；
   arr = 'hz'  // 如果直接给数组名赋值会覆盖掉前面的数组元素；

   ❤️案例：设置一个数组，数组元素为1～10；
   var arr = [];  // 设置一个空数组
   for (var i = 0; i < 10; i++) {  // 索引从0开始，所以i=0；1-10位10个数，所以i<10；
     arr[i] = i + 1;  // 因为从0开始，所以需i+1；因需输出数组，所以需arr[i]=i;
   }

   ❤️案例：将数组[2, 0, 6, 1, 77, 0, 52, 25, 7]中大于等于10的数组成一个新的数组
   方法A：
   var arr = [2, 0, 6, 1, 77, 0, 52, 25, 7];
   var arr1 = [];  // 将新数组设置一个变量赋值为空数组；
   var j = 0;  // 设置一个新数组的索引变量为0；
   for (var i = 0; i < arr.length; i++) {
     if (arr[i] >= 10) {
         arr1[j] = arr[i]; // 新数组应该从0开始依次递增
         j++;
      }
   }
   方法B：
   var arr = [2, 0, 6, 1, 77, 0, 52, 25, 7];
   var arr1 = [];
   for (var i = 0; i < arr.length; i++) {
      if (arr[i] >= 10) {
         arr1[arr1.length] = arr[i];  // 设arr1.length检测数组元素，
      }
   }
   ```

6. 数据排序（冒泡排序）

   ```javascript
   是一种简单算法，可以将一系列数据按照一定的顺序进行排列（从小到大或从大到小）
   // 将数组从小到大排列
   var arr =[5,4,3,2,1];
   for (var i = 0; i <= arr.length-1; i++){  // 外层循环管理的是总交换的次数
      for (var j = 0; j <= arr.length - i - 1; i++){  //里层循环管理的是每一次交换时的次数
      // 内部交换两个变量值，前一个与后一个相比较
         if（arr[j] > arr[j + 1]){
            var temp = arr[j];
            arr[j] = arr[j + 1];
            arr[j + 1] = temp;
         }
      }
   }
   ```

❤️ 案例

```javascript
a. 将数组[2, 0, 6, 1, 77, 0, 52, 25, 7]内容反过来输出
var arr = [2, 0, 6, 1, 77, 0, 52, 25, 7];
var arr1 = [];
for (var i = arr.length - 1; i >= 0; i--) {
   // 将新数组的最后一个（arr.length - 1)给新数组索引第0个元素（arr1.length）；新数组元素索引从0开始所以i>=0；采取递减形式
   arr1[arr1.length] = arr[i];
}
```

### 10. javascrip 函数

1. 函数的概念

   > a. 封装一段可以被重复执行调用的代码块，为了让大量代码重复使用
   >
   > b. 封装：把一个或多个功能通过函数进行封装，对外只提供一个简单的函数接口

2. 函数的使用

   ```javascript
   a. 申明函数   //  函数时做某些事，函数名一般用动词；函数不调用自己不执行
   	function 函数名(){
       // 函数体（函数代码）;
      }

   b. 调用函数  // 调用函数时勿忘加小括号
   	函数名();

   ❤️案例：利用函数计算1～100总和
   function getSum(num1,num2){
      var sum = 0;
      for (var i = num1; i <= num2; i++){
         sum += i;
     }
   }
   getSum(1,100); // 1～100的总和
   getSum(10,50); // 10～50的总和
   ```

3. 函数的参数

   ```javascript
   // 参数的作用：在函数内部的值不固定时，可通过参数在调用函数时传递不同的值进去

   function 函数名(形参1,形参2...){
       // 在声明函数的小括号内是形参（形式上的参数）
   }
   函数名(实参1,实参2...)；  // 在函数调用的小括号内是实参（实际的参数）

   形参与实参的执行过程：
   function cook(aru){  // 形参类似于一个变量，是接收实参的
      console.log(aru);
   }
   cook('IU');
   a. 先进行函数调用，在进行函数判断
   b. 调用函数后，实参的值赋值给形参，进行代码输出

   ❤️案例：利用函数求任意两个的和

   function getSum(num1, num2){
   	console.log(num1 + num2);
   }
   getSum(1,100); // 输出为101，多个参数用逗号隔开

   ⚠️ 函数实参与形参个数不匹配的情况
   function getSum(num1, num2){
   	console.log(num1 + num2);
   }
   getSum(1,2,3)； // 输出为3，多出的实参3，不会加入运算
   getSum(1)； // 输出为NaN，num2未赋值为undefined,数值+undefined=NaN

   ```

4. 函数的返回值

   ```javascript
   a. return语句：将函数返回值返回给函数调用者
   b. return是终止函数，return后的代码不会执行；
   c. return只会返回一个值，多个值的情况会返回最后一个值；
   d. 函数中没有return返回的值为undefined;

   function 函数名(){
      return 需要返回的结果;  // 当函数遇到return会把后面的结果返回给函数的调用者；函数名()=return后面的结果；
   }
   函数名();

   function cook(aru){
      return aru;
   }
   console.log(cook('IU'));  // 输出为IU

   ❤️案例：求两个数的最大值
   function getMax(num1,num2){
      if(num1 > num2){
         return num1;
      } else {
         return nmu2;
      }
   }
   console.log(getMax(1,2));  // 输出为2

   ❤️案例：利用函数求数组中的最大值
   function getMax(arr){
      var max = arr[0];
      for (var i = 1; i < arr.length; i++) {
         if (age[i] > max) {
         max = age[i];
     	   }
   	}
      return max;
   }
   var re = getMax([5,2,99,101]);  // 实际开发中常用一个变量接收函数的返回结果
   console.log(re); // 输出为101；
   ```

5. arguments 的使用

   ```javascript
   a. 当不确定有多少个参数传递的情况下，可以用arguments来获取
   b. arguments是当前函数的一个内置对象，argumets对象中存储了传递的所有实参
   c. 展示形式是一个伪数组（不是真正意义上的数组），伪数组的特性：
      i. 具有数组的length属性；
      ii. 按照索引的方式进行存储；
      iii. 没有真正数组的一些方法;

   function fn(){
      console.log(arguments); // 里面存储了所有传递过来的实参。输出[1,2,3];
      console.log(arguments[2]);  // 输出为3
   }
   fn(1,2,3);

   function age(){
      for (var i = 0; i < arguments.length; i++){
         console.log(arguments[i]);
      }
   }
   ```