## Documentation is important and on this blog post I have tried list down for git.

1. Reset the git commit which hasn't been pushed yet

	``` git reset --hard HEAD~; ``` 
	
2. Default branch 

	I hate using ```master/slave``` naming convention when you have power to change it to ```main/worker``` 
	
	i.  Upgrade your git to 2.28.0+
	ii. Make your default branch as ```main```
	```
		git config --global init.defaultBranch main
	```	
3. Delete the remote branch 
	``` 
	git push origin --delete [remote branch name ]
	``` 
4. Limit the short commit abbrev hash to length of 8
	```
	git config --global log.abbrevcommit yes
	git config --global core.abbrev 8
	```
5. Prune the stale branches 
	``` 
	git remote prune origin 
	``` 
	
6. Git squash 
	```
	git checkout [your_branch]
	git rebase -i HEAD~[number_of_last_commits]
	#On master branch
	git merge --squash [your_branch]
	git branch --merged
	```
