# Vagrant Setup for Slurm testing.

## Setting up Vagrant on Ubuntu

### Add latest vagrant repo

    curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
    echo "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main
    #deb-src [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/vagrant.list
    sudo apt-get update

### Install vagrant/libvirt/qemu

    sudo apt-get install vagrant qemu libvirt-daemon-system libvirt-clients \
        libxslt-dev libxml2-dev libvirt-dev zlib1g-dev ruby-dev ruby-libvirt \
        ebtables dnsmasq-base

### Setup the latest vagrant libvirt plugin

    vagrant plugin install vagrant-libvirt

### Add yourself to the libvirt group

    sudo usermod -a -G libvirt $USER

For this to take full effect, you may need to log out and back in.  You can
veryfy that you are in the group with:

    groups

## Basic usage

After entering a directory with a 'Vagrantfile' you can run a number of commands
to interact with the vm.  Most of these will also accept a "hostname" as an
argument so if you have multiple machines defined you can pick which one to
perform an action on.

### Starting a VM/Group of VMs

    vagrant up

When run from a directory with a VagrantFile will start a vm if it is down, and
prepare/build the vm if it is the first time running it.

### Stopping VM(s)

   vagrant halt

Stops a running vm.

   vagrant destroy

Shuts down and then destroys the vms.

### Accessing a VM

   vagrant ssh

Will ssh to the vm if it is up.

## Useful Links

https://github.com/hashicorp/vagrant
https://github.com/vagrant-libvirt/vagrant-libvirt
