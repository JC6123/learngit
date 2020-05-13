# This is a readme file

<center>From JC6123</center>

## Git库的创建和文件修改

1. 初始化一个Git仓库，使用`git init`命令。

2. 添加文件到Git仓库，分两步：

>+ 使用命令`git add <file>`，注意，可反复多次使用，添加多个文件；\
>+ 使用命令`git commit -m <message>`，完成。

3. 使用`git status`查看工作区状态，是否发生过文件修改。

4. 使用`git diff`查看文件修改的差异。

>每当你觉得文件修改到一定程度的时候，就可以“保存一个快照”，这个快照在Git中被称为`commit`。

5. 版本更替：

>+ `HEAD`指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令`git reset --hard commit_id`。 `HEAD^^`指的是上上个版本；`HEAD~100`指的就是前100个版本\
>+ 穿梭前，用`git log`可以查看提交历史，以便确定要回退到哪个版本。\
>+ 要重返未来，用`git reflog`查看命令历史，以便确定要回到未来的哪个版本。

6. 丢弃当前的修改：

>+ 当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- file_name`。\
>+ 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD file_name`，就回到了场景1，第二步按场景1操作。

7. 命令`git rm file_name`用于删除一个文件（还需要`git_commit`）。如果一个文件已经被提交到版本库，那么你永远不用担心误删。如果误删的话，可以用`git checkout -- file_name`恢复，但是要小心，你只能恢复文件到最新版本，将丢失历史记录。

## 远程库管理

8. 要关联一个远程库，使用命令`git remote add origin "git@server-name:path/repo-name.git"`；
关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；

9. 使用`git clone git@github.com:michaelliao/gitskills.git`克隆远程库
