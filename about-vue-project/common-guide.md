### 关于Vue项目的一些约定

+ 项目的目录
```
.
├── build       # 关于构建的目录
├── config      # 关于项目的配置目录
├── hooks       # hooks目录
├── server      # 我们的模拟数据服务
├── src         # 我们主要的工作目录
├── static      # 静态资源目录
```

### 关于分支
+ `develop`分支是大家合并的分支,开发的时候我们都在自己的分支开发;等到功能开发好了之后,
   **先把`develop`分支的代码合并到自己的分支,然后把自己的分支在合并到`develop`分支**.

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

``` html
<style lang="scss" scoped>
  $red: #fa4a4a;

  .game-center {
    color: $red;
  }
</style>
```

### 关于静态资源的处理
+ `css`文件夹放置整个应用的公用样式
+ `lib`文件夹放置我们需要的类库
+ `icons`文件夹放置我们的字体文件
+ `images`文件夹放置我们的图片**图片也要分门别类的放好,划分好模块**

### 关于代码格式的约定
+ 项目的目录下面有一个`.editorconfig`文件,里面是关于我们文件格式的配置;包括缩进,换行等等
  如果你是用的是IDE的话,就不需要额外的下载插件;但是如果是`sublime text`或者是`atom`或者
  是`vs code`需要下载相应的插件来配合使用  
