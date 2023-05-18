Create a Fedora container via [distrobox](https://github.com/89luca89/distrobox)
[why is this good for](https://github.com/89luca89/distrobox#what-it-does)
```
Seamlessly integrates with the rest of the operating system by providing access to the user's home directory, 
the Wayland and X11 sockets, networking, removable devices (like USB sticks), systemd journal, 
SSH agent, D-Bus, ulimits, /dev and the udev database, etc...
``` 
## Image includes:
Via pip: 
  - pipenv
  - poetry
  - pre-commit
  - git-review
  - tox
  - ipython
  - ipdb
  - docker

Via dnf:
  - zsh
  - sshpass
  - git
  - wget
  - vim
  - neovim
  - tmux
  - origin-clients (oc)
  - awscli
  - ocm-cli
- [bash-insulter](https://github.com/hkbakke/bash-insulter) :)
- [kubectl](https://kubernetes.io/docs/reference/kubectl/)
- [rosa](https://docs.openshift.com/rosa/rosa_cli/rosa-get-started-cli.html)

## Requirements
[ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html): install using package manager

## Installation
Clone the repository and install Ansible community plugins:
```bash
git clone https://github.com/myakove/distrobox-fedora.git
cd distrobox-fedora
ansible-galaxy collection install community.general
```
## Create the box
```bash
ansible-playbook -K fedora-distro-box.yml --extra-vars "home=<user home dir> user=<user name> box_name=<box name (default is distrobox-fedora)>"
```
where home will be the home directory for the user inside the box and user should be the current login user 

## Usage
```bash
distrobox-enter distrobox-fedora # Or the name of the box if passed in the command
```

## vim Usage
vim uses [AstroNvim](https://github.com/AstroNvim/AstroNvim)


## Tips
To enter automatically configure your terminal to exec ```distrobox-enter distrobox-fedora``` on each new shell  
Inside the box $HOME will be the box home (under distrobox/<box name>) and the local user home is $HOST_HOME  
To execute command on the host from the box run `distrobox-host-exec <command>`  
