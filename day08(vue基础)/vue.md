### 模版
    {{}} ：插槽
    v-model ：数据双向绑定
### 配置
    el:挂载节点
    data ：存放响应数据
    methods : 函数(事件对应的回调  普通函数)
    computed ： 计算属性
    watch ： 监听数据
    components ： 定义局部组件
    templata : 模版
    props ： 表示子组件接受了父组件的那些数据
    beforeCreate
    created
    beforeMount
    mounted ： 生命周期钩子，在vue的生命周期中会被自动调用
    beforeUpdate
    updated
    beforeDestroy
    destroyed
### 声明式编程
    只要声明就可以使用
    
### 响应式数据
    data中的数据发生改变，页面会更新
    只有data中注册过才具备响应式
    data中的数据都会转绑诶vm实例对象
    
### 数据双向绑定
    使用 v-model获取数据  data中注册数据

### 指令
    {{}} ：插槽
    v-text
    v-on   简写 @
    v-bind 简写 :
    v-if 直接删除标签
    v-show display变成none
    v-model ：数据双向绑定
    
### 计算属性
    1. 支持缓存，只有依赖数据发生改变，才会重新进行计算
    
    2. 不支持异步，当computed内有异步操作时无效，无法监听数据的变化
    
    3.computed 属性值会默认走缓存，计算属性是基于它们的响应式依赖进行缓存的
        ，也就是基于data中声明过或者父组件传递的props中的数据通过计算得到的值
        
    4. 如果一个属性是由其他属性计算而来的，这个属性依赖其他属性，
        是一个多对一或者一对一，一般用computed
        
    5.如果computed属性属性值是函数，那么默认会走get方法；
        函数的返回值就是属性的属性值；在computed中的，
        属性都有一个get和一个set方法，当数据变化时，调用set方法
        
### watch
    1. 不支持缓存，数据变，直接会触发相应的操作；
    2.watch支持异步；
    3.监听的函数接收两个参数，第一个参数是最新的值；第二个参数是输入之前的值；
    4. 当一个属性发生变化时，需要执行对应的操作；一对多；
    5. 监听数据必须是data中声明过或者父组件传递过来的props中的数据，
        当数据变化时，触发其他操作，函数有两个参数，
            immediate：组件加载立即触发回调函数执行，
        　　deep: 深度监听，为了发现对象内部值的变化，复杂类型的数据时使用，
       例如数组中的对象内容的改变，注意监听数组的变动不需要这么做。
       注意：deep无法监听到数组的变动和对象的新增，参考vue数组变异,
            只有以响应式的方式触发才会被监听到。
      
### 方法
    Vue.prototype.$mount   : 相当于el配置;决定了vue的模板以及挂载节点
    Vue.prototype.$set     : 给vue添加新的响应式属性
    Vue.prototype.$watch   : 相当于watch配置
    
### 事件
    Vue.prototype.$on      : 给vue实例注册自定义事件
    Vue.prototype.$emit    : 触发对应vue实例的自定义事件
    Vue.prototype.$off     :
            不传参数:解除所有对应vue实例的自定义事件
            传一个参数:解除对应vue实例的对应的自定义事件
            传一个参数 传一个函数的名字:解除对应vue实例的对应的自定义事件的对应回调
    Vue.prototype.$once : 触发对应vue实例的自定义事件(只触发一次)           

### 组件使用细节
    1. 不要和html5的规范产生冲突
        ----组件的命名不能使用已有的html标签 (组件命名的时候加个v-)
        ----table下只能跟tr这种类型的元素 (is属性来指定将tr最终渲染成哪个组件)
            table                   table
                <v-row></v-row>       <tr is="v-row"></tr>
    
    2. 组件上使用@ 注册的是vue的自定义事件
        <v-row @click="fn"></v-row>
    
    3. 组件上的标签属性分3拨
            props属性 : 出现在了组件props配置中属性
                子组件要接收的数据
            vue指令   : v-开头的属性
                不同的指令有不同的意义
            非props属性: 排除以上两种 都是非props属性
                class
                子组件会继承下来

### vue实例&组件化
    在vue中一个组件就是一个vue实例
    $mount 1.el帮我们指定了模板 2.确定了vm对应的挂载节点
    $once : 注册vue自定义事件（一次性的）
    $off : 解绑vue的自定义事件
    