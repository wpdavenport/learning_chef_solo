#Install Vagrant

Simple example using chef-solo and vagrant:

1. Vagrant/VirtualBox:
    - Setting up Vagrant 
		- [Install vagrant](http://www.vagrantup.co/)
		- [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads)
    - [Create basic vagrant image](http://docs.vagrantup.com/v2/getting-started/index.html) Basically just run these three commands:
```
vagrant init precise32 http://files.vagrantup.com/precise32.box
vagrant up
vagrant ssh
```
`vagrant ssh` is really to test that the VM (virtual machine) is running. Type `exit` to quit the ssh session. <br />
2. Chef-solo<br/>
In the directory that you created your VM you'll find 'Vagrantfile'. Open this file. Towards the bottom of the file you'll see a block of code for Chef-solo
```
config.vm.provision :chef_solo do |chef|
    ...
end
```
To get started, uncomment the first and last lines - keeping any code inside commented.

###Setting up a Cookbook

Next we'll setup a some folders and we'll download a cookbook. Chef doesn't create a folder structure for you but we'll follow the basic convention.
```
- vagrant
  |- Vagrantfile
  \_ cookbooks

```