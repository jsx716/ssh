## git使用前配置
+ 在使用git前，告诉git你是谁，
 - 配置提交人姓名： git config --global user.name 姓名 （姓名不需要使用单引号括起来）
 - 配置提交人email： git config --global user.email 邮箱
 - 查看你刚才配置的信息 git config --list  
 - 如果想修改配置信息，只需要重复上述操作即可

### git提交步骤
- git init 初始化git仓库
- git status 查看文件状态
- git add 将文件提交到暂存区中
- git commit -m '提交信息' 将文件存储到仓库中
- git log 查看提交日志

### 撤销操作
- 使用缓存区中的文件覆盖当前目录中的文件 git checkout 文件名
- 从缓存区中删除文件，不想提交到git中了 git rm --cached 文件名
- 从git仓库中恢复到原来提交的文件 git reset --hard commitID
 + 如何找到commitID  git log 通过提交日志可以找到这个commitID
 
## git分支
- 当一个项目太过复杂时，可以使用分支进行分别开发，最后在进行合并，相当于UG当中的图层
- 主分支-开发分支-具体功能分支
- git branch 查看分支
- git branch 分支名称 创建分支
- git checkout 分支名称 切换分支 （切换分支是一定要将分支当中的任务进行commit了才可以）
- git merge 来源分支 合并分支 
- git branch -d 分支名称 （分支合并之后才可以进行删除）（-D强制删除）

## 暂时保存分支上的修改
- 当你想切换分支时，你又不想对文件进行commit提交，因为这个分支的任务还没有完成
 + 临时切换分支
 + git stash 存储临时改动
 + git stash pop 回复改动
 
 # github远程推送管理，多人开发
 - 注意： 再进行远程推送之前，一定要先进性本地提交commit之后才可以
 - 目的：就是将本地仓库的内容提交到远程仓库
 - git push https://...(远程提交的网址) master（提交的分支名称）
   +　这个提交地址太长了，可以为提交地址起个别名
   + git remote add origin(别名，你起什么名称都可以， 一般叫做origin) https://...(远程的网址)　
   
 - 下次提交就可以使用 git push origin master(分支名称)
 - 但是这样还是比较麻烦，我们想直接使用 git push 进行提交如何做到呢： 
  + 设置 git push -u origin master 之后，就可以直接使用 git push 进行提交了
  
## 密钥配对，不需要每次输入密码才可以push
- 运行 ssh-keygen 生成密钥
- 密钥存储目录 c:/用户/jiashixing/.ssh文件夹中
- id_rsa 保存在自己电脑上
- id_rsa.pub 打开文件，复制里面的代码到github账户上