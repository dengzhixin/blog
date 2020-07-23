* number
* string
* bool
* symbol
* undefied
* null
* object
* bigint(es11,2020年6月)

> 注意数组、函数、正则表达式、日期都是object

## numer
JavaScript中，number全是以浮点数的形式存储的，没有单独的整数
特殊值：
    正0 负0
    Infinity -Infinity 
    NaN 不能表示的数字
    
## bool
相当于false，但不是false的值
五个falsy值：undefied null 0 null ''

## undefied和null
* 如果一个变量声明了，但是没有赋值，默认值是undefined
* 如果一个函数没有写return,默认 return undefined
* 习惯上，把非对象的空值写为undefined，把对象的空值写为null


## 变量let 和常量const
es6中，这两个语法的出现是为了代替有各种问题的var
* let
    只作用于块级作用域
    全局声明let不会成为window的属性，var会
    for循环常搭配let使用
    不能重复声明
* const
    不能改变
    必须声明同时赋值
    不能重复声明
    只作用于块级作用域
    
