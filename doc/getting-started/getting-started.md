## Getting-start
`webpack` 用于编译 `javascript` 模块

## Basic Setup
```bash
mkdir webpack-demo # 创建目录
cd webpack-demo
npm init -y # 初始化 npm
npm install webpack webpack-cli --save-dev # locally install webpack
```
> [`installation`](../installation/installation.md)  

> `webpack-demo/src/index.js` 依赖 `lodash`；它假设全局变量 `_` 存在，没有明确地声明对 `lodash` 的依赖

### 问题
1. 脚本是否依赖于外部库不明显
2. 如果缺少依赖项或包含在错误的顺序中，则应用程序将无法正常运行
3. 如果包含依赖项但未使用，浏览器将被迫下载不必要的代码