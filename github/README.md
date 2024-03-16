# Setting up for Github

Need to setup the keys for the github.

```bash
$ ssh-keygen -t ed25519 -C "<your email address>"
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_ed25519
```

Add the last two lines in the .zshrc so that you do not need to do it every time you reboot the machine.

Note: I prefer it to be in a slightly different way. I have added the following line in the /.zshrc

```bash
$ tail -1 ~/.zshrc
source ~/.extended
$ cat ~/.extended
eval "$(ssh-agent -s)" > /dev/null
ssh-add ~/.ssh/id_ed25519 2> /dev/null
```

> This makes me insulated from the any refreshing of the .zshrc so that my aliases do not go away and I can get that back quickly by just adding the last line in the .zshrc.

Finally, copy the content of ~/.ssh/id_ed25519.pub and put it to the github > settings > SSH and GPG keys > Add new SSH Key. 

To check if the configuration is working, try this:

```bash
$ ssh -T git@github.com
Hi <your username>! You've successfully authenticated, but GitHub does not provide shell access.
```