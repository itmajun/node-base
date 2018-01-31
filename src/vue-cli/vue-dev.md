# Vue 开发环境解读

1. 命令 `dev` 运行开发环境

    ```
        webpack-dev-server --inline --progress --config build/webpack.dev.conf.js
    ```

    webpack-dev-server: 支持热更新, inline 重载脚本插入到bundle中. progress 打印进度到控制台, 之后读取webpack 配置文件

2. webpack.dev.conf.js

读取配置，根据commonjs标准 执行 
module.exports = new Promise() 该方法异步执行，首先判断端口是否被占用（portfinder），然后增加一个开发环境的插件`friendly-errors-webpack-plugin`用于 友好的错误提醒。 成功之后调用devWebpackConfig，返回一个webpack配置。 


3. dev webpack配置详情


devWebpackConfig 依赖 baseWebpackConfig， 通过使用`webpack-merge`插件进行配置文件的合并。

base

```
1. context: 入口绝对路径
2. entry: 入口在 content/src/main.js 名字是app
3. output：path,filename,publicPath(图片，文件等路径公开的url ／)
4. resolve： 解析 （extensions： 自动解析扩展名，在import时候不用带后缀；alias：import的别名，其中$,是精确匹配）
5. module-loader：预处理文件
	5.1 *.vue -> vue-loader
	5.2 *.js --> babel-loader
	5.3 images, video, fonts --> url-loader 路径使用base64编码
	5.4 *.js,*.vue --> eslint-loader， 开启测试需要预处理（pre） ，并且配置formatter

```

dev

```
1. loader: 增加css支持，并且支持postcss
2. devtool： cheap-module-eval-source-map
3. devServer： 开发服务器配置
4. plugins： 
	4.1 DefinePlugin： 定义全局变量
	4.2 HotModuleReplacementPlugin： 开启热替换模式
	4.3 NamedModulesPlugin： 开启热更替模式后，显示模块的相对路径
	4.4 NoEmitOnErrorsPlugin： 编译错误，跳过输出
	4.5 HtmlWebpackPlugin： 生成html文件
	4.6 CopyWebpackPlugin： 复制文件插件


```