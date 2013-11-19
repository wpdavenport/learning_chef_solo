#Install Vagrant

Simple example using chef-solo and vagrant:

1. Vagrant/VirtualBox:
    - Setting up Vagrant 
		- [Install vagrant](http://www.vagrantup.co/)
		- [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads)
    - [Create basic vagrant image per thier instruction](http://docs.vagrantup.com/v2/getting-started/index.html)
2. Chef-solo<br/>
In the directory that you created your VM you'll find 'Vagrantfile'. Open this file. Towards the bottom of the file you'll see a block of code for Chef-solo
```
config.vm.provision :chef_solo do |chef|
    ...
end
```
To get started, uncomment the first and last lines - keeping any code inside commented.