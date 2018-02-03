# vuex
---

之前学习过react-native ,其中需要维护全局的state 使用了redux进行状态管理。这里的vuex应该也类似，只不过一个是react的标配，一个是vue的轮子，再发展下去，可能还会再出现一个vue版本react-native，名字我都想好了。vue-native - -!

# 概念
---

* state: vuex就是为了维护一份state
* store: 用来保存state
* Getter: 通过getter方法访问state
* Mutation:  通过mutations 改变state的状态`store.commit('increment')`
* Action: 同mutations，改变state状态，不过前者必须同步进行，Action可以包含一步操作
* Module: 分割store，避免越来越多的state太过臃肿
