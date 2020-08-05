# Development Guides 2020

### Windows development environment

#### prerequisite

- [update windows kernel](https://aka.ms/wsl2kernel)

#### needed apps

- [wsl 2](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
- [windows terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab)
- [VScode](https://code.visualstudio.com/)

#### needed packages

- [oh-my-zsh]()
```
$ sudo apt install zsh
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
- [nvm]()
```
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash # then copy export path to .zshrc
```
- [NodeJS]()
```
$ nvm install node
```

- [MariaDB](https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04)
```
$ sudo apt install mariadb-server
$ sudo apt mysql_secure_installation
```

#### configurations

- [Windows-Linux configuration](https://dev.to/seanwelshbrown/setting-up-windows-subsystem-for-linux-wsl-2-as-a-bootcamp-grad-1e7)

## macOS development environment

#### prerequisite

- [Xcode command utilities](https://osxdaily.com/2014/02/12/install-command-line-tools-mac-os-x/)
```
$ xcode-select --install
```

#### needed apps

- [Homebrew](https://brew.sh/)
- [VScode](https://code.visualstudio.com/)

#### needed packages

- [oh-my-zsh]()
```
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
- [NodeJS]()

```
$ brew install node
```

- [MariaDB]()

```
$ brew install mariadb
```
