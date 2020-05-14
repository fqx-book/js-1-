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
| [`sort()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) | 对数组元素进行排序，并返回当前数组。                         |
| [`unshift()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) | 在数组的开头增加一个或多个元素，并返回数组的新长度。         |
| [`slice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) | 抽取当前数组中的一段元素组合成一个新数组。                   |
| [`indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) | 返回数组中第一个与指定值相等的元素的索引，如果找不到这样的元素，则返回 -1。 |
| [`lastIndexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf) | 返回数组中最后一个（从右边数第一个）与指定值相等的元素的索引，如果找不到这样的元素，则返回 -1。 |
| [`join()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/join) | 连接所有数组元素组成一个字符串。                             |
| [`splice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) | 在任意的位置给数组添加或删除任意个元素。                     |

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



## 函数

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



```js

```





# 收场

## JSON对象/对象（*）

对象是一个包含相关数据和方法的集合（通常由一些变量和函数组成，我们称之为对象里面的属性和方法）

![](imgs\person-diagram.png)

```js
// 简单变量
var person = {};
```



## 作用域(*)

**作用域**就是变量与函数的可访问范围,即**作用域**控制着变量与函数的可见性和生命周期。 

### 全局作用域

任何地方都能访问到的对象拥有全局作用域。比如window对象

### 局部作用域

只在固定的代码片段内可访问到。比如函数，for循环。

#### var 和let的区别

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



## DOM

DOM（Document Object Model——文档对象模型）是用来呈现以及与任意 HTML 或 XML文档交互的API。DOM 是载入到浏览器中的文档模型，以节点树的形式来表现文档，每个节点代表文档的构成部分



### 获取标签

| 函数名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`getElementById(String id)`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementById) | 返回一个匹配特定 [ID](https://developer.mozilla.org/en-US/docs/DOM/element.id)的标签.由于标签的 ID 在大部分情况下要求是独一无二的，这个方法自然而然地成为了一个高效查找特定元素的方法。 |
| [`querySelector()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelector) | 返回文档中与指定选择器或选择器组匹配的第一个 html标签[`Element`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element)。 如果找不到匹配项，则返回`null`。 |
| [`querySelectorAll()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll) | 返回与指定的选择器组匹配的文档中的元素列表 (使用深度优先的先序遍历文档的节点)。返回的对象是 [`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList) 。<br />**注意：** 如果`selectors`参数中包含 [CSS伪元素](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)，则返回的列表始终为空。 |
| [`getElementsByTagName()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementsByTagName) | 返回一个包括所有给定标签名称的元素的HTML集合[`HTMLCollection`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLCollection)。 |
| [`getElementsByClassName()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementsByClassName) | 返回一个包含了所有指定类名的子元素的类数组对象。             |

### 属性操作

