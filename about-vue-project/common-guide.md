### 关于Vue项目的一些约定
+ 项目的目录
    - `build` 关于构建的目录
    - `config` 关于项目的配置目录
    - `hooks` hooks目录
    - `server` 我们的模拟数据服务
    - `src` 我们主要的工作目录
    - `static` 静态资源目录
------

### 模块化开发
+ 所有的组件,指令,过滤器,页面等都要划分好自己的目录;不要在一个文件夹中堆积过多的文件.
+ 目录也是按照我们的开发模块来命名

### 文件命名的约定
+ 文件名全部使用小写,多个单词以`-`链接
+ 组件名字后缀`*.component.vue`
+ 页面名字后缀`*.page.vue`
+ 过滤器名字后缀`*.filter.js`
+ 指令名字后缀`*.directive.js`
+ 模块的路由后缀`*.route.js`

### 关于JavaScript的约定
+ 能使用`ES6`的尽量使用`ES6`
+ 在`ES6`文件的头部标注`use strict`
+ 遵循的规范可以参考[JavaScript](https://github.com/XJFE/javascript)

### 关于CSS的约定
+ 命名方法使用[**BEM**](https://en.bem.info/)的命名法则,建议使用
+ 可以选择使用CSS,Less,Sass语言;建议使用Sass
+ 关于公共的类每次添加的时候都要表明好注释,说明是用于哪个部分
