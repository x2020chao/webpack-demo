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



## create a Bundle
1. 稍微调整目录结构，区分 __源代码（`webpack-demo/src`）__ 和 __分发代码（`webpack-demo/dist`）__
   - `source code`：由我们编写的代码
   - `distribution code`：构建输出

2. 在 `webpack-demo/src/index.js` 中绑定 `lodash`，同时需要本地安装 `lodash`
   ```bash
   # locally insall lodash
   npm install --save lodash
   ```
3. 修改 `webpack-demo/dist/index.html` 中 `<script>` 的 `src` 为 `main.js`
   > 此时为手动创建 `index.html`，使用自动创建 `index.html`，需要清空 `dist/` 并生成里边所有的内容
4. 运行 `npx webpack` 进行打包，npx 将会运行 `webpack` 二进制文件 `webpack-demo/node_modules/.bin/webpack` 把 `webpack-demo/src/index.js` 作为入口点， 生成 `webpack-demo/dist/main.js`，
   ```bash
   npx webpack
   ```
5. 此时使用浏览器打开 `webpack-demo/dist/index.html`，可以看到 `hello webpack`



## Modules
> `import` 和 `export` 声明在 `ES2015` 中标准化，现在大多数浏览器都支持，然而还是有部分浏览器不能识别这种语法，`wepback` 为它们提供了开箱即用的支持。

> 如果需要使用 `ES2015` 的其他功能，应使用 `webpack` 的加载器加载 `babel` 等



## Using a Configuration
```bash
npx webpack --config webpack.config.js
```
> 配置文件比CLI使用更具灵活性。我们可以通过这种方式指定加载程序规则、插件、解析选项和许多其他增强功能。  



### NPM Scripts
调整 `package.json`，使用 `scripts`
```bash
## 可以替换 npx webpack
npm run bulid
```