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

变量用于临时存储程序运行所需要的数据



### 小知识

- 通过ID获取指定输入框的值

  ```js
  document.getElementById('id_val').value;
  ```

### 定义

```js
// 定义变量
// var 变量名称;
var date;
let time;    // IE11以下的版本不支持
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
  `不符合规范:   var  _a =1 ;`
- 变量名不要以数字开头。这种行为是不被允许的，并且将引发一个错误。
  `不符合规范: var 1abc = 'hi';`
- 一个可靠的命名约定叫做 ["小写驼峰命名法"](https://en.wikipedia.org/wiki/CamelCase#Variations_and_synonyms)，用来将多个单词组在一起，小写整个命名的第一个字母然后大写剩下单词的首字符。
  符合规范: var  createTime = '2020-04-02 12:00:00';
- 让变量名直观，它们描述了所包含的数据。不要只使用单一的字母/数字，长句，拼音缩写，中文，不好出现特殊符号 。
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

// 数组(---后面讲---)
var	names = ['猪八戒','唐僧','沙僧','孙悟空'];
var nums = [-10,11.2,12,9];

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
// 不等于  值判断
console.log(num4 != num5);
// 等于  值判断
console.log(num4 == num5);
// 全等于   类型+数值判断
console.log(num4 === num5);
console.log(num5 === num6);

// 全不等   类型+数值判断
console.log(num4 !== num5);
console.log(num5 !== num6);

```

## 条件语句

<img src="imgs\cookie-choice-small.png" style="zoom: 50%;" />

### if语句

用于等值，范围多条件判断等场景

#### if ... else 语句

if可以单独使用，但是else 不能单独使用，else if不能单独使用

**语法**

```js
if (条件判断) {
  // 条件成立则执行 
} else {
  // 条件不成立则执行
}


if(result ==0){// 当 result ==0 满足条件时，则执行代码
				alert('你输入的是   偶数');
			}else{ // 当if条件不成立执行				
				alert('你输入的是   奇数');
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


if(inputVal < 60 && inputVal >=0){
				alert("不合格");
			}else if(inputVal <70 && inputVal >=60){
				alert("B-");
			}else if(inputVal <80 && inputVal >=70){
				alert("B");
			}else if(inputVal <90 && inputVal >=80){
				alert("B+");
			}else if(inputVal <=100 && inputVal >=90){
				alert("A+");
			}else{
				alert("别搞~~~");
			}
```

#### 逻辑运算符

- `&&` — 逻辑与; 使得并列两个或者更多的表达式成为可能，只有当这些表达式每一个都返回`true`时，整个表达式才会返回`true.`

  ```js
  // 当所有的条件都满足时，再回进入if语句
  if(inputVal < 60 && inputVal >=0){
  				alert("不合格");
  			}
  ```

  

- `||` — 逻辑或; 当两个或者更多表达式当中的任何一个返回 `true` 则整个表达式将会返回 `true`.

  ```js
  // 所有条件，只要其中一个条件得到满足，则执行if语句
  if(money >=10 || score > 50 || buyCount >= 200){
  			alert("能买牙膏");
  		}else{
  			alert("您没有购买资格");
  		}
  ```

  

- ! — 逻辑非; 对一个布尔值取反, 非true返回false,非false返回true.



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



### 三目运算符

一个if简洁版版的条件判断语句

**语法**

```js
condition ? exprIfTrue : exprIfFalse
```

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

