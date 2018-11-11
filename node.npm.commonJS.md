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

### 模块化应用