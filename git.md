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
# git reset HEAD <file>可以把暂存区的修改撤销掉（unstage），重新放回工作区

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

# 命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。总之，就是让这个文件回到最近一次git commit或git add时的状态。

# git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令，

# 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

# 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

# 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

# 命令git rm用于删除一个文件。

# 可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人

# 把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。

# 由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

# 要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；

# 关联后，使用命令git push -u origin master第一次推送master分支的所有内容；

# 此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

# Username for 'https://github.com': 输入的是github上的邮箱账号, 而不是github中设置的username, 这是个巨坑!!!
# Password for 'https://你的github邮箱@github.com': 输入github的登录密码,点击enter键即可.

# git clone克隆一个本地库：

# Ctrl  +ins  复制
# Shift +ins  粘贴

# 查看分支：git branch

# 创建分支：git branch <name>

# 切换分支：git checkout <name>或者git switch <name>

# 创建+切换分支：git checkout -b <name>或者git switch -c <name>

# 合并某分支到当前分支：git merge <name>

# 删除分支：git branch -d <name>  
# 删除分支：git branch -d <name>

# 当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
# 解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容，再提交。
# 用git log --graph命令可以看到分支合并图
