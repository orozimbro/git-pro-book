# GIT PRO 

## intro

```
untracked	unmodified	modified	staged
   |----------------|---------------|----------->>>|	add the file
   |                |------------>>>|              |	edit the file
   |                |               |----------->>>|	stage the file
   |<<<-------------|               |              |	remove the file
   |                |<<<------------|--------------|	commit
```

## git config
The 'git config' can be stored in three diferent places:
- /etc/gitconfig file; contains values for every user on the system, if you pass the option '--system' to 'git config', it reads and writes from this file;
- ~/.gitconfig or ~/.config/git/config file: specific to your user, if you pass the option '--global' to 'git config', it reads and writes from this file;
- config file in the git repository (that is .git/config on each project), specific to that single repository;
Each level overrides values in the previos  level;
### Setting your identity
```
$ git config --global user.name "Mauricio Orozimbro de Souza"  
$ git config --global user.email "orozimbro@gmail.com"
```
### Checking your settings
`$ git config --list`

## git status
`$ git status`  
### Git short status
`$ git status -s`  

## git diff
```
$ git diff
$ git difftool
$ git difftool --tool-help  
$ git difftool --tool=winmerge  
```

## git commit
`$ git commit`: will open your default editor (git config --global core.editor) to you add your commit message  
`$ git commit -m <your message>`: commit of all files on stage area  
`$ git commit -a -m <your message>`: stage and commit all MODIFIED AND TRACKED files  
`$ git commit --amend`: increases the last commit  

## git rm
`$ git rm <file>`: remove file from stage and working directory  
`$ git rm --cached <file>`: remove file only from stage area, useful if you forgot to add something to yout .gitgnore  
`$ git rm log/\*.log`: you can pass files, directories and file-glob patterns to `git rm`  

## git mv
This command rename files on git, if you only rename the file on your filesystem, git will see a DELETE (old name) and ADD (new file) of files. With this command de file is renamed and staged.  
`$ git mv rm-file.txt remove-file.txt`

## git log
```
$ git log			# list all log from the last until the first
$ git log -p -2			# -p: show difference, -2: only the last two commits
$ git log --since=2.weeks	# --since=2.weeks: commits made in the last two weeks
$ git log -S<funcion_name>	# -S: list commits that changed a specific function/word
$ git log --stat		# --stat: some abbreviated stats for each commit
$ git log --graph		# --graph: show ASCII graph of your branch history 
$ git log --pretty=oneline	# --pretty=oneline: show each commit on only one line, others ptions: short, full, fuller
$ git log --pretty=format:"%h - %an, %ar : %s" # see below options 
```
| Option	| Description of Output		|
|---------------|-------------------------------|
| %H		| commit hash			|
| %h		| abbreviated commit hash	|
| %T		| tree hash			|
| %t		| abbreviated  tree hash	|
| %P		| parent hashes			|
| %p		| abbreviated parent hashes	|
| %an		| author name			|
| %ae		| author email			|
| %ad		| author date			|
| %ar		| author date, relative		|
| %cn		| committer name		|
| %ce		| committer email		|
| %cd		| committer date		|
| %cr		| committer date,  relative	|
| %s		| subject			|

author: who originally wrote the work  
committer: who last applied the work

## git reset
`$ git reset HEAD <file>`: remove a file from staging area  

## git checkout (keep in mind, it is a dangerous command)
`$ git checkout -- <file>`: revert file changes in working directory

# --------------------- Working with remotes -------------------------

## git remote
`$ git remote`: list de name of each remote available on local repository  
`$ git remote -v`: show the URLs that git has stored for each remote
`$ git remote add bitbucket https://orozimbro@bitbucket.org/orozimbro/git-pro-book.git`: add new remote
