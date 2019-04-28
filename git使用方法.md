=git常用指令
- git init 代表初始化 git 仓库 ,当前目录已经是一个 git 仓库了。
	- git status 这个命令顾名思义就是查看状态，这个命令可以算是使用最频繁的一个命令了，建议大家没事就输入下这个命令，来查看你当前 git 仓库的一些状态。
	- git add 文件   提交到暂存区
	- git commit -m 'firstcommit' 提交到 Git仓库
	- git branch
		branch 即分支的意思，分支的概念很重要，尤其是团队协作的时候，假设两个人都在做同一个项目，这个时候分支就是保证两人能协同合作的最大利器了。举个例子，A, B俩人都在做同一个项目，但是不同的模块，这个时候A新建了一个分支叫a， B新建了一个分支叫b，这样A、B做的所有代码改动都各自在各自的分支，互不影响，等到俩人都把各自的模块都做完了，最后再统一把分支合并起来。



=第一步：建立git仓库

新建一个本地仓库，其实也就是新建一个文件夹。最简单的创建方式就是直接在桌面鼠标右键，新建文件夹(test)，然后进去该文件夹。鼠标右键，打开git -> Git Bash Here -> git init。执行命令后目录下创建一个.git文件夹。

git init

=第二步：添加需要上传到github的代码到本地仓库如何添加，首先将需要上传的代码复制粘贴到本地仓库，也就是test文件夹。

然后git status，这时候会发现多了一些东西，这些东西就是你刚刚复制进来的文件，显示为红色，就是待添加到本地仓库的意思

=第三步：将项目的所有文件添加到仓库中

既然待添加，下一步自然就是添加了，如何添加，git add + 需要添加的文件名 或者git add --all 将所有的文件全部添加，我这里是git add test.txt，然后再次git status 查看状态，可以发现test.txt变成了绿色，这时候文件就已经添加到本地仓库了

git add test.txt
这个命令会把当前路径下的所有文件，添加到待上传的文件列表中。

第四步：将add的文件commit到仓库

添加之后，最后提交就行，git commit -m “修改说明”。-m后面添加的是对本次操作的说明，加入你修改了代码或者重新上传了什么东西都做个简单说明，别人看了就知道是怎么回事了。然后再次git status查看状态，如下，已经添加成功：

git commit -m "第一次提交"

第五步：去github上创建自己的Repository

点击Create repository，一步一步执行下去即可，创建成功后拿到创建的仓库的https地址

第六步：将本地的仓库关联到github上

git remote add origin git@github com:leiphp/awesome-python3-webapp.git

第七步，上传代码到github远程仓库

执行完后，如果没有异常，等待执行完就上传成功了，中间可能会让你输入Username和Password，你只要输入github的账号和密码就行了。但是在这一步很多人执行会报错，报类似failed to push some refs to......的错误，那是因为本地代码目录缺失README.md文件。我们只需要先

通过如下命令进行代码合并【注：pull=fetch+merge]

git pull --rebase origin master
执行成功后，发现test文件夹已经把github之前的代码克隆下来了

此时再执行语句 git push -u origin master即可完成代码上传到github

git push -u origin master

1.git status
2.git add --all
3.git commit -m '提交信息' (注：“提交信息”里面换成你需要，如“first commit”)
4.git push -u origin master
5.输入邮箱
6.输入密码