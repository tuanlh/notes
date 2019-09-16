# My install and config (personal-like)

```bash
sudo apt install git
git config --global user.name tuanlh
git config --global user.email "tuanlh2704@gmail.com"
git config --global credential.helper store
git config --global alias.st status
git config --global alias.ci commit
git config --global alias.br branch
git config --global alias.co checkout
```

## Explain above features

This command:

```bash
git config --global user.name tuanlh
git config --global user.email "tuanlh2704@gmail.com"
```

to config username and email default.

This command:

```bash
git config --global credential.helper store
```

to remember username and password for push/pull again.

This command:

```bash
git config --global alias.st status
git config --global alias.ci commit
git config --global alias.br branch
git config --global alias.co checkout
```

to alias some command to quick type.
