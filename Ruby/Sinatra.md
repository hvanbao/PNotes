
Start server 
```ruby
rackup -p 4567
rackup -p 4567 -h 0.0.0.0
```

Call VIEWS 

```ruby
get '/' do
  erb :hello_world
end
```

## Mongo with Sinatra
1. [Mongo Model] (http://recipes.sinatrarb.com/p/models/mongo)

```ruby
gem install mongo
gem install mongodb
```

Migrate database

```ruby
rake db:create_migration NAME=create_public_bookmarks

```


