# Git使用总结

## 暂存区

- ```git add <name>```
添加指定文件到暂存区
- ```git add .```  ```git add -A```
添加所有工作空间的修改到暂存区
- ```git add -u```
添加所有工作空间中对tracked file的修改到暂存区
- ```git rm --cached <file>```
把修改从暂存区中移除

## 分支

- ```git branch```
列出所有分支，前面带```*```号的为当前HEAD指向的分支
- ```git checkout [-b] <name>```
切换分支, 如果带-b，则是创建并切换分支
- ```git branch -d <name>```
删除分支
- ```git checkout <name>```
切换分支
- ```git merge <name>```
合并某分支到当前分支
- ```git log dev ^master```  ```git log dev..master```
查看dev分支有而master分支没有的提交历史，反之亦然
- ```git log --left-right dev...master```
查看两个分支的提交历史差异，这里的位置是left对应dev，right对应master，所以显示的结果中，带左箭头<的是dev分支上的提交，带右箭头的是master分支上的提交
- ```git diff <branch1> <branch2> >> diff.txt```
查看两个分支的差异
- ```git stash save -a "保存gengg"```
在切换分支前保存当前分支的更改，并让当前工作空间回到未修改状态，以避免切换到其他分支时影响其他分支， 如果不指定-a参数，那么新增文件将不会被保存
- ```git stash list```
查看stash列表
- ```git stash apply stash@{0}```  ```git stash pop stash@{0}```
回到指定的修改状态，pop与apply的区别在于pop会删除对应的stash
