# GitOrder
git 命令的收集以及总结

## git操作指令

### 版本回退
 1. git reflog   ——记录你的每一次命令
 2. git reset --hard HEAD^    ——回退到上一个版本
 3. git reset --hard 3628164  ——回到你想要的版本
 4. git log -n 1 --stat       ——查看修改的文件

总结一下：

HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

### 工作原理

 1. 工作区（Working Directory）   ——就是你在电脑里能看到的目录，比如我的GitOrder文件夹就是一个工作区
 2. 版本库（Repository）   ——工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库
 3. 版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。
 ![image](https://github.com/fayou147/GitOrder/blob/master/image/0.jpg)

 总结一下：

 git add把文件添加进去，实际上就是把文件修改添加到暂存区

 git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支（默认就是Git为我们自动创建的第一个分支master）

### 撤销修改

 1. 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

 2. 当你不但改乱了工作区某个文件的内容，还git add了到暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

 3. 已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退，不过前提是没有推送到远程库。

### 分支管理

 1. 查看分支：git branch

 2. 创建分支：git branch < name >

 3. 切换分支：git checkout < name >

 4. 创建+切换分支：git checkout -b < name >

 5. 合并某分支到当前分支：git merge < name >

 6. 删除分支：git branch -d < name >

 每次commit，分支都会向前移动一步，这样，随着你不断提交，分支的线也越来越长
  ![image](https://github.com/fayou147/GitOrder/blob/master/image/QQ图片20160918173126.png)

 当我们创建新的分支，例如dev时，Git新建了一个指针叫dev，指向master相同的提交，再把HEAD指向dev，就表示当前分支在dev上 

  ![image](https://github.com/fayou147/GitOrder/blob/master/image/1.png)

 从现在开始，对工作区的修改和提交就是针对dev分支了，比如新提交一次后，dev指针往前移动一步，而master指针不变：

  ![image](https://github.com/fayou147/GitOrder/blob/master/image/2.png)




![image](https://github.com/fayou147/GitOrder/blob/master/image/Git-Cheat-Sheet-by-RebelLabs.png)
