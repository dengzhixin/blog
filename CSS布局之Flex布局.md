## 什么是flex布局
Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。
## 实现
flex布局有两种，一种是`display:flex;`一种是`display:inline-flex;`,区别类似于`block`和`inline_block`
采用flex布局的元素，我们称之为容器`containner`,它的子元素自动成为flex项目，称为`flex item`
## 容器containner的常用属性
* `flex-direction`决定主轴的方向，取值有`row` `row-reverse` `column` `column-reverse`,默认值是`row`
* `flex-wrap` 是否换行，取值有`wrap ` `nowrap`,默认值是`nowrap`,常用值是`wrap`
* `justify-content` 控制子元素在主轴上的对齐方式
   * flex-start
   * flex-end 
   * center
   * space-between 平均分布，两端没有空间
   * space-around 平均分布，两端**有空间**
* `align-items` 控制元素在交叉轴的对齐方式
    * flex-start
    * flex-end
    * center
    * baseline
    * stretch 撑满
* align-content 只有在多跟轴线时生效

 ## item项目的常用属性
 * order 控制项目的排序，默认值是0，数值越小，排列越靠前
 * flex-grow 定义项目的放大比例，默认为0，假设给某个元素设置为1，那么这个元素的宽度将会占满剩余的宽度
 * flex-shrink 定义了项目的缩小比例，默认为1，即如果空间不足，数值越大的被缩小的越多，如果设置为0，那么空间不足时它不会缩小
 * align-self 某个元素单独设置对齐方式
