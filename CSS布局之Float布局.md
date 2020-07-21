##  如何选择布局
需要兼容IE9? 
* 需要选择Float布局
* 不需要
    * 只兼容最新浏览器？
        * 是的,选择grid布局
        * 不是,选择flex布局
        

## 实现
1. 在子元素加上`float:left` 和`width`
2. **在父元素加上.clearfix** 
```css
/*
清除浮动
*/
.clearfix::after{
    content:'';
    display:block;
    clear:both;
}
```
## 注意事项
* 有建议到的开发者会多留一些空间或者最后一个元素不设置宽度
* 不需要做响应式，手机上没有IE，Float布局是专门为IE打造的
* 当我们使用`margin-left`时，在IE67中`margin-left`会变成双倍，解决办法是使用`_margin-left:一半`,也可以使用`display:inline-blocl`

## 使用负margin实现平均布局
![7676fad5efca1d4294d22ff60a9752ac.png](evernotecid://1FA57AF5-685F-408C-ABAA-E9E7D59A2831/appyinxiangcom/23431486/ENResource/p19)
* 如图，一个box的宽度是430px
* 有4张图片需要在box里平均分布
* 当给image设置`margin-right:10`发现最后一个元素会掉下去
* 这时在父元素和子元素中间再加一个div,给这个div设置负margin
* 注意此时要将.clearfix添加到这个div

## 缺点
* 需要程序员自己计算宽度，不灵活