| 函数名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`getAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/getAttribute) | 返回元素上一个指定的属性值。如果指定的属性不存在，则返回  `null` 或 `""` （空字符串）； |
| [`getAttributeNames()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/getAttributeNames) | 返回一个[`Array`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Array)，该数组包含指定元素（Element）的所有属性名称，如果该元素不包含任何属性，则返回一个空数组。 |
| [`hasAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/hasAttribute) | 返回一个布尔值，指示该元素是否包含有指定的属性（attribute）  |
| [`removeAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/removeAttribute) | 从指定的标签中删除一个属性。                                 |
| [`setAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/setAttribute) | 设置指定元素上的某个属性值。如果属性已经存在，则更新该值；否则，使用指定的名称和值添加一个新的属性。 |

### 标签小知识

- 获取输入框内的值

  ```js
  input.value;
  ```

- 获取下拉框中的所有项

  ```js
  HTMLSelectElement.options;
  ```

- 获取下拉框选择项的下标

  ```js
  HTMLSelectElement.selectedIndex;
  ```

- 获取/修改标签内容

  ```js
  element.innerText;
  ```

- 获取/修改标签的子标签 

  ```
  elemetn.innerHTML;
  ```

- 

### 操作CSS及class

```js
// 在单个语句中设置多个样式   等同于编写行内样式
elt.style.cssText = "color: blue; border: 1px solid black"; 
// 或者
elt.setAttribute("style", "color:red; border: 1px solid blue;");

// 设置特定样式，同时保持其他内联样式值不变
elt.style.color = "blue"; 
elt.style.marginLeft = "10px";

// 设置class
div.className = 'red bk'

// 注意: 以下方法，IE浏览器不支持
// 增加一个或多个class
div.classList.add("anotherclass");
div.classList.add("foo", "bar", "baz");
// 移除一个或多个class
div.classList.remove("foo");
div.classList.remove("foo", "bar", "baz");
// 判断class是否存在
div.classList.contains("foo");

```

### 事件

在某一刻发生的一连串动作

#### 浏览器事件

##### 加载事件

当网页的标签加载完成时触发

**语法**

```js
//在网页的所有标签加载完成后执行回调
window.onload = funcRef;

window.onload=function(){
    // 编写正常的CSS代码
}
```

##### 滚动条事件

元素的 `scroll `事件处理函数。

**语法**

```js
element.onscroll = functionReference
```

#### 常见事件

| 事件名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`onclick`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onclick) | 点击事件                                                     |
| [`ondblclick`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/ondblclick) | 双击事件                                                     |
| [`onfocus`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onfocus) | 得到焦点事件                                                 |
| [`onblur`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onblur) | 失去焦点事件                                                 |
| [`onkeydown`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onkeydown) | 键盘按下事件                                                 |
| [`onkeypress`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onkeypress) | 按键按住事件（连续触发。）除 Shift、Fn、CapsLock 外的任意键以外 |
| [`onkeyup`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onkeyup) | 按键释放事件                                                 |
| [`onmouseenter`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onmouseenter) | 鼠标进入事件                                                 |
| [`onmouseleave`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onmouseleave) | 鼠标离开事件                                                 |
| [`onchange`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onchange) | 改变事件                                                     |

### 创建

通过下列语句可以创建一个html标签

```js
var element = document.createElement(tagName[, options]);
```

### 新增

```js
/*
	
    insertedNode 已经经过插入newNode的新的节点
    parentNode 新插入节点的父节点
    newNode 用于插入的节点
    referenceNode newNode 将要插在这个节点之前

如果 referenceNode 为 null 则 newNode 将被插入到子节点的末尾。
*/
// 在共同父节点内的指定节点前插入行的节点
var insertedNode = parentNode.insertBefore(newNode, referenceNode);

/*
    parentNode 新插入节点的父节点
    newNode 用于插入的节点
*/
// 将一个节点附加到指定父节点的子节点列表的末尾处。
parentNode.appendChild(newNode)
```

### 删除

```js
/*
	
    child 是要移除的那个子节点.
    node 是child的父节点.
    oldChild保存对删除的子节点的引用. oldChild === child.

*/
let oldChild = node.removeChild(child);

//OR

element.removeChild(child);
```

更多事件名称请移步MDN网址：https://developer.mozilla.org/zh-CN/docs/Web/Events



## 定时器

### setTimeOut

设置一个计时器，一旦计时器到期，该计时器将执行功能或指定的代码段。

```js
// 开启定时器器
var timeoutID = window.setTimeout(function[, delay, arg1, arg2, ...]);
var timeoutID = window.setTimeout(function[, delay]);
var timeoutID = window.setTimeout(code[, delay]);

// 清除/取消定时器
window.clearTimeout(timeoutID);
```

### setInterval

重复调用一个函数或执行一个代码段，在每次调用之间具有固定的时间延迟。

```js
// 开启重复任务
var intervalID = window.setInterval(func, delay, [arg1, arg2, ...]);
var intervalID = window.setInterval(code, delay);

// 清除重复调用
window.clearInterval(intervalID);
```



## 本地存储(*)

## ES5/ES6(*)



# 常用对象及其函数

## 标准内置对象

### String

#### 字符串模板（ES6）

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

#### 字符串拼接

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



#### 构建方式

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

### Date

构建方式

```js
new Date();
new Date(value);
new Date(dateString);
new Date(year, monthIndex [, day [, hours [, minutes [, seconds [, milliseconds]]]]]);
```

| 函数名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`now()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/now) | 返回自 1970-1-1 00:00:00  UTC（世界标准时间）至今所经过的毫秒数。 |
| [`getDate()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getDate) | 根据本地时间返回指定日期对象的月份中的第几天（1-31）。       |
| [`getDay()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getDay) | 根据本地时间返回指定日期对象的星期中的第几天（0-6）。        |
| [`getFullYear()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getFullYear) | 根据本地时间返回指定日期对象的年份（四位数年份时返回四位数字）。 |
| [`getHours()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getHours) | 根据本地时间返回指定日期对象的小时（0-23）。                 |
| [`getMilliseconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMilliseconds) | 根据本地时间返回指定日期对象的毫秒（0-999）。                |
| [`getMinutes()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMinutes) | 根据本地时间返回指定日期对象的分钟（0-59）。                 |
| [`getMonth()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMonth) | 根据本地时间返回指定日期对象的月份（0-11）。                 |
| [`getSeconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getSeconds) | 根据本地时间返回指定日期对象的秒数（0-59）。                 |
| [`getTime()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime) | 返回从1970-1-1 00:00:00 UTC（协调世界时）到该日期经过的毫秒数，对于1970-1-1 00:00:00 UTC之前的时间返回负值。 |

### Math

它拥有一些数学常数属性和数学函数方法。

| 函数或属性                                                   | 描述                                                 |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| [`PI`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/PI) | 圆周率，一个圆的周长和直径之比，约等于 `3.14159`。   |
| [`ceil(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil) | 返回大于一个数的最小整数，即一个数向上取整后的值。   |
| [`floor(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) | 返回小于一个数的最大整数，即一个数向下取整后的值。   |
| [`max([x[, y[, …\]]])`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/max) | 返回零到多个数值中最大值。                           |
| [`min([x[, y[, …\]]])`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/min) | 返回零到多个数值中最小值。                           |
| [`random()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/random) | 返回一个 0 到 1 之间的伪随机数。                     |
| [`round(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/round) | 返回四舍五入后的整数。                               |
| [`trunc(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc) | 返回一个数的整数部分，直接去除其小数点及之后的部分。 |

## **全局对象**

#### Window

`window`作为全局变量，代表了脚本正在运行的窗口，暴露给 Javascript 代码。



| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`console`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/console)`只读` | 返回 console 对象的引用，该对象提供了对浏览器调试控制台的访问。 |
| [`document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/document)`只读` | 返回对当前窗口所包含文档的引用。                             |
| [`history`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/history)`只读` | 返回一个对 history 对象的引用。                              |
| [`innerHeight`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/innerHeight)`只读` | 获得浏览器窗口的内容区域的高度，包含水平滚动条(如果有的话)。 |
| [`innerWidth`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/innerWidth)`只读` | 获得浏览器窗口的内容区域的宽度，包含垂直滚动条(如果有的话)。 |
| [`outerHeight`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/outerHeight)`只读` | 返回浏览器窗口的外部高度。                                   |
| [`outerWidth`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/outerWidth)`只读` | 返回浏览器窗口的外部宽度。                                   |
| [`location`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/location) | 获取、设置 window 对象的 location, 或者当前的 URL.           |
| [`localStorage`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/localStorage)`只读` | 返回用来存储只能在创建它的源下访问的数据的本地存储对象的引用 |
| [`pageXOffset`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollX)/[`scrollX`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollX)`只读` | 返回文档/页面水平方向滚动的像素值。                          |
| [`pageYOffset`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollY)/[`scrollY`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollY)`只读` | 返回文档在垂直方向已滚动的像素值。                           |
| [`alert()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/alert) | 弹出一个警告框                                               |
| [`close()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/close) | 关闭当前标签页面（注意：该方法只能由 [`Window.open()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/open) 方法打开的窗口的 `window` 对象来调用。如果一个窗口不是由脚本打开的，那么，在调用该方法时，JavaScript 控制台会出现类似下面的错误：`不能使用脚本关闭一个不是由脚本打开的窗口。` 或 `Scripts may not close windows that were not opened by script.` 。） |
| [`confirm()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/confirm) | 显示一个具有一个可选消息和两个按钮(确定和取消)的模态对话框   |



##### 小知识

- innerHeight与outerHeight的区别(备注：innerWidth与outerWidth区别与之类似)
  ![](imgs\FirefoxInnerVsOuterHeight2.png)



### History

**`window.history`**是一个只读属性，用来获取[`History`](https://developer.mozilla.org/zh-CN/docs/Web/API/History) 对象的引用，[`History`](https://developer.mozilla.org/zh-CN/docs/Web/API/History) 对象提供了操作浏览器*会话历史*



| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`back()`](https://developer.mozilla.org/zh-CN/docs/Web/API/History/back) | 前往上一页, 用户可点击浏览器左上角的返回按钮模拟此方法. 等价于 `history.go(-1)`. |
| [`forward()`](https://developer.mozilla.org/zh-CN/docs/Web/API/History/forward) | 在浏览器历史记录里前往下一页，用户可点击浏览器左上角的前进按钮模拟此方法. 等价于 `history.go(1)`. |
| [`go()`](https://developer.mozilla.org/zh-CN/docs/Web/API/History/go) | 通过当前页面的相对位置从浏览器历史记录( 会话记录 )加载页面。比如：参数为-1的时候为上一页，参数为1的时候为下一页. 当整数参数超出界限时。例如: 如果当前页为第一页，前面已经没有页面了，我传参的值为-1，那么这个方法没有任何效果也不会报错。调用没有参数的 `go() `方法或者不是整数的参数时也没有效果。( 这点与支持字符串作为url参数的IE有点不同)。 |

### Location

**`Location `**接口表示其链接到的对象的位置（URL）。



| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`href`](https://developer.mozilla.org/zh-CN/docs/Web/API/Location/href) | 包含整个URL的一个[`DOMString`](https://developer.mozilla.org/zh-CN/docs/Web/API/DOMString)或者指定跳转位置 |
| [`search`](https://developer.mozilla.org/zh-CN/docs/Web/API/Location/search) | 包含URL参数的一个[`DOMString`](https://developer.mozilla.org/zh-CN/docs/Web/API/DOMString)，开头有一个`“?”`。 |
| [`reload()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Location/reload) | 重新加载来自当前 URL的资源。他有一个特殊的可选参数，类型为 [`Boolean`](https://developer.mozilla.org/zh-CN/docs/Web/API/Boolean)，该参数为true时会导致该方法引发的刷新一定会从服务器上加载数据。如果是 `false`或没有制定这个参数，浏览器可能从缓存当中加载页面。 |

# 常用函数（持续更新）

js自带常用函数

| 函数名称                                                     | 阐述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`isNaN()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/isNaN) | `**isNaN()**`函数判断一个值是否是[`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)。 |
| [`parseInt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseInt) | `**parseInt()**` 函数解析字符串参数，并返回指定的基数（基础数学中的数制）的整数。 |
| [`parseFloat()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseFloat) | `**parseFloat()**` 函数解析字符串参数，并返回一个浮点数。    |

   