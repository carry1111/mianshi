#### 1、如何判断一个对象是否属于某个类？
使用instanceof （待完善）
```javascript
if(a instanceof Person){
    alert('yes');
}
```
#### 2、instanceof的实现代码:
```javascript
function instance_of(L,R){
    var O = R.prototype;
    L = L.__proto__;
    while(true){
        if(L === null){
            return false;
        }
        if(O === L){
            return true;
        }
        L = L.__proto__;
    }
}
```