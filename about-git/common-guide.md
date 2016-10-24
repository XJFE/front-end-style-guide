### 项目git分支操作的流程(以`webstrom`为例子)

+ 首先把项目克隆下来

```
    git clone https://github.com/XJFE/front-end-style-guide.git
```

+ 切换到大家公共提交的分支(以`master`为例子)

+ 在公共的分支上新建一个分支作为自己的工作分支(以`dev-name`为例子),然后把我们刚才新建的这个分支同步到远程的服务器上,也就是提交当前的代码
  `git commit`然后是`git push`
  
+ 然后在自己的分支上做修改,修改完成后,把修改提交到自己的远程分支上去也就是`origin/dev-name`分支上

+ 切换到`master`分支,拉取最新内容`git pull`

+ 切换到自己的分支`dev-name`,然后把`master`的内容合并到我们自己的分支上`dev-name`.

+ 然后把这次的改动提交到自己的远程分支上`origin/dev-name`.

+ 切换到`master`分支上,把`dev-name`分支的内容合并到`master`上。然后提交到远程的`origin/master`分支。

+ 切换回自己的分支。