remark:
1:git init     		create a git res... use "git init"
2:(1)git add 
  (2)git commit 	add file to the repository:	(1)git add <file> (2)git commit
3:"git status"		in order to get the stuation,use "git status"
4:"git diff"		if the file has been modified,use "git diff"
5:回滚
  "git reset --hard commit_id"  we can use this command to go through the different version,and the head is to lead the current version.
  				For example, "git reset --hard head^" refer to the last version.
  "git log"			we can use this command to check the **submition** history/  "git log --pretty=oneline" the short type
  "git reflog" 			we can use this command to check the **command** history,in case you feel regret about the rolling back

6:暂存区和工作区的区别
当多个文件修改完成放入暂存区的时候，发现其中一个文件的代码有问题，这时候你可以用checkout单独将这个文件还原重改；如果你将这些文件一次性全部放进库里，等你发现有问题时就不能单独拿出一个文件了，只能版本回档，那时你就要重新修改所有文件的代码。
7:git同一文件必须要在add之后进行commit，否则就会出错
8:撤销修改
	(1)git checkout --file   改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用此命令
	(2)git reset  HEAD file  不仅改乱了工作区的内容，而且还提交到了暂存区，想丢弃修改，分两步，第一：使用此命令，第二：回到(1)
	(3)已经提交到了版本库，想要撤销，

*******************远程仓库***********************
1:注册一个GitHub账号，就可以免费获得Git远程仓库。创建key
2:关联一个远程仓库，使用命令git remote add origin git@server-name:path/repo-name.git
3:关联后，使用命令git push -u origin master，第一次推送master的所有分支，此后，每次本地递交后，只要有必要，就可以使用命令git push origin master
4:从远程库克隆需要知道仓库的地址，然后使用git clone https://github.com/YiZhendong/gitskills.git这样的命令就可以.

********************分支管理********************
1:创建和合并分支
	查看分支 git branch
	创建分支 git branch <name>
	切换分支 git checkout <name>
	创建+切换分支 git checkout -b <name>
	合并某分支到当前分支 git merge <name>
	删除分支 git branch -d <name>
2:解决冲突
	当git master和其他分支有冲突时，无法自动合并分支，先必须解决冲突。解决后再提交。
3:Fast forward下可能会在删除分支后，丢掉分支信息。如果强制禁用ff模式，git就会在merge时生成一个新的commit：git merge --no-ff -m "xxxx" dev  中的 --no-ff表示禁用 fast forward模式	
4：bug分支
	当当前工作还没提交时，有了bug，为了可以方便的解决bug，可以使用git stash来将当前现场储藏起来。可以使用git stash list来查看stash号码，用git stash apply（stash不删除）或者git stash pop（删除）来进行恢复。
5:feature分支
	当实验一个新特性时，最好添加一个新的feature分支，在上面开发，修改，完成后再进行删除。 使用git branch -D xxxx进行删除
6:多人协作
	查看远程仓库-----   git remote -v
	从本地推送分支----	git push origin branch-name，如果推送失败，先用git pull抓取新的远程的提交
	在本地创建和远程分支对应的分支，使用 git checkout -b branch-name origin/branch，本地和远程的名字最好一样
	建立本地和远程的分支的关联，使用git branch --set-upstream branch-name origin/branch-name
	从远程抓取分支，使用git pull，如果有冲突，则先处理冲突

********************标签管理*******************
发布一个版本时，我们通常先在版本库中打一个标签，将来无论什么时候，取某个标签的版本，就是把那个打标签的时刻的历史版本取出来。所以，标签也是版本库的一个快照。

1:创建标签
	git tag <name>用于新建一个标签，默认为HEAD，也可以指定一个commit id
	git tag 		可以查看所有标签
	git tag -a <tagname> -m "blabla"	可以指定标签信息
	git tag -s <tagname> -m "blabla"	可以用PGP签名标签
2:操作标签
	git push origin <tagname> 可以推送一个本地标签
	git push origin tags	  可以推送所有本地标签
	git tag -d <tagname>	  可以删除一个本地标签
	git push origin :refs/tags/<tagname>  可以删除一个远程标签

*******************使用github********************
	在GitHub上，可以任意Fork开源仓库(点“Fork”就在自己的账号下克隆了一个bootstrap仓库,然后，从自己的账号下clone)
	自己拥有Fork后的仓库的读写权限；
	可以推送pull request给官方仓库来贡献代码(如果你希望bootstrap的官方库能接受你的修改，你就可以在GitHub上发起一个pull request)

