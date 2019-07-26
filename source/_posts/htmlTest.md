---
title: htmlTest
date: 2019-07-26 16:01:04
tags:
---
HTML测试
---


<html>
<head>
<meta charset="UTF-8">
<title>domTest</title>
<script>
function myFunction(){
	var node=document.createElement("LI");
	var textnode=document.createTextNode("Water");
	node.appendChild(textnode);
	document.getElementById("myList").appendChild(node);
}
function showURI(){
document.getElementById("demo1").innerHTML=document.baseURI;
}
function showHTML(){
document.getElementById("demo1").innerHTML=document.body.innerHTML;
}
function creatP(){
    var x = document.createElement("P");
    var t = document.createTextNode("这是新的段落。");
    x.appendChild(t);
    document.body.appendChild(x);
}
function createDoc(){
    var doc=document.open("text/html","replace");
	var txt="<!DOCTYPE html><html><body>学习 HTML DOM 很有趣!</body><html>";
	document.write(txt);
	doc.close();
}
function createWindow(){
    var w=window.open();
    w.document.write("HelloWorld!");
}
function removeEvent(){
    document.removeEventListener("click",addEvent);
}
function addEventF(){
    document.addEventListener("click",addEvent);
}
</script>
</head>

<body>
<p>addEventListener()方法向文件中添加点击事件。</p>
<p>尝试点击文档的任何地方。</p>
<p id="demo"></p>
<p id="demo1"></p>
<script>
document.addEventListener("click",addEvent);
function addEvent(){
	document.getElementById("demo").innerHTML = "Hello World"};
</script>
<button onclick="myFunction()">添加按钮</button>
<button onclick="showURI()">显示URI</button>
<button onclick="showHTML()">显示HTML内容</button>
<button type="button" onclick="creatP()">创建新的段落</button>
<input type="button" value="创建窗口" onclick="createWindow()">
<input type="button" value="创建文档" onclick="createDoc()">
<input type="button" value="移除点击事件" onclick="removeEvent()">
<input type="button" value="添加点击事件" onclick="addEventF()">
<ul id="myList"><li>Coffee</li><li>Tea</li></ul>
<p>单击按钮将项目添加到列表中</p>


</body>
</html>
<!--more-->

结论
---
1.MD重新定义了一些HTML语句的使用方法使其更加适合纯文本展示
2.MD在最终展示时还是转换成了HTML语言
3.如果想要在md中使用JS需要在浏览器中打开才有效果，而且需要在md文件内部声明函数，如果在翻译成html时语法正确那么就可以在浏览器中正确运行
