# a
* href 是hyper refrence（超级的引用） 的缩写

  有以下取值：
   网址
   `https//google.com`  `http//google.com`  `//google.com` 这三个值优先使用**//**，会自动适应应该使用http还是https

   路径
   `/a/b/c.html`中的/指的是项目的根目录而不是系统的根目录(使用http服务启动的项目)

   伪协议
   `javascriput:aler();`执行JavaScript代码，可以使用 `href="javascripit:;"`来实现a标签点击后不执行任何操作

   ID 跳转到制定的锚点

   mailto:邮箱

   tel:手机号
 
* target
 内置取值：
   1. _black 使用新标签打开
   2. self 在当前标签打开，默认值
   3. top 在最顶层打开，在iframe中使用到
   4. parent  在父层打开
 程序员的取值
   1. window的name
      给不同的a标签的target设置了系统的自定义值，那么不同的标签都会在同一个标签页打开
   2. iframe的name
   
# iframe 内嵌窗口，不常用，过时
# table
* 表头中的th表现为加粗
```html
<table>
      <thead>
        <tr>
          <th>表头1</th>
          <th>表头2</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>2</td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td1>1</td1>
          <td2>2</td2>
        </tr>
      </tfoot>
  </table>
```
* table的相关样式
```css
table{
  table-layout:auto; //表格会根据表头的内容自适应分配宽度
  border-spacing:0; //单元格的间隔为0
  border-collapse:collapse; //是否合并，collapse表示塌陷的意思，即边框是否塌陷：塌陷
}
```

# img
* 发起get请求，展示一张图片
* 常用的属性有 `src` `height` `width` `alt`
* 常用的事件有 `onload` `onerror`
* 给标签加上 `max-width:100%`样式即可实现响应式

```javascript
<script>
      tp.onload=function(){
        console.log("图片加载成功")
      }
      tp.onerror=function(){
        console.log("图片加载失败")
        tp.src="备用图.png"
      }
</script>

```

# form 
* 作用：发起get或post请求，然后刷新页面
* `action` 请求地址
* `method` 请求方法，取值有`GET` 和 `POST`
* autocomplete 用于指示 input 元素是否能够拥有一个默认值，此默认值是由浏览器自动补全的
* target 提交action后，在哪里显示响应信息

> 一个type="submit"的input和button有什么区别？
button里面可以有其他标签，如图片等等，而input是自闭合标签，它的value只能是

# input
* type的取值有
  1. text
  2. color
  3. password
  4. radio
  5. checkbox
  6. file
  7. textarea
  8. select + option
  
* textarea常见样式
```
textarea{
  resize:none;
  width:xxx;
  height:xxx;
  
}
```
* 常见事件
  1. oncahnge 值改变
  2. onfocus 获得焦点
  3. onblur 失去焦点
  
> 
* 一般input标签不监听click事件
* form表单里的input要有name
* form表单里必须有一个type="submit"才能出发submit事件

   
