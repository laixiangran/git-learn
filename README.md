# git学习笔记

[参考教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

## 常用命令

- `git init`：初始化一个Git仓库。

- `git add file`：添加文件到仓库（暂存区）。

- `git commit -m "commit a file"`：提交文件到仓库（当前分支）。`-m` 后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

- `git status`：查看当前仓库状态。

- `git diff file`：查看文件的修改内容。

- `git diff HEAD -- file`：查看工作区和版本库里面最新版本的区别。

- `git log`：查看提交日志。

- `git reflog`：查看命令运行日志。

- `git reset --hard commit_id`：回退到指定版本。用`HEAD`表示当前版本，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`，当然也可以直接写commit id。

- `git reset HEAD file`：将文件在暂存区的修改撤销掉，重新放回工作区。

- `git branch`：查看分支。

- `git branch <name>`：创建分支。

- `git branch -d <name>`：删除分支。

- `git checkout <name>`：切换分支。

- `git checkout -b <name>`：创建并切换分支。

- `git checkout -- file`：撤销文件在工作区的修改，一定记得加`--`，不然是切换分支。

- `git merge <name>`：合并某分支到当前分支。

- `git tag`：查看所有标签。

- `git tag <name>`：新建标签，默认为HEAD，也可以指定一个commit id。

- `git tag -a <tagname> -m "blablabla..."`：指定标签信息。

- `git push origin <tagname>`：推送一个本地标签。

- `git push origin --tags`：推送全部未推送过的本地标签。

- `git tag -d <tagname>`：删除一个本地标签。

- `git push origin :refs/tags/<tagname>`：删除一个远程标签。

## 分支策略

在实际开发中，我们应该按照几个基本原则进行分支管理：

首先，`master`分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活；

那在哪干活呢？干活都在`dev`分支上，也就是说，`dev`分支是不稳定的，到某个时候，比如1.0版本发布时，再把`dev`分支合并到`master`上，在`master`分支发布1.0版本；

你和你的小伙伴们每个人都在`dev`分支上干活，每个人都有自己的分支，时不时地往`dev`分支上合并就可以了。

所以，团队合作的分支看起来就像这样：

![分支策略](./cl.png)
