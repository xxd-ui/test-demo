## 事件的三要素:事件源 事件 事件驱动程序
代码书写步骤如下：（重要）
（1）获取事件源：document.getElementById(“box”);
（2）绑定事件： 事件源 box.事件 onclick = function(){ 事件驱动程序 };
（3）书写事件驱动程序：关于 DOM 的操作。
### 1、获取事件源的方式（DOM 节点的获取）
```
var div1 = document.getElementById("box1"); //方式一：通过id获取单个标签

var arr1 = document.getElementsByTagName("div"); //方式二：通过 标签名 获得 标签数组，所以有s

var arr2 = document.getElementsByClassName("hehe"); //方式三：通过 类名 获得 标签数组，所以有s
```
### 2、绑定事件的方式
方式一：直接绑定匿名函数 
方式二：行内绑定
### 3、事件驱动程序
注意事项：
- 在 js 里写属性值时，要用引号.
- 在 js 里写属性名时，是backgroundColor，不是 CSS 里面的background-color。
## DOM
### 什么是DOM
DOM：Document Object Model，文档对象模型。DOM 为文档提供了结构化表示，并定义了如何通过脚本来访问文档结构。目的其实就是为了能让 js 操作 html 元素而制定的一个规范。

在 HTML 当中，一切都是节点：（非常重要）
- 元素节点：HMTL 标签。
- 文本节点：标签中的文字（比如标签之间的空格、换行）
- 属性节点：：标签的属性。
### DOM 可以做什么
- 找对象（元素节点）
- 设置元素的属性值
- 设置元素的样式
- 动态创建和删除元素
- 事件的触发响应：事件源、事件、事件的驱动程序
### DOM 节点的获取
DOM 节点的获取方式其实就是获取事件源的方式.
### DOM 访问关系的获取 
#### 获取父节点 
调用者就是节点。一个节点只有一个父节点，调用方式就是
节点.parentNode;
#### 获取兄弟节点
下一个兄弟节点 = 节点.nextElementSibling || 节点.nextSibling;
前一个兄弟节点 = 节点.previousElementSibling || 节点.previousSibling;
#### 获取单个的子节点
第一个子元素节点 = 节点.firstElementChild || 节点.firstChild;
最后一个子元素节点 = 节点.lastElementChild || 节点.lastChild;
#### 获取所有的子节点
子节点数组 = 父节点.childNodes; //获取所有节点。
子节点数组 = 父节点.children; //获取所有节点。用的最多。
### nodeType 属性
- nodeType == 1 表示的是元素节点（标签） 。记住：元素就是标签。
- nodeType == 2 表示是属性节点。
- nodeType == 3 是文本节点。
- nodeType == 8 注释节点.
获取除自己以外的所有兄弟节点
## DOM 节点的操作（重要）
### 创建节点
新的标签(元素节点) = document.createElement("标签名");
### 插入节点
方式 1：

父节点.appendChild(新的子节点);
解释：父节点的最后插入一个新的子节点。

方式 2：

父节点.insertBefore(新的子节点, 作为参考的子节点);
解释：

- 在参考节点前插入一个新的节点。
- 如果参考节点为 null，那么他将在父节点里面的最后插入一个子节点。
#### 删除节点
父节点.removeChild(子节点);
node1.parentNode.removeChild(node1);
#### 复制节点（克隆节点）
要复制的节点.cloneNode(); //括号里不带参数和带参数false，效果是一样的。
要复制的节点.cloneNode(true);
### 设置节点的属性
#### 1、获取节点的属性值
方式 1：
元素节点.属性;
元素节点[属性];

方式 2：
元素节点.getAttribute("属性名称");
console.log(myNode.getAttribute("class")); //注意是class，不是className
#### 2、设置节点的属性值
方式 1
 举例：（设置节点的属性值）
myNode.src = "images/2.jpg"; //修改src的属性值
myNode.className = "image2-box"; //修改class的name

方式 2：
元素节点.setAttribute(属性名, 新的属性值);
#### 3、删除节点的属性
元素节点.removeAttribute(属性名);
####总结：

获取节点的属性值和设置节点的属性值，都有两种方式，但这两种方式是有区别的。
方式一的元素节点.属性和元素节点[属性]:绑定的属性值不会出现在标签上。
方式二的get/set/removeAttribut: 绑定的属性值会出现在标签上。
这其实很好理解，方式一操作的是属性而已，方式二操作的是标签本身。
### DOM 对象的属性
DOM 对象的属性和 HTML 的标签属性几乎是一致的。例如：src、title、className、href 等。
#### innerHTML 和 innerText 的区别
- value：标签的 value 属性。
- innerHTML：双闭合标签里面的内容（识别标签）。
- innerText：双闭合标签里面的内容（不识别标签）。


