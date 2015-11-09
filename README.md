# rails_for_anyone

This is a tutorial repository for anyone who wants to learn how to make a rails app, test it and deploy it on a server.

## STEP 1

### create new rails app
```bash
rails new rails_for_anyone -d postgres -T
```

### add config/database.yml to .gitignore

 make a copy of config/database.yml
```bash
cp config/database.yml config/database.example.yml
```

```
default: &default
  adapter: postgresql
  encoding: unicode
  pool: 5

development:
  <<: *defalut
  database: rails_for_anyone_development

test:
  <<: *default
  database: rails_for_anyone_test
```



and add the following line to .gitignore
```
config/database.yml
```

### set up your local database
make sure you have postgresql on your machine
```bash
rake db:create db:migrate
```


### add free template adminlte

add the following in Gemfile
```
gem 'adminlte-rails'
```

and run bundle install

```bash
bundle
```

### create rails controller named 'home'
```bash
rails g controller home
```

