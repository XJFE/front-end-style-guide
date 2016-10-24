# 后面模拟的一些规范

## Mock 目录

```
.
├── server        # 我们的模拟数据服务
    ├── app.js    # 启动脚本
    ├── mocks     # 模拟数据目录
        ├── home  # 首页接口
        ⎪   ├── data.json  # 具体的接口数据
        ├── user  # 用户模块接口
        ⎪   ├── data.json  # 具体的接口数据
        ├── game  # 游戏中心接口
            ├── data.json  # 具体的接口数据

```

## Mock JSON 语法

 [Mock.js 0.1 文档](https://github.com/nuysoft/Mock/wiki)  
 [Mock示例](http://mockjs.com/examples.html)  


## data.json 文件数据规范

虽然语法是 `Mock JSON 语法` 但这不是真正的 `json` 文件，因为我们需要定义接口地址，接口说明，参数说明等消息。
例如，有个 `./server/mocks/user/list.json` 文件，内容如下。

``` js
/**
 * 用户列表接口 v1
 *
 * @url /user-list
 *
 * 参数说明：
 * uid: 用户ID
 * name: 用户名
 * email: 邮箱
 */

{
  "code": 10000,
  "result|5": [
    {
      "uid|+1": 1,
      "name": "@cname",
      "email": "@email"
    }
  ]
}
```

其中 `@url` 是接口地址，也就是最终访问的地址，例如 `http://localhost:8001/api/user-list`。
如果省略 `@url` 参数，则默认使用文件名作为地址 `http://localhost:8001/api/list` **这是非常不推荐的做法**。

生成数据如下:

``` js
{
  "code": 10000,
  "result": [
    {
      "uid": 1,
      "name": "万艳",
      "email": "p.jcoubia@kgwkefkuq.kh"
    },
    {
      "uid": 2,
      "name": "白静",
      "email": "p.qkkgw@qjcjk.ge"
    },
    {
      "uid": 3,
      "name": "林强",
      "email": "e.mhfxt@tndrqs.et"
    },
    {
      "uid": 4,
      "name": "史洋",
      "email": "m.bospd@juxgtua.ky"
    },
    {
      "uid": 5,
      "name": "石强",
      "email": "j.pjoisdd@wosjn.qa"
    }
  ]
}
```


## 占位图使用

对于图片上传接口，推荐使用占位图接口。
例如对 `http://localhost:8001/api/upload-img` 上传图片，并且返回多个格式的图片，可以定义如下接口。
数据文件路径：`./server/mocks/upload/img.json`，内容为：

``` js
/**
 * xx模块图片上传接口 v1
 *
 * @url /upload-img
 *
 * 参数说明：
 * uid: 用户ID
 * name: 用户名
 * email: 邮箱
 */

{
  "code": 10000,
  "result": {
    "size1": "/img/300x200", // 300x200 的图
    "size2": "/img/300x200/360/fff", // 300x200 的图，背景色360，字体颜色fff
    "size3": "/img/300x200/360/fff?text=图片说明" // 300x200 的图，背景色360，字体颜色fff，图片内容为 '图片说明'
    "size4": "/img/300?text=图片说明" // 参数可以省略，300x300 的图，背景色eee，字体颜色aaa，图片内容为 '图片说明'
  }
}
```

占位图接口是在 `http://localhost:8001/img/` 路径下，当然可以在配置里修改。
