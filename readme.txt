hello this is a little test about git/11/3/2016
git is a distributed version control system
git is a free software

remark:
1:git init     		create a git res... use "git init"
2:(1)git add 
  (2)git commit 	add file to the repository:	(1)git add <file> (2)git commit
3:"git status"		in order to get the stuation,use "git status"
4:"git diff"		if the file has been modified,use "git diff"
5:roll back
  "git reset --hard commit_id"  we can use this command to go through the different version,and the head is to lead the current version.
  				For example, "git reset --hard head^" refer to the last version.
  "git log"			we can use this command to check the **submition** history/  "git log --pretty=oneline" the short type
  "git reflog" 			we can use this command to check the **command** history,in case you feel regret about the rolling back
