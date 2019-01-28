# GIT PRO 

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

outro teste':
