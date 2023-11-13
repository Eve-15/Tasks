# <center>GitHub进阶学习</center>

## 一、本地仓库

#### 1. 添加hello.md文件并写入内容

#### 2. 使用GitBash将本地项目推送到远程GitHub仓库

1. 在本地仓库中打开gitbash。
2. 使用指令git add .把所有本地项目加入到缓存区。
3. 使用指令git commit -m “里面为注释”把缓存区的文件提交到本地仓库。
4. 最后使用git push origin master把仓库中的文件推送到GitHub的远程仓库里。

## 二、与他人协同做项目

#### 1.对Fork和Pull request的初步理解

##### 	1.Fork

* 意为分支，相当于创建一个分支，可以理解为一个物理副本。
* 在这个分支上的操作不会改变源代码，两个代码是独立的互不干扰。
* 下载别人的源代码进行自己的开发、优化、完善。

##### 	2.Pull request

* 译为拉取请求，可以与git pull结合理解。
* 当别人fork了自己的项目后进行一定的修改、优化、完善后，将他的内容合并到源代码之中。

##### 	3.两者联系

* 两者共同使用，在与他人完成协同项目
* 两者的关系下图易于理解

![GitHub的工作流](C:\Users\Lenovo\Pictures\Saved Pictures\CSDN_1699885737336.jpg)

#### 2.协同项目的操作流程

##### 1.在GitHub页面上操作

* 访问仓库界面后，点击Fork按钮即可创建自己的名下分支。
* 将自己的想法或是修改完成后后直接点击pull request按钮进行推送，推送至fork的来源。
* 点击merge pull request按钮进行合并。
* 需要在write栏中详细写出修改原因，方便对方理解，随后点击creat pull request，此时对方即可收到pull request。

##### 2.在本地仓库进行操作

* 访问仓库后，点击fork自己的仓库中多出一个名为：自己账户名/fork的仓库名称
* 通过指令git clone 仓库地址克隆远程仓库至本地仓库
* 在本地仓库中修改源码
* 修改完成后
