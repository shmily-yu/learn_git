# 初始化一个Git仓库，使用git init命令。

# 添加文件到Git仓库，分两步：
# 使用命令git add <file>，注意，可反复多次使用，添加多个文件；
# 使用命令git commit -m <message>，完成。

# 要随时掌握工作区的状态，使用git status命令。
# 如果git status告诉你有文件被修改过，用git diff可以查看修改内容。
# git diff  顾名思义就是查看difference

# git log命令显示从最近到最远的提交日志 
# 如果嫌输出信息太多，可以试试加上--pretty=oneline参数：

# 在Git中，用HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版 本写100个^比较容易数不过来，所以写成HEAD~100。
# git reset --hard HEAD^ 回退到上一个版本

# Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。版本号没必要写全，前几位就可以了

# 找不到新版本的commit id怎么办? Git提供了一个命令git reflog用来记录你的每一次命令

# 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
# 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

# 工作区（Working Directory）就是你在电脑里能看到的目录
# 工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。
# Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。
# 第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；
# 第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。
# 你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。

# 每次修改，如果不用git add到暂存区，那就不会加入到commit中

