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
