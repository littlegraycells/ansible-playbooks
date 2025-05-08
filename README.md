# Ansible playbook for GNOME workstation setup

Ansible playbook for Fedora workstation. Tested on Fedora 41 but `apt` based distros like Ubuntu or Debian _should_ also work. GNOME (wayland) only.

#### Steps
1. Ensure git and ansible are installed.

   Using `dnf` for Fedora
   ```
   sudo dnf install git ansible -y
   ```

   or, `apt` for Ubuntu/Debian etc

   ```
   sudo apt update
   sudo apt install git software-properties-common -y
   sudo add-apt-repository --yes --update ppa:ansible/ansible
   sudo apt install ansible -y
   ```
1. Run `ansible-pull`

   ```
   sudo ansible-pull -U https://github.com/littlegraycells/ansible-playbooks.git -C main
   ```

1. (optional) By default, this will also include developer tooling. To skip it pass `devel: false`
   ```
   sudo ansible-pull -U https://github.com/littlegraycells/ansible-playbooks.git -C main -e '{ devel: false }'
   ```
1. Additional options
   ```
   {
	devel: true,		// Install dev tooling. Defaults to true
	devel-flutter: false,	// Installs flutter tooling. Defaults to false
	kill_gnome: true	// Kills the GNOME session at the end to apply GNOME changes. Defaults to false
   }
1. (optional) Follow [instructions](https://discuss.linuxcontainers.org/t/tutorial-installing-the-web-ui-for-incus-on-fedora-or-other-redhat-based-distros/20986/1) for setting up a Web GUI for Incus.