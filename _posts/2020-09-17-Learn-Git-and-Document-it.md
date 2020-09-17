1. Reset the git commit which hasn't been pushed yet
	``` git reset --hard HEAD~; ``` 
	
2. Git default branch 
I hate using ```master/slave``` naming convention when you have power to change it to ```main/worker``` 
	```
	i.  Upgrade your git to 2.28.0+
	ii. Make your default branch as ```main```
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
