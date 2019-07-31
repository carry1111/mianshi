# web前端面试题
+ js
    + [最简单的数组去重方式](https://github.com/carry1111/mianshi#%E6%9C%80%E7%AE%80%E5%8D%95%E7%9A%84%E6%95%B0%E7%BB%84%E5%8E%BB%E9%87%8D%E6%96%B9%E5%BC%8F) 
    + [数组排序(从小到大)](https://github.com/carry1111/mianshi#数组排序(从小到大))
    + [创建ajax过程](https://github.com/carry1111/mianshi#创建ajax过程)
    + [闭包](https://github.com/carry1111/mianshi#闭包)
+ 正则表达式
    + [给string添加一个trim方法，去掉开头和结尾的空格符号](https://github.com/carry1111/mianshi#给string添加一个trim方法，去掉开头和结尾的空格符号)
+ 编程题
    + [如何判断一个对象是否为数组](https://github.com/carry1111/mianshi#如何判断一个对象是否为数组)
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
    闭包是指有权访问另一个函数作用域中的变量的函数。
    创建闭包的常见方式，就是在一个函数内部创建另一个函数。
    闭包会导致原有作用域链不释放，造成内存泄漏
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

