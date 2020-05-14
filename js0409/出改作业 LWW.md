# 内置对象

1. 转换姓名为 (姓**) 如，猪八戒 ---> 猪\*\*    、 司马光  --->  司马\*\*   [先定义好姓氏数组，匹配再替换]

   ```js
   let name='猪八戒',name2='司马光';
   		
   let fname1=name.slice(0,1);
   	console.log(fname1);
   let fname2=name2.slice(0,2);
   	console.log(fname2);
   		
   name=name.replace(name,fname1+'**');
   	console.log(name);
   		
   name2=name2.replace(name2,fname2+'**');
   	console.log(name2);
   ```

   **正确答案**

   ```html
   <!DOCTYPE html>
   <html>
   	<head>
   		<meta charset="utf-8">
   		<title>姓氏</title>
   	</head>
   	<body>
   		<input id="name" /><button id="conv">转换</button>
   	</body>
   	<script type="text/javascript">
   		// 定义姓氏数组
   		var fname = ['张','李','王','诸葛','欧阳','西门','司马','爱新觉罗'];
   
   		
   		// 为转换按钮增加点击事件
   		document.getElementById("conv").onclick=function(){
   			// 获取输入框中的姓名
   			let name = document.getElementById("name").value;
   			// 转换
   			// name.substring(0,1); // 此种方式只能截取一个字，复姓将会失败
   			// 匹配姓氏
   			for(let i=0;i<fname.length;i++){
   				// 获取某一个姓氏
   				let fn = fname[i];
   				
   				/*
   					startsWith 方案
   					
   					// 判断用户名是否为当前姓氏
   					let fnExists = name.startsWith(fn);
   					// 用户名称是当前姓氏
   					if(fnExists){
   						alert(`${fn}**`);
   						// 找到姓氏后，就没有循环下去的必要
   						break;
   					}
   				*/
   				// 判断用户名是否为当前姓氏
   				let fnExists = name.indexOf(fn);
   				// 用户名称是当前姓氏
   				if(fnExists != -1){
   					alert(`${fn}**`);
   					// 找到姓氏后，就没有循环下去的必要
   					break;
   				}
   			}
   		}
   
   	</script>
   </html>
   
   ```

   

2. 将字符串（我是程序员我是程序员） 变成 （我是一个大老板我是一个大老板） 条件：使用循环完成

   ```js
   let masg='我是程序员我是程序员';
   let repeat=masg.slice(0,2);
   	console.log(repeat);
   let repeat2=masg.slice(5,7);
   	console.log(repeat2);
   let bot=[repeat,repeat2];
   	console.log(bot);
   for(let i=0;i<bot.length;i++){
   	let boss=bot[i];
   	boss=masg.replace(masg,repeat+'一个大老板');
   		console.log(boss);
   }
   ```

   **正确答案**

   ```html
   <!DOCTYPE html>
   <html>
   	<head>
   		<meta charset="utf-8">
   		<title>替换关键字</title>
   	</head>
   	<body>
   	</body>
   	<script type="text/javascript">
   		let msg = '我是程序员我是程序员我是程序员';
   
   		let newMsg = "一个大老板";
   		let oldMsg = "程序员";
   		// 判断字符串是否出现过oldMsg中的字符
   		let index = msg.indexOf(oldMsg);
   		while (index != -1) {
   			// 元字符串中还出现oldMsg的字符
   			// 执行替换操作
   			msg = msg.replace(oldMsg, newMsg);
   			// 替换完成后，再检查msg中是否还存在oldMsg的字符
   			index = msg.indexOf(oldMsg);
   		}
   		console.log(msg);
   		
   		// 通过正则表达式（暂时没有教）
   		console.log(msg.replace(/(大老板*)/g,'程序员'));
   		
   	</script>
   </html>
   
   ```

   
   

3. 截取文件名的格式   阿.凡.达.mp4  ---> .mp4

   ```js
   // 正确答案
   let film='阿.凡.达.mp4';
   let last=film.lastIndexOf('.');
   console.log('.最后出现的位置：',last);
   let fix = film.substring(last);
   console.log(fix);
   ```

   

