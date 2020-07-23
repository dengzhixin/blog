
## 对象
对象是无需的数据集合，也是键值对的集合，键名必须是字符串(es6新增了symbol也可以是属性名)，如果要使用变量名为键，可以使用[变量名]
## 声明对象
* 大括号创建法
```js
let obj = {
  'foo': 'Hello',
  'bar': 'World'
};
```
* new创建法
```js
let obj = new Obj({ name:'arleen; age:18' })
```

## 删
delete obj.name 可以删除属性

## 读
* ` Object.keys() `可以查看所有的key
* `Object.values() `可以查看所有的值
* `Object.entries()` 可以查看所有的键和所有的值，返回的是一个数组
* `console.dir(log)` 在控制台打印出obj
* `obj.hasOwnPreperty('toString')` 判断属性是否是对象自生携带的属性，还是原型带来的共有属性,与`'name' in obj`不同，它只会判断obj是否可用使用name,不管是自身的，还是原型上的

## 写
* 直接赋值
* 批量赋值
    `Object.assign(obj,{a:1,b:2})`
    这句会把第二个对象赋值给obj，有时也会将obj设置为空对象，用来浅拷贝对象
    
* 修改或添加共有属性
    1. 无法通过自身修改或者增加共有属性，自身的修改只会影响到自身
    2. 但是可以通过在原型上修改达到影响所有对象的共有属性，千万不要这么做
* `Object.create(x)` 会创建一个以x为原型的对象
* `new Object(x)`创建了x对象，但是原型不变

## 一些奇奇怪怪的属性名
![](https://dengzhixin-halo.oss-cn-shenzhen.aliyuncs.com/halo/image_1595538763667.png?x-oss-process=style/pic)

## 原型
什么是原型？
每个对象都有原型，里面存着对象的共有属性，比如声明了一个空对象obj,obj的原型就是一个对象，在obj中，存在一个隐藏的属性，__proto__，这个属性就存着obj的原型这个对象的地址，这个对象有`toString`、`valueOf`等等共有属性
对象的原型也是对象，所以对象的原型也有原型，空对象的原型是所有对象的原型，这个原型包含所有对象的共有属性，是对象的根，这个原型的原型的值是null
![image.png](https://dengzhixin-halo.oss-cn-shenzhen.aliyuncs.com/halo/image_1595538779644.png?x-oss-process=style/pic)

