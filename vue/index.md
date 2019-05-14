#### 1.MVVM的理解？
    MVVM 是Model-View-ViewModel的缩写。
    Model 代表数据模型，可以定义数据修改和操作的业务逻辑，
    View 代表UI组件，负责将数据模型转化成UI展现出来，
    ViewModel 监听模型数据的改变，控制视图行为
#### 2.vue的生命周期
    beforeCreate(创建前) 数据观测，初始化事件还未开始
    created(创建后) 完成数据观测，属性和方法的运算，初始化事件，$el属性还没有显示出来
    beforeMount(载入前) 在挂载之前被调用，实例已完成以下的配置：编译模板，将data中的数据和模板生成html
    mounted(载入后) 在挂载之后被调用，实例已完成以下的配置：将编译好的模板渲染到页面中
    beforeUpdate(更新前) 在数据更新之前调用，发生在虚拟dom重新渲染之前，可以在该钩子中进一步更改状态，
                        不会触发附加的重渲染过程
    Updated(更新后) 在由于数据更改导致的虚拟dom重渲染之后调用
    beforeDestroy(销毁前) 在实例销毁之前调用，实例仍然完全可用
    Destroyed(销毁后) 在实例销毁之后调用。调用后，所有的事件监听器被移除，所有的子实例也被销毁
    (1)什么是vue生命周期？
        vue实例从创建到销毁的过程，就是vue的生命周期。从开始创建，初始化数据，编译模板，挂载dom->渲染，
        更新->渲染，销毁，等一系列过程。
    (2)vue生命周期的作用是什么？
        它的生命周期中有多个事件钩子，便于我们更好地控制整个vue实例的过程
    (3)第一次页面加载会触发哪几个钩子？
        答：会触发 下面这几个beforeCreate, created, beforeMount, mounted 。
#### 3.Vue实现数据双向绑定的原理：Object.defineProperty()
    通过Object.defineProperty()来劫持各个属性的getter，setter，
    在数据变动时发布消息给订阅者，触发相应监听回调
#### 4.vuex是什么？怎么使用？哪种功能场景使用它？
    vuex是一种状态管理模式；
    怎么使用：创建一个store实例，在main.js中引入，注入。
    场景：单页应用中，组件之间的状态，登陆状态，加入购物车等
    state:存放状态
    mutaitions：动态修改状态，通过commit触发
    action: 异步操作数据，view 层通过 store.dispath 来分发 action。
    getters:类似于vue的计算属性，主要用来过滤一些数据
#### 5.vue-router
    使用步骤：(1)配置路由，一个路由对应一个组件，(2)创建router实例，传入路由配置，(3)根实例注入路由
    使用router-link组件导航，to属性指定链接
    router-view渲染匹配到的组件
