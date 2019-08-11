# Git 学习记录
## Git 简介
Git是一个分布式的版本管理工具，所有的开发者在本地都拥有一个完整的版本库。
借助远程仓库，合作开发者可以向远程仓库上传改动文件，并从远程仓库获得最新的版本库文件。
## Git 基本命令
`git init` :在本地当前路径下创建新的库。\
`git add`:将工作区指定文件添加到缓存区。\
`git commit -m [message]`:将缓存区的文件上传至当前分支,message为本次修改记录。\
`git diff`:比较工作区与缓存区，或工作区与仓库文件（工作区空时）。\
`git status`:查看当前缓存区的状态。\
`git reset --hard HEAD~[num]`:将版本退回至倒数第num个版本。\
`git reset --hard <commit_id>`:将版本退回到指定commit_id位置。\
`git reset HEAD <filename>`:把缓存区的修改撤销，重新放回工作区。\
`git reflog`:查看每一次命令，可以用来查看每次操作的id。\
`git log --pretty=oneline`:查看提交历史记录, oneline可以简化输出格式。\
`git rm <filename>`:本地文件删除后，执行该命令，然后执行commit，可以删除版本库中的文件。\
`git checkout -- <filename>`: 更改撤销，恢复至缓存区（若有）或版本库的状态。\
## Git 分支与合并 
-  当只有一条线时，master 指向最新提交，HEAD指向master,每次提交，master移动一次。
-  当创建新的分支时，git新建一个指针指向master，然后head指向这个新分支，每次提交时，新分支的指针向前移动一步，而master的指针位置不变。
-  当在新分支的任务完成时，需要将新分支merge到master上，可以直接将master的指针指向新分支的最新提交，然后删除旧分支，合并完成，只剩下了master分支,同时将HEAD指向master。
## Git 分支与合并相关命令
`git checkout -b <branch>`:创建新分支，并切换至新分支。\
`git branch <branch>`:创建新分支，但不切换至该分支。\
`git checkout <branch>`:切换至某分支。\
`git branch`:查看当前分支。\
- 
## Git 远程仓库
github是支持git操作的远程仓库。通过SSH协议，可以实现本地与远程仓库的通信。将本地生成的SSH公钥复制到个人github账户的SSH通讯录中，即可实现本地上传及远程下载。
## Git 远程操作相关命令
`git remote add origin git@github.com:<user_name>/<repo_name>.git`:将远程仓库与本地的仓库建立关联。远程库的名字之后就叫做origin。\
`git push -u origin master`:将本地库的所有内容推送到远程库上, -u参数会让本地master和远程master建立关联，以后的推送就可以简化命令。\
`git clone git@github.com:<user_name>/<repo_name>.git`:从远程仓库克隆到本地。\
