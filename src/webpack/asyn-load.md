# 异步加载
---
webpack 打包时候可以把一个块打包成一个js, 需要的话就加载, 不需要就不加载,避免了首页一下子加载几M的文件.

```
const home = r => require.ensure([], () => r(require('../page/home/home')), 'home')
```
**该语法至今没有看懂 - -!**
