# 数组

1. 构建一个数组，并填入  唐僧师徒四人的名称
   
   ```js
   // 直接定义并赋值
   let journey = ['唐僧','沙僧','猪八戒','孙悟空'];
   		console.log(journey);
   		for(let index in journey){
   			console.log(journey[index]);
   		}
   // 定义空数组
   let team = [];
   // 填充数组的数据
   team.push('唐僧','沙僧','猪八戒','孙悟空');
   ```
   
   
   
2. 利用for循环，将0-9索引上的数据设置为1-10

   ```json
   // 不符合题意 ***
   let number = [0,1,2,3,4,5,6,7,8,9]
   number.push(10);
   	
   	number.shift();
   	for(let index in number){
   		console.log(number[index]);
   	}
   
   // 正确答案
   let nums = [];
   // 通过for进行按位赋值
   for(let i =0;i<10;i++){
       nums[i] = i+1;
   }
   ```

   ​		

3. 将题目2中的数组元素去掉1，3，5，7，9

   ​	

   ```js
   // 手动删除
   		// [1,2,3,4,5,6,7,8,9,10]
   		number.splice(0,1); // 正确  删除1
   		// [2,3,4,5,6,7,8,9,10]
   		number.splice(1,1); // 正确  删除3
   		// [2,4,5,6,7,8,9,10]
   		number.splice(2,1); // 正确  删除5
   		// [2,4,6,7,8,9,10]
   		number.splice(3,1); // 正确  删除7
   		// [2,4,6,8,9,10]
   		number.splice(4,1); // 正确  删除9
   		// [2,4,6,8,10]
   
   // 循环删除
   for(let i=0;i<5;i++){ 
       nums.splice(i,1);
   }
   ```

   ​		

   ```js
   	// 显示，可有可无
   	//number.splice(0,j % 2 != 0);
   	for(let index in number){
   		console.log(number[index]);
   		
   		}
   ```

4. 将题目2中的数组元素去掉1，3，4，5，6

   ```js
   		// [1,2,3,4,5,6,7,8,9,10]
   		number.shift();
   		// [2,3,4,5,6,7,8,9,10]
   		number.splice(1,4);
   		// [2,7,8,9,10]
   		for(let index in number){
   			console.log(number[index]);
   		}
   // 匹配删除
   // 删除组
   let nums =[1,2,3,4,5,6,7,8,9,10];
   // 参照组
   let needDel = [1,3,4,5,6,20];
   		
   // 循环参照组，将参照组中每一个元素去查看删除组中是否存在该元素
   for(let i=0;i<needDel.length;i++){
       // 获取参照组中的每一个元素
       let delNum = needDel[i];
       // 判断参照元素是否存在于删除组中
       console.log('参照元素:',delNum,',存在于删除组的索引：',nums.indexOf(delNum));
   			
       // 判断indexOf返回值不是-1的情况，则表明参照元素存在删除组中
       let needDelIndex = nums.indexOf(delNum);
       if(needDelIndex != -1){
           nums.splice(needDelIndex,1);
       }			
   }
   console.log(nums);
   ```

   

5. 数组1[1,2,3,4,5]与数组2[6,7,8,9]进行合并，得出数组3[1,2,3,4,5,6,7,8,9]

   ​		

   ```js
   // 甲队伍	  ***
   		let num1 =[1,2,3,4,5]
   		let num2 =[6,7,8,9]
           // 合并后将会把原本的数组变成字符串
   		let num3 =[num1+','+num2]
   		for(let index in num3){
   			console.log(num3[index]);
   		}
   // 乙队伍   
   let num1 =[1,2,3,4,5]
   let num2 =[6,7,8,9]
   // 函数合并
   const array1 = ['a', 'b', 'c'];
   const array2 = ['d', 'e', 'f'];
   const array3 = array1.concat(array2);
   
   console.log(array3);
   
   
   
   // expected output: Array ["a", "b", "c", "d", "e", "f"]
   // 丙队伍  
   for(let i=0;i<num2.length;i++){
       // 将单个元素压入num1数组中
       num1.push(num2[i]);
   }
   	
   ```

   

6. 去除数组1[1,2,3,4,5]与数组2[1,3,5,7,9]中共同的元素

   ```js
   // *** 此题参照题目4中的匹配删除		
   let number1 =[1,2,3,4,5]
   		let number2 =[1,3,5,7,9]
   		number1.splice(0,1);
   		number1.splice(1,1);
   		number1.splice(2,1);
   		number2.splice(0,3)
   		for(let index in number1){
   			console.log(number1[index]);
   		}
   		for(let index in number2){
   			console.log(number2[index]);
   		}
   ```

   

