# Using Roles with Chef-solo

Using roles will help us to build out more complex configurations. Before, we only installed ntp and only had one cookbook. But no we want to install PostgreSQL, a Rails app, and Ruby 1.9.3 using RVM. Fortuneatly, we can build a role that will handle all these complexities.

This process can be a lot of trial and error. Some cookbooks have requirements or dependencies. Initially, we don't really know how to know what they are. So we'll let provisioning give us some insight on what is missing and fix it as we go along.

## Installing via Role
    
Let's start off by updating our current configuration to use a role. Then we can begin to add other roles.
```
config.vm.provision :chef_solo do |chef|
  chef.cookbooks_path = "cookbooks"
  chef.roles_path = "roles"
  chef.add_role "my_server_setup"
end

```

## 