```js
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
#### 为什么上面的代码会打印出6个6？
let i 定义在for循环外面，setTimeout是在for循环执行完之后执行，因此在循环执行完成后，i已经等于0，然后setTimeout执行是，打印出的都是6。
我们要打印出0,1,2,3,4,5的话，将代码修改成下面的代码
```js
for(let i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
这是let的特性，在for循环执行时，每次循环都会创建单独的作用域，相当于有6个i，setTimeout分别调用的是不同的i，这样可以使代码打印出0,1,2,3,4,5

我们还可以这样解决,在setTimeout的函数里面在return一个函数
```
for (var i = 0; i < 6; i++) {
    setTimeout((function(i){
        return function() {
            console.log(i);
        }
    }(i)),0)
}
// 0 1 2 3 4 5
```


