# Ansible Pop!_OS setup 🧑🏼‍💻
This is my own "personal" fork for Ansible roles to setup Pop!_OS. This playbook is focused on quickly deploying a "ready to use" Pop!_OS machine. It installs a number of utilites that I use for homelab work, "dev" work and gaming. This is also where I learn and test out Git and GitHub features and tools. So if you see a lot of odd, pointless commits that would be why.


## Requirements
- Git
- Ansible 2+ (automatically installed from [Ansible offical PPA](https://launchpad.net/~ansible/+archive/ubuntu/ansible) with the provided install.sh script)


## Installation
First, you need to install Git and Ansible :
```
$ sudo apt-get install git
$ git clone https://github.com/W00glin/ansible-pop_os-desktop.git
$ cd ansible-pop_os-desktop
$ bash ./install.sh
```

Then you need to copy the `group_vars/all.yml` to `group_vars/local.yml` and customize the which role you need suits your needs. All roles are disabled by default. To customize the install, simply enable any of the boolean options in the  `all.yml` file. 

Run `ansible-playbook ansible-desktop.yml --ask-become-pass` and enter your sudo password to run the playbook

Optionaly you can run just some of the tags like:
`ansible-playbook ansible-desktop.yml --ask-become-pass --tags=common,locales`

Tags are named the same as role dirs. If a role is in a sub dir then the tag for that specific role is sepparated with a colon like: `aws:cli`. But you can also use `aws` and that should install all the roles under the `aws` dir.

## Roles included

| Role                     | Description|
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                         |**General**|
| common                  | Install a lot of usefull packages (curl, htop, less, zip ... see [corresponding task file](hhttps://github.com/W00glin/ansible-pop_os-desktop/blob/master/roles/common/tasks/main.yml) |
| java-openjdk            | Install Default Java JDK.|
|                         | **🖥️ Desktop tools 💻** |
| desktop                 | Install a lot of usefull packages (meld, tilda, vlc, xclip). |
| filezilla               | Install [Filezilla](https://filezilla-project.org/) (no particular settings, basic installation). | 
| firefox                 | Install [Firefox](https://www.mozilla.org/firefox/) (no particular settings, basic installation). | 
| gimp                    | Install [Gimp](https://www.gimp.org/) and some minor settings. |
| nautilus-plugins        | Install Nautilus plugins.|
| remmina                 | Install [Remmina](http://www.remmina.org/) RDP/SSH/VNC management GUI. |
| tmux                    | Install [tmux](https://github.com/tmux/tmux/wiki), is a terminal multiplexer. It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. And do a lot more. |
| vagrant                 | Install [Vagrant](https://www.vagrantup.com/) from online deb file. |
| virtualbox              | Install [VirtualBox](https://www.virtualbox.org/) from VirtualBox APT repositories. |
| qemu                    | Install [qemu](https://www.qemu.org/) as an alternative to virtualbox if you want to avoid virtualbox and Oracle.| 
| steam                   | Install [steam](https://store.steampowered.com/) video game platform with add GNU/Linux compatability layers.|
| numix-circle            | Install [numix-circle](https://github.com/numixproject/numix-icon-theme-circle) as the icon theme. |
| visual studio code      | Install [Visual Studio Code](https://code.visualstudio.com/) |
| neofetch                | Install [neofetch](https://github.com/dylanaraps/neofetch), a CLI tool for system info.|
| lutris                  | Install [lutris](https://lutris.net/), a game manager tool for GNU/Linux.|
| Signal                  | Install [Signal](https://signal.org/en/) for encrypted chat messaging |
| GNOME Screenshot        | Install [GNOME Screenshot](https://help.gnome.org/users/gnome-help/stable/screen-shot-record.html.en) to screenshot all the things. |
| Obsidian                | Install [Obsidian](https://obsidian.md/), a personal knowledge base and note-taking software application that operates on Markdown files. |
|                         | **📡 Services & server tools 🛠️** |
| docker                  | Install [Docker](https://www.docker.com/) and Docker compose from Docker deb repository. |
| ssh                     | Install [OpenSSH Server](http://www.openssh.com/)      | 
| ufw                     | Install [ufw](https://help.ubuntu.com/community/UFW), it is the uncomplicated firewall. |
| gufw                    | Install [gufw](https://help.ubuntu.com/community/Gufw), it is a graphical interface for ufw.|
| cutecom                 | Install [cutecom](https://help.ubuntu.com/community/Cutecom), it is a graphical interface for interacting with console ports.|
| ipmitool                | Install [ipmitool](https://help.ubuntu.com/community/IPMI), it is a CLI tool for managing old IPMI interfaces |
| gns3                    | Install [gns3](https://www.gns3.com/), a graphical network simulator and emulator. It can be used for learning advanced networking concepts without access to hardware. |
| virt-manager            | Install [virt-manager](https://virt-manager.org/) KVM managment tool. |
| wireshark               | Install [wireshark](https://www.wireshark.org/) PCAP file analysis tool. |
| nmap                    | Install [nmap](https://nmap.org/), a common CLI tool for network troubleshooting and information gathering. |
| openvpn                 | Install [openvpn](https://help.ubuntu.com/community/OpenVPN), for utilizing VPN configs for PIA. |
| vagrant                 | Install [Vagrant](https://www.vagrantup.com/) from online deb file. |

## Contributing
Do whatever you want. This is my fork. I don't plan on upstreaming any of my changes. If you like it, go ahead and fork it, or not. If you want to make changes, feel free to submit a PR.
