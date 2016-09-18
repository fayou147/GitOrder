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
![image](https://github.com/fayou147/GitOrder/blob/master/image/0.jpg)