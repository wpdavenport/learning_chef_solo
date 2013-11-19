#Learning Chef

" Chef is an infrastructure automation and configuration management framework. Simply put, Chef is 'Infrastructure as Code' ". - [opscode.com](https://learnchef.opscode.com/)


This pdf is dedicated to my leanring of chef. I had a difficult time finding a simple "Hello World" example for learning Chef and a even harder time learning by reading the Chef leanrning site. My first break through was with a blog post by [Jonathan Otto](http://jonathanotto.com/blog/chef-tutorial-in-minutes.html).  

I decided to take this idea and modify it using Vagrant and create a basic "Hello World" example that is a reflection of my learning proceess.

## 10,000 Feet View

Think of Chef as having 4 components:

1. A gem [`chef`](http://rubygems.org/gems/chef) - For our purposes chef-solo is built into vagrant.
2. Create one or more cookbooks in a structure that looks like this ~/vagrant/cookbooks/NAME_OF_PACKAGE/
3. Roles - Which can take multiple cookbooks (even specific roles within that cookbook) for installing software packages
4. Overrides or Attribures: It doesn't take long before you'll be confronted with creating or overwriting attributes using JSON or specifing attributes in a Ruby file. Say you want to create a default user for your database or overwrite default configurations for PostgreSQL. There are also ways to make configurations based on OS. 