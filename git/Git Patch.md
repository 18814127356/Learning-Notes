###  Git Patch

#### 生成patch

```git format-patch  0d8013```

这条命令会生成自commit(0d8013)以后（不包括这个commit本身）的所有commit的patch，每个commit会生成一个patch文件

#### 应用patch
##### 方式一
```git apply xxx.patch```

这条命令会把该patch应用用到当前分支上，所有应用的更改都在工作区（因此需要先加到暂存区再提交）

##### 方式二
```git am xxx.patch```

这条命令会把该patch应用到当前分支上，打完后当前分支直接就会多出来一个commit

> **注意: **```git apply```与```git am```的区别是，```git apply```并不会将```commit message```等打上去，打完patch后需要重新```git add```和```git commit```，而```git am```会直接将patch的所有信息打上去，而且不用重新```git add```和```git commit```,```author```也是```patch```的```author```而不是打```patch```的人


#### 工具方法
```git apply --stat xxx.patch```
查看patch的情况

```git apply --check xxx.patch```
检查patch是否能够打上，如果没有任何输出，则说明无冲突，可以打上

```git am --abort```
当git am失败时，用以将已经在am过程中打上的patch废弃掉(比如有三个patch，打到第三个patch时有冲突，那么这条命令会把打上的前两个patch丢弃掉，返回没有打patch的状态)

```git am --resolved```
当git am失败，解决完冲突后，这条命令会接着打patch

#### 解决冲突
- 根据```git am```失败的信息，找到发生冲突的具体```patch```文件，然后用命令```git apply --reject <patch_name>```，强行打这个patch，发生冲突的部分会保存为```.rej```文件（例如发生冲突的文件是```a.txt```，那么运行完这个命令后，发生conflict的部分会保存为```a.txt.rej```），未发生冲突的部分会成功打上patch
- 根据```.rej```文件，通过编辑该patch文件的方式解决冲突。
-  废弃上一条```am```命令已经打了的```patch```：```git am --abort```
- 重新打```patch```：```git am ~/patch-set/*.patchpatch```
