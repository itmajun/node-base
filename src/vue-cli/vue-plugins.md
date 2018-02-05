# Vue plugins
---

Vue 插件机制, 在阅读源码时候, 发现别人提供的组件都是插件的形式进行注入到Vue中.

# Vue plugin 知识
---

插件就是增加Vue的全局功能.

**install**: 插件必须提供该方法.第一个参数为Vue对象,第二个参数为options(可选参数)
```
MyPlugin.install = function (Vue, options) {
  // 1. 添加全局方法或属性
  Vue.myGlobalMethod = function () {
    // 逻辑...
  }

  // 2. 添加全局资源
  Vue.directive('my-directive', {
    bind (el, binding, vnode, oldVnode) {
      // 逻辑...
    }
    ...
  })

  // 3. 注入组件
  Vue.mixin({
    created: function () {
      // 逻辑...
    }
    ...
  })

  // 4. 添加实例方法
  Vue.prototype.$myMethod = function (methodOptions) {
    // 逻辑...
  }
}
```
官方给出的例子已经说明了一切.

```
//使用
Vue.use(MyPlugin, { someOption: true })
```

```
比如: iview 组件中
插件中通过Vue.component 注入了全局的组件, 和若干全局方法.
Vue.component(key, iview[key]);
Vue.prototype.$Loading = LoadingBar;
```