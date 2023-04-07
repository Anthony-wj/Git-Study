# Git常用命令

git init

git branch 查看本地所有分支

git status 查看当前状态

git add 添加文件

git commit 提交

git push origin master 将文件推送到服务器

git checkout 

# Git配置用户签名

#### 配置格式

##### 方式一(单个仓库有效)

```
git config user.name 用户名
git config user.email 邮箱
```

> 该种方式配置信息会保存在当前仓库目录下的.git/config文件中，打开查看发现保存的格式为

```
[user]
	name = 用户名
	email = 邮箱
```

##### 方式二(全局有效)

git conf

```
git config --global user.name 用户名
git config --global user.email 邮箱
```

> 该种方式配置信息会保存在系统盘的系统用户目录下的.gitconfig文件中，保存格式同上面一样

# Git初始化本地库

#### 初始化命令

git init

#### Git目录

git目录是为你的项目存储所有历史和元信息的目录 - 包括所有的对象(commits, trees, blobs, tags),这些对象指向不同的分支。

每一个项目只能有一个git目录，这个叫.git的目录在你项目的根目录下(这是默认设置，但不是必须的)。如果你查看这个目录的内容，你可以看所有的重要文件。

HEAD  # 这个git项目当前指向哪个commit对象

config  #项目的配置信息

description  #项目的描述信息

hooks/  #系统默认钩子脚本目录

index   # 索引文件，暂存区(Stage)

logs/   # 各个refs的历史信息  

objects/   #Git本地仓库的所有对象(commits, trees, blobs, tags)

refs/   #表示你项目里每个分支指向了哪个提交

# 查看Git状态

#### 命令

git status



#### 状态

git status命令表示：文件，文件夹在工作区、暂存区的状态。

​	1.`Changes to be committed:`表示已经从工作区add到暂存区的file，可以通过git restore ==staged filename 命令将该file从暂存区一处，只有工作区有该文件，该文件就为Untracked files。

​	2.`Changes not staged for commit:`表示工作区、暂存区都存在该file，在工作区进行修改或删除，但是没有add到暂存区。

​	3.`Untracked files:`表示只有在工作区有的file，也就是暂存区没有该file

# Git将代码添加到暂存区

#### 基本用法

git add 命令可以将该文件添加到暂存区。

1. ​	添加一个或多个文件到暂存区

   git add file1 file2

2. ​	添加指定目录到暂存区，包括子目录

   git add [dir]

3. ​	添加当前目录下所有文件到暂存区

   git add .



#### 区别

git add . 添加当前目录以及孙目录下所有变动到暂存区

git add -A 添加项目所有文件的所有变动到暂存区

git add -u 仅添加已经被add的文件，不会添加untracked file到暂存区



# Git添加代码

#### 作用

git commit 命令将暂存区内容添加到本地仓库

#### 命令

git commit -m [message]

#### 提交指定文件

git commit [file] -m [message]

#### 直接提交

-a 参数设置**修改**文件后不需要执行git add命令，直接来提交

git commit -am [message]





# Git版本切换

查看版本信息

reflog 

log



切换版本

git reset --hard 版本号