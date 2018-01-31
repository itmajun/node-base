# Vue.cli
---

Vue的相关知识不做过多的整理, vue现在很流行离不开完整的中文文档. 距离目标越来越近了. 如果看的懂vue 项目? 以及如何编写vue 项目? 
官方鼓励使用vue-cli进行vue开发, 并且cli会创建默认的开发环境. 前期的准备就是为了了解如何进行vue开发.


# 项目理解

1. node环境

npm , package.json 通过之前的学习这里可以看的懂. 其中 browserslist 配合autoprefixer 进行的使用.

2. babel

```
"babel-core": "^6.22.1",        // babel支持
"babel-eslint": "^8.2.1",       // eslint 使用 babel-eslint 
"babel-helper-vue-jsx-merge-props": "^2.0.3",
"babel-jest": "^21.0.2",        //测试
"babel-loader": "^7.1.1",       //webpack 使用
"babel-plugin-dynamic-import-node": "^1.2.0",   //测试使用
"babel-plugin-syntax-jsx": "^6.18.0",       //vue-jsx 依赖包  
"babel-plugin-transform-es2015-modules-commonjs": "^6.26.0",    //测试使用
"babel-plugin-transform-runtime": "^6.22.0",     //babel 支持
"babel-plugin-transform-vue-jsx": "^3.5.0",     // vue中支持jsx,
"babel-preset-env": "^1.3.2",   //babel 支持
"babel-preset-stage-2": "^6.22.0",  //babel stage-2 支持
"babel-register": "^6.22.0",    //babel 扩展支持.es6,.es,.jsx...
``

3. editorconfig

IDE 支持 开发环境配置 , 一些文本标准. 可以通过插件支持, 比如sublime ,webstorm 都提供的有插件支持该配置.

4. eslint

```
"eslint": "^4.15.0",        // 支持eslint
"eslint-config-standard": "^10.2.1",    // standard 支持
"eslint-friendly-formatter": "^3.0.0",  //sublime 友好支持
"eslint-loader": "^1.7.1",      //webpack 预处理检测(pre)
"eslint-plugin-import": "^2.7.0",       //
"eslint-plugin-node": "^5.2.0",
"eslint-plugin-promise": "^3.4.0",
"eslint-plugin-standard": "^3.0.1",     //standard 智慧城
"eslint-plugin-vue": "^4.2.2",      //vue 支持
```


5. postcss


```
"postcss-import": "^11.0.0",    // 支持 postcss 中的 @import
"postcss-loader": "^2.0.8",     // webpack postcss 支持
"postcss-url": "^7.2.1",        // postcss中 url支持.
```


6. vue

```

"vue-loader": "^13.3.0",        //webpack 支持ｖｕｅ
"vue-style-loader": "^3.0.1",       //vue 扩展 style-loader
"vue-template-compiler": "^2.5.2",  // 提供vue 预编译
```




7. webpack


```
"webpack": "^3.6.0",        //webpack 支持
"webpack-bundle-analyzer": "^2.9.0",    // webpack 包统计
"webpack-dev-server": "^2.9.1",     //webpack 热部署
"webpack-merge": "^4.1.0"       // webpack merge

```
