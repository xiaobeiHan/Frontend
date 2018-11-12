### 相关概念
1. 浏览器V8引擎
> 首先，js是解释型语言，没有预编译，是需要边解释边执行的；

> 浏览器中的渲染引擎里面包括 jsCore 或者 浏览器V8引擎，作为js执行环境，用于解释和执行js；
2. Node.js
> 是一种js的运行环境，能够使得js脱离浏览器运行，可以进行服务端的js处理；

> 故，node是一个基于Chrome V8引擎运的服务端运行环境；

> nodejs应用的组成：a 使用require指令载入nodejs模块；b 创建服务器，监听客户请求，类似于http服务器； c 响应请求；
3. npm
> npm是随同node一起安装的包管理工具（node package manager）；

> 允许用户从npm服务器下载第三方包到本地使用；
4. commonJS
> node由模块组成，采用commonJS模块规范；

### 模块化的细节
> 阮一峰老师的详细讲解地址： http://javascript.ruanyifeng.com/nodejs/module.html；

> 我的理解：
- 每个模块内部，module变量是一个对象，代表当前模块；其 exports属性 是对外的接口；当我们加载某个模块的时候，其实是加载的它的 module.exports 属性；
- require方法用于加载模块： var example = require('./example.js');
- 

### node模块化应用

1. 创建package.json文件

> npm init 命令可以创建package.json文件; 文件中的dependencies:{} 就是将要安装的包；

> （这样就可以在拷别人代码的时候，不拷node_modules文件夹，只要有其package.json文件 即可；）；

2. 生成node_modules文件夹

> npm install 命令会生成node_modules文件夹以及下面各种安装包；

3. 如何安装node模块？安装到了哪里？

> npm安装nodejs模块： npm install <模块名>； 就会讲模块安装到 ./node_modules （当前目录是运行命令时候的目录）目录下；

> 更新nodejs模块： npm update  <模块名>；

> 注意：引用包的时候，可以写包的相对路径； 或者不写路径： 就会首先在本项目的node_modules文件夹中寻找；
> 如果，连js文件扩展名都不写：require("people"); 就会寻找people文件夹， 然后加载其下面的index.js
> 或者如果该文件夹下存在package.json文件，就会找文件中 main: "xxx.js" 这个文件；
