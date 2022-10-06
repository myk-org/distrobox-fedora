install ansible
ansible-galaxy collection install community.general
ansible-playbook fedora-distro-box.yaml --extra-vars "home=<user home dir> user=<user name>"
distrobox-enter distrobox-fedora