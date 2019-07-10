1、gitignore规则不生效

.gitignore只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。

解决方法就是先把本地缓存删除（改变成未track状态），然后再提交:

git rm -r --cached .

git add .

git commit -m 'update .gitignore'



2、git忽略某个指定的文件(不从版本库中删除)

执行命令如下：

git update-index --assume-unchanged config.conf

用git status查看一下，已经得到了自己想要的效果



3、git取消忽略某个指定的文件

git update-index --no-assume-unchanged config.conf



4、将当前版本回退到上一个版本，命令如下：

git reset --hard HEAD^



5、 回退到上两个版本

git reset – hard HEAD^^



6、回退到指定版本

git log //显示从最近到最远的提交日志

git reset --hard commit_id //回退到指定版本



7、查看命令历史

git reflog



8、拉取暂存区文件并将其替换成工作区文件

gitcheckout-- <file>



9、跟踪取消，即把文件从git中拿出来，不再进行版本跟踪，但保留工作区的文件。

git rm - - cached filename



10、查看工作区和版本库里面最新版本的区别

git diff HEAD – readme.txt

git diff命令比较的是工作目录中当前文件与暂存区快照之间的差异，也就是修改之后还没有暂存起来的变化内容



11、将工作去的内容放入版本库的暂存区

git add readme.txt



12、将暂存区的内容提交到当前分支

git commit -m "git tracks changes"



13、显示工作目录和暂存区的状态

git status



14、删除一个文件

git rm test.txt



15、从远程库克隆项目

git clone 项目地址



16、创建分支，然后切换到分支

git checkout -b dev

git checkout命令加上-b参数表示创建并切换，相当于以下两条命令：

git branch dev

git checkout dev



17、查看当前分支

git branch

git branch命令会列出所有分支，当前分支前面会标一个*号



18、git merge命令用于合并指定分支到当前分支

git merge dev



19、删除本地分支

git branch -d dev



20、删除远程dev分支

git push origin :dev



21、切换分支

git checkout <name>



22、查看远程库的信息

git remote 或 git remote -v



23、推送分支，就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上：

git push origin master

如果要推送其他分支，比如dev，就改成：

git push origin dev



24、拉取分支

git pull