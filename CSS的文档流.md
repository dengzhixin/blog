## 概念
文档流的英文是Normal Flow，应该翻译成常规流或者普通流，表示的含义是文档元素流动的方向

## 流动方向
* inline 元素 从左到右，到达行位会折行，如果里面的一个元素在行位不够位置，会将元素强行切开，一部分在上，一部分在下一行
* block 元素 从上到下，元素独占一行
* inline-block 从左到右和inline一样
## 宽度
* inline的宽度由内部inline元素决定，不能指定width 
* block 可以用width指定，默认值是auto，能多宽就多宽
* inline-block 结合两者特定，可以用width指定
## 高度
* inline 间接由line-height决定，更height无关
* block 默认由内部文档流元素决定，可以指定
* inline-block 和block一样

## 注意事项
* 不要在inline元素里面写block元素，浏览器不会保存，但是会渲染得乱七八糟，没有人这么写
* 慎用宽度100%
## span的高度由谁决定？
从图片上看，padding看似成高了span，其实span只是撑高了span的可视高度，并不会撑高span的实际高度，从“您好”的文字所在位置和div的高度可以确定。
![](https://dengzhixin-halo.oss-cn-shenzhen.aliyuncs.com/halo/image_1595254443123.png?x-oss-process=style/pic)
那么span的高度由什么确定的呢？
![](https://dengzhixin-halo.oss-cn-shenzhen.aliyuncs.com/halo/image_1595254448818.png?x-oss-process=style/pic)

在span中修改`line-height`的值可以看出，实际高度是有line-height间接确定的
> 此外元素的字体也会隐藏span的高度，原因是否复杂。[一篇详细介绍原因的文章](https://zhuanlan.zhihu.com/p/25808995)
> 

