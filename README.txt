下载vscode 
装一个中文的插件 chinese 
设置 fontsize
设置代码的自动保存

git：叫版本控制系统，目前是世界上最先进的版本控制系统，没有之一。
    1.0版
    2.0版

主流的版本控制系统主要分两类：
    1，集中式版本控制系统  SVN
    2，分布式版本控制系统  GIT

GIT的历史：大家自己查一下。

集中式版本控制（SVN）系统缺点：
1）中央服务器如果挂了，一切都over。
2）需要联网才能提交代码和拉取代码。
3）是基于文件传输的，速度慢


分布式版本控制系统的优点：
1）有了本地仓库，不需要联网就可以进行代码的管理
2）不需要过多的依赖中央仓库。
3）基于文件流传输的，速度非常快。

github 和 git 不一样：
git：版本控制工具。
github：是一个网站。

使用git的步骤：
1）下载安装git工具。通过git bash打开黑窗口。
2）注册一个github的账号：https://github.com/
3）创建仓库（git init）  会生成一个.git文件夹，这个文件夹就本地仓库。
4）告诉git你是谁，设置用户名和邮箱。(设置成和github上面的用户名和邮箱一样)
    git config user.name yuanfang1024
    git config user.email 1935952410@qq.com

1）把文件从工作区扔到暂存区：git add index.html  /   git add *   /  git add -A 
2）把文件从暂存区扔到历史区，形成一个历史版本：git commit -m "注释"
3）查看当前文件的状态:  git status    如果文件名是红色的，代表还没提交到暂存区。绿色表示还没有把文件提交到历史区。
4）查看本地仓库的历史区都有哪些版本：git log
6）回退一个版本：git reset 版本id

git中的三大区：
    工作区：.git之外的区域叫工作区。
    本地仓库（.git）：
        暂存区 ：
        历史区：

=========================================== 快速再来一遍git的使用流程 
第一步：通过git init创建一个本地仓库。 只有第1次需要设置用户名和密码。
第二步：编写项目，创建了一个index.html文件，完成首页面的开发。
第三步：把工作区中的index.html扔到暂存区，通过git add * 
第四步：把暂存区的内存扔到历史区，通过git commit -m "版本1"

然后就是重复第二步到第四步。

版本的回退：
    git reset --hard/--soft 版本id     表示回退到指定的版本
    git reset --hard/--soft HEAD^     表示回退到上一个版本
    git reset --hard/--soft HEAD^^    表示回退到上上一个版本
    git reset --hard/--soft HEAD^^^   表示回退到上上上一个版本

    假如有三个版本（版本1，版本2，版本3），如果回退到了版本1，但是后悔了，又想回退到版本3，

辅助命令：
    1）git status  查看状态
    2）git log 查看当前历史区都有哪些版本
    3）git reflog 查看之前存储过的所有的版本

设置用户名和密码:
    git config user.name xxx 
    git config user.email xxx@qq.com 

注册一个github的账号  

=========================================== github的基本使用

注册一个github账号。

注册完一个github，都有自己的首页，如：https://github.com/yuanfang1024    https://github.com/用户名

对于github的设置操作：
    更改用户名：在设置中找到Account选项中更改。
    更改密码：在设置中找到Security选项中更改。
    更改绑定邮箱：在设置中找到Emails选项更改。
    更改个人信息与头像：在设置中找到Profile选择更改。

在github上面可以创建很多的远程仓库，需要联网才能向远程仓库去扔代码。在github上面的创建的仓库，都是远程仓库。

如何创建远程仓库：               repository 仓库的意思
    在github中右上角找+号，+号下面找 new repository，填写对应的仓库信息，就可以创建一个远程仓库。

=========================================== 本地仓库与远程仓库的关联 与 取消关联 

现在创建了一个本地仓库，一个远程仓库，此时它们两个还没有关联。如何关联？
首先通过一个命令查看一下，此时本地仓库没有没关联的远程仓库：git remote -v     没有打印出任何的东西表示没有关联任何远程仓库。

关联远程仓库：git remote add origin 远程仓库的地址
    如：git remote add origin https://github.com/yuanfang1024/didiproject.git

取消关联：git remote rm origin

=========================================== 开发项目，使用本地仓库和远程仓库来管理项目

第1步：创建一个文件（index.html），是项目的首页面，一个模块开发完后，先进行本地仓库的管理。
第2步：把工作区的代码提交到暂存区  git add *
第3步：把暂存区的代码提交到历史区，形成版本    git commit -m "xxx"   此时我已经形了一个版本（本地仓库）
第4步：把历史区中的版本推送到远程仓库（推送前必须让本地仓库与远程仓库进行关联）  git push origin master     master表示主分支
第5步：别人也可以向远程仓库中推送别的模块（同步）
第6步：当我又写了一个模块，需要push时，先进行pull，保证你的代码是远程仓库中最新版本。  git pull origin master


辅助命令：  
    git status  查看文件状态 
    git log 查看历史区的版本 

=========================================== 删除远程仓库
在github中，找到你的仓库，在仓库中找到setting，找到删除按钮，可以删除远程仓库






