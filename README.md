# Ansible playbook for GNOME workstation setup

Ansible playbook with some basic workstation setup. Tested with Fedora, Ubuntu but might work with others too. GNOME only.

#### Steps
1. Ensure ansible is installed.

   Using `dnf` for Fedora
   ```
   sudo dnf install ansible -y
   ```

   or, `apt` for Ubuntu

   ```
   sudo apt update
   sudo apt install software-properties-common
   sudo add-apt-repository --yes --update ppa:ansible/ansible
   sudo apt install ansible
   ```
1. Run `ansible-pull`

   ```
   sudo ansible-pull -U https://github.com/littlegraycells/ansible-playbooks.git
   ```