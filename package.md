# 收集平时用到的各种包、插件、loader

## 第三方包

### [`chalk`](https://github.com/chalk/chalk)

chalk，英译为粉笔，顾名思义可以有各种各样的颜色

用途：在终端处理字符串的颜色样式，可以链式调用

~~~ js
const chalk = require('chalk');

console.log(chalk.blue('Hello world!'));

const error = chalk.bold.red;
const warning = chalk.keyword('orange');

console.log(error('Error!'));
console.log(warning('Warning!'));
~~~

### [`semver`](https://github.com/npm/node-semver)

一个用于版本比较的包

### [`webpack-merge`](https://github.com/survivejs/webpack-merge)

webpack-merge提供了一个merge连接数组并合并创建新对象的对象的函数。如果遇到函数，它将执行它们，通过算法运行结果，然后再次将返回的值包装在函数中。

这种行为在配置webpack时特别有用，尽管它有超出它的用途。无论何时需要合并配置对象，webpack-merge都可以派上用场。

### [`opn`](https://github.com/sindresorhus/opn)

打开网站，文件，可执行文件等内容。跨平台。

~~~ javascript
const opn = require('opn');

// 在默认图像查看器中打开图像
opn('unicorn.png').then(() => {
    // 图像查看器关闭后回调
});

// 在默认的浏览器打开url
opn('http://sindresorhus.com');

// 指定要打开的应用程序
opn('http://sindresorhus.com', {app: 'firefox'});

// 指定要打开的应用程序，带参数
opn('http://sindresorhus.com', {app: ['google chrome', '--incognito']});
~~~

### express

### webpack

### webpack.DefinePlugin

### webpack.HotModuleReplacementPlugin

### webpack.NoEmitOnErrorsPlugin

### webpack.BannerPlugin

### babel-polyfill

### fetch-ie8

### ts-loader

### babel-loader

### url-loader

### http-proxy-middleware

### webpack-dev-middleware

### webpack-hot-middleware

### connect-history-api-fallback

### html-webpack-plugin

### friendly-errors-webpack-plugin

### ora

### shelljs

## Nodejs包

### child_process

### path