4. 获取数组中最大及最小的值

   ```js
   result=Math.max(1,3,4,5,2,5,6);
   	console.log(result);
   		
   result=Math.min(1,3,4,5,2,5,6);
   	console.log(result);
   ```

   **正确答案**

   ```js
   
   		// 获取数组中的最大值
   		let nums = [1,2,3,100,4,20,0.5];
   		// 存储最大值
   		let max = 0;
   		for(let i=0;i<nums.length;i++){
   			// 如果当前的数组元素，比max大，则将max更新当前元素
   			let curr = nums[i];
   			if(max < curr){
   				max = curr;
   			}
   		}
   		console.log(max);
   	 
   		// 获取数组中的最小值
   		// 存储最小值
   		let min = nums[0];
   		for(let i=0;i<nums.length;i++){
   			// 如果当前的数组元素，比max大，则将max更新当前元素
   			let curr = nums[i];
   			if(min > curr){
   				min = curr;
   			}
   		}
   		console.log(min);
   ```

   

5. 通过search解析出url中的参数：?name=jack&sex=m。得出两个数组 [name,sex]与[jack,m]   （需要用到字符串）

   ```html
   <!DOCTYPE html>
   <html>
   	<head>
   		<meta charset="utf-8">
   		<title>解析url中的参数</title>
   	</head>
   	<body>
   		<a href="0408w4.html?name=jack&sex=m">跳转当前页面</a>
   	</body>
   	<script type="text/javascript">
   		/*
   			需求：将参数 ?name=jack&sex=m  转换为[name,sex] 和 [jack,m]
   			1/通过split('&')分割字符  ['?name=jack','sex=m']
   		*/
   		// 定义参数名称和参数值的数组
   		let pName=[],pVal=[];
   		// 获取url中的参数
   		let params = location.search;
   		// 清除 问号 ?name=jack&sex=m --->  name=jack&sex=m
   		// 获取参数集合
   		params = params.replace("?","");
   		// 通过split('&')分割字符 得到子参数： ['name=jack','sex=m']
   		let subParams = params.split('&');
   		// 再次切割子参数
   		for(let i=0;i<subParams.length;i++){
   			// 取得一个自参数   'name=jack'
   			let subParam = subParams[i];
   			// 对子参数进行切割  'name=jack' ---> ['name','jack']
   			let subParamStruct = subParam.split("=");
   			// 将参数名称放入参数名称数组中
   			pName.push(subParamStruct[0]);
   			pVal.push(subParamStruct[1]);
   		}
   		
   		console.log('原始参数： ',params,",参数名称：",pName,",参数值：",pVal);
   		
   	</script>
   </html>
   
   ```

   

6. 通过字符串或时间戳构建一个时间对象（时间为：2019-01-01 00:00:00），并计算当前时间计算，获得两个时间的天数差

   ```js
   let old=new Date('2019-01-01 00:00:00');
   	console.log(old);
   
   let now=new Date();
   	console.log(now);
   		
   let day=old.getDate();
   	console.log(day);
   			
   let day2=now.getDate();
   	console.log(day2);
   		
   	console.log(day-day2);
   ```

   **正确答案**

   ```js
   
   		// 创建 2019-01-01 00:00:00 时间对象
   		let old=new Date('2019-01-01 00:00:00');
   		// 获取当前时间
   		let now = new Date();
   		// 计算天数查  
   		// 计算公式: 年-年，月-月，日-日 ...    非常复杂
   		// 利用时间戳计算
   		
   		// 获取2019年的时间戳
   		let oldTimeStamp = old.getTime();
   		// 获取当前时间的时间戳
   		let nowTimeStamp = now.getTime();
   		console.log('2019年：',oldTimeStamp,'，当前时间：',nowTimeStamp);
   		// 当前时间的时间戳 - 2019年的时间戳 = 得到两个时间的毫秒差
   		let timeDiff = nowTimeStamp - oldTimeStamp;
   		// 计算出一天的总毫秒数
   		let dayMs = 1000*60*60*24;
   		console.log('一天的总毫秒数：',dayMs);
   		// 两个时间的毫秒差 / 一天的总毫秒数 = 天数
   		let dayDiff = timeDiff / dayMs;
   		console.log("两个时间的天数差:",dayDiff);
   ```

   

7. 构建一个函数，调用这个函数将返回当前时间字符串：yyyy-MM-dd hh:mm:ss格式

