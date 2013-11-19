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
cd cookbooks
git clone https://github.com/opscode-cookbooks/ntp.git
```

### Vagrant VM and Chef-solo
When you do `vagrant up` and chef-solo is enabled in the Vagrantfile, the specified folders within the `config :chef_solo` block will become a shared folder. If there are any changes within that folder you will need to reload. To do that run:
```
vagrant reload
```
You should see the following output that lets you know that the chef-solo folers are now shared.
```
...
[default] Mounting shared folders...
[default] -- /vagrant
[default] -- /tmp/vagrant-chef-1/chef-solo-1/cookbooks
```

### Finding a Role Name Within a Recipe
Within the ntp folder you will find a file called metedata.rb. Once you open the file at the very top you'll see `name`. This is the name of the role for this cookbook. We will use this in our config when specifying a role.

### Roles
"A role is a way to define certain patterns and processes that exist across nodes in an organization as belonging to a single job function" ~ chef site.

I see a role is a way to specify a job. We are starting out by directly calling a role name within a recipe. Later we'll create a role file that will do more than one thing. 

### Config Chef-solo / Update Vagrant and Run Chef-solo
Let's enable and setup our config and finally get to running chef-solo. Update the config block to the following:
```
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "ntp"
  end
```

For Chef-solo Vagrant offers a special command called `provision`. This runs chef-solo for us. If we run this command now we'll get the following error:
```
$ vagrant provision
[default] Running provisioner: chef_solo...
Shared folders that Chef requires are missing on the virtual machine.
This is usually due to configuration changing after already booting the
machine. The fix is to run a `vagrant reload` so that the proper shared
folders will be prepared and mounted on the VM.
```
To fix this we'll `reload` then `provision`.
```
vagrant reload
vagrant provision
```

You've completed your first running of chef-solo. Now onto utilizing roles.
