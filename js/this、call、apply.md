#### 1.this
    this是函数运行时自动生成的一个内部对象，只能在函数内部使用，但总指向调用它的对象。
    this的指向
        1）在全局作用域下直接调用函数，this指向window
        2）对象函数调用，哪个对象调用就指向哪个对象
        3）使用 new 实例化对象，在构造函数中的this指向实例化对象。
        4）使用call或apply改变this的指向
#### 2.call,apply？
    联系：作用都是改变this指向
    区别：apply传参数数组，call只能一个一个传参数
#### 3.箭头函数中的 this
```javascript
function a() {
    return () => {
        return () => {
        	console.log(this)
        }
    }
}
console.log(a()()())
```
箭头函数其实是没有 this 的，这个函数中的 this 只取决于他外面的第一个不是箭头函数的函数的 this。在这个例子中，因为调用 a 符合前面代码中的第一个情况，所以 this 是 window。并且 this 一旦绑定了上下文，就不会被任何代码改变。