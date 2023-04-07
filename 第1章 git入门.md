# Git的四个工作区域



Git本地有四个工作区域：工作目录(Working Directory)、暂存区(Stage/Index)、资源库(Repository)、git仓库(Remote Directory)

![image-20230330173624803](D:\project\Git\images\image-20230330173624803.png)

Workspace: 工作区，也就是平时存放项目代码的地方
Index/Stage: 暂存区，用于临时存放你的变动。事实上它只是一个文件，保存即将提交到文件列表信
Repository: 仓库区，就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本
Remote: 远程仓库，托管代码的服务器，可以简单的认为是你项目组中一台电脑用于远程数据交换



# Git的四种状态

git工作流程一般是这样的：

1.在工作目录中添加、修改文件

2.将需要进行版本管理的文件放入暂存区域

3.将暂存区域的文件提交到git仓库

![image-20230330175047084](D:\project\Git\images\image-20230330175047084.png)

Untracked：未跟踪，此文件在文件夹中，但并没有加入到git库，不参与版本控制，通过git add状态变为Staged。

Unmodify：文件已经入库，未修改，即版本库中的文件快照内容与文件夹中完全一致，这种类型的文件有两种去处，如果它被修改，而变为Modified，如果使用git rm移除版本库，则成为Untracked文件。

Modified：文件已修改，仅仅是修改，并没有进行其他的操作，这个文件也有两个去处。通过git add可进入暂存staged状态，使用git checkout则丢弃修改过，返回到Unmodified状态，这个git checkout即从库中取出文件，覆盖当前修改。

Staged：暂存状态，执行git commit则将修改同步到库中，这时库中的文件和本地文件又变为一致，文件为Unmodified状态，执行git reset Head filename 取消暂存，文件状态变为Modified



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