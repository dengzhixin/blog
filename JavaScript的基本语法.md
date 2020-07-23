## 什么是表示式和语句
var a =1 是语句
a=1是表达式
1+2是表达式
add(1,2)表达式的值是函数的返回值
console.log表达式的值是函数本事
**console.log(3)表达式的值是undefined**
## 注意
* JS大小写敏感
* 代码多个空格，换行一般不会影响，只有一个地方不行，就是**return 的时候**
![](https://dengzhixin-halo.oss-cn-shenzhen.aliyuncs.com/halo/image_1595486194599.png?x-oss-process=style/pic)

## 标识符
* 第一个字符：可以是Unicode字母、&、_、中文
* 其他字符：除了上面的还可以是数字

## if else
```
if(表达式){语句1}else{语句2}
```
* 当语句只有1句的时候，花括号可以省略（不建议使用，容易引起歧义）

```javascript
a=1
if(a===2)
    console.log(a)
    console.log("a=2")
    
```
输出 a=2
原因：if语句省略的花括号只会管1个语句,上面的代码等同于
```js
a=1
if(a===2){
    console.log(a)
}
console.log("a=2")
    
```

* 三元表达式
    表达式？语句1:语句2
    表达式为真执行语句1，假执行语句2
* A&&B
    例如`console && console.log && console.log(1)`的意思是`console`存在时，向后执行`console.log`也存在时，执行`console.log(1)`

* A || B 常用于做保底值
    a = a || 100
    如果a存在`a=a`,不存在`a=100`

## while 和for
* while(表达式){语句}
表示式为真是执行语句，语句执行完后再次判断表达式


```js
let a = 0.1
while(a!==1){
a=a+0.1
}
```
上面是一个死循环，原因是浮点数不精确

* for(定义变量;循环执行条件;语句体执行完后执行的语句){
        语句体
    }

    
* break 跳出循环
* continue 执行next下一个循环
## label标签
```
{a:1}
```
这是什么意思？
a是一个标签，它的语句是一个1

```
var a = {a:1}
```
这才是对象
