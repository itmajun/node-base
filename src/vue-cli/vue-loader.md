# vue-loader
---

入口main.js开始进行js的解释。 其中发现了`*.vue`文件，该文件使用vue-loader进行解释。 如何解释的呢？

# 概述
---
vue-loader 重要的三个标签 
`<template>
<script>
<style>`


# template
---

* 默认html
* 每个vue文件中最多只能有一个template
* 块中的内容作为字符串提取出来翻译成vue组件

# script
---

* 默认js， 如果使用了babel-loader，buble-loader自动支持es2015语法
* 每个vue文件中最多只能有一个script标签
* 必须export一个vue.js组件选项对象，或者Vue.extend

# style
---

* 默认css
* 每个vue文件支持多个style标签
* 支持scoped／module属性：使用scoped表示局部样式，只在当前页面生效，使用module，可以注入vue对象，通过$style 进行使用，也可以制定module名称
* 默认内容会使用style-loader进行解释然后插入到`<head>`标签中 `<style>` 
# 自定义
---

自定义名称，找到之后会去查询使用那个webpack loader进行解释，可以通过vue-loader options进行设置


# 导入
---
通过使用src进行依赖导入

# 注释
`<!-- -->`

# Postcss
---

如果存在postcss配置文件则自动使用配置文件进行postcss处理