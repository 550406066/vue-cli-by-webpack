# vue-cli-by-webpack
##初始化项目

- npm init -y（-y默认安装）
##安装webpack

- npm install --save-dev webpack

##配置webpack

### 1.创建webpack.config.js ###
在根目录下创建webpack.config.js
    `const path = require('path')

    module.exports ={
	    entry:'./dev/main.js',
	    output:{
	    path:path.resolve(__dirname,'dist'),
	    filename:"js/main.js"
	    }
    }

项目目录如下:


![项目目录](https://i.imgur.com/geetyv5.png)

之后再目录下输入webpack --mode development进行打包
![打包结果](https://i.imgur.com/Fg5vsfP.png)

###2.引入一系列的依赖和loader###
- 安装vue

 `npm install --save vue`

- 安装vue-loader

`npm install --save-dev vue-loader vue-template-compiler`

- 安装babel-loader

 `npm install --save-dev babel-core babel-loader`

- 安装css-loader

`npm install --save-dev css-loader style-loader`

- 安装url-loader
> （vue-cli中有安装，会将小于限制的文件改成base64格式直接传入src里面，可以降低网络请求次数）

`npm install --save-dev file-loader url-loader`

- 安装sass-loader

 `npm install --save-dev node-loader sass-loader`
###3.常用插件###

- HtmlWebpackPlugin 
>(主要用于生成HTML，可以规定 模板HTML，也可以为 模板传入参数，压缩文件等）

`npm install --save-dev html-webpack-plugin`

- webpack-dev-server 
>(webpack-dev-server 为我们提供了一个简单的web服务器，并且能够实时重新加载（live reloading)



**到此基本完成vue-cli的功能，之后会加上判断环境和压缩代码的抽离，以及对js的压缩**

- 具体内容可以看源码

##判断环境和压缩代码
- 安装cross-env

 `npm install --save cross-env`
>在package.json中的dev改为： "dev": "cross-env NODE_ENV=development webpack-dev-server --hot-only --open",

之后在webpack.config.js中加上判断对NODE_ENV的判断

效果如图：

生产环境：
<hr>
![判断环境](https://i.imgur.com/KDtDr7H.png)

开发环境：
<hr>
![判断环境](https://i.imgur.com/MreQQVy.png)

- 拷贝静态资源地址

 `npm i -D copy-webpack-plugin`


**后面会再加上公共代码的抽离，和代码的封装**
