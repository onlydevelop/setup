# Setting up the git

Of course, you need to setup the git config.

## Setting up git

```bash
$ cat ~/.gitconfig
[user]
        name = [Your Name]
        email = [Your Email]
[push]
        default = tracking
[branch]
        autosetuprebase = always
[core]
        editor = vi
        autocrlf = input
[color]
        ui = auto
[alias]
        br = branch
        ci = commit
        cia = commit --amend
        cm = commit -m
        cp = cherry-pick
        lol = log --graph --decorate --pretty=oneline --abbrev-commit
        next = "!f() { cmid=`git log|grep commit|head -1|cut -d' ' -f2`; \
                 git log --all|grep commit|grep -B 1 $cmid|head -1|cut -d' ' -f2|xargs git co;  }; f"
        pl = pull
        prev = "!f() { git log -n 2 --pretty=format:'%H'|tail -1|xargs git co; }; f"
        rbi = rebase -i
        st = status
```

I love using the aliases like:

```bash
{10:59}~/setup:master ✓ ➭ git st
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        git/

nothing added to commit but untracked files present (use "git add" to track)
{11:10}~/setup:master ✗ ➭ git add .
{11:10}~/setup:master ✗ ➭ git st
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   git/README.md

{11:10}~/setup:master ✗ ➭ git cm "Added git folder"
[master e6ab496] Added git folder
 1 file changed, 39 insertions(+)
 create mode 100644 git/README.md
```
