
# Git操作

1.系统级别签名

git config --global user.email "fenglixiong123@163.com"
git config --global user.name "fenglixiong"

2.克隆代码

git clone https://github.com/fenglixiong123/DesignModel.git

3.查看分支

git branch -a

4.创建分支

git branch test

5.删除分支

git branch -d dev

6.切换分支

git checkout dev

7.添加文件

git add note.text

8.将暂存区内容提交到本地库

git commit -m “提交笔记文件” note.text
提交当前目录所有修改的文件
git commit -a

9.提交至远程

git push
git push <远程主机名> <本地分支名>:<远程分支名>
git push origin dev:dev

10.拉取

git pull
git pull <远程主机名> <远程分支名>:<本地分支名>
git pull origin dev:dev

11.撤销之前操作

git reset HEAD~
撤销add操作的某个文件或目录：
git reset HEAD -name
Git撤销commit的操作命令 git reset –hard HEAD^
Git撤销commit的操作命令 git reset –hard HEAD~1

git 删除 错误 提交的 commit
方法:

根据–soft –mixed –hard，会对working tree和index和HEAD进行重置:
推荐使用默认的，因为这样只会回退commit，而hard会直接删除文件完全回退到之前版本
git reset --mixed：此为默认方式，不带任何参数的git reset，即时这种方式，它回退到某个版本，只保留源码，回退commit和index信息
git reset --soft：回退到某个版本，只回退了commit的信息，不会恢复到index file一级。如果还要提交，直接commit即可
git reset --hard：彻底回退到某个版本，本地的源码也会变为上一个版本的内容，此命令 慎用！

HEAD 最近一个提交
HEAD^ 上一次提交
HEAD^ ^ 上一次的 上一次的提交（倒数第三次）
HEAD^^^ 倒数 第四次的 提交
----------------------
HEAD~0 最近一个提交
HEAD~1 上一次提交（推荐，回退到上一个版本中去，比较常用）
HEAD^2 上一次的 上一次的提交（倒数第三次）
HEAD^3 倒数 第四次的 提交



12.查看提交历史

git log --oneline

git log 查看提交记录

a. git log 查看提交历史记录

b. git log --oneline  或者 git log --pretty=oneline 以精简模式显示

c. git log --graph 以图形模式显示

d. git log --stat 显示文件更改列表

e. git log --author= 'name' 显示某个作者的日志

f. git log -p filepath 查看某个文件的详细修改

g. git log -L start,end:filepath 查看某个文件某几行范围内的修改记录

h. git log --stat commitId  或者 git show --stat commitId 查看某一次提交的文件修改列表 
