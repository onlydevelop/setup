# Setting up the shell

## Setting up zsh

My preference is zsh.

```bash
$ sudo apt install zsh # Install
$ sudo vi /etc/passwd
# Change the shell for your user like
# ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/zsh
$ zsh # And press 0, just to create the .zshrc file
$ sudo timedatectl set-timezone Asia/Kolkata # Setting my timezone
```

## Setting up oh-my-zsh

I like the oh-my-zsh like others and I like the theme `crunch` (minimalistic)

```bash
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
$ vi ~/.zshrc
# Change the line to: ZSH_THEME="crunch"
```

Reference: https://ohmyz.sh