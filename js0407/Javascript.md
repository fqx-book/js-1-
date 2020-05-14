![](imgs\cake.png)

JavaScript 是一种脚本，一门编程语言，它可以在网页上实现复杂的功能，网页展现给你的不再是简单的静态信息，而是实时的内容更新，交互式的地图，2D/3D 动画，滚动播放的视频等等。





# 初识

## 应用场景

- 处理网页功能及部分特效
- 基于NodeJS开发服务端



## 环境准备

```html
<html>
	<head>
        <title>JavaScript初识</title>
    </head>
    <body></body>
    <!-- 我才是压轴戏 -->
    <script>
    	console.log('学海无涯苦作舟。');
    </script>
</html>
```



## 无话不说的人

```javascript
// 控制台输出
console.log('输出内容');

// 警告框
alert('确定离开页面？');
```



## 内嵌还是外链？

- 内嵌

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
  </head>
  <body>
  
  </body>
  <script>
  	console.log('窗前明月光，疑是地上霜。');
  </script>
  </html>
  ```

- 外链

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
  </head>
  <body>
  
  </body>
  <script src="js/index.js" type="text/javascript"></script>
  </html>
  ```



## 箱子（变量）

装载数据的容器

<img src="imgs\boxes.png" style="zoom:50%;" />



### 小知识

- 通过ID获取指定输入框的值

  ```js
  document.getElementById('id_val').value;
  ```

### 定义

```js
// 定义变量
var date;
let time;
```

### 赋值

```js
date = '2019';
time= '12:00:00';
```

### 更新

```js
date = '2020';
time = '13:00:00';
```

### 关于变量命名的规则

