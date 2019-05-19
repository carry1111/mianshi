#### 1.实现一个函数clone，可以对JavaScript中的5种主要的数据类型（包括Number、String、Object、Array、Boolean）进行值复制
    考察点1：对于基本数据类型和引用数据类型在内存中存放的是值还是指针这一区别是否清楚
    考察点2：是否知道如何判断一个变量是什么类型的
    考察点3：递归算法的设计
```
function clone(obj){
    if(obj instanceof Array || obj instanceof Object){
        var a = obj.constructor === Array ? [] : {};
        for(var i in obj){
            a[i] = typeof obj[i] == 'object' ? clone(obj[i]) : obj[i];
        }
        return a;
    }else{
        return obj;
    }
}
var str = clone('我是');
console.log(typeof str);
var obj = {a:{c:1},b:2};
var newObj = clone(obj);
console.log(newObj);
```