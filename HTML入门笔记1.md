# HTML的起源
HTML在1990年左右诞生，由Tim Berners-Lee，称为李爵士创造，2017年被授予图灵奖。
李爵士创造了第一个浏览器、第一个服务器、用自己的浏览器访问自己的服务器、发明了www（万维网）、发明了URL、HTML、HTTP。
> 万维网≠互联网，万维网是提供的是DNS域名解析服务，让人们通过访问域名而不是IP地址

# HTML起手应该写是吗
在vscode输入，!回车即可快速打出以下代码片段，一般情况只需将`lang="en"`修改为`lang="zh_CN"`和修改title标签
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

# 常用的表章节的标签

* 标题h1~h6
* 章节 section
* 文章 arcticle
* 段落 p
* 头部 header 
* 脚部 footer 常用于底部版权声明，版权标识：`&copy;`&copy;
* 主要内容 main
* 旁支内容 aside 常在侧边导航栏中使用
* 划分 div

# 全局属性
* class 类
在css中使用`.xxx{}`修改样式，原始写法为`[class="xxx"]{}`,原始写法的弊端是当元素有多个class时非常不方便
* contenteditable 内容可以被编辑
常用于做编辑器
* hidden 隐藏
优先级高于{display:none}？hidden可以被CSS{display:block}挽回；
* id
`[id="xxx"]`简写`#xxx`
在HTML中，id标识全局唯一，但是在实际使用时又可以给不同的元素设置相同的id，所以建议多用class少用id；在js中，可以使用id直接找到dom元素，如xxx.style.border="",但是如果id在window中已经存在，则会实现，也不建议使用这种方式。
* style
* tabindex 
按下tab时的响应顺序，0标识最后访问，-1标识不被访问
* title 
鼠标附上去时的提示文字，常在内容超长被省略时使用
文字溢出解决办法：
```
white-space:nowrap;/*不换行*/
text-overflow:ellipsis;/*溢出部分用省略号表示*/
overflow:hidden;/*溢出的文字隐藏*/
```

# 常用标签
* ol +li 有序列表
* ul +li 无序列表
* dl + dt + dd 描述列表
dl:desc list dt:desc term dd:desc data
* pre 会保留空格、换行、tab
* hr 分割线
* br 换行
* a 超文本
* em 标识语气强调，表现为斜体
* strong 标识内容强调，表现为加粗
* quote 行内引用
* blockquote 块级引用
* code 常用于存放代码，表现为等宽的字体

# 从淘宝拔下来修改一下的reset.css
```
* {
  margin: 0;
  padding: 0;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-size: 100%;
}
address,
cite,
dfn,
em,
var {
  font-style: normal;
}
code,
kbd,
pre,
samp {
  font-family: courier new, courier, monospace;
}
small {
  font-size: 12px;
}
ol,
ul {
  list-style: none;
}
a {
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}
sup {
  vertical-align: text-top;
}
sub {
  vertical-align: text-bottom;
}
legend {
  color: #000;
}
fieldset,
img {
  border: 0;
}
button,
input,
select,
textarea {
  font-size: 100%;
}
button {
  border-radius: 0;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}

```

