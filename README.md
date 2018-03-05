# vue全家桶收银系统

## 创建侧边栏导航
新建 src/componets/common/leftNav.vue

引入到 App.vue
```html
<template>
  <div id="app">
    <!-- 左侧导航 -->
    <leftNav></leftNav>
    <!-- 内容区 -->
    <router-view></router-view>
  </div>
</template>

<script>
import leftNav from './components/common/leftNav'
export default {
  name: 'App',
  components: {
    leftNav,
  },
}
</script>
```

## 安装element-ui

安装
```bash
cnpm i element-ui --save
```
main.js
```js
import ElementUI from 'element-ui'
import 'element-ui/lib/theme-chalk/index.css'

Vue.use(ElementUI)
```
使用原生JS

使用 vue 的 mounted 钩子执行原生JS，该钩子会在 编译好的 html 挂在到页面完成后执行，且只执行一次

```js
export default {
  name: "pos",
  mounted:function(){
    var orderListHeight = document.body.clientHeight
    console.log(orderListHeight)
    document.querySelector('.order-list').style.height = orderListHeight + 'px'
  },
}
```
