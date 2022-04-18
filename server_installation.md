# Server installation

This document describes the installation of the server for HCK-CI.

## Fedora

### Update the system

* sudo dnf check-update
* sudo dnf update
* sync
* sudo reboot

### Install needed packages

* sudo dnf install net-tools
* sudo dnf groupinstall "Development Tools" "Development Libraries"
* sudo dnf install git bridge-utils docker python-devel python3-devel qemu-kvm gcc-c++ vim-enhanced samba screen wget ethtool
* sudo dnf install ruby ruby-devel
* sudo dnf builddep qemu-kvm
* sudo dnf group install --with-optional virtualization
* sudo dnf install java-1.8.0-openjdk
* sudo gem install bundler rake


### Disable SELinux

Set "SELINUX=disabled" in /etc/selinux/config, and reboot.

### Disable Firewall

* sudo systemctl disable firewalld
* sudo systemctl stop firewalld
* sudo systemctl mask firewalld
