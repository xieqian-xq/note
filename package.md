# 收集平时用到的各种包、插件、loader

## **第三方包**

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

先科普：`npm` 采用`语义版本`管理软件包。所谓语义版本，就是指版本号为`a.b.c`的形式，其中a是大版本号，b是小版本号，c是补丁号。

再介绍：semver，semantic versioner，正是一个对语义版本处理的包。

~~~ js
const semver = require('semver')

// 返回解析后的版本，如果无效，则返回null
semver.valid('1.2.3') // '1.2.3'
semver.valid('a.b.c') // null
semver.clean('  =v1.2.3   ') // '1.2.3'
// 是否满足条件
semver.satisfies('1.2.3', '1.x || >=2.5.0 || 5.0.0 - 7.2.3') // true
// 比较
semver.gt('1.2.3', '9.8.7') // false
semver.lt('1.2.3', '9.8.7') // true
// 将字符串强制转换为semver
semver.valid(semver.coerce('v2')) // '2.0.0'
semver.valid(semver.coerce('42.6.7.9.3-alpha')) // '42.6.7'
~~~

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

// google chrome on macOS
// google-chrome on Linux
// chrome on Windows

~~~

### [`ora`](https://github.com/sindresorhus/ora)

优雅的终端微调器，一个用于命令行的loadding。

~~~ js
const ora = require('ora');

const spinner = ora('Loading unicorns').start();

setTimeout(() => {
    spinner.color = 'yellow';
    spinner.text = 'Loading rainbows';
    spinner.succeed("succeed")
    spinner.fail("fail")
    spinner.warn("warn")
    spinner.info("info")
}, 1000);
~~~

### [`shelljs`](https://github.com/shelljs/shelljs)

Node.js的Unix shell命令

~~~ js
var shell = require('shelljs');

// 删除文件 -r 递归 -f强制
shell.rm('-rf', '/tmp/*');
shell.rm('some_file.txt', 'another_file.txt');
shell.rm(['some_file.txt', 'another_file.txt']);

// 创建文件夹 -p 完整路径（并在必要时创建中间目录）
shell.mkdir('-p', '/tmp/a/b/c/d', '/tmp/e/f/g');
shell.mkdir('-p', ['/tmp/a/b/c/d', '/tmp/e/f/g']);

// 复制文件
shell.cp('file1', 'dir1');
shell.cp('-R', 'path/to/dir/', '~/newCopy/');
shell.cp('-Rf', '/tmp/*', '/usr/local/*', '/home/tmp');
shell.cp('-Rf', ['/tmp/*', '/usr/local/*'], '/home/tmp');

// 是否禁止echo()输出，默认false
shell.config.silent = true;
~~~

### [`babel-polyfill`](https://github.com/babel/babel/tree/master/packages/babel-polyfill)

ie9和一些低版本的高级浏览器对es6新语法并不支持，所以需要引入`babel-polyfill`。

~~~ js
// 第一种
require("babel-polyfill");

// 第二种
import "babel-polyfill";

// 第三种
module.exports = {
　　entry: ["babel-polyfill", "./app/js"]
};
// 关于兼容的问题，这并不是最优解决方案，还需要再研究babel才行。
~~~

### [`fetch-ie8`](https://github.com/camsong/fetch-ie8)

+ fetch兼容性，支持IE10+、谷歌、火狐等
+ 引入一个额外的补丁es6-promise.js可以使它很好的支持IE9以上的版本
+ `fetch-ie8`就是为了解决window.fetch在IE8的兼容问题

### [`webpack-merge`](https://github.com/survivejs/webpack-merge)

`webpack-merge`提供了一个`merge`连接数组并合并创建新对象的对象的函数。如果遇到函数，它将执行它们，通过算法运行结果，然后再次将返回的值包装在函数中。

这种行为在配置`webpack`时特别有用，尽管它有超出它的用途。无论何时需要合并配置对象，`webpack-merge`都可以派上用场。

### [`connect-history-api-fallback`](https://github.com/bripkens/connect-history-api-fallback)

通过指定索引页面代理请求的中间件，对使用HTML5 History API的单页应用程序很有用。
