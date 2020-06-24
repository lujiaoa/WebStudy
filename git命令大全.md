# 然哥：git命令大全

###### 在cmd中检查git版本号的命令   git --version

##### ①：把项目文件夹变为本地git的操作空间

​	git初始化，对于一个项目只需要初始化一次。

\# 设置你的用户名 

```` git
git config --global user.name "你的姓名" 
````

#设置你的邮箱地址 

````git
git config --global user.email "你的邮箱地址"
````

#重置你的用户名或密码

~~~~git
 git config --global --replace-all user.name "你的 git 的名称"
~~~~



查看配置信息列表

~~~~git
git config --list        
~~~~

常用命令

~~~~git
q  #退出命令
clear  #清屏
~~~~

##### ②：把文件加入到暂存区

~~~~
git add 文件名   #将这个文件加入暂存区
git add .  #添加所有文件
~~~~

③：把暂存区的文件提交给本地仓库

~~~~
git commit -m  #-m后的位置是用来写注释的（说明书）。
比如： git commit -m "本次提交操作的说明"

~~~~



##### #git的操作

~~~~git
git init      #可以把当前目录变成Git管理的仓库.
git status    #查询操作的空间的状态

~~~~

##### 版本查询

~~~~git
git log #查看当前版本， 以及当前版本之前的所有版本
git refog  #查看所有的版本及恢复记录

~~~~

##### 回滚

从==暂存区==把==上一次add==的某个文件回滚到操作空间

~~~~git
git checkout 文件名
~~~~

从仓库中获取任意一次记录，回到操作空间

~~~~git
git reset --hard id  # id就是版本查询中的commit码
~~~~

##### 如果有不想提交的文件，咋处理

​	1.使用开发工具，创建一个文件， .gitignore

​	2.把不提交的文件名称，写入.gitignore

​			一个名称占一行，同时.gitignore本身也不提交，也需要写在文件中

#### git的分支设置

​	git的分支结构支持分布式开发，各个分支之间的代码不可见。

​	有依赖性的分支，会把依赖的分支做一个备份发给你使用。

​	一个分支就是一个功能模块。

~~~~git
#查看所有分支
git branch    #前面带*的表示当前在那个分支中
~~~~

·创建分支

~~~~
git branch 分支名
~~~~

·切换分支

~~~~git
git checkout 分支名

#新版本中提供另一种写法
git switch 分支名
~~~~

创建分支+切换分支 合并写法

~~~~
git checkout -b 分支名
~~~~

合并分支

~~~~
git merge 分支名（其他分支名）  # 在当前分支上合并其他分支

#回退到合并以前
git reset --merge  
~~~~

删除分支

~~~~
#普通分支
git branch -d 分支名

#强行删除未合并的分支
git branch -D 分支名
~~~~







#### git实现原理





# GitHub使用

从网络仓库中，把所有内容拉取到本地操作空间上

~~~~git
#将仓库改个名字，叫origin
git remote add origin https://github.com/lujiaoa/WebStudy.git
#将仓库的文件拉到本地仓库
git push -u origin master
~~~~

