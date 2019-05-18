### 引入
-   js的引入
-   在body末尾写入script标签,或者在head里写入script标签,写在head里可能会导致body元素先加载以至于js元素失效
### 变量
-   通过var声明一个变量,每一句代码结束,分号结尾.
-       变量名 命名规则
		字母 数字 _ $ 
		不能以数字开头
		严格区分大小写
		不能使用关键字,保留字
	    驼峰命名
		见名知意
### 数据类型
-   Number类型
    整数和浮点数（小数）
-   String类型 字符串
-   boolean布朗类型 布尔值
	true 和 false
-   undefined 类型 只有一个值 undefined
    当一个变量声明了,但是没有被赋值  他就是undefined
-   null 指向一个空对象
-   var str = 'hello "wo" rld';
		console.log(str)
		字符串需要使用引号引起来，使用双引号或单引号都可以，但是不要混着用。
		引号不能嵌套：双引号里不能再放双引号，单引号里不能再放单引号。但是单引号里可以嵌套双引号。
-       var age = 29;
		var num = 12.3;
		console.log(age);
		无穷大（正无穷）：Infinity，无穷小（负无穷）：-Infinity
		NaN：是一个特殊的数字，表示Not a Number，非数值。
		console.log("abc" / 18);  //结果是NaN
		console.log("abc" * "abcd"); //按理说，字符串相乘是没有结果的，
        但如果你非要让JS去算，它就一定会给你一个结果。结果是NaN
-   isNaN(); 任何不能被转换为数值的值，都会让这个函数返回 true。
-   var c;
		console.log(c); undefined  声明但是未被赋值
### 复杂数据类型
-   数组 array
		var arr = [1,'str',4,true,[1,23,4]];
-   对象 object  key value 形式 
		 var obj = {
		 	name: '张三',
		 	age:28,
		 	sex:'男',
		 	like:['篮球','足球','乒乓球']
		 	child:{
		 		name:'zhang',
		 		age:2,
		 		sex:'nv'
		 	}
		 }
-   函数 function

	function foo (){
			
	}

### if语句
- if 语句 - 只有当指定条件为 true 时，使用该语句来执行代码
- if...else 语句 - 当条件为 true 时执行代码，当条件为 false 时执行其他代码
- if...else if....else 语句 - 使用该语句来选择多个代码块之一来执行
- switch 语句 - 使用该语句来选择多个代码块之一来执行
- If...else if...else 语句
使用 if....else if...else 语句来选择多个代码块之一来执行。
+ JavaScript Switch 语句
switch 语句用来选择要执行的多个代码块之一
switch(n)
{
case 1:
  执行代码块 1
  break;
case 2:
  执行代码块 2
  break;
default:
  n 与 case 1 和 case 2 不同时执行的代码
}
工作原理：首先设置表达式 n（通常是一个变量）。随后表达式的值会与结构中的每个 case 的值做比较。如果存在匹配，则与该 case 关联的代码块会被执行。请使用 break 来阻止代码自动地向下一个 case 运行。
使用 default (关键词)来规定匹配不存在时做的事情
### JavaScript 循环
不同类型的循环
JavaScript 支持不同类型的循环：

 for - 循环代码块一定的次数
for/in - 循环遍历对象的属性
while - 当指定的条件为 true 时循环指定的代码块
do/while - 同样当指定的条件为 true 时循环指定的代码块
+ For 循环
for (语句 1; 语句 2; 语句 3)
  {
  被执行的代码块
  }

语句 1 在循环（代码块）开始前执行

语句 2 定义运行循环（代码块）的条件

语句 3 在循环（代码块）已被执行之后执行
语句 1
通常我们会使用语句 1 初始化循环中所用的变量 (var i=0)。

- 语句 1 是可选的，也就是说不使用语句 1 也可以。

您可以在语句 1 中初始化任意（或者多个）值：
- 语句 2
通常语句 2 用于评估初始变量的条件。

语句 2 同样是可选的。

如果语句 2 返回 true，则循环再次开始，如果返回 false，则循环将结束。

提示：如果您省略了语句 2，那么必须在循环内提供 break。否则循环就无法停下来。这样有可能令浏览器崩溃。请在本教程稍后的章节阅读有关 break 的内容。
- 语句 3
通常语句 3 会增加初始变量的值。

语句 3 也是可选的。

语句 3 有多种用法。增量可以是负数 (i--)，或者更大 (i=i+15)。

语句 3 也可以省略（比如当循环内部有相应的代码时）
+ While 循环
只要指定条件为 true，循环就可以一直执行代码。
- while (条件)
  {
  需要执行的代码
  }

  =====================================
-   while (i<5)
  {
  x=x + "The number is " + i + "<br>";
  i++;
  }

+ do/while 循环
do/while 循环是 while 循环的变体。该循环会执行一次代码块，在检查条件是否为真之前，然后如果条件为真的话，就会重复这个循环。
- do
  {
  需要执行的代码
  }
while (条件);
- do
  {
  x=x + "The number is " + i + "<br>";
  i++;
  }
while (i<5);
只要 i 小于 5 就一直循环代码块
+ Break 语句
用于跳出 switch() 语句。

	break 语句可用于跳出循环。

	break 语句跳出循环后，会继续执行该循环之后的代码（如果有的话）

+ Continue 语句
continue 语句中断循环中的迭代，如果出现了指定的条件，然后继续循环中的下一个迭代。