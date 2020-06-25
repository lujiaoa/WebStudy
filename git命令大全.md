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
git status -s        #加了参数以后会以短命令显示，不会显示详细信息

git diff
执行 git diff 来查看执行 git status 的结果的详细信息。

git diff 
命令显示已写入缓存与已修改但尚未写入缓存的改动的区别。
git diff 有两个主要的应用场景。

  # 尚未缓存的改动：git diff
  # 查看已缓存的改动： git diff --cached
  # 查看已缓存的与未缓存的所有改动：git diff HEAD
  # 显示摘要而非整个diff： git diff --stat
~~~~

##### git命令基本和linux差不多

~~~~git
touch 文件名              #在该文件下创建一个文件
mkdir 文件夹名           #创建一个文件夹
cd  文件夹名              #移动到文件夹下
ls                      # 查看该文件夹下所有内容
vim 文件名               #编辑该文件
~~~~



##### 拷贝项目

~~~~git
git clone 路径   #将项目拷贝到本文件夹中
git clone 路径 文件夹名（a）  # 在本文件中创建一个文件夹将项目拷贝进去
~~~~



##### 版本查询

~~~~git
git log #查看当前版本， 以及当前版本之前的所有版本
git refog  #查看所有的版本及恢复记录

~~~~

### git reset HEAD

~~~~git
git reset HEAD 文件名 #命令用于取消已缓存的内容，不写文件名就是取消所有
					#简而言之，执行 git reset HEAD 以取消之前 git add 添加，但不希望包含在下一提交快照中的缓存。
~~~~

### git rm

如果只是简单地从工作目录中手工删除文件，运行 **git status** 时就会在 **Changes not staged for commit** 的提示。

要从 Git 中移除某个文件，就必须要从已跟踪文件清单中移除，然后提交。可以用以下命令完成此项工作

~~~~git
git rm <file>   #删除文件，对于没上传到暂存区的文件
git rm -f <file> #以上传执行这个命令
git rm -f <file >   #如果把文件从暂存区域移除，但仍然希望保留在当前工作目录中，换句话说，仅是从跟踪清单中删除，使用 --cached 选项即可

~~~~

### git mv

git mv 命令用于移动或重命名一个文件、目录、软连接。

~~~~git
前提是要把文件加入缓存区
git add old new
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