7. 将数组[1,2,7,4,9,6,8,3,10,5]进行排序，升序结果为：[1,2,3,4,5,6,7,8,9,10]，倒序结果：[10,9,8,7,6,5,4,3,2,1]

   ```js
   // 正确答案
   let number7 =[1,2,7,4,9,6,8,3,10,5];
   		number7=number7.sort(function(n1,n2){
   			
```
   
   
   ```js
   			if(n1 < n2){
   				return -1;  
   			}
   			// return a-b;
   		});  
   		console.log(number7);
   	number7=number7.sort(function(n1,n2){
   		
   			if(n1 > n2){
   				return -1;  
   			}
           	// return b-a;
		});  
   		console.log(number7);
   
   // 如果sort函数，返回0 则n1与n2不调换位置
   // 如果sort函数，返回1 n2是在n1的前面
   // 如果sort函数，返回-1 n1是在n2的前面
   
   
   // 利用两个循环来实现排序的效果 ***   自己实现的排序
   ```
   
   

# 函数

1. 构建一个无参函数，执行函数后显示：身体健康真好：）
   
   ```js
   <html>
   	<head>
   		<meta charset="utf-8">
   		<title>函数</title>
   	</head>
   	<body>
   		<button id="health">发送模板信息</button>
   	</body>
   	<script type="text/javascript">
   		
           // 扣一分答案    有复杂
           document.getElementById('health').onclick = function() {
   			sendTemplateMsg();
   		};
   		function sendTemplateMsg() {
   			console.log("身体健康真好");
   		}
   
   		// 简单答案
   		// 定义函数
   		function showMsg() {
   			console.log("身体健康真好");
   		}
   		// 执行函数
   		showMsg();
   	</script>
   	
   </html>
   ```
   
   
   
2. 构建一个带参函数，执行函数后显示 参数1是否大于参数2的比较结果

   ```js
   <input id="comput" /> <button id="cha">查询</button>
   // 不符合题意   ***
function comput(js, num1=0, num2=0) {
   			switch (js) {
				case '<':
   					return num1 < num2;
   					break;
   				case '>':
   					return num1 > num2;
   					break;
                    	}
   	document.getElementById('cha').onclick=function(){
   		let js = document.getElementById('comput').value;
   	
   		comput(js);
           	}
   	console.log(js)
      	}
   // 正确答案
   function comp(num1 ,num2){
       // 获取比较结果
   	let result=  num1 > num2;
       console.log('n1是否大于n2：',result);
   }
   // 执行函数
   comp(10,3);
   comp(10,20);
   
   ```
   
   




3. 构建一个计算器函数：参数（计算法则，数字1，数字2）、构建一个计算平均值函数，在函数中执行 1.求和，2.求平均数，3.求每个数字与平均数的差

   ```js
   // 定义计算器函数
   function jsq(rule,n1,n2){
       switch(rule){
           case '+':
               return n1+n2;
               break;
           case '-':
               return n1-n2;
               break;
           case '*':
               return n1*n2;
               break;
           case '/':
               return n1/n2;
               break;
       }
   }
   
   // 计算平均值函数
   function avg(){
       // 1 求和
       let num1=10,num2=20,num3=30;
       let result = jsq('+',num1,num2);
       // 得出num1~num3的相加总和
       result = jsq('+',num3,result);
       
       // 2 求平均数
       let avgVal = jsq('/',result,3);
       
       // 3 求数字与平均值的查
   	let n1AvgDiff = jsq('-',num1,avgVal); // 得出n1与平均值的差
   	let n2AvgDiff = jsq('-',num2,avgVal); // 得出n2与平均值的差    
   	let n3AvgDiff = jsq('-',num3,avgVal); // 得出n3与平均值的差
   	console.log('n1与平均值的差:',n1AvgDiff);
   	console.log('n2与平均值的差:',n2AvgDiff);
       console.log('n3与平均值的差:',n3AvgDiff);
   }
   
   // 执行avg函数进行计算
   avg();
   
   // 题意：函数调函数
   ```

4. 构建一个函数：参数（身高，体重，年龄）。函数执行：如果年龄<18并且身高<170cm或者年龄<18并且体重<60kg则返回0(0为不合格)，如果满足条件则返回1(1为合格)。并且根据返回值在页面上输出，条件合格/条件不合格

   ```js
   // 显示一个显示信息的函数
   function showInfo(height,weight,age){
       if(height <170 && age < 18 || age <18 && weight< 60){
           // 返回0  不合格
           return 0;
       }else{
           // 返回1  合格
           return 1;
       }
   }
   // 调用函数并获取返回值
   let result = showInfo(160,70,19);
   // if写法
   if(result == 0){
       console.log('不合格');
   }else{
       console.log('合格');
   }
   // 三目运算符写法
   console.log(result ==0 ? '不合格':'合格');
   ```

   

5. 利用立即执行函数去调用题目4的函数

   ```js
   (function(){
       // 函数体
        showInfo(160,70,19);
   })();
   ```

   






提示：请在每题后的空白处填入答案，做完作业后，请将本作业文件更名为：`JS作业年月日 姓名`（如`JS作业20200407 张三丰`） 发送至 `1754349918@qq.com`邮箱