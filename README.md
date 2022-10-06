Create a Fedora container via [distrobox](https://github.com/89luca89/distrobox)

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
ansible-playbook fedora-distro-box.yaml --extra-vars "home=<user home dir> user=<user name>"
```
where home will be the home directory for the user inside the box and user should be the current login user 

## Usage
```bash
export DBX_CONTAINER_MANAGER="docker"
distrobox-enter distrobox-fedora
```

## Tips
To enter automatically configure your terminal to exec ```distrobox-enter distrobox-fedora``` on each new shell  
Inside the box $HOME will be the box home (under distrobox/fedora) and the local user home is $HOST_HOME  
To execute command on the host from the box run `distrobox-host-exec <command>`  

