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

八、远程同步

# 下载远程仓库的所有变动
$ git fetch [remote]

# 显示所有远程仓库
$ git remote -v

# 显示某个远程仓库的信息
$ git remote show [remote]

# 取回远程仓库的变化，并与本地分支合并
$ git pull [remote] [branch]

# 上传本地指定分支到远程仓库
$ git push [remote] [branch]

九、撤销

# 恢复暂存区的指定文件到工作区
$ git checkout [file]

# 恢复某个commit的指定文件到暂存区和工作区
$ git checkout [commit] [file]

# 恢复暂存区的所有文件到工作区
$ git checkout .

# 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
$ git reset [file]

# 重置暂存区与工作区，与上一次commit保持一致
$ git reset --hard

# 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变
$ git reset [commit]

# 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致
$ git reset --hard [commit]

# 重置当前HEAD为指定commit，但保持暂存区和工作区不变
$ git reset --keep [commit]

# 新建一个commit，用来撤销指定commit
# 后者的所有变化都将被前者抵消，并且应用到当前分支
$ git revert [commit]

# 暂时将未提交的变化移除，稍后再移入
$ git stash
$ git stash pop
