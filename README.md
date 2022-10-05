install ansible
ansible-galaxy collection install community.general
ansible-playbook fedora-distro-box.yaml --extra-vars "home=/home/myakove user=myakove"
distrobox-enter fedora