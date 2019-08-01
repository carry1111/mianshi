## web前端面试题
+ js基础
    + [最简单的数组去重方式](https://github.com/carry1111/mianshi#%E6%9C%80%E7%AE%80%E5%8D%95%E7%9A%84%E6%95%B0%E7%BB%84%E5%8E%BB%E9%87%8D%E6%96%B9%E5%BC%8F) 
    + [数组排序(从小到大)](https://github.com/carry1111/mianshi#%E6%95%B0%E7%BB%84%E6%8E%92%E5%BA%8F%E4%BB%8E%E5%B0%8F%E5%88%B0%E5%A4%A7)
    + [创建ajax过程](https://github.com/carry1111/mianshi#%E5%88%9B%E5%BB%BAajax%E8%BF%87%E7%A8%8B)
    + [闭包](https://github.com/carry1111/mianshi#%E9%97%AD%E5%8C%85)
    + [原型、原型链](https://github.com/carry1111/mianshi#%E5%8E%9F%E5%9E%8B%E5%8E%9F%E5%9E%8B%E9%93%BE)
    + [判断[] == ![]](https://github.com/carry1111/mianshi#%E5%88%A4%E6%96%AD--)
+ js进阶
    + [new](https://github.com/carry1111/mianshi#new)
    + [instanceof 的原理](https://github.com/carry1111/mianshi#instanceof-%E7%9A%84%E5%8E%9F%E7%90%86)
+ es6
    + [var、let 及 const 区别？](https://github.com/carry1111/mianshi#varlet-%E5%8F%8A-const-%E5%8C%BA%E5%88%AB)
+ 正则表达式
    + [给string添加一个trim方法，去掉开头和结尾的空格符号](https://github.com/carry1111/mianshi#%E7%BB%99string%E6%B7%BB%E5%8A%A0%E4%B8%80%E4%B8%AAtrim%E6%96%B9%E6%B3%95%E5%8E%BB%E6%8E%89%E5%BC%80%E5%A4%B4%E5%92%8C%E7%BB%93%E5%B0%BE%E7%9A%84%E7%A9%BA%E6%A0%BC%E7%AC%A6%E5%8F%B7)
+ 编程题
    + [如何判断一个对象是否为数组](https://github.com/carry1111/mianshi#%E5%A6%82%E4%BD%95%E5%88%A4%E6%96%AD%E4%B8%80%E4%B8%AA%E5%AF%B9%E8%B1%A1%E6%98%AF%E5%90%A6%E4%B8%BA%E6%95%B0%E7%BB%84)

### js

#### 最简单的数组去重方式
    [...new Set(array)]
#### 数组排序(从小到大)
```javascript
function incSort(arr){
    let len = arr.length;
    let mid;
    for(var i = len - 1; i > 0; i--){
        for(var j = 0; j < i; j++){
            if(arr[j] > arr[j+1]){
                mid = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = mid;
            }
        }
    }
    return arr;
}
```
#### 创建ajax过程
- 创建XMLHttpRequest对象,也就是创建一个异步调用对象.
- 创建一个新的HTTP请求,并指定该HTTP请求的方法、URL及验证信息.
- 设置响应HTTP请求状态变化的函数.
- 发送HTTP请求.
- 获取异步调用返回的数据.
- 使用JavaScript和DOM实现局部刷新.
#### 闭包
    闭包的定义其实很简单：函数 A 内部有一个函数 B，函数 B 可以访问到函数 A 中的变量，那么函数 B 就是闭包。
    闭包是指有权访问另一个函数作用域中的变量的函数。
    创建闭包的常见方式，就是在一个函数内部创建另一个函数。
    闭包会导致原有作用域链不释放，造成内存泄漏
#### 原型、原型链
    原型：我们创建的构造函数都有一个prototype属性，指向原型对象，原型对象的用途是包含这个构造函数的所有实例共享的属性和方法。
    原型链：对象的  __proto__  属性指向原型，  __proto__  将对象和原型连接起来组成了原型链
####  判断[] == ![] 
    [] == ![]  =>  
    [] == false  =>  
    [] == 0  =>  
    '' == 0  =>  
    0 == 0  =>  
    true

### js进阶

#### new
    在调用  new  的过程中会发生以上四件事情：
    1. 新生成了一个对象 
    2. 链接到原型 
    3. 绑定 this 
    4. 返回新对象
#### instanceof 的原理
instanceof  可以正确的判断对象的类型，因为内部机制是通过判断对象的原型链中是不是能找到类型的 prototype 。
```javascript
function myInstanceof(left,right) {
    let prototype = right.prototype;
    left = left.__proto__;
    while(true){
        if(left === null || left === undefined){
            return false;
        }
        if(left === prototype){
            return true;
        }
        left = left.__proto__;
    }
}
```

### es6

#### var、let 及 const 区别？
首先在全局作用域下使用  let  和  const  声明变量，变量并不会被挂载到  window  上，这一点就和  var  声明有了 区别。
使用  var  声明的变量会被提升到作用域的顶部，let 和 const 则不会。
    
### 正则表达式

#### 给string添加一个trim方法，去掉开头和结尾的空格符号
```javascript
String.prototype.trim = function(str){
    return this.replace(/(^\s*)|(\s*$)/g,'');
}
```

### 编程题

#### 如何判断一个对象是否为数组
```javascript
function isArray(arg){
    if(typeof arg == 'object'){
        return Object.prototype.toString.call(arg) == '[object Array]';
    }
    return false;
}
```

