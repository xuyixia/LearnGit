添加远程库
Git远程库可以是主机或Git服务器，本节中指的是Git服务器，实例则是GitHub。
在实际使用过程中，关联远程库有两种方式：
1. 本地库向远程库推
2. 本地库从远程克隆

分开讨论
1. 
GitHub创建仓库需要注意不能自动生成README.md文件，否则无法将本地库的分支推向远程库。原因是远程库在创建md文件的同时，会自动创建一个默认分支master。而没有相同版本历史的分支是无法合并的。

首先关联版本库`$ git remote add origin git@github.com:xuyixia/learngit.git`,origin是远程库默认的叫法。这里用到的是SSH协议，我们也可使用HTTPS协议`https://github.com/xuyixia/xuylearngit.git`。

关联后就是同步了。同步本质上是分支的同步。在当前这种”本地库往远程库推“的方式下，第一次push需要带上-u参数`git push -u origin master`。-u起到将本地指定分支同步到空的远程库中，并关联两个分支。此后的push和pull就可简化命令，简化的命令我试过直接用`git push`也能正确推送，但是信息不是很明确。不过为了保险起见，还是`git push origin master`。

在第一次向远程库推送并同步分支后，会收到来自SSH的警告。警告内容包含了远程主机的域名和Ip地址，以及我们用私钥解密加密信息得出的远程库的Ip地址，通过简单对比就能对方是否可信。

2.
如果是重新开发，建议先在Git服务器上创建远程库，然后从克隆到本地机器上。

我在用克隆功能时发现，在本地的一个文件夹下克隆远程库时，会产生两个仓库。不知其用意。

在创建远程库的同时需要生成一个README.md文件，原因有二。一是创建md文件的时候会默认commit一次，第一次commit会生成默认分支master。克隆远程库就是克隆远程库的分支，没有分支自然无法克隆。二是RM文件可以记录一些项目信息，十分有用。

克隆当然也使用到Git的传输协议，我们知道Git传输协议有两种，HTTPS和SSH。因此`$ git clone git@github.com:yourAccount/reposition.git`或`$ git clone https://yourRepositionPath`二选一。

克隆只会克隆主分支一个，如果要克隆其它分支，就输入命令`git checkout -b dev origin/dev`，或者用一个土办法，本地创建分支，然后push到远程分支，这样合并分支后就相当于克隆了远程分支。

查看远程库权限信息
git remote -v

pull操作
虽然pull操作本质上也是分支的合并，但是它仍然有它的特点。
pull之前要关联分支`git branch --set-upstream-to=origin/branch branch`,关联后才能用`git pull`。

pull冲突
push不会有冲突,pull会。虽然是分支的合并，但是pull冲突只会在本地分支上创建一个新的提交。这个版本是怎么分配的还有待研究。

如果本地分支的工作区或暂存区有未提交的更改，此时pull远程库会失败，因为合并会将它们重写掉。此时Git会提醒我们提交或stash解决。[11](https://blog.csdn.net/qq_38363371/article/details/78518736)因此每次pull最好是在提交后进行。


理解同步操作
库与库之间的同步，本质上是分支与分支的合并。这样看来就很简单了，毕竟本地版本库中经常用到分支的合并。
推送即是合并，那免不了会有冲突

删除远程仓库的分支
如果远程仓库只有一个主分支，删除分支的操作会失败。
命令为`$ git push origin <space> : <Branch>`,为方便记忆可理解为push一个空到指定分支。


#常用远程库的操作
添加远程库： git add remote origin <ssh> 
推送并关联分支(将当前分支绑定到远程分支上，git push就会自动找关联远程分支)： git push -u origin <branch>
推送分支：git push origin <branch> ，如果关联了远程分支，直接git push
查询远程库分支信息：git remote show origin
查看远程库：git remote -v
查看远程库日志：git log origin/master -n 3





