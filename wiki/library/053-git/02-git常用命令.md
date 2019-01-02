### 一、新建代码库

### 克隆或新建
```shell
git init
git init --bare
git clone [url]
```

### 增加
```shell
git add -A
```

### 代码提交
```shell
git commit -m [message]
```

### 分支
```shell
git branch
git branch -a
git checkout -b [branch]          //新建一个分支，并切换到该分支
git checkout [branch-name]        //切换到指定分支，并更新工作区
git merge [branch]                //合并指定分支到当前分支
git branch -d [branch-name]       //删除分支
git branch -dr [remote/branch]    //删除远程分支
```

### 查看信息
```shell
git status    //显示有变更的文件
git log       //显示当前分支的版本历史
```

### 远程同步
```shell
git pull [remote] [branch]    //取回远程仓库的变化，并与本地分支合并
git push [remote] [branch]    //上传本地指定分支到远程仓库
```

### 撤销
```shell
git reset --hard    //重置暂存区与工作区，与上一次commit保持一致
$ git stash
$ git stash pop    //暂时将未提交的变化移除，稍后再移入
```