- 变量名不要以下划线开头—— 以下划线开头的被某些JavaScript设计为特殊的含义，因此可能让人迷惑。
- 变量名不要以数字开头。这种行为是不被允许的，并且将引发一个错误。
- 一个可靠的命名约定叫做 ["小写驼峰命名法"](https://en.wikipedia.org/wiki/CamelCase#Variations_and_synonyms)，用来将多个单词组在一起，小写整个命名的第一个字母然后大写剩下单词的首字符。
- 让变量名直观，它们描述了所包含的数据。不要只使用单一的字母/数字，或者长句。
- 变量名大小写敏感——因此`myage`与`myAge`是2个不同的变量。
- 最后也是最重要的一点—— 你应当避免使用JavaScript的保留字给变量命名。保留字，即是组成JavaScript的实际语法的单词！因此诸如 `var`, `function`, `let和` `for`等，都不能被作为变量名使用。浏览器将把它们识别为不同的代码项，因此你将得到错误。

### 数据类型

```js
// 数值
var age = 18;
var weight = 65.5;

// 字符串
var text = '床前明月光';
var text2 = "疑是地上霜";

// bool
var result = false;
var result2 = true;
var result3 = 1 > 3;

// 箱子不存在(undefined)
var d;
console.log(d);

// 箱子里面是空(null)的
var d=null;
```

## 运算符号

### 算术运算符

| 运算符 | 名称                 | 作用                                                         | 示例                                                |
| :----- | :------------------- | :----------------------------------------------------------- | :-------------------------------------------------- |
| `+`    | 加法                 | 两个数相加。                                                 | `6 + 9`                                             |
| `-`    | 减法                 | 从左边减去右边的数。                                         | `20 - 15`                                           |
| `*`    | 乘法                 | 两个数相乘。                                                 | `3 * 7`                                             |
| `/`    | 除法                 | 用右边的数除左边的数                                         | `10 / 5`                                            |
| `%`    | 求余(有时候也叫取模) | 在你将左边的数分成同右边数字相同的若干整数部分后，返回剩下的余数 | `8 % 3` (返回 2，8除以3的倍数，余下2 。)            |
| `**`   | 幂                   | 取底数的指数次方，即指数所指定的底数相乘。它在EcmaScript 2016 中首次引入。 | `5 ** 5` (返回 3125，相当于 `5 * 5 * 5 * 5 * 5` 。) |

```js
// 定义基础变量
var num1 = 100;
var num2 = 3;
// 加法
console.log(num1+num2);
// 减法
console.log(num1-num2);
// 乘法
console.log(num1*num2)
// 除法
console.log(num1/num2);

// 额外内容
// +号可以作为字符串的拼接
var date='2020-04-01';
var time='12:00:00';
console.log(date+" "+time);

// - 可以作为负号使用
var num3 = -10;
console.log(num3);
// 自增
num3++;
// 自减
numb1--;
```

### 赋值运算符

| 运算符 | 名称     | 作用                                           | 示例             | 等价于              |
| :----- | :------- | :--------------------------------------------- | :--------------- | :------------------ |
| `+=`   | 加法赋值 | 右边的数值加上左边的变量，然后再返回新的变量。 | `x = 3;x += 4;`  | `x = 3;x = x + 4;`  |
| `-=`   | 减法赋值 | 左边的变量减去右边的数值，然后再返回新的变量。 | `x = 6;x -= 3;`  | `x = 6;x = x - 3;`  |
| `*=`   | 乘法赋值 | 左边的变量乘以右边的数值，然后再返回新的变量。 | `x = 2;x *= 3;`  | `x = 2;x = x * 3;`  |
| `/=`   | 除法赋值 | 左边的变量除以右边的数值，然后再返回新的变量。 | `x = 10;x /= 5;` | `x = 10;x = x / 5;` |

```js
// 直接赋值
var name = '张三';
var age = 100;

// 复合赋值
name+= '丰'; 	// 等于: name = name + '丰';
age-=10;		// 等于: age = age-10;
```



### 比较运算符

| 运算符 | 名称       | 作用                           | 示例          |
| :----- | :--------- | :----------------------------- | :------------ |
| `===`  | 严格等于   | 测试左右值是否相同             | `5 === 2 + 4` |
| `!==`  | 严格不等于 | 测试左右值是否**不**相同       | `5 !== 2 + 3` |
| `<`    | 小于       | 测试左值是否小于右值。         | `10 < 6`      |
| `>`    | 大于       | 测试左值是否大于右值           | `10 > 20`     |
| <=     | 小于或等于 | 测试左值是否小于或等于右值。   | `3 <= 2`      |
| >=     | 大于或等于 | 测试左值是否大于或等于正确值。 | `5 >= 4`      |

```js
// 定义基础变量
var num4 = 10;
var num5 = 12;
var num6 = '12';

// 大于
console.log(num4 > num5);
// 小于
console.log(num4 < num5);
// 不等于
console.log(num4 != num5);
// 等于
console.log(num4 == num5);
// 全等于
console.log(num4 === num5);
console.log(num5 === num6);

// 全不等
console.log(num4 !== num5);
console.log(num5 !== num6);

```

## 条件语句

<img src="imgs\cookie-choice-small.png" style="zoom: 50%;" />

### if语句

用于等值，范围多条件判断等场景

#### if ... else 语句

**语法**

```js
if (条件判断) {
  // 条件成立则执行 
} else {
  // 条件不成立则执行
}
```

#### if ...elseif... else 语句

```js
if (条件判断A) {
  // 条件A成立则执行 
} else if(条件判断B) {
  // 条件B成立则执行
} else {
  // 所有条件不成立则执行
}
```

#### if语句小知识

```js
// 当if语句、else if语句、else语句对应代码块中只存在一行代码，可以不写`{}`
// 为了代码的阅读性，请不要省略`{}``
// 下面三句代码意思相等
// 1
if(score >=60) console.log('等分及格');
else console.log('得分不及格');
// 2
if(score >=60) 
    console.log('等分及格');
else 
    console.log('得分不及格');
// 3
if(score >=60){
    console.log('等分及格');
}else{
    console.log('得分不及格');
} 
```



#### 逻辑运算符

- `&&` — 逻辑与; 使得并列两个或者更多的表达式成为可能，只有当这些表达式每一个都返回`true`时，整个表达式才会返回`true.`
- `||` — 逻辑或; 当两个或者更多表达式当中的任何一个返回 `true` 则整个表达式将会返回 `true`.
- ! — 逻辑非; 对一个布尔值取反, 非true返回false,非false返回true.

### 三目运算符

一个if简洁版版的条件判断语句

**语法**

```js
condition ? exprIfTrue : exprIfFalse
```

### switch语句

用于匹配等值判断的条件语句

**语法**

```js
switch (表达式) {
  case choice1:
    // 当表达式结果等于 choice1时，执行此代码块
    break;

  case choice2:
     // 当表达式结果等于 choice2时，执行此代码块
    break;
    
  default:
    // 当表达式结果与所有 case的值都不匹配时，则执行
}
```

#### 小知识

case对应语句需要增加执行的break，否则将会出现不在预期的错误。

### 嵌套控制

```js
// if嵌套
if(条件a){
	if(条件b){
		// 当条件a+条件b同时满足是则运行
	}
}
// 三目嵌套
条件1?条件2?表达式2-1:表达式2-2:表达式1-2
```





## 循环

重复执行某组动作或者重复完成某个任务

<img src="imgs\loop_js-02-farm-cn.png" style="zoom: 67%;" />



### while循环

```js
while (循环条件) {
  // 循环体
}
```

### do...while循环

```js
do {
  // 循环体
} while (循环条件)
```

### for循环

```js
for (初始语句; 循环条件; 迭代语句) {
  // 循环体
}
```

### 嵌套循环

```js
for (初始语句; 循环条件; 迭代语句) {
	for (初始语句2; 循环条件2; 迭代语句2) {
		// 循环体
	}
}
```





# 中场

## 数据类型判断

简介

**`typeof`** 操作符返回一个字符串，表示未经计算的操作数的类型。

### 语法

```js
typeof operand
typeof(operand)
```

**`operand`**

需要判断数据类型的`表达式`或者`对象`

### 常见类型及返回值

| 类型                                                         | 结果                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [Undefined](https://developer.mozilla.org/zh-CN/docs/Glossary/undefined) | `"undefined"`                                                |
| [Null](https://developer.mozilla.org/zh-CN/docs/Glossary/Null) | `"object"` (见[下文](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/typeof#null)) |
| [Boolean](https://developer.mozilla.org/zh-CN/docs/Glossary/Boolean) | `"boolean"`                                                  |
| [Number](https://developer.mozilla.org/zh-CN/docs/Glossary/Number) | `"number"`                                                   |
| [BigInt](https://developer.mozilla.org/zh-CN/docs/Glossary/BigInt) | `"bigint"`                                                   |
| [String](https://developer.mozilla.org/zh-CN/docs/Glossary/字符串) | `"string"`                                                   |
| [Symbol](https://developer.mozilla.org/zh-CN/docs/Glossary/Symbol) (ECMAScript 2015 新增) | `"symbol"`                                                   |
| 宿主对象（由 JS 环境提供）                                   | *取决于具体实现*                                             |
| [Function](https://developer.mozilla.org/zh-CN/docs/Glossary/Function) 对象 (按照 ECMA-262 规范实现 [[Call]]) | `"function"`                                                 |
| 其他任何对象                                                 | `"object"`                                                   |



## 常量

一旦赋值就不能改变的变量

### **语法**

```js
const valName = val;
```



## 数组

用于多数据存储的特殊结构，数组需要通过索引（下标）进行数据的访问。

### **语法**

```js
[element0, element1, ..., elementN]
new Array(element0, element1[, ...[, elementN]])
new Array(arrayLength)
```

### 常用属性

| 属性名称                                                     | 属性含义               |
| ------------------------------------------------------------ | ---------------------- |
| [`length`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/length) | 返回当前数组的元素个数 |

### 常用函数

| 函数名称                                                     | 函数描述                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`pop()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) | 删除数组的最后一个元素，并返回这个元素。                     |
| [`push()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/push) | 在数组的末尾增加一个或多个元素，并返回数组的新长度。         |
| [`shift()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) | 删除数组的第一个元素，并返回这个元素。                       |
| [`sort()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) | 对数组元素进行排序，并返回当前数组。默认排序顺序是在将元素转换为字符串，然后比较它们的UTF-16代码单元值序列时构建的 |
| [`unshift()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) | 在数组的开头增加一个或多个元素，并返回数组的新长度。         |
| [`slice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) | 抽取当前数组中的一段元素组合成一个新数组。                   |
| [`indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) | 返回数组中第一个与指定值相等的元素的索引，如果找不到这样的元素，则返回 -1。 |
| [`lastIndexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf) | 返回数组中最后一个（从右边数第一个）与指定值相等的元素的索引，如果找不到这样的元素，则返回 -1。 |
| [`join()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/join) | 连接所有数组元素组成一个字符串。                             |
| [`splice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) | 在任意的位置给数组添加或删除任意个元素。<br />array.splice(start[, deleteCount[, item1[, item2[, ...]]]]) |

### 迭代/遍历数组

```js
// for循环遍历
for(let i=0;i<arr.length;i++){
    console.log(arr[i]);
}
// for...in循环遍历
for(let i=0;i<arr.length;i++){
    console.log(arr[i]);
}
// 自带函数遍历
fruits.forEach(function (item, index, array) {
    console.log(item, index);
});
```



## 函数（方法）

### **简介**

**function**，**函数**，是一个可以被其他代码或其自身调用的代码片段，或者是一个指向该函数的[变量](https://developer.mozilla.org/en-US/docs/Glossary/variable) 。



一个**函数定义**（也称为**函数声明**，或**函数语句**）由一系列的[`function`](https://developer.mozilla.org/zh-CN/docs/JavaScript/Reference/Statements/function)关键字组成，依次为：

- 函数的名称。
- 函数参数列表，包围在括号中并由逗号分隔。
- 定义函数的 JavaScript 语句，用大括号`{}`括起来。



### **语法**

```js
function name([param,[, param,[..., param]]]) {
   [statements]
}
```

- `name`

  函数名

- `param`

  要传递给函数的参数的名称。不同引擎中的最大参数数量不同。

- `statements`

  包含函数体的语句。

### 创建

#### 具名函数

*自身拥有名字的函数*

```js
// 无参具名函数
function foo() {
    // 函数体
}
```

#### 匿名函数

自身没有名称的函数，需要通过引用调用或者执行运行

```js
function () {};
// 引用调用
var getDate = function (){
    // 方法体    
}

// 通过立即调用函数表达式可直接运行
(function(){
    // 方法体
})();
```

### 参数

```js
// 无参函数
function getDate(){
    // 方法体
}

// 带参函数
function getDiff(num){
   // 方法体 
}

// 带参函数，参数设置默认值
function getDiff(num=0){
    // 方法体
}
```

### 返回值

```js
/*
	1.return可以将某一个值或者表达式计算后的结果返回给调用者
	2.return可以返回空的结果（将return作为停止符来使用）
	3.return之后的代码将不能被执行
*/
// 无参无返回值函数
function getTime(){
    console.log('2019-12-01 00:00:00');
}

// 带参、返回值函数
function add(num1,num2){
	return num1+num2;
}

// 函数停止符
function scroeLevel(score){
    if(score <0){
        return 0;
    }
}
```

### 作用域





### this关键字

在绝大多数情况下，函数的调用方式决定了`this`的值。`this`不能在执行期间被赋值，并且在每次函数被调用时`this`的值也可能会不同。

-  在对象方法中， this 指向调用它所在方法的对象。
-  单独使用 this，它指向全局(window)对象。   
-  函数使用中，this 指向函数的所属者。
-  严格模式下函数是没有绑定到 this 上，这时候 this 是 undefined。
-  在 HTML 事件句柄中，this 指向了接收事件的 HTML 元素。
-  apply 和 call 允许切换函数执行的上下文环境（context），即 this 绑定的对象，可以将 this 引用到任何对象。



#### 全局环境

在全局执行环境中（在任何函数体外部）`this` 都指向全局对象。

```js
// 在浏览器中, window 对象同时也是全局对象：
console.log(this === window); // true

a = 37;
console.log(window.a); // 37

this.b = "MDN";
console.log(window.b)  // "MDN"
console.log(b)         // "MDN"
```





## 对象

对象是一个包含相关数据和方法的集合（通常由一些变量和函数组成，我们称之为对象里面的属性和方法）



# 常用对象及其函数

## String

### 字符串模板（ES6）

```js
`string text`

`string text line 1
 string text line 2`

`string text ${expression} string text`

tag `string text ${expression} string text`


let name ='张三丰';
let age = 100;
// 变量获取例子
let temp1 = `我的名字是：${name}，今年${age}岁。`
// 变量及表达式例子
let temp2 = `我的名字是：${name}，今年${age}岁，再过三年我就${age+3}岁了。`

```

### 字符串拼接

```js
// 通过 + 号连接
let desc = "JavaScript ( JS ) 是一种具有函数优先的轻量级，解释型或即时编译型的编程语言。 " +
                 " JavaScript 的标准是 ECMAScript 。" +
                 "不要将 JavaScript 与 Java编程语言 混淆。";
// 
let desc = "JavaScript ( JS ) 是一种具有函数优先的轻量级，解释型或即时编译型的编程语言。 \
JavaScript 的标准是 ECMAScript 。\
不要将 JavaScript 与 Java编程语言 混淆。";
```



### 构建方式

```js
let str = "JavaScript真好玩，我要学习。";
let str2 = String('JavaScript真好用，我要学习。');
let str3 = new String('JavaScript真简单，我要学习。');
```



| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`length`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/length) | 返回了字符串的长度。                                         |
| [`endsWith()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith) | 判断一个字符串的是否以给定字符串结尾，结果返回布尔值。       |
| [`startsWith()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith) | 判断字符串的起始位置是否匹配其他字符串中的字符。             |
| [`indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf) | 从字符串对象中返回首个被发现的给定值的索引值，如果没有找到则返回-1。 |
| [`lastIndexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf) | 从字符串对象中返回最后一个被发现的给定值的索引值，如果没有找到则返回-1。 |
| [`replace()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace) | 被用来在正则表达式和字符串直接比较，然后用新的子串来替换被匹配的子串。 |
| [`split()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/split) | 通过分离字符串成字串，将字符串对象分割成字符串数组。         |
| [`substring()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/substring) | 返回在字符串中指定两个下标之间的字符。                       |
| [`toLowerCase()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase) | 将字符串转换成小写并返回。                                   |
| [`toUpperCase()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) | 将字符串转换成大写并返回。                                   |
| [`trim()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/trim) | 从字符串的开始和结尾去除空格。                               |
| [`slice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/slice) | 摘取一个字符串区域，返回一个新的字符串。                     |



# 常用函数（持续更新）

js自带常用函数

| 函数名称                                                     | 阐述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`isNaN()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/isNaN) | `**isNaN()**`函数判断一个值是否是[`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)。 |
| [`parseInt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseInt) | `**parseInt()**` 函数解析字符串参数，并返回指定的基数（基础数学中的数制）的整数。 |
| [`parseFloat()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseFloat) | `**parseFloat()**` 函数解析字符串参数，并返回一个浮点数。    |

