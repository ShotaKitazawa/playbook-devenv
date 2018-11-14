# About

Setup development environment for Mac/Linux/WSL

# Execution

## Before execution

### Mac

TODO

### Linux

* install & start sshd

### WSL (c.f. Ubuntu)

* install sshd

```
apt install openssh-server
```

* config sshd

```
sed -i -e 's|^\(PermitRootLogin\).*|\1 yes|g' /etc/ssh/sshd_config
sed -i -e 's|^\(PasswordAuthentication\).*|\1 no|g' /etc/ssh/sshd_config
sed -i -e 's|^\(UsePrivilegeSeparation\).*|\1 no|g' /etc/ssh/sshd_config
```

* start sshd

```
/usr/sbin/sshd
```

## Execute playbook

```
$ ansible-playbook -i inventory site.yml [-k -c paramiko]
```

## After Execution

* finish sshd

# Memo

* NeoVim
    * python3
        * `pip install neovim`
* Vim Plugin
    * python3
        * `pip install
* mattn/memo
    * peco
    * GoogleDrive ($HOME/GoogleDrive)
        * for Linux: https://github.com/harababurel/gcsf
* tmux
    * shared clipboard
        * mac: nothing required
        * wsl: download from https://github.com/equalsraf/win32yank/releases & deploy to $PATH
        * redhat: `yum install xsel`
        * debian: `apt install xsel`

## Mac


```
brew update
brew install python3
brew install neovim/neovim/neovim
pip3 install neovim
# MacVim
brew install cask
brew cask install macvim
# Go
brew install golang
go get -u github.com/nsf/gocode
go get -u github.com/golang/lint/golint
# C/C++
brew install clang-format
# Python
pip3 install jedi flask autopep8
# LaTeX
brew cask install mactex
brew install ghostscript
brew install imagemagick
```
