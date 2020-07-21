## 什么是grid布局
网格布局（Grid）是最强大的 CSS 布局方案。
它将网页划分成一个个网格，可以任意组合不同的网格，做出各种各样的布局。
> [推荐一个学习grid的小游戏](https://cssgridgarden.com/#zh-cn) 通关后基本就可以使用了

> PS : 只有较新的浏览器才支持，比如百度浏览器等不支持，具体可以通过[这个网站查询](https://caniuse.com/#search=grid)，强大的grid布局在之后必定会成为主流


## 容器的属性
* grid-template-columns 和 grid-template-rows 
    * 指定每行 每列所占的大小
     ```css
    .container {
        display: grid;
        grid-template-columns: 100px 100px 100px;
        grid-template-rows: 100px 100px 100px;
    }
    ```
    * 也可以使用`fr`的单位表示占几分 如 `grid-template-columns:1fr 2fr 1fr`
    * 还可以使用`repeat(3,100px)`css函数来简写重复的书写
    * 

* grid-gap 间隙
* grid-template-areas 定义区域,这里需要和子项目的`grid-area`属性指定的名字一致
     ```css
     .container{
         display:grid;
         grid-template-areas: 'header header header'
                       'aside main main'
                       'footer footer footer';
     }
     ```

## 项目的属性
* grid-column-start、grid-column-start、grid-row-start、grid-row-end
    * 指定元素在不同方向上的起始位置和结束位置
    
    * 结束位置`end`也可以输入`span 数字`表示占积分，不输入具体的位置在哪条先

* grid-area 和父元素的`grid-template-areas`配合使用

> 这里只列举了部分常用的属性，过多可以查看[阮一峰的教程](https://www.ruanyifeng.com/blog/2019/03/grid-layout-tutorial.html)
