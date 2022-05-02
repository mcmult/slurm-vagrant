# Vagrant Setup for Slurm testing.

## Setting up Vagrant on Ubuntu

### Get the latest vagrant

curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -

echo "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main
#deb-src [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/vagrant.list

sudo apt-get update && apt-get install vagrant

### Install libvirt/qemu

sudo apt-get install qemu libvirt-daemon-system libvirt-clients libxslt-dev libxml2-dev libvirt-dev zlib1g-dev ruby-dev ruby-libvirt ebtables dnsmasq-base

### Setup the latest vagrant libvirt plugin

vagrant plugin install vagrant-libvirt
