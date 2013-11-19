##Install Vagrant

Simple example using chef-solo and vagrant:

1. Vagrant/VirtualBox:
    - Setting up Vagrant 
		- [Install vagrant](http://www.vagrantup.co/)
		- [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads)
    - [Create basic vagrant image](http://docs.vagrantup.com/v2/getting-started/index.html) 
    - Create a folder called vagrant (could be any name really).
```
mkdir vagrant
cd vagrant
```
In this directory, run these three commands:
```
vagrant init precise32 http://files.vagrantup.com/precise32.box
vagrant up
vagrant ssh
```

`vagrant ssh` is really to test that the VM (virtual machine) is running. Type `exit` to quit the ssh session.