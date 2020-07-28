## 事件机制(事件模型)

> 历史背景：在早期的时候，当一个元素被点击的时候，时间是要从内到外执行（冒泡），还是从外到内执行(捕获)，IE和网景发生过激烈的争论，最终W3C确定了标准，浏览器都要支持这两种事件机制，浏览器先执行捕获阶段再执行冒泡，而事件要放在捕获阶段还是冒泡阶段由开发者决定。

* IE主张： `element.attachEvent('click',fn)`
* 网景主张：`element.addEventListener('click',fn)`
* W3C确认标准为：`element.addEventListener('click',fn,bool)`
    `bool` 不填默认为`false`,事件放在冒泡阶段，一般情况不填
    
##### 特例
同一个元素同时监听了两个click事件，一个放在冒泡阶段，一个放在捕获阶段，不遵循上面的规律，谁先监听谁先执行，上面的标准是有层级的元素关系的事件机制

##### 阻止冒泡
`e.stopPropagation`

##### 怎么阻止浏览器的滚动条
> `sroll`滚动事件阻止冒泡是不能阻止浏览器滚动的
1. 阻止`wheel`和`touchStart`事件的默认动作(`e.prevenDefault`)
2. 使用css样式隐藏滚动条[web](http://caibaojian.com/hide-scrollbar.html)
```css
.element::-webkit-scrollbar { width: 0 !important }
```

##### 自定义事件
1. new CustomEvent() + dispatchEvent 触发事件
2. addEventListener 监听事件

```js
div.addEventListener("myEvent",()=>{
  console.log("myEvent")
})


div.onclick=(e)=>{
  const event = new CustomEvent('myEvent')
  div.dispatchEvent(event)
}
```

## 事件委托

场景1:有一百个按钮需要监听事件
场景2:监听暂时还不存在的元素事件

##### 解决方法
借用元素事件机制的原理，监听父元素，通过判断e.target判断当前点击的元素来执行不同的操作

##### 优点
1. 减少多个事件监听器占用的内存
2. 可以监听动态生成的元素

代码：把button的事件的响应委托到#div上
```js
on("a","#div","button",()=>{
   console.log("button被点击了")
})
function on(eventType,element,selector,fn){
  if(!(element instanceof Element)){
    
    element = document.querySelector(element)
    
  }
  element.addEventListener(eventType,(e)=>{
    
    let t = e.target
    console.log("123")
    if(t.matches(selector)){
      fn(e)
    }
  })
}
```