#TITLE
```ruby
name 'my_server_setup'

description 'Configures postgres, postgres user and openssl'

run_list 'recipe[openssl]', 'recipe[postgresql]', 'recipe[postgresql::server]', ''
```