### DOM节点的获得
+ 操作节点，必须首先找到该元素。有三种方法来做这件事：
-	document.getElementById("demo");
最准确的 ， 需要获取的dom元素，必须有id，而且一个页面不能有重复的id
-	document.getElementsByTagName("div");
效率低
没办法定位元素

-	document.getElementsByClassName("a");
如果在移动使用，移动端浏览器完全支持。
目前先不考虑ie8情况，之后学了jQuery或者html5（新的选择器）;
通过类名查找 HTML 元素在 IE 5,6,7,8 中无效
+ 获取节点
DOM的节点并不是孤立的，因此可以通过DOM节点之间的相对关系对它们进行访问。
全世界你可以通过6个人联系到任意一个人。
节点的访问关系，是以属性的方式存在的。  A.parent   a.parent();

+ 	父节点  （ parentNode ）   
调用者就是节点。一个节点只有一个父节点。调用方式就是节点.parentNode.
#### 兄弟节点
-	nextSibling：调用者是节点。（存在浏览器兼容问题）
    IE678中指下一个元素节点（标签、注释）。在火狐谷歌IE9+(标准)以后都指的是下一个节点（包括空文档和换行节点）。
-    nextElementSibling：在火狐谷歌IE9都指的是下一个元素节点。

-    总结：在IE678中用nextSibling，在火狐谷歌IE9+
    ie10以后用   nextElementSibling
兼容写法：nextEle =节点.nextElementSibling || 节点.nextSibling 
注意：兼容写法位置不能交换
-	previousSibling：调用者是节点。IE678中指前一个元素节点（标签）。在火狐谷歌IE9+以后都指的是前一个节点（包括空文档和换行节点）。
-	previousElementSibling：在火狐谷歌IE9都指的是前一个元素节点。
总结：在IE678中用previousSibling，在火狐谷歌IE9+以后用previousElementSibling。

#### 单个子节点
-	firstChild：调用者是父节点。IE678中指第一个子元素节点（标签）。在火狐谷歌IE9+以后都指的是第一个节点（包括空文档和换行节点）。
-	firstElementChild:在火狐谷歌IE9都指的第一个元素节点。
-	lastChild:调用者是父节点。IE678中指最后一个子元素节点（标签）。在火狐谷歌IE9+以后都指的是最后一个节点（包括空文档和换行节点）。
-	lastElementChild：在火狐谷歌IE9都指的最后一个元素节点。

#### 所有子节点
-	childNodes：它是标准属性，嫡出，它返回指定元素的子元素集合，包括HTML节点，所有属性，文本节点   （他还是W3C的亲儿子 ）
火狐 谷歌等高本版会把换行也看做是子节点
nodeType==1时才是元素节点(标签)
      nodeType  ==  1  表示的是元素节点   记住   元素就是标签
 nodeType  ==  2  表示是属性节点   
      nodeType  ==  3  是文本节点   
	   nodeType = 8   注释  

-   children：非标准属性，庶出，它返回指定元素的子元素集合。
但它只返回HTML节点，甚至不返回文本节点，虽然不是标准的DOM属性，但它和innerHTML方法一样，得到了几乎所有浏览器的支持。
children在IE6/7/8中包含注释节点 
在IE678中，注释节点不要写在里面。

##### 创建节点
使用方法是这样的document.createElement();
##### 插入节点（使用节点）
使用方法： 父节点.appendChild();
使用方法：父节点.insertBefore(要插入的节点，参考节点)；

如果参考节点为null，那么他将在节点最后插入一个节点。

##### 删除节点   
用法：父节点.removeChild（子节点）。
节点自己删除自己：
不知道父级的情况下，可以这么写：node.parentNode.removeChild(node)

#####复制节点 
用法：oldNode.cloneNode（true）
想要复制的节点调用这个函数cloneNode()，得到一个新节点。 方法内部可以传参，入股是true，深层复制，如果是false，只复制节点本身。
#####节点属性（节点.属性）
获取：getAttribute(名称)
设置：setAttribute(名称, 值)
删除：removeAttribute(名称)
#####value和innerHTML和innerText和textContent
1.老版本的火狐不支持innerText，支持textContent
Value只对表单有效果，是属性
innerHTML插入可执行的标签，标签和样式会被解析，常用于动态生成页面元素
innerText 插入文本内容，标签和样式会被当做文本内容处理。

#####定时器
- 4.1 setTimeout()    延迟执行
	
- 4.2 setInterval()   clearInterval()  循环执行






