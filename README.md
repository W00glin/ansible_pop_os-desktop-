# Ansible Pop!_OS setup 🧑🏼‍💻
This is my own "personal" fork for Ansible roles to setup Pop!_OS. This playbook is focused on quickly deploying a "ready to use" Pop!_OS machine. It install a number of utilites that I use for homelab work, "dev" work and gaming.


## Requirements
- Git
- Ansible 2+ (automatically installed from [Ansible offical PPA](https://launchpad.net/~ansible/+archive/ubuntu/ansible) with the provided install.sh script)


## Installation
First, you need to install Git and Ansible :
```
$ sudo apt-get install git
$ git clone https://github.com/sys0dm1n/ansible-ubuntu-desktop.git
$ cd ansible-ubuntu-desktop
$ bash ./install.sh
```

Then you need to copy the `group_vars/all.yml` to `group_vars/local.yml` and customize the which role you need suits your needs. All roles except `locales`,`common`, and `desktop` are disabled by default.

Run `ansible-playbook ansible-desktop.yml --ask-become-pass` and enter your sudo password to run the playbook

Optionaly you can run just some of the tags like:
`ansible-playbook ansible-desktop.yml --ask-become-pass --tags=common,locales`

Tags are named the same as role dirs. If a role is in a sub dir then the tag for that specific role is sepparated with a colon like: `aws:cli`. But you can also use `aws` and that should install all the roles under the `aws` dir.

## Roles included

| Role                     | Description|
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                         |**General**|
| common                  | Install a lot of usefull packages (curl, htop, less, zip ... see [corresponding task file](https://github.com/sys0dm1n/ansible-ubuntu-desktop/blob/master/roles/common/tasks/main.yml)) |
| locales                 | Configure system locales and timezone. I currently have it disabled |
| java-openjdk            | Install Default Java JDK|
|                         | **Desktop tools** |
| desktop                 | Install a lot of usefull packages (meld, tilda, vlc, xclip)|
| filezilla               | Install [Filezilla](https://filezilla-project.org/) (no particular settings, basic installation) | 
| firefox                 | Install [Firefox](https://www.mozilla.org/firefox/) (no particular settings, basic installation) | 
| gimp                    | Install [Gimp](https://www.gimp.org/) and some minor settings |
| libreoffice             | Install [LibreOffice](https://www.libreoffice.org/) using [LibreOffice 5.1 PPA](https://launchpad.net/~libreoffice/+archive/ubuntu/libreoffice-5-1) |
| nautilus-plugins        | Install Nautilus plugins|
| remmina                 | Install [Remmina](http://www.remmina.org/) |
| tmux                    | Install [tmux](https://github.com/tmux/tmux/wiki) tmux is a terminal multiplexer. It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. And do a lot more. |
| vagrant                 | Install [Vagrant](https://www.vagrantup.com/) from online deb file|
| virtualbox              | Install [VirtualBox](https://www.virtualbox.org/) from VirtualBox APT repositories | 
|                         | **Services & server tools** |
| docker                  | Install [Docker](https://www.docker.com/) and Docker compose from Docker deb repository|
| ssh                     | Install [OpenSSH Server](http://www.openssh.com/)      | 
| ufw                     | Install [ufw](https://help.ubuntu.com/community/UFW) |
| gufw                    | Install [gufw](https://help.ubuntu.com/community/Gufw) graphical interface for ufw.|
| cutecom                 | Install [cutecom](https://help.ubuntu.com/community/Cutecom) graphical interface for interacting with console ports.|
| ipmitool                | Install [ipmitool](https://help.ubuntu.com/community/IPMI) CLI tool for managing old IPMI interfaces |
| gns3                    | Install [gns3](https://www.gns3.com/) is a graphical network simulator and emulator. It can be used for learning advanced networking concepts without access to hardware. |


## Contributing
Do whatever you want. This is my fork. I don't plan on upstreaming any of my changes. If you like it, go ahead and fork and if you want to make changes, feel free to submit a PR.
