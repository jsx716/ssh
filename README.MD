## git使用前配置
+ 在使用git前，告诉git你是谁，
 - 配置提交人姓名： git config --global user.name 姓名 （姓名不需要使用单引号括起来）
 - 配置提交人email： git config --global user.email 邮箱
 - 查看你刚才配置的信息 git config --list  
 - 如果想修改配置信息，只需要重复上述操作即可

## git提交步骤
- git init 初始化git仓库
- git status 查看文件状态
- git add 你想添加的文件名称
- git commit -m '提交信息' 向仓库中提交代码
- git log 查看提交日志