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

