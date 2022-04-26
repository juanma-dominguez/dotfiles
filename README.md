# dotfiles

[Ansible](https://www.ansible.com/)-based dotfile setup for macOS systems that is really simple and easy to understand. Copy from [frdmn](https://github.com/frdmn/dotfiles).

### Features

- Dotfile wrapper based on [Ansible](https://www.ansible.com/)
  - dotfiles symlink checks
  - Homebrew and Cask checks ensure that your packages / GUI apps are installed and up-to-date
  - Mac App Store package checks
  - Node `npm` package checks
  - Ruby `gem` package checks
  - Python `pip` package checks
  - macOS `defaults` (plist settings)
  - Docker host cleanup/prune
- [Vundle](https://github.com/gmarik/Vundle.vim) VIm plugin manager
- Several additional, preconfigured ZSH plugins (using [zplug](https://github.com/zplug/zplug)):
  - [zsh-history-substring-search](https://github.com/zsh-users/zsh-history-substring-search) plugin
  - [zsh-notify](https://github.com/marzocchi/zsh-notify) plugin
  - [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-notify) plugin
  - [zsh-autosuggestions](https://github.com/tarruda/zsh-autosuggestions) plugin
- Configured GnuPG including `gpg-agent` and enabled commit signatures in git
- [One Dark Pro](https://github.com/Binaryify/OneDark-Pro) themes for iTerm and VSCode (even though VSCode is _currently_ controlled by the [built-in sync](https://code.visualstudio.com/docs/editor/settings-sync))

### Installation

1. Make sure to install Homebrew and the Ansible packages:
   `brew install ansible`
1. Fork this repository:
   `git clone https://github.com/juanma-dominguez/dotfiles ~/.dotfiles`
1. Run the bootstrap script to initially install and setup the dotfiles:
   `~/.dotfiles/bootstrap`

### Available commands

```sh
# Install/update all available tags
$ dotfiles

# Install/update a specific tag
$ dotfiles <tag>
```

### Information

Explanation of the directories:

```
./files/
└── This directory contains all optional files that are not related to
    Ansible roles in specific. For example: dotfile source files, iTerm
    configuration files, etc.

./files/dotfiles/
└── This folder contains all the source dotfiles.

./files/iterm2/
└── This folder contains the iTerm 2 plist configuration.

./roles/
└── In this directory you will find all available Ansible roles that I
    currently use within this project.

./roles/{rolename}/defaults/main.yml
└── This file contains variables and lists to work with in the actual
    Ansible tasks, like package names/lists.

./roles/{rolename}/tasks/main.yml
└── This is the actual Ansible tasks that uses the variable (defaults)
    file and proceeds with the role specific function.

./bootstrap
└── Basically the base wrapper that I use to install and update the
    dotfiles as well as interact with the `ansible-playbook` command.

./hosts
└── The inventory file for Ansible, for now it only contains the
    localhost machine
```

### Todo

- encrypt email
- manage ssh keys
- npm error, works with sudo

### License

[MIT](LICENSE)

### Version

2.0
