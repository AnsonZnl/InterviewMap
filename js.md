## 课工场 2019-2-21 周四 上午
### 1， 查看输出结果
```
fn();// fn is not function
var fn = function(){
    console.log('ok');
}
fn();// ok
```
### 2, 原生JavaScript中的添加、移除、替换、插入的方法是什么？

#### DOM
**添加：**
```
//添加节
var ele = document.getElementById("my_div");
var oldEle = document.createElement("p");
var newEle=document.createElement("div");
ele.appendChild(oldEle);
```
**移除：**
```
//移除
ele.removeChild(oldEle);
```
**替换：**
```
//替换
ele.replaceChild(newEle,oldEle);
```
**插入：**
#### Array
**添加：**`push()、unshift()`
**移除：**`pop()、shift()`
**替换：**`splice()`
**插入：**
#### Object
**添加：**`obj.xxx`
**移除：**`delete obj.xxx `
**替换：**`obj.xxx= yyy`
**插入：**
### 3， 查看输出结果
  ```
var User = {
  count: 1,
  getCount: function(){
    return this.count;
  }
}
console.log(User.getCount());//1 this指向User
var cont = User.getCount;
console.log(cont());//undefined this指向window
```
### 4, js原型、原型链有什么作用?

>每个对象都有原型对象，其中`null`和`Object.creat(null)`构造的对象除外。
每个函数都有`prototype`属性，指向实例的原型对象。
每个对象都有原型对象（`null`除外），我们用`__proto__`表示。
- **什么是原型：**当读取实例的属性时，如果找不到，就会查找与对象关联的原型中的属性，如果还查不到，就去找原型的原型，一直找到最顶层为止,如果还没找到就返回 `undefined`。
- **什么事原型链：**实例对象和原型对像之间用`__proto__`所连接的链状结构。原型链的基本实现就是将一个构造函数的实例赋值给另一个构造函数的原型。这样，这个函数的实例就会继承那构造函数的属性和方法。
- **原型有什么作用：**为新创建的对象提供原型上已有的属性或者方法，比如经常使用`toString()`方法，如果没有原型链，总不能给每个对象都定义一遍吧。有点像“类”的概念
- **原型链有什么作用：**实现属性和方法的继承（引用）,当访问对象`a.b`的时候，首先会查找当前对象的b属性，如果没有，然后依次按照`prototype`往上找直到找到`Object.prototype`为止，没有则返回`undefined`，所以说无处不在。

### 5 ，查看输出结果
```
var length = 10;
function fn(){
  console.log(this.length);
}
var obj = {
  length: 5,
  method: function(fn){
    fn();//10
    arguments[0]();//2 this.length所打印的是arguments的长度
  }
};
obj.method(fn, 1);
```
解析链接：https://segmentfault.com/q/1010000004129717
