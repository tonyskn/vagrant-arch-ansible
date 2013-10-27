# Vagrant Arch Linux Bootstrap

Templates for bootstrapping an Arch Linux Ansible-ready Vagrant box.

## Creating an Arch Linux Vagrant base

An up to date Arch Linux 64 bits Vagrant base box can be created using the
[Packer.io](http://packer.io) template in ./packer-arch64 (I got the template
and bootstrap script [here](https://github.com/elasticdog/packer-arch)).

Install the [latest version](http://www.packer.io/downloads.html) of Packer for your platform, then run:

```
packer build arch-template.json
vagrant box add arch64 packer_arch_virtualbox.box
```

The Vagrant base box you get is a minimal Arch installation based on the 2013.10.01 ISO.
It only has the `base` and `base-devel` package groups.  `python2` is also included so we 
could provision VMs with Ansible out of the box.

## Usage

A simple VM using the `arch64` box and provisionned with Ansible is described in `Vagrantfile`:

```
vagrant up
vagrant provision
```

Tested on an Arch host with `VirtualBox 4.3.0` and `Vagrant 1.3.5`
