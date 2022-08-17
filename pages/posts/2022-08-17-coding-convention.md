---
title: Javascript编码规范
---

<!-- [[toc]] -->

一些编码规范，维护性、可读性第一

## 使用规定的缩进和行长
* 每行代码缩进两个空格
* 每行限制78字符
***
```js
class Index extends Component {
  state = {
    list: [],
    name: '',
    listLoading: false
  }
}
```   

## 命名规范
* 变量名使用a - z、A - Z、0 - 9、下划线和$符号
* 语义化
* 变量名不以数字开头
* 当变量作用域是整个模块时使用驼峰式（模块名字空间的所有地方都可以访问该变量)
* 当变量作用域不是整个模块时使用下划线 (模块名字空间内的某个函数的局部变量)
* 确保所有模块作用域内的变量至少有两个音节，这样作用域就会很清晰（例如下：）
* 全局变量用 const 定义，常量性质，字母全部大写（尽量少定义）
<div color='#26c6da' size='5'> 用户中心 ⇒ userCenter  商品列表 ⇒ goodsList   消息通知 ⇒ messageInfo</div>

## 提升JS性能
* 未使用的功能性代码以及与之相关的代码（它一样的会编译，运行）
* 数组与对象避免使用构造函数（new Array(), new Object()等）
```js
kissObj = () => {
  let kObj = new Object();
  kObj.name = 'xxx'
  return kObj
}
```   
* 推荐
```js
kissObj = () => {
  let kObj = {
    name: 'xxx'
  }
  return kObj
}
``` 
* 避免全局变量（js 的垃圾回收机制是不会销毁全局变量）
* 合理使用闭包（闭包会携带包含它的函数的作用域,因此会比其他函数占用更多的内存，造成网页的性能问题,在IE中可能导致内存泄露）
* 减少循环中的活动（数据量大耗性能）

<style>
hr {
  border-width: 1px 0 0 0 !important;
  margin: 1.25em 0 !important;
}
</style>