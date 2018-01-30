1. install
```shell
LTS 已经内置了 npm 所以不用安装
npm install npm@latest -g

```
2. install local

```
安装到当前路径node_modules下
npm install <package_name>
npm install -g  全局安装
```

3. npm init

```
npm init --yes 创建默认package.json

```
4. dependencies, devDependencies
开发环境依赖不会打包到生产环境中.
```
npm install <package_name> --save   生产环境依赖 
npm install <package_name> --save-dev   开发环境依赖
```

5. 更新

```
npm outdated 查看是否存在更新
npm update 更新
npm update -g  更新全局包
```

6. 删除

```
npm uninstall   删除node_modules包文件
npm uninstall --save  删除dependencies
npm uninstall --save-dev 删除devDependencies
npm uninstall -g   删除全局包
```

7. version 管理 semver

```
npm install --save semver
<,>,<=,>=,=.
X,x,* [major][minor][patch]
~ [minor]存在则允许patch 改变, 不存在则允许[minor]改变
^ 版本以上都可以,^1.0.0 

```

8. 命令

```
npm build = npm run-script build  
npm link 依赖某个包,改变之后都改变
npm ls 列出所有的包依赖
```
