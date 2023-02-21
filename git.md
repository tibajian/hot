# git 安装初始化
```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
// 查看
git config user.name
```
# git 创建仓库与本地链接
```
git init
git add -A
git commit -m 'change one'
git remote add origin git@github.com:xxx/xxx.git
git push -u origin main

// git remote -v
// git remote rm origin
// git log
// git status
// git branch
// git reset --hard HEAD^ --回退版本
// git diff HEAD -- readme.txt --查看diff
// git reflog --查看命令记录
// git checkout -- readme.txt --撤销修改
// git rm a.txt --删除
```
# 克隆
```
git clone git@github:xxx/xxx.git

```
# 分支创建与合并
```
git branch dev
git checkout dev | git switch <name>
// git checkout -b dev  | git switch -c <name> --创建并切换分支
git branch --查看分支
git merge dev --合并指定分支(dev)到当前分支(main)
git branch -d dev --删除分支
git branch --set-upstream-to branch-name origin/branch-name  --建立本地分支和远程分支的关联，使用
```
# 合并冲突
```
git log --graph  --命令可以看到分支合并图
git stash  --把当前工作现场“储藏”起来，等以后恢复现场后继续工作
git stash apply  --恢复之前的工作，不删除stash内容
git stash pop  --恢复之前的工作，并删除stash内容
// git stash list
// git stash apply stash@{0}  --恢复之前指定的工作
// git cherry-pick <commit>      --在master分支上修复的bug，想要合并到当前dev分支，把bug提交的修改“复制”到当前分支，避免重复劳动。

1. main(发布) dev(开发) feature(新功能) bug 三个分支， 因此将bug分支提交到main和dev
```
