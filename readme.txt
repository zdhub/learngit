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
	(3)已经提交到了版本库，想要撤销，回滚

*******************远程仓库***********************
1:注册一个GitHub账号，就可以免费获得Git远程仓库。创建key
2:关联一个远程仓库，使用命令git remote add origin git@server-name:path/repo-name.git
3:关联后，使用命令git push -u origin master，第一次推送master的所有分支，此后，每次本地递交后，只要有必要，就可以使用命令git push origin master
4:从远程库克隆需要知道仓库的地址，然后使用git clone https://github.com/YiZhendong/gitskills.git这样的命令就可以