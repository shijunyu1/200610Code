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
### 响应式数据
    data中的数据发生改变，页面会更新
    
### 数据双向绑定
    使用 v-model获取数据  data中注册数据

### 指令
    v-text
    v-on   简写 @
    v-bind 简写 :
    v-if 直接删除标签
    v-show display变成none