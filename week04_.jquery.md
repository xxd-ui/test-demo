## jQuery
### jQuery 是什么
jQuery 是一个快速、简洁的 JavaScript 框架
### jQuery 的基本使用
- 获取源文件
- 引入页面
### 入口函数
```
// 何时引入业务代码
$(document).ready(function() {});
$(function() {}); //推荐
```
### 事件处理
- 事件源
1.触发事件的对象
2.在 js 中就是 dom 对象
3.在 jQuery 中 是包装过的 dom 对象
- 事件
1.js 中 指的是 onclick , onmouseenter/onmouseleave , onmouseup/onmousedown
2.jQuery 中 就是 click , mouseenter/mouseleave , mouseup/mousedown
- 事件处理程序
```
// 1. js中
obj.onclick = function() {
	// 事件处理
};
// jQuery中
$(obj).click(function() {
	// 事件处理
});
// 区别
// obj.onclick  调用属性
// obj.click()  调用方法
```
### 详细介绍
$
### js 和 jQuery 入口函数的区别
