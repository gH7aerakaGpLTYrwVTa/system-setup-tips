# General Tips
Make sure:
`git config pull.rebase true`

# Quick SSH setup:
For example the IP could be 192.168.0.25

Run command:
`sudo nano ~/.ssh/config`

Example config file:
```
Host rockpro
Hostname = 192.168.0.25
User = userone
```

Example SSH login command:
`ssh rockpro`

# Bash Git Prompt:
See: https://github.com/magicmonty/bash-git-prompt

1. Follow instructions to git clone and edit ~/.bashrc

2. Make sure `~/bash-git-prompt` is renamed to `~/.bash-git-prompt`

Add the following to ~/.bashrc:
```
if [ -f "$HOME/.bash-git-prompt/gitprompt.sh" ]; then
    GIT_PROMPT_ONLY_IN_REPO=1
    source /usr/share/bash-completion/completions/git
    source $HOME/.bash-git-prompt/gitprompt.sh
fi
```

3. Change directory to any git repo and test:

`source ~/.bashrc`

4. For final touches run:

`nano .gitconfig`

5. Add:
```
[alias]
    aa = add --all
    bv = branch -vv
    ba = branch -ra
    bd = branch -d
    bup = remote update origin --prune
    ca = commit --amend
    cb = checkout -b
    cm = commit -a --amend -C HEAD
    ci = commit -a -v
    co = checkout
    di = diff
    ll = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat
    ld = log --pretty=format:"%C(yellow)%h\\ %C(green)%ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short --graph
    ls = log --pretty=format:"%C(green)%h\\ %C(yellow)[%ad]%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=relative
    last = log -1 HEAD
    mm = merge --no-ff
    st = status --short --branch
    tg = tag -a
    pu = push --tags
    un = reset --hard HEAD
    uh = reset --hard HEAD^
    up = pull --rebase origin master
[color]
    diff = auto
    status = auto
    branch = auto
[push]
        default = simple
[core]
        editor = vim
[user]
	name = XXX
	email = XXX
	signingkey = XXXXXXXXXXXXXXXX
[commit]
	gpgsign = true
```
