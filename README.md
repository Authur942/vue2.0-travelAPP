# vue2.0-travel

## 技术栈 vue + vue-router + axios + vuex


> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## 项目目录结构
***
```
vue2.0-travel
├── build
│   ├── build.js
│   ├── check-versions.js
│   ├── logo.png
│   ├── utils.js
│   ├── vue-loader.conf.js
│   ├── webpack.base.conf.js
│   ├── webpack.dev.conf.js
│   └── webpack.prod.conf.js
├── config
│   ├── dev.env.js
│   ├── index.js
│   └── prod.env.js
├── index.html
├── package-lock.json
├── package.json
├── README.md
├── src
│   ├── App.vue
│   ├── assets
│   ├── main.js
│   ├── pages
│   └── router
└── static
    └── mock
```
*** 
## 项目初始化
* 配置meta标签
* 初始化默认样式
* 解决1像素边框方案
* 引入fastclick库
* 配置使用iconfont
* 自定义目录

**第一步 配置meta标签**

index.html里加个 meta 标签:`<meta name="viewport"content="width=device-width,initial-scale=1.0, minimum-scale=1.0,maximum-scale=1.0,user-scalable=no">`

复制代码在网页的标签中增加以上代码，可以让网页的宽度自动适应手机屏幕的宽度。 其中： width=device-width ： 表示宽度是设备屏幕的宽度 initial-scale=1.0 ： 表示初始的缩放比例 minimum-scale=1.0 ： 表示最小的缩放比例 maximum-scale=1.0 ： 表示最大的缩放比例 user-scalable=no ： 表示用户是否可以调整缩放比例 以上我设置的参数的目的是：想要一打开网页，就自动以原始比例显示，并且不允许用户修改，不允许用户缩放。

**第二步 初始化默认样式**

在不同的手机浏览器上，默认的一些样式是不同统一的。我们需要把这些不同手机的初始化样式做一个统一。

所以可以引入个 reset.css
这是一个初始化的代码，其中一些初始化配置可以自行根据需求修改。

**第三步 解决1像素边框方案**

在移动端页面开发，常常有个 1像素边框 的问题。 也就是有的手机屏幕分辨率比较高，如果我们在页面上写border-bottom啥的样式，会导致这些手机屏幕分辨率高的当中，1px边框显示成2px边框或3px边框等显示成多像素。 为了解决这个1像素边框问题，我们就引入了 border.css

具体这个解决方案的用法，看过border.css代码的同志就会发现很简单：在元素上根据想要的需求加以下这些类名。 

按照字面意思理解就行。 比如要给一个元素加上一像素的下边框，就直接加个类名：`<div class="border-bottom>"`就行了。 要给一个元素加上一像素的上边框和下边框，就直接加类名：`<div class="border-topbottom">`就行了。

**第四步 引入fastclick库**

在移动端开发中，某些机型、某些浏览器上，click点击事件要延迟300ms执行。 要解决这个问题，我们引入个fastclick库 `npm install fastclick --save` --save的意思是：不管在开发环境测试，还是线上跑代码，安装了的库都可以使用。并且下载好后，自动存到package.json的dependencies属性中，比如这里install的fastclick：

然后在入口函数main.js中引入和使用：

`import fastClick from 'fastclick'、 fastClick.attach(document.body)`

**第五步 配置使用iconfont**

先在[阿里巴巴矢量图标库](https://www.iconfont.cn/)创建一个项目

然后在iconfont上选购，添加到购物车，选好后添加到自己的项目，然后下载到本地。

下载的东西中只要用到这几个：  然后把iconfont.css放到一个文件夹中并且在入口函数main.js处引入后就可以全局使用了。

举个使用的例子:  注意类名要加iconfont，然后这里在span里输入的代码就是你选中的图标的代码： 

**第六步 自定义目录**

这样有配置后就可以使用自定义目录了。比如按照我上面的配置的话`import src/assets/styles/border.css`就可以写成`import styles/border.css`了。