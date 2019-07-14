#### v-if与v-show的区别
    相同点：v-if与v-show都可以动态控制dom元素显示隐藏
    不同点：v-if显示隐藏是将dom元素整个添加或删除，而v-show隐藏则是为该元素添加css--display:none，dom元素还在。
    
    性能消耗：v-if有更高的切换消耗；v-show有更高的初始渲染消耗；
    使用场景：v-if适合运营条件不大可能改变；v-show适合频繁切换。