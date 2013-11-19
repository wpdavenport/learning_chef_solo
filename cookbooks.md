#Cookbooks with Chef-solo
In the directory that you created your VM you'll find 'Vagrantfile'. Open this file. Towards the bottom of the file you'll see a block of code for Chef-solo.

```
config.vm.provision :chef_solo do |chef|
    ...
end
```
To get started, uncomment the first and last lines - keeping any code inside commented.

##Setting up a Cookbook

Next we'll setup a some folders and we'll download a cookbook. Chef doesn't create a folder structure for you but we'll follow the basic convention.<br />

- Create a folder named `cookbooks`

```
- vagrant
  |- Vagrantfile
  \_ cookbooks

```

- Lets install PostgreSQL to our VM using a cookbook.
```
git clone https://github.com/opscode-cookbooks/postgresql.git
```
