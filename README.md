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

    usermod -a -G libvirt $USER

## Useful Links

https://github.com/hashicorp/vagrant
https://github.com/vagrant-libvirt/vagrant-libvirt
