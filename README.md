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

* config `inventory` file

```
[target]
$TARGET_ADDR
```

* execute

```
$ ansible-playbook -i inventory site.yml [-k -c paramiko]
```

## After Execution

* finish sshd

# Memo

* Base package
    * mac: `xcode-select --install`
    * redhat: `yum install @base`
    * debian: `apt install build-essential software-properties-common`
* Repository
    * mac: install homebrew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)`
    * redhat: `yum install epel-release`
    * debian: `add-apt-repository ppa:neovim-ppa/unstable`
* Xserver
    * mac/linux: default ok
    * wsl: download from https://sourceforge.net/projects/vcxsrv/ & install
* Python
    * install pyenv from https://github.com/pyenv/pyenv
* NeoVim
    * python3
        * `pip install neovim`
* Vim Plugin
    * python3
        * `pip install jedi flask autopep8`
    * golang
        * `go get -u github.com/nsf/gocode`
        * `go get -u github.com/golang/lint/golint`
    * C/C++
        * mac: `brew install clang-format`
        * redhat: TODO
        * debian: `apt install clang-format`
* mattn/memo
    * peco
        * install from https://github.com/peco/peco
    * GoogleDrive ($HOME/GoogleDrive)
        * for Linux: https://github.com/harababurel/gcsf
* tmux
    * shared clipboard
        * mac: nothing required (tmux2.6+)
        * wsl: download from https://github.com/equalsraf/win32yank/releases & deploy to $PATH
        * redhat: `yum install xsel`
        * debian: `apt install xsel`

* Other
    * mac
        * cask: `brew install cask`
        * macvim: `brew cask install macvim`
    * wsl
        * /bin/open: `cmd.exe /c start $@
`

