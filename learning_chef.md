#Learning Chef with Chef-solo

" Chef is an infrastructure automation and configuration management framework. Simply put, Chef is 'Infrastructure as Code' ". - [opscode.com](https://learnchef.opscode.com/)

This pdf is dedicated to my leanring of chef. I had a difficult time finding a simple "Hello World" example for learning Chef and a even harder time learning by reading the Chef leanrning site. My first break through was with a blog post by [Jonathan Otto](http://jonathanotto.com/blog/chef-tutorial-in-minutes.html).  

This inspired me to modify it using Vagrant and create a basic "Hello World" example.

## 10,000 Feet View

### Think of Chef as having 3 components:

- *Chef server* Here you store all your configurations for all of your nodes and roles. The chef server distributes cookbooks to the nodes.
- *Chef clients (Nodes)* Every client will be registered as a node at the chef server. Each node will receive its cookbooks from the chef server.
- *Your workstation* You will control each node using chefs command line tool knife.

### Chef-solo: A breakdown

1. For our purposes, chef-solo is built into vagrant. There is no separate gem or library you need to install.
2. Create a basic structure with one or more cookbooks that looks like this:
    ```
    ~/vagrant/cookbooks/NAME_OF_PACKAGE/
    ```
3. Roles - Which can take multiple cookbooks (even specific roles within a cookbook) for installing software packages
4. Overrides or Attributes: It doesn't take long before you'll be confronted with creating or overwriting attributes using JSON or specifing attributes in a Ruby file. Say you want to create a default user for your database or overwrite default configurations for PostgreSQL. There are also ways to make or overwrite configurations based on OS. Configuration creation is apart of Chef and Chef-solo. Vagrant has some good documentation on their site too for [chef-solo](http://docs.vagrantup.com/v2/provisioning/chef_solo.html).