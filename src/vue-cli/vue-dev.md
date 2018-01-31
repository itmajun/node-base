# Vue 开发环境解读

1. 命令 `dev` 运行开发环境

    ```
        webpack-dev-server --inline --progress --config build/webpack.dev.conf.js
    ```

    webpack-dev-server: 支持热更新, inline 重载脚本插入到bundle中. progress 打印进度到控制台, 之后读取webpack 配置文件