| 格式 | 描述 |
| ---- | ---- |
| yyyy | 年份 |
| MM   | 月份 |
| dd   | 几号 |
| hh   | 时   |
| mm   | 分   |
| ss   | 秒   |

```js
 // 正确答案
function getDay(){
	let today=new Date();
	let newDay=`${today.getFullYear()}-${today.getMonth()+1}-${today.getDate()} ${today.getHours()}:${today.getMinutes()}:${today.getSeconds()}`;
	return newDay;
}
	getDay();
```

提示：更多时间格式请移步博客：http://www.foxtable.com/help/topics/0362.htm



# DOM(部分)

1. 获取下列标签中的所有p标签，并且设置字体颜色为红色

   ```html
   <body>
   	<p>我是普通段落</p>
   	<div>
   		<p>我是div里面的段落</p>
   	</div>
   </body>
   
   <script type="text/javascript">
   		// 1 获取下列标签中的所有p标签，并且设置字体颜色为红色
   		// 通过标签名获取标签对象
   		// let pList = document.getElementsByTagName('p');
   		let pList = document.querySelectorAll("p");
   		for(let i=0;i<pList.length;i++){
   			// 取得某一个p标签
   			let pTag =pList[i];
   			pTag.style.cssText='color:red;';
   		}
   	</script>
   ```

2. 获取下列所有class为txt的标签，并设置字体大小为30px

   ```html
   <body>
   	<p class="txt">我是普通段落</p>
   	<div>
   		<p class="text">我是div里面的段落</p>
   		<p class="txt">我是div里面的段落2</p>
   	</div>
   </body>
   <script type="text/javascript">
   		
   		// 通过class名称获取标签对象
   		// let pList = document.getElementsByClassName('txt');
   		let pList = document.querySelectorAll(".txt");
   		for(let i=0;i<pList.length;i++){
   			// 取得某一个p标签
   			let pTag =pList[i];
   			pTag.style.cssText='color:red;';
   		}
   	</script>
   ```

3. 获取下列标签中为p的标签，设置背景颜色为绿色

   ```html
   <body>
   	<p class="txt">我是普通段落</p>
   	<div>
   		<p class="text">我是div里面的段落</p>
   		<p class="txt">我是div里面的段落2</p>
   	</div>
   </body>
   <script type="text/javascript">
   		// 通过标签名获取标签对象
   		// let pList = document.getElementsByTagName('p');
   		let pList = document.querySelectorAll("p");
   		for(let i=0;i<pList.length;i++){
   			// 取得某一个p标签
   			let pTag =pList[i];
   			pTag.style.cssText='background:green;';
   		}
   	</script>
   ```

4. 获取标签id为main里面的第一个li标签并设置颜色粉色

   ```html
   <body>
   	<p class="txt">我是普通段落</p>
   	<ul id="main">
   		<li>我是普通列表项1</li>
   		<li>我是普通列表项2</li>
   		<li>我是普通列表项3</li>
   	</ul>
   </body>
   <script type="text/javascript">
   		// 通过css选择器获取标签对象
   		// let pList = document.getElementsByTagName('p');
   		let pList = document.querySelector("#main li");
   		for(let i=0;i<pList.length;i++){
   			// 取得某一个p标签
   			let pTag =pList[i];
   			pTag.style.cssText='color:pink;';
   		}
   	</script>
   ```

   

5. 获取标签id为main里面的所有li标签并设置颜色粉色

   ```html
   <body>
   	<p class="txt">我是普通段落</p>
   	<ul id="main">
   		<li>我是普通列表项1</li>
   		<li>我是普通列表项2</li>
   		<li>我是普通列表项3</li>
   	</ul>
   </body>
   <script type="text/javascript">
		// 通过css选择器获取标签对象
   		// let pList = document.getElementsByTagName('p');
   		let pList = document.querySelectorAll("#main li");
   		for(let i=0;i<pList.length;i++){
   			// 取得某一个p标签
   			let pTag =pList[i];
   			pTag.style.cssText='color:pink;';
   		}
   	</script>
   ```
   
   



提示：请在每题后的空白处填入答案，做完作业后，请将本作业文件更名为：`JS作业年月日 姓名`（如`JS作业20200407 张三丰`） 发送至 `1754349918@qq.com`邮箱