# WebPack
---

打包工具.
1. 入口: 从哪里开始打包
2. 输出: 打包后放到哪里
3. loader: 如何打?
4. plugins: 扩充loader功能.

# Install
---
```
npm install --save-dev webpack
yarn add webpack --dev
```

# 使用
---

```
webpack src/index.js dist/bundle.js
webpack --config webpack.config.js
```

# webpack.config.js
---

我们发现项目都是通过config进行配置的, config说明了所有webpack的配置以及功能. webpack中文文档已经非常的全面.我们只关注使用的方式.


# 疑问
---

1. webpack 转换js流程?

在之前通过babel 可以进行js的相关转换. 在webpack中如何使用babel呢?

```
npm install babel-loader babel-core babel-preset-env webpack

module: {
  rules: [
    {
      test: /\.js$/,
      exclude: /(node_modules|bower_components)/,
      use: {
        loader: 'babel-loader',
        options: {
          presets: ['@babel/preset-env']
        }
      }
    }
  ]
}

options: https://babeljs.io/docs/usage/api/#options
options 默认会查找 .babelrc 文件
```

2. webpack 中 css 打包流程?

```
css-loader 指定需要解释的 css文件中出现的 @import , url().
style-loader 可以在一个dom中注入一个<style>
postcss-loader 可以把css 转换成多浏览器支持的格式
```


*待续: webpack东西太多了. 所有的知识点最终发现还是要配合webpack进行使用.*

