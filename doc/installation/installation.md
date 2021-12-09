## installation
> 运行 `webpack5` 的最低 `node.js` 版本为 `10.13.0 (LTS)`, 理想的版本为当前的 `node.js LTS` 版本


## local installation __推荐__
```bash
npm install --save-dev webpack
### webpack4 or later 
### want to call webpack from the command line need to install the CLI
npm install --save-dev webpack-cli 
```
配置如下 `npm scripts` 可以在目录下查找 `webpack` 安装
```json
"scripts": {
    "build": "webpack --config webpack.config.js"
}
```


## global installation __不推荐__
> 全局安装会锁定 `node` 版本，可能对其他项目有影响
```bash
npm install -g webpack
```


## bledding edge (beta version)
> 注意：测试版本可能会有 `bug`
```bash
npm install --save-dev webpack@next
```