# Using Roles with Chef-solo

Using roles will help us to build out more complex configurations. Before, we only installed ntp and only had one cookbook. But what if we want to install PostgreSQL, a Rails app, and Ruby 1.9.3 using RVM. Fortuneatly, we can build a role that will handle all these complexities.

## 