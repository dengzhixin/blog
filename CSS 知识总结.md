## 浏览器渲染原理
1. 根据HTML构建DOM树
2. 根据CSS构建CSS树（CSSOM树）
3. 将上面的两棵树构建成一个渲染树
4. layout布局(文档流、盒模型，计算大小和位置)
5. paint绘制（把边框颜色，文字颜色等进行绘制）
6. compose合成（根据层叠关系展示出用户看到的画面）

> 在渲染过程中遇到JS文件怎么处理？
JavaScript的加载、解析与执行会阻塞DOM的构建,但是不完善的CSSOM是无法使用的，所以浏览器会先下载和构建CSSOM，然后再执行JavaScript，最后在继续构建DOM。这也是一般情况为了首页速度渲染加快，把js放在body标签底部的原因。[扩展阅读](https://blog.fundebug.com/2019/01/03/understand-browser-rendering/)

### 三种会导致更新的方式
* 全走:  remove 会触发当前元素消失，其他元素relayout
* 跳过layout：改变背景色，直接repaint+compose
* 跳过layout和paint：改变transform，只需composite
![61ce62efba15f58ce4c80375f12ffd72.png](evernotecid://1FA57AF5-685F-408C-ABAA-E9E7D59A2831/appyinxiangcom/23431486/ENResource/p27)
> 每个CSS的样式都有不一样的渲染过程以及浏览器内核不同也会导致渲染过程不一样。[csstriggers](https://csstriggers.com/)列出了很多样式的渲染过程
## CSS 动画的两种做法
1. transition
在CSS中，transition是用来制作过渡效果的，只能是一个样式过渡到另外一个样式，这时可以使用js控制元素的样式来完成动画，具体做法是用一个按钮事件，点击之后使用`id.classList.add()` 添加类，再结合`setTimeout`、`id.classList.add()` `id.classList.remove()`完成简单动画
2. animation
* 基本语法
animation: 动画名 时间 | 过渡方式 | 延迟 | 次数 | 方向 | 填充模式 | 是否暂停 |
* 使用@keyfrmaes生成关键帧
```css
@keyframes heart {
      0%{
        transform: scale(1);
      }
      100%{
        transform: scale(1.2);
      }
    }
```
    
    [跳动的心完整代](http://js.jirengu.com/notil/1/edit?html,css,js,output)
    
    
## 不是所有的属性都可以过渡
例如`display:none => block`就没有过渡效果，一般使用`visibility:hidden=>visible`
这里有两个方法的区别[如何让DOM元素消失](https://dengzhi.xin/archives/%E5%A6%82%E4%BD%95%E8%AE%A9dom%E5%85%83%E7%B4%A0%E6%B6%88%E5%A4%B1)

## 动画渲染优化
* 不用left等做动画，使用transform
* js优化，使用HTML5的`requestAnimationFrame`代替`setTimeout`或者`setInterval`
> `requestAnimationFrame`告诉浏览器——你希望执行一个动画，并且要求浏览器在下次重绘之前调用指定的回调函数更新动画。该方法需要传入一个回调函数作为参数，该回调函数会在浏览器下一次重绘之前执行
