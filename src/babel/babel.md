# Babel
---

在很多项目中都会看到babel ，在ES6之后开始鼓励使用新的语法。nodeJS现在已经支持到了ES2018，
ES2015（ES6）作为新语法的基础一直在推广，然而并不是所有的浏览器都支持ES6+语法。
Babel 提倡使用新语法进行javascript的编写。不支持的浏览器，babel会把新语法编译之后转换成兼容
旧的方式。那么我们就不需要关心，我写的新语法，有些浏览器不支持怎么办这样的问题了。

# Babel-core

```
1. 在 webpack中使用babel
npm install --save-dev babel-loader babel-core 

2. 配置webpack
module: {
  rules: [
    { test: /\.js$/, exclude: /node_modules/, loader: "babel-loader" }
  ]
}
3..babelrc

npm install babel-preset-env --save-dev

{
  "presets": ["env"]
}

```

# babel-plugins
---

babel 主要负责进行解析-》转换-》生成 ，在这三个过程中， 首先babel 通过babel-preset-env解析各种
es6+ 语法。之后开始把这些新语法转换成兼容的语法， plugins主要作用于这个阶段。比如我们经常使用
stage2，说明一些新的规范，不过并没有发布实施。

* babel-plugin-transform-vue-jsx： 用于转换vue代码中jsx的语法
* babel-plugin-dynamic-import-node： 用于转换import()--> require()
* babel-plugin-transform-runtime: 用于防止Promise，set，map 污染全局对象
* babel-preset-stage-2： 用于支持没有发布的新的规范
* babel-register： 用于转码require（）

