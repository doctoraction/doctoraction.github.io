# Git

Github

At home, HTTPS cloning

`git config --list --show-origin` show all config, and where it's from
`git config --local user.name "Local User"`

Update report local config to override existing config (eg. corporate config for SSH etc):

```
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "origin"]
	url = https://github.com/doctoraction/aoc2023.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "main"]
	remote = origin
	merge = refs/heads/main
[user]
	name = doctoraction
[http]
	sslVerify = false
[credential]
	helper = 
[commit]
	gpgsign = false
```
