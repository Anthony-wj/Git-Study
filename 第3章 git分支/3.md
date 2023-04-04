# Git分支简介

#### 为什么使用分支

- 为项目添加新特性，与其将特性加入到其它人正在使用的master分支，更好的办法是在仓库的其他分支中变更代码。
- Git其设计用于写作。如果所有人都在master分支上进行操作，会引发很多混乱。



#### 使用分支的好处

1. 同时并行推进多个功能开发，提高开发效率。
2. 各个分支在开发过程中，如果某一个分支开发失败，不会对其他分支有影响。失败的分支删除重新开始即可。



# Git分支常用命令

#### 查看分支

`git branch -v`

#### 创建分支

`git branch 新分支名` 

#### 删除分支

`git branch -d 分支名`

#### 修改分支

`git branch -m 旧分支名 新分支名`

#### 切换分支

`git checkout 分支名`

#### 合并分支

`git merge 分支名`



# Git分支合并

#### 创建分支

`git branch newBranch`

#### 切换分支

`git checkout newBranch`

#### 在分支上修改文件

`vim index.html`

#### 在分支上提交

`git commit -am "newBranch"`

#### 切换到主分支

`git checkout master`

#### 合并分支

`git merge newBranch`