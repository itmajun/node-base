# node.Js
---
Node.js 运行环境 建立在V8 引擎之上, 使用event-driven , non-blocking I/O 模型. 特别要指出的就是
npm 是目前最大的生态环境.

# node.js 与 javascript

javascript 目前由 ECMA 进行规格和标准的制定.
刚开始接触js的时候并不了解那个时候什么标准, ECMAScript 2015 (ES6) 开始才发现市面上开始都鼓励使用
ES6语法. 现在到了ECMA2018了. 不过市面上还是ES6作为 前端开发的基础在推广.

目前V8引擎之上的Chrome浏览器成为了前端标配. 而建立在V8之上的NodeJS也成了服务端的标配.(font-end)

这里就有些概念容易混淆,V8 是C++ 编写的javascript 运行环境, 就相当于 java与jvm. 在浏览器中,我们熟知的
DOM.BOM.javascript. 这三者搭配呈现了html web. 而在服务器node环境提供, 系统 + javascript
提供了io/os/file/net/db等操作.

# npm

其实我并不需要用nodejs编写服务端程序, 之所以了解下nodejs 主要是npm 这个包管理工具. 就相当于了解java常用的包
一样, 服务器端在编写ES6语法时候会依赖很多其他js. 最后混淆,打包成我们需要的js 文件.

