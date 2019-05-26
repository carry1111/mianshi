#### 判断一个数是否是整数
```javascript
function isIntefer(x){
    return x%1===0; //返回布尔
}
```
#### 0.1 + 0.2 === 0.3 表达式的值是？
这个表达式的计算结果为 false ，这是因为 JavaScript 遵循 IEEE 754 数学标准，使用 64 位浮点数进行运算。在进行十进制运算时会导致精度丢失，简言之，计算机是以 2 为基础进行运算的，而十进制是以 10 为基础进行运算的
```javascript
0.1 + 0.2 // 0.30000000000000004
```
一个解决方案是，定义一个误差值（epsilon），使得两数之差小于这个值，然后通过函数判断它们是否近似相等
```javascript
const approxEqual = (n1, n2, epsilon = 0.0001) => Math.abs(n1 - n2) < epsilon
approxEqual(0.1 + 0.2, 0.3) // true
```