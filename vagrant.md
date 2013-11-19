#Install Vagrant

" Chef is an infrastructure automation and configuration management framework. Simply put, Chef is 'Infrastructure as Code' ". - [opscode.com](https://learnchef.opscode.com/)


This pdf is dedicated to my leanring of chef. I had a difficult time finding a simple "Hello World" example for learning Chef and a even harder time learning by reading the Chef leanrning site. My first break through was with a blog post by [Jonathan Otto](http://jonathanotto.com/blog/chef-tutorial-in-minutes.html). Here he lays out an overview and a way to get working. 

I decided to take this idea and modify it using Vagrant. 

This is the most basic example or the "Hello World" for learning Chef. In my initial, learning of Chef I found it rather difficult ...

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