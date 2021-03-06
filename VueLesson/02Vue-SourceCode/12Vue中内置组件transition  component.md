---
title:  Vue中内置组件源码实现
date: 2018-01-08 
categories: vue
---

### 1 内置组件包括：有以下内置的抽象组件

* keep-alive
* transition
* transition-group
* component
* slot

### 2 `transition`组件的作用：元素作为单个元素/组件的过渡效果。`<transition>` 只会把过渡效果应用到其包裹的内容上，而不会额外渲染 DOM 元素，也不会出现在检测过的组件层级中



### 3 component组件

```javascript
var vm = new Vue({
  el: '#example',
  data: {
    currentView: 'home'
  },
  components: {
    home: { /* ... */ },
    posts: { /* ... */ },
    archive: { /* ... */ }
  }
})
```

```Vue
<component v-bind:is="currentView" prop-a="someValue" >
  <!-- 组件在 vm.currentview 变化时改变！ -->
</component>
props会直接传递到对应的组件上，作为组件的props
```



