# 在熟悉整个git push和git pull流程后

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