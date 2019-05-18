###jQuery笔记.md
#####$
a)命名归法：下划线、字母、$、数字
b)但是不能以数字作为开头
	
jQuery的两个变量：$ 和 jQuery
注意：不能再使用这两个变量 防止引起冲突，什么时候使用jQuery？当有其他框架中使用$造成冲突的时候使用jQuery。
#### js入口函数跟jQuery入口函数的区别：
1.执行时间
window.onload必须等到页面内包括图片的所有元素加载完毕后才能执行。
$(document).ready()是DOM结构绘制完毕后就执行，不必等到加载完毕。只加载了dom框架，对于大的图片需要时间，这个不等。  <img scr=’’>
2.编写个数不同
window.onload不能同时编写多个，如果有多个window.onload方法，只会执行一个
$(document).ready()可以同时编写多个，并且都可以得到执行
3.简化写法
window.onload没有简化写法
$(document).ready(function(){})可以简写成$(function(){});
####jq选择器写法
- ID:$(“#demo”)
- Class:$(“.d1”)
-