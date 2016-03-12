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