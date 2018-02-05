# Component 组件化
---

```
全局注册一个组件
Vue.component('my-component', {
  // 选项
})

局部组件
new Vue({
  // ...
  components: {
    // <my-component> 将只在父组件模板中可用
    'my-component': Child
  }
})

```

# data 必须是函数

```
Vue.component('simple-counter', {
  template: '<button v-on:click="counter += 1">{{ counter }}</button>',
  // 技术上 data 的确是一个函数了，因此 Vue 不会警告，
  // 但是我们却给每个组件实例返回了同一个对象的引用
  data: function () {
    return data
  }
})

```

# 父子组件传参


父-->子: 通过props进行传递
```
Vue.component('child', {
  // 声明 props
  props: ['message'],
  // 就像 data 一样，prop 也可以在模板中使用
  // 同样也可以在 vm 实例中通过 this.message 来使用
  template: '<span>{{ message }}</span>'
})

<child message="hello!"></child>

props支持驼峰命名,不过在 template中要使用横线的方式进行分割比如: myMessage --> my-message

// 绑定父组件的数据
<child :my-message="parentMsg"></child>

//属性的传递 只能是父-->子, 不允许子修改父的数据, 如果要修改数据需要定义局部变量

// props 支持验证:  propB: [String, Number],
```

子-->父: 通过事件进行沟通

```
1. 绑定父监听事件v-on　  <button-counter v-on:increment="incrementTotal"></button-counter>
2. 实现子事件   <button v-on:click="incrementCounter">{{ counter }}</button>

methods: {
    incrementCounter: function () {
      this.counter += 1
      this.$emit('increment')
    }
  },

3. 编写父事件监听

methods: {
    incrementTotal: function () {
      this.total += 1
    }
  }

4. 子组件触发事件 this.$emit('increment')

```

# slot
---

* 插槽. 有些类似于java中的sitemesh. 定义了需要替换的部分.
* 如果子组件没有slot 则无法接受到父组件中的内容.
* slot 可以指定名称接受内容.<slot name="header"></slot>

#  