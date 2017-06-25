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

- `git reset --hard commit_id`：回退到指定版本。用`HEAD`表示当前版本，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。当然也可以直接写版本号。

- `git reset HEAD file`：将文件在暂存区的修改撤销掉，重新放回工作区。

- `git checkout <name>`：切换分支。

- `git checkout -- file`：撤销文件在工作区的修改，一定记得加`--`，不然是切换分支。
