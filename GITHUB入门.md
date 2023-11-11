#GITHUB入门
一、GitHub的访问
GitHub的流畅访问是这次学习遇到的第一个问题，因为GitHub是一个外国网站，所以访问起来会很慢或是无法访问，通过搜集资料，我了解了几种访问GitHub的方法。

1.通过加速器Watt Toolkit（目前在用）

2.访问GitHubfast

3.修改hosts文件（还未尝试）

4.edge插件

二、设置用户及本地文件夹的操作

1.打开后首先设置用户

* git config --global user.name“用户名”
* * git config --global user.email“注册邮箱”

2.设置本地文件夹
* 在选中的文件夹以gitbash打开

三、GitHub创建远程仓库并链接

1.初始化本地仓库，进入想建立本地仓库的文件夹使用＄ git init初始化本地仓库。

2.新建远程仓库

3.建立连接

* 配置SSH连接
* 在本地仓库打开gitbash使用＄ git remote add +仓库名字 +链接地址（GitHub上的）注：若不想使用某仓库则输入git remote remove +仓库名字


四、GitHub和gitdash之间的连接

1.文件上传

* git add 将修改的文件（新建、更改、删除文件）添加缓存区git add -A提交所有变化
* git commit -m“修改注释”将当前暂存区的文件实际保存到仓库的历史记录中可以简单理解为给刚才add的东西加备注，当上传到远程仓库后，修改的文件后边会显示这个注释
* git push 将文件推到远程仓库。向一个空的新仓库中推文件：$ git push -u 仓库名称 分支（只有第一次推送master分支时加上-u）以后的推送只输入$ git push 名称 分支。注：＄ git push 名称 分支 -f 强制推送
* 此后网页版的GitHub就有本地仓库的东西了


2.文件下拉

* $ git pull 仓库名称
* 在远程仓库中修改某个文件后git pull 后修改的内容已进入本地仓库
3.文件克隆
* $ git clone 想克隆内容的地址
* 下载完之后，克隆文件夹里就有远程仓库的名字的文件夹此时可用git remote -v 检查本地仓库是否与远程仓库连接


总结：初步学习并了解GitHub和gitbash之间的连接，学会创建本地仓库和远程仓库，并能将本地仓库内容推入远程仓库以及远程仓库内容的改变下拉至本地仓库