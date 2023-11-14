# 在熟悉整个git push和git pull流程后在学习廖雪峰老师的Git教程

# 一、版本回退

1. git log 可以查询近三次的版本：由近至远append GPL、add distributed、wrote a readme file

* 若嫌输出信息太多可以加上 --pretty=oneline

2. git reset --hard HEAD回退到上一个版本

* HEAD^上一个版本
* HEAD^^上上个版本
* HEAD^^^上上上个版本

3. git reset --hard + commit id 指定回到未来的某个版本

* 版本号写前几位即可

4. git reflog 可以记录每一次命令

* 故在关掉电脑后仍可查到commit id

# 二、工作区和暂存区

下图对工作区和暂存区以及add，commit可以方便理解

![git-repo](https://www.liaoxuefeng.com/files/attachments/919020037470528/0)

* .git目录是git的版本库其中存有

1. stage（暂存区）
2. 自动创建的第一个分支master
3. 指向master的指针 HEAD

* **ps：**用**git commit**提交更改，实际上就是把暂存区的所有内容**提交到当前分支**。

# 三、修改

#### 1.管理修改

* git diff HEAD --文件名 此命令可以查看工作区和版本库里面最新版本的区别

#### 2.撤销修改

* git checkout -- file把文件在工作区的修改全部撤销分两种情况：

1. 文件自修改后还没有被放到暂存区，现在撤销修改就回到和版本库相同的状态
2. 文件已经添加到暂存区后，又做了修改，现在，撤销修改就回到添加暂存区后的状态

即让这个文件回到最近一次git commit或git add时的状态。

**ps：git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令**

* git reset HEAD file 可以把暂存区的修改撤销掉（unstage），重新放回工作区用来处理上文第2种情况

#### 3.删除文件

* ##### 在文件管理器中或者用 rm file 命令删除文件后工作区和版本库不一致

##### 1.确实要从版本库删除该文件

* 用 git rm删掉并且 git commit 将

##### 2.删错了，因为版本库里仍有，可以把误删文件恢复到最新版本

* 用指令 git checkout -- file 将版本库的版本替换工作区版本

**注：从来没有被添加到版本库就被删除的文件无法恢复**

# 四、远程仓库

#### 1.本地仓库和远程仓库连接

* git remote add 仓库名 地址  关联远程仓库
* git push -u origin master  把本地仓库内容推送到远程仓库

#### 2.从远程仓库克隆

* git clone +仓库地址

# 五、分支管理

分支之间互不干扰，可以合并

#### 1.创建与合并分支

* ##### 创建分支

​	创建分支时，git新建了一个指针指向master相同的提交，两者工作区内容相	同，当切换分支后，HEAD指向新的指针，当前分支指针变化，其他分支指针	保持不变

1. 首先创建新分支并切换

   > $ git checkout -b <branch_name>

2. 或者分两步进行先创建后切换

   > $ git branch <branch_name>
   >
   > $ git checkout <branch_name>

3. 用git branch查看分支

   > $ git branch 查看本地分支
   >
   > $ git branch -r 查看远程分支
   >
   > $ git branch -a 查看所有分支

4. 随后便可以在新分支上进行操作并提交

   > $ git add .
   > $ git commit -m "注释"

5. 切换回master分支

   > $ git checkout master

6. 把新分支上的内容合并到master分支上

   > $ git merge <branch_name> **注：此语句是将某分支合并到当前分支，合并前注意切换分支**

7. 合并完成后删除新分支,再次查看branch确定

   > $ git branch -d <branch_name>
   >
   > $ git branch

* ##### 切换分支

1. > $ git checkout -b <branch_name> 创&切
   >
   > $ git checkout <branch_name>

2. > $ git switch -c <branch_name> 创&切
   >
   > $ git switch <branch_name>

#### 2.合并冲突及解决

* ##### 冲突原因：

​		在新建分支上进行修改后提交随后切换到master分支上并在master分支上同样对文件进行修改并提交。此时master分支和新分支各自都分别有新的提交此时git无法执行快速合并。

* ##### 解决冲突：；手动解决冲突

* 直接查看文件内容
* Git用<<<<<<<，=======，>>>>>>>标记出不同分支的内容
* 修改后再次提交

#### 3.分支管理策略

通常合并分支时，如果可能，git会用Fast forward模式，在这种模式下删除分支后，会丢掉分支信息

若强制禁用Fast forward模式，git会在merge时生成一个新的commit，从分支历史上可以看出分支信息

* 流程与创建分支一致，在合并阶段有所不同

  > $ git merge **--no-ff** -m "注释" <branch_name>

* 合并后查看分支历史

  > git log

注意：**--no-ff**参数表示禁用fast forward同时合并后要创建一个新的commit故加上-m参数把commit描述写进去

* master分支非常稳定，所以工作时在其他分支上进行，再将其它分支合并到一起，最后将合并后的内容合并到master分支上

#### 4.Bug分支（玩游戏听了这么久的bug，第一次了解bug是怎么修复的）

​		在Git中，由于分支的强大，所以，每个bug都可以通过一个新的临时分支来修复，修复后，合并分支，然后将临时分支删除。

* Git提供一个stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作

  > $ git stash

* 工作现场的保存查看

  > $ git stash list

* 恢复并删除stash内容

  > $ git stash apply  恢复内容
  >
  > $ git stash drop  删除stash内容
  >
  > $ git stash pop  恢复并删除stash内容

* 可以多次stash，回复时先查看list然后回复指定stash

  > $ git stash apply stash@{0}

- ##### Bug修复

1. 首先确定要在哪个分支上修复bug，例如从master分支开始，创建一个issue-101的分支修复它

   > $ git checkout master
   >
   > $ git checkout -b issue-101

2. 修复bug后提交
3. 切换到master分支并合并
4. 删除issue-101分支

* ##### git cherry-pick  < commit>

​	将指定提交应用到当前分支	

​	还在理解ing

##### 5.feature分支

* 新建feature分支开发完成后合并，最后删除feature分支

* 学到强制删除分支的指令

  > git branch -D < name>

# 六、多人合作

##### 1.推送分支

* 理解查看远程库信息的指令

  > $ git remote
  >
  > $ git remote -v  更详细会显示可以抓取和推送的远程仓库地址

* 本地分支推送至远程分支

  > $ git push <branch_name>

总之分支推送很灵活

##### 2.抓取分支