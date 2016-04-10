# Prerequisites

**Installing PostgreSQL**

<http://www.postgresql.org/download/linux/ubuntu/>

>    sudo apt-get install postgresql postgresql-contrib libpq-dev python-dev

Installation of postgres creates a "postgres" user by default

> sudo su - postgres

```
[sudo] password for droid: 
postgres@droidserver:~$ psql
psql (9.5.2)
Type "help" for help.

postgres=# 
```

**Creating the application**

> onBB/Ruby-on-Rails$ rails new publication-app --database=postgresql

```
      create  
      create  README.rdoc
      create  Rakefile
      create  config.ru
      create  .gitignore
      create  Gemfile
      create  app
      create  app/assets/javascripts/application.js
      create  app/assets/stylesheets/application.css
      create  app/controllers/application_controller.rb
      create  app/helpers/application_helper.rb
      create  app/views/layouts/application.html.erb
      create  app/assets/images/.keep
      create  app/mailers/.keep
      create  app/models/.keep
      create  app/controllers/concerns/.keep
      create  app/models/concerns/.keep
      create  bin
      create  bin/bundle
      create  bin/rails
      create  bin/rake
      create  bin/setup
      create  config
      create  config/routes.rb
      create  config/application.rb
      create  config/environment.rb
      create  config/secrets.yml
      create  config/environments
      create  config/environments/development.rb
      create  config/environments/production.rb
      create  config/environments/test.rb
      create  config/initializers
      create  config/initializers/assets.rb
      create  config/initializers/backtrace_silencers.rb
      create  config/initializers/cookies_serializer.rb
      create  config/initializers/filter_parameter_logging.rb
      create  config/initializers/inflections.rb
      create  config/initializers/mime_types.rb
      create  config/initializers/session_store.rb
      create  config/initializers/wrap_parameters.rb
      create  config/locales
      create  config/locales/en.yml
      create  config/boot.rb
      create  config/database.yml
      create  db
      create  db/seeds.rb
      create  lib
      create  lib/tasks
      create  lib/tasks/.keep
      create  lib/assets
      create  lib/assets/.keep
      create  log
      create  log/.keep
      create  public
      create  public/404.html
      create  public/422.html
      create  public/500.html
      create  public/favicon.ico
      create  public/robots.txt
      create  test/fixtures
      create  test/fixtures/.keep
      create  test/controllers
      create  test/controllers/.keep
      create  test/mailers
      create  test/mailers/.keep
      create  test/models
      create  test/models/.keep
      create  test/helpers
      create  test/helpers/.keep
      create  test/integration
      create  test/integration/.keep
      create  test/test_helper.rb
      create  tmp/cache
      create  tmp/cache/assets
      create  vendor/assets/javascripts
      create  vendor/assets/javascripts/.keep
      create  vendor/assets/stylesheets
      create  vendor/assets/stylesheets/.keep
         run  bundle install
Fetching gem metadata from https://rubygems.org/...........
Fetching version metadata from https://rubygems.org/...
Fetching dependency metadata from https://rubygems.org/..
Resolving dependencies.......
Using rake 11.1.2
Using i18n 0.7.0
Using json 1.8.3
Using minitest 5.8.4
Using thread_safe 0.3.5
Using tzinfo 1.2.2
Using activesupport 4.2.4
Using builder 3.2.2
Using erubis 2.7.0
Using mini_portile2 2.0.0
Using nokogiri 1.6.7.2
Using rails-deprecated_sanitizer 1.0.3
Using rails-dom-testing 1.0.7
Using loofah 2.0.3
Using rails-html-sanitizer 1.0.3
Using actionview 4.2.4
Using rack 1.6.4
Using rack-test 0.6.3
Using actionpack 4.2.4
Using globalid 0.3.6
Using activejob 4.2.4
Using mime-types-data 3.2016.0221
Using mime-types 3.0
Using mail 2.6.4
Using actionmailer 4.2.4
Using activemodel 4.2.4
Using arel 6.0.3
Using activerecord 4.2.4
Using debug_inspector 0.0.2
Using binding_of_caller 0.7.2
Using bundler 1.10.6
Using byebug 8.2.2
Using coffee-script-source 1.10.0
Using execjs 2.6.0
Using coffee-script 2.4.1
Using thor 0.19.1
Using railties 4.2.4
Using coffee-rails 4.1.1
Using concurrent-ruby 1.0.1
Using multi_json 1.11.2
Using jbuilder 2.4.1
Using jquery-rails 4.1.1
Installing pg 0.18.4 with native extensions
Using sprockets 3.5.2
Installing sprockets-rails 3.0.4
Using rails 4.2.4
Installing rdoc 4.2.2
Installing sass 3.4.22
Using tilt 2.0.2
Using sass-rails 5.0.4
Using sdoc 0.4.1
Installing spring 1.6.4
Using turbolinks 2.5.3
Installing uglifier 3.0.0
Using web-console 2.3.0
Bundle complete! 12 Gemfile dependencies, 55 gems now installed.
Use `bundle show [gemname]` to see where a bundled gem is installed.
Post-install message from rdoc:
Depending on your version of ruby, you may need to install ruby rdoc/ri data:

<= 1.8.6 : unsupported
 = 1.8.7 : gem install rdoc-data; rdoc-data --install
 = 1.9.1 : gem install rdoc-data; rdoc-data --install
>= 1.9.2 : nothing to do! Yay!
         run  bundle exec spring binstub --all
* bin/rake: spring inserted
* bin/rails: spring inserted
```

### Snapshots

**Application Structure**

![](_misc/application%20structure.png)

**Expanded Application Structure**

![](_misc/expanded%20application%20structure.png)


### Exploring Contents

*publication-app/Gemfile*

```ruby
source 'https://rubygems.org'


# Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
gem 'rails', '4.2.4'
# Use postgresql as the database for Active Record
gem 'pg'
# Use SCSS for stylesheets
gem 'sass-rails', '~> 5.0'
# Use Uglifier as compressor for JavaScript assets
gem 'uglifier', '>= 1.3.0'
# Use CoffeeScript for .coffee assets and views
gem 'coffee-rails', '~> 4.1.0'
# See https://github.com/rails/execjs#readme for more supported runtimes
# gem 'therubyracer', platforms: :ruby

# Use jquery as the JavaScript library
gem 'jquery-rails'
# Turbolinks makes following links in your web application faster. Read more: https://github.com/rails/turbolinks
gem 'turbolinks'
# Build JSON APIs with ease. Read more: https://github.com/rails/jbuilder
gem 'jbuilder', '~> 2.0'
# bundle exec rake doc:rails generates the API under doc/api.
gem 'sdoc', '~> 0.4.0', group: :doc

# Use ActiveModel has_secure_password
# gem 'bcrypt', '~> 3.1.7'

# Use Unicorn as the app server
# gem 'unicorn'

# Use Capistrano for deployment
# gem 'capistrano-rails', group: :development

group :development, :test do
  # Call 'byebug' anywhere in the code to stop execution and get a debugger console
  gem 'byebug'
end

group :development do
  # Access an IRB console on exception pages or by using <%= console %> in views
  gem 'web-console', '~> 2.0'

  # Spring speeds up development by keeping your application running in the background. Read more: https://github.com/rails/spring
  gem 'spring'
end
```

*publication-app/Gemfile.lock*

```
GEM
  remote: https://rubygems.org/
  specs:
    actionmailer (4.2.4)
      actionpack (= 4.2.4)
      actionview (= 4.2.4)
      activejob (= 4.2.4)
      mail (~> 2.5, >= 2.5.4)
      rails-dom-testing (~> 1.0, >= 1.0.5)
    actionpack (4.2.4)
      actionview (= 4.2.4)
      activesupport (= 4.2.4)
      rack (~> 1.6)
      rack-test (~> 0.6.2)
      rails-dom-testing (~> 1.0, >= 1.0.5)
      rails-html-sanitizer (~> 1.0, >= 1.0.2)
    actionview (4.2.4)
      activesupport (= 4.2.4)
      builder (~> 3.1)
      erubis (~> 2.7.0)
      rails-dom-testing (~> 1.0, >= 1.0.5)
      rails-html-sanitizer (~> 1.0, >= 1.0.2)
    activejob (4.2.4)
      activesupport (= 4.2.4)
      globalid (>= 0.3.0)
    activemodel (4.2.4)
      activesupport (= 4.2.4)
      builder (~> 3.1)
    activerecord (4.2.4)
      activemodel (= 4.2.4)
      activesupport (= 4.2.4)
      arel (~> 6.0)
    activesupport (4.2.4)
      i18n (~> 0.7)
      json (~> 1.7, >= 1.7.7)
      minitest (~> 5.1)
      thread_safe (~> 0.3, >= 0.3.4)
      tzinfo (~> 1.1)
    arel (6.0.3)
    binding_of_caller (0.7.2)
      debug_inspector (>= 0.0.1)
    builder (3.2.2)
    byebug (8.2.2)
    coffee-rails (4.1.1)
      coffee-script (>= 2.2.0)
      railties (>= 4.0.0, < 5.1.x)
    coffee-script (2.4.1)
      coffee-script-source
      execjs
    coffee-script-source (1.10.0)
    concurrent-ruby (1.0.1)
    debug_inspector (0.0.2)
    erubis (2.7.0)
    execjs (2.6.0)
    globalid (0.3.6)
      activesupport (>= 4.1.0)
    i18n (0.7.0)
    jbuilder (2.4.1)
      activesupport (>= 3.0.0, < 5.1)
      multi_json (~> 1.2)
    jquery-rails (4.1.1)
      rails-dom-testing (>= 1, < 3)
      railties (>= 4.2.0)
      thor (>= 0.14, < 2.0)
    json (1.8.3)
    loofah (2.0.3)
      nokogiri (>= 1.5.9)
    mail (2.6.4)
      mime-types (>= 1.16, < 4)
    mime-types (3.0)
      mime-types-data (~> 3.2015)
    mime-types-data (3.2016.0221)
    mini_portile2 (2.0.0)
    minitest (5.8.4)
    multi_json (1.11.2)
    nokogiri (1.6.7.2)
      mini_portile2 (~> 2.0.0.rc2)
    pg (0.18.4)
    rack (1.6.4)
    rack-test (0.6.3)
      rack (>= 1.0)
    rails (4.2.4)
      actionmailer (= 4.2.4)
      actionpack (= 4.2.4)
      actionview (= 4.2.4)
      activejob (= 4.2.4)
      activemodel (= 4.2.4)
      activerecord (= 4.2.4)
      activesupport (= 4.2.4)
      bundler (>= 1.3.0, < 2.0)
      railties (= 4.2.4)
      sprockets-rails
    rails-deprecated_sanitizer (1.0.3)
      activesupport (>= 4.2.0.alpha)
    rails-dom-testing (1.0.7)
      activesupport (>= 4.2.0.beta, < 5.0)
      nokogiri (~> 1.6.0)
      rails-deprecated_sanitizer (>= 1.0.1)
    rails-html-sanitizer (1.0.3)
      loofah (~> 2.0)
    railties (4.2.4)
      actionpack (= 4.2.4)
      activesupport (= 4.2.4)
      rake (>= 0.8.7)
      thor (>= 0.18.1, < 2.0)
    rake (11.1.2)
    rdoc (4.2.2)
      json (~> 1.4)
    sass (3.4.22)
    sass-rails (5.0.4)
      railties (>= 4.0.0, < 5.0)
      sass (~> 3.1)
      sprockets (>= 2.8, < 4.0)
      sprockets-rails (>= 2.0, < 4.0)
      tilt (>= 1.1, < 3)
    sdoc (0.4.1)
      json (~> 1.7, >= 1.7.7)
      rdoc (~> 4.0)
    spring (1.6.4)
    sprockets (3.5.2)
      concurrent-ruby (~> 1.0)
      rack (> 1, < 3)
    sprockets-rails (3.0.4)
      actionpack (>= 4.0)
      activesupport (>= 4.0)
      sprockets (>= 3.0.0)
    thor (0.19.1)
    thread_safe (0.3.5)
    tilt (2.0.2)
    turbolinks (2.5.3)
      coffee-rails
    tzinfo (1.2.2)
      thread_safe (~> 0.1)
    uglifier (3.0.0)
      execjs (>= 0.3.0, < 3)
    web-console (2.3.0)
      activemodel (>= 4.0)
      binding_of_caller (>= 0.7.2)
      railties (>= 4.0)
      sprockets-rails (>= 2.0, < 4.0)

PLATFORMS
  ruby

DEPENDENCIES
  byebug
  coffee-rails (~> 4.1.0)
  jbuilder (~> 2.0)
  jquery-rails
  pg
  rails (= 4.2.4)
  sass-rails (~> 5.0)
  sdoc (~> 0.4.0)
  spring
  turbolinks
  uglifier (>= 1.3.0)
  web-console (~> 2.0)

BUNDLED WITH
   1.10.6
```

> publication-app$ bin/bundle list

```
Gems included by the bundle:
  * actionmailer (4.2.4)
  * actionpack (4.2.4)
  * actionview (4.2.4)
  * activejob (4.2.4)
  * activemodel (4.2.4)
  * activerecord (4.2.4)
  * activesupport (4.2.4)
  * arel (6.0.3)
  * binding_of_caller (0.7.2)
  * builder (3.2.2)
  * bundler (1.10.6)
  * byebug (8.2.2)
  * coffee-rails (4.1.1)
  * coffee-script (2.4.1)
  * coffee-script-source (1.10.0)
  * concurrent-ruby (1.0.1)
  * debug_inspector (0.0.2)
  * erubis (2.7.0)
  * execjs (2.6.0)
  * globalid (0.3.6)
  * i18n (0.7.0)
  * jbuilder (2.4.1)
  * jquery-rails (4.1.1)
  * json (1.8.3)
  * loofah (2.0.3)
  * mail (2.6.4)
  * mime-types (3.0)
  * mime-types-data (3.2016.0221)
  * mini_portile2 (2.0.0)
  * minitest (5.8.4)
  * multi_json (1.11.2)
  * nokogiri (1.6.7.2)
  * pg (0.18.4)
  * rack (1.6.4)
  * rack-test (0.6.3)
  * rails (4.2.4)
  * rails-deprecated_sanitizer (1.0.3)
  * rails-dom-testing (1.0.7)
  * rails-html-sanitizer (1.0.3)
  * railties (4.2.4)
  * rake (11.1.2)
  * rdoc (4.2.2)
  * sass (3.4.22)
  * sass-rails (5.0.4)
  * sdoc (0.4.1)
  * spring (1.6.4)
  * sprockets (3.5.2)
  * sprockets-rails (3.0.4)
  * thor (0.19.1)
  * thread_safe (0.3.5)
  * tilt (2.0.2)
  * turbolinks (2.5.3)
  * tzinfo (1.2.2)
  * uglifier (3.0.0)
  * web-console (2.3.0)
```

*publication-app/config/database.yml*

```yml
# PostgreSQL. Versions 8.2 and up are supported.
#
# Install the pg driver:
#   gem install pg
# On OS X with Homebrew:
#   gem install pg -- --with-pg-config=/usr/local/bin/pg_config
# On OS X with MacPorts:
#   gem install pg -- --with-pg-config=/opt/local/lib/postgresql84/bin/pg_config
# On Windows:
#   gem install pg
#       Choose the win32 build.
#       Install PostgreSQL and put its /bin directory on your path.
#
# Configure Using Gemfile
# gem 'pg'
#
default: &default
  adapter: postgresql
  encoding: unicode
  # For details on connection pooling, see rails configuration guide
  # http://guides.rubyonrails.org/configuring.html#database-pooling
  pool: 5

development:
  <<: *default
  database: publication-app_development

  # The specified database role being used to connect to postgres.
  # To create additional roles in postgres see `$ createuser --help`.
  # When left blank, postgres will use the default role. This is
  # the same name as the operating system user that initialized the database.
  #username: publication-app

  # The password associated with the postgres role (username).
  #password:

  # Connect on a TCP socket. Omitted by default since the client uses a
  # domain socket that doesn't need configuration. Windows does not have
  # domain sockets, so uncomment these lines.
  #host: localhost

  # The TCP port the server listens on. Defaults to 5432.
  # If your server runs on a different port number, change accordingly.
  #port: 5432

  # Schema search path. The server defaults to $user,public
  #schema_search_path: myapp,sharedapp,public

  # Minimum log levels, in increasing order:
  #   debug5, debug4, debug3, debug2, debug1,
  #   log, notice, warning, error, fatal, and panic
  # Defaults to warning.
  #min_messages: notice

# Warning: The database defined as "test" will be erased and
# re-generated from your development database when you run "rake".
# Do not set this db to the same as development or production.
test:
  <<: *default
  database: publication-app_test

# As with config/secrets.yml, you never want to store sensitive information,
# like your database password, in your source code. If your source code is
# ever seen by anyone, they now have access to your database.
#
# Instead, provide the password as a unix environment variable when you boot
# the app. Read http://guides.rubyonrails.org/configuring.html#configuring-a-database
# for a full rundown on how to provide these environment variables in a
# production deployment.
#
# On Heroku and other platform providers, you may have a full connection URL
# available as an environment variable. For example:
#
#   DATABASE_URL="postgres://myuser:mypass@localhost/somedatabase"
#
# You can use this database configuration with:
#
#   production:
#     url: <%= ENV['DATABASE_URL'] %>
#
production:
  <<: *default
  database: publication-app_production
  username: publication-app
  password: <%= ENV['PUBLICATION-APP_DATABASE_PASSWORD'] %>
```

### Create the Database

> publication-app$ rake db:create

```
FATAL:  role "droid" does not exist
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:665:in `rescue in connect'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `connect'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:242:in `initialize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `new'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `postgresql_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:438:in `new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:448:in `checkout_new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:422:in `acquire_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:349:in `block in checkout'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:348:in `checkout'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:263:in `block in connection'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:262:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:571:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:113:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:87:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:8:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:17:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:93:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:107:in `block in create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:275:in `block in each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:106:in `create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/railties/databases.rake:17:in `block (2 levels) in <top (required)>'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `call'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `block in execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:187:in `block in invoke_with_call_chain'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:180:in `invoke_with_call_chain'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:173:in `invoke'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:150:in `invoke_task'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block (2 levels) in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:115:in `run_with_threads'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:100:in `top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:78:in `block in run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:176:in `standard_exception_handling'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:75:in `run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/bin/rake:33:in `<top (required)>'
/usr/local/bin/rake:23:in `load'
/usr/local/bin/rake:23:in `<main>'
Couldn't create database for {"adapter"=>"postgresql", "encoding"=>"unicode", "pool"=>5, "database"=>"publication-app_development"}
FATAL:  role "droid" does not exist
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:665:in `rescue in connect'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `connect'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:242:in `initialize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `new'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `postgresql_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:438:in `new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:448:in `checkout_new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:422:in `acquire_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:349:in `block in checkout'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:348:in `checkout'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:263:in `block in connection'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:262:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:571:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:113:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:87:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:8:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:17:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:93:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:107:in `block in create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:275:in `block in each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:106:in `create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/railties/databases.rake:17:in `block (2 levels) in <top (required)>'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `call'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `block in execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:187:in `block in invoke_with_call_chain'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:180:in `invoke_with_call_chain'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:173:in `invoke'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:150:in `invoke_task'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block (2 levels) in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:115:in `run_with_threads'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:100:in `top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:78:in `block in run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:176:in `standard_exception_handling'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:75:in `run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/bin/rake:33:in `<top (required)>'
/usr/local/bin/rake:23:in `load'
/usr/local/bin/rake:23:in `<main>'
Couldn't create database for {"adapter"=>"postgresql", "encoding"=>"unicode", "pool"=>5, "database"=>"publication-app_test"}
```

> publication-app$ psql

```
psql: FATAL:  role "droid" does not exist
```

### Create a new role in Postgres

> publication-app$ sudo su - postgres

```
[sudo] password for droid:
postgres@droidserver:~$ psql
psql (9.5.2)
Type "help" for help.
postgres=#
```

**Create a role 'publication-app'**

As per the comments in *publication-app/config/database.yml*

> publication-app$ createuser --help

```
createuser creates a new PostgreSQL role.

Usage:
  createuser [OPTION]... [ROLENAME]

Options:
  -c, --connection-limit=N  connection limit for role (default: no limit)
  -d, --createdb            role can create new databases
  -D, --no-createdb         role cannot create databases (default)
  -e, --echo                show the commands being sent to the server
  -E, --encrypted           encrypt stored password
  -g, --role=ROLE           new role will be a member of this role
  -i, --inherit             role inherits privileges of roles it is a
                            member of (default)
  -I, --no-inherit          role does not inherit privileges
  -l, --login               role can login (default)
  -L, --no-login            role cannot login
  -N, --unencrypted         do not encrypt stored password
  -P, --pwprompt            assign a password to new role
  -r, --createrole          role can create new roles
  -R, --no-createrole       role cannot create roles (default)
  -s, --superuser           role will be superuser
  -S, --no-superuser        role will not be superuser (default)
  -V, --version             output version information, then exit
  --interactive             prompt for missing role name and attributes rather
                            than using defaults
  --replication             role can initiate replication
  --no-replication          role cannot initiate replication
  -?, --help                show this help, then exit

Connection options:
  -h, --host=HOSTNAME       database server host or socket directory
  -p, --port=PORT           database server port
  -U, --username=USERNAME   user name to connect as (not the one to create)
  -w, --no-password         never prompt for password
  -W, --password            force password prompt

Report bugs to <pgsql-bugs@postgresql.org>.
```

Switch to 'postgres' user and create a new role 'publication-app'

```
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ createuser -d -l -P publication-app
Enter password for new role: 
Enter it again: 
createuser: could not connect to database postgres: FATAL:  role "droid" does not exist
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ sudo su postgres
[sudo] password for droid: 
postgres@droidserver:/home/droid/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ createuser -d -l -P publication-app
could not change directory to "/home/droid/onBB/Ruby-on-Rails-Sample-Apps/publication-app": Permission denied
Enter password for new role: 
Enter it again: 
postgres@droidserver:/home/droid/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ su droid
Password: 
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$
```

Set the environment variable. As environment variables cannot have a '-' in them, replace with a '_'. Also make changes to the environment variable used in *publication-app/config/database.yml*

```
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ export PUBLICATION-APP_DATABASE_PASSWORD='password'
bash: export: `PUBLICATION-APP_DATABASE_PASSWORD=password': not a valid identifier
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ export PUBLICATION_APP_DATABASE_PASSWORD='password'
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ echo $PUBLICATION_APP_DATABASE_PASSWORD
password
```

```yml
# PostgreSQL. Versions 8.2 and up are supported.
#
# Install the pg driver:
#   gem install pg
# On OS X with Homebrew:
#   gem install pg -- --with-pg-config=/usr/local/bin/pg_config
# On OS X with MacPorts:
#   gem install pg -- --with-pg-config=/opt/local/lib/postgresql84/bin/pg_config
# On Windows:
#   gem install pg
#       Choose the win32 build.
#       Install PostgreSQL and put its /bin directory on your path.
#
# Configure Using Gemfile
# gem 'pg'
#
default: &default
  adapter: postgresql
  encoding: unicode
  # For details on connection pooling, see rails configuration guide
  # http://guides.rubyonrails.org/configuring.html#database-pooling
  pool: 5

development:
  <<: *default
  database: publication-app_development

  # The specified database role being used to connect to postgres.
  # To create additional roles in postgres see `$ createuser --help`.
  # When left blank, postgres will use the default role. This is
  # the same name as the operating system user that initialized the database.
  username: publication-app                           --------------------

  # The password associated with the postgres role (username).
  password: <%= ENV['PUBLICATION_APP_DATABASE_PASSWORD'] %>

  # Connect on a TCP socket. Omitted by default since the client uses a
  # domain socket that doesn't need configuration. Windows does not have
  # domain sockets, so uncomment these lines.
  #host: localhost

  # The TCP port the server listens on. Defaults to 5432.
  # If your server runs on a different port number, change accordingly.
  #port: 5432

  # Schema search path. The server defaults to $user,public
  #schema_search_path: myapp,sharedapp,public

  # Minimum log levels, in increasing order:
  #   debug5, debug4, debug3, debug2, debug1,
  #   log, notice, warning, error, fatal, and panic
  # Defaults to warning.
  #min_messages: notice

# Warning: The database defined as "test" will be erased and
# re-generated from your development database when you run "rake".
# Do not set this db to the same as development or production.
test:
  <<: *default
  database: publication-app_test
  username: publication-app                           --------------------
  password: <%= ENV['PUBLICATION_APP_DATABASE_PASSWORD'] %>  

# As with config/secrets.yml, you never want to store sensitive information,
# like your database password, in your source code. If your source code is
# ever seen by anyone, they now have access to your database.
#
# Instead, provide the password as a unix environment variable when you boot
# the app. Read http://guides.rubyonrails.org/configuring.html#configuring-a-database
# for a full rundown on how to provide these environment variables in a
# production deployment.
#
# On Heroku and other platform providers, you may have a full connection URL
# available as an environment variable. For example:
#
#   DATABASE_URL="postgres://myuser:mypass@localhost/somedatabase"
#
# You can use this database configuration with:
#
#   production:
#     url: <%= ENV['DATABASE_URL'] %>
#
production:
  <<: *default
  database: publication-app_production
  username: publication-app
  password: <%= ENV['PUBLICATION_APP_DATABASE_PASSWORD'] %>
```

Run the rake command:

```
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ rake db:create
FATAL:  Peer authentication failed for user "publication-app"
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `initialize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `new'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `connect'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:242:in `initialize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `new'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `postgresql_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:438:in `new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:448:in `checkout_new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:422:in `acquire_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:349:in `block in checkout'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:348:in `checkout'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:263:in `block in connection'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:262:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:571:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:113:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:87:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:8:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:17:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:93:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:107:in `block in create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:275:in `block in each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:106:in `create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/railties/databases.rake:17:in `block (2 levels) in <top (required)>'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `call'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `block in execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:187:in `block in invoke_with_call_chain'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:180:in `invoke_with_call_chain'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:173:in `invoke'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:150:in `invoke_task'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block (2 levels) in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:115:in `run_with_threads'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:100:in `top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:78:in `block in run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:176:in `standard_exception_handling'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:75:in `run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/bin/rake:33:in `<top (required)>'
/usr/local/bin/rake:23:in `load'
/usr/local/bin/rake:23:in `<main>'
Couldn't create database for {"adapter"=>"postgresql", "encoding"=>"unicode", "pool"=>5, "database"=>"publication-app_development", "username"=>"publication-app", "password"=>"password"}
FATAL:  Peer authentication failed for user "publication-app"
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `initialize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `new'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:655:in `connect'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:242:in `initialize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `new'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/postgresql_adapter.rb:44:in `postgresql_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:438:in `new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:448:in `checkout_new_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:422:in `acquire_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:349:in `block in checkout'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:348:in `checkout'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:263:in `block in connection'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:262:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_adapters/abstract/connection_pool.rb:571:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:113:in `retrieve_connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/connection_handling.rb:87:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:8:in `connection'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/postgresql_database_tasks.rb:17:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:93:in `create'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:107:in `block in create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:275:in `block in each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:274:in `each_current_configuration'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/tasks/database_tasks.rb:106:in `create_current'
/usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/railties/databases.rake:17:in `block (2 levels) in <top (required)>'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `call'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:248:in `block in execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:243:in `execute'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:187:in `block in invoke_with_call_chain'
/usr/local/lib/ruby/2.2.0/monitor.rb:211:in `mon_synchronize'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:180:in `invoke_with_call_chain'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/task.rb:173:in `invoke'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:150:in `invoke_task'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block (2 levels) in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `each'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:106:in `block in top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:115:in `run_with_threads'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:100:in `top_level'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:78:in `block in run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:176:in `standard_exception_handling'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/lib/rake/application.rb:75:in `run'
/usr/local/lib/ruby/gems/2.2.0/gems/rake-11.1.2/bin/rake:33:in `<top (required)>'
/usr/local/bin/rake:23:in `load'
/usr/local/bin/rake:23:in `<main>'
Couldn't create database for {"adapter"=>"postgresql", "encoding"=>"unicode", "pool"=>5, "database"=>"publication-app_test", "username"=>"publication-app", "password"=>"password"}
```

Change the following line in */etc/postgresql/9.5/main/pg_hba.conf*

local   all             all                                     peer

to

local   all             all                                     md5

```
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ sudo gedit /etc/postgresql/9.5/main/pg_hba.conf
```

Run the rake command now

```
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ rake db:create
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app
```

### Start the server

> publication-app$ rails server

```
=> Booting WEBrick
=> Rails 4.2.4 application starting in development on http://localhost:3000
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server
[2016-04-07 07:41:18] INFO  WEBrick 1.3.1
[2016-04-07 07:41:18] INFO  ruby 2.2.3 (2015-08-18) [x86_64-linux]
[2016-04-07 07:41:18] INFO  WEBrick::HTTPServer#start: pid=9039 port=3000
```

*Snapshot*

![](_misc/in%20browser.png)

----------

# Creating users

**Using devise gem**

Follow the instructions provided at: <https://github.com/plataformatec/devise>

```ruby
source 'https://rubygems.org'

gem 'devise'  <--------------

# Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
gem 'rails', '4.2.4'
# Use postgresql as the database for Active Record
gem 'pg'
# Use SCSS for stylesheets
gem 'sass-rails', '~> 5.0'
# Use Uglifier as compressor for JavaScript assets
gem 'uglifier', '>= 1.3.0'
# Use CoffeeScript for .coffee assets and views
gem 'coffee-rails', '~> 4.1.0'
# See https://github.com/rails/execjs#readme for more supported runtimes
# gem 'therubyracer', platforms: :ruby

# Use jquery as the JavaScript library
gem 'jquery-rails'
# Turbolinks makes following links in your web application faster. Read more: https://github.com/rails/turbolinks
gem 'turbolinks'
# Build JSON APIs with ease. Read more: https://github.com/rails/jbuilder
gem 'jbuilder', '~> 2.0'
# bundle exec rake doc:rails generates the API under doc/api.
gem 'sdoc', '~> 0.4.0', group: :doc

# Use ActiveModel has_secure_password
# gem 'bcrypt', '~> 3.1.7'

# Use Unicorn as the app server
# gem 'unicorn'

# Use Capistrano for deployment
# gem 'capistrano-rails', group: :development

group :development, :test do
  # Call 'byebug' anywhere in the code to stop execution and get a debugger console
  gem 'byebug'
end

group :development do
  # Access an IRB console on exception pages or by using <%= console %> in views
  gem 'web-console', '~> 2.0'

  # Spring speeds up development by keeping your application running in the background. Read more: https://github.com/rails/spring
  gem 'spring'
end
```

Run the following to install the gem in the project

> publication-app$ bin/bundle install

```
Fetching gem metadata from https://rubygems.org/...........
Fetching version metadata from https://rubygems.org/...
Fetching dependency metadata from https://rubygems.org/..
Resolving dependencies...
Using rake 11.1.2
Using i18n 0.7.0
Using json 1.8.3
Using minitest 5.8.4
Using thread_safe 0.3.5
Using tzinfo 1.2.2
Using activesupport 4.2.4
Using builder 3.2.2
Using erubis 2.7.0
Using mini_portile2 2.0.0
Using nokogiri 1.6.7.2
Using rails-deprecated_sanitizer 1.0.3
Using rails-dom-testing 1.0.7
Using loofah 2.0.3
Using rails-html-sanitizer 1.0.3
Using actionview 4.2.4
Using rack 1.6.4
Using rack-test 0.6.3
Using actionpack 4.2.4
Using globalid 0.3.6
Using activejob 4.2.4
Using mime-types-data 3.2016.0221
Using mime-types 3.0
Using mail 2.6.4
Using actionmailer 4.2.4
Using activemodel 4.2.4
Using arel 6.0.3
Using activerecord 4.2.4


Your user account isn't allowed to install to the system Rubygems.
You can cancel this installation and run:

    bundle install --path vendor/bundle

to install the gems into ./vendor/bundle/, or you can enter your password
and install the bundled gems to Rubygems using sudo.

Password: 
Installing bcrypt 3.1.11 with native extensions
Using debug_inspector 0.0.2
Using binding_of_caller 0.7.2
Using bundler 1.10.6
Using byebug 8.2.2
Using coffee-script-source 1.10.0
Using execjs 2.6.0
Using coffee-script 2.4.1
Using thor 0.19.1
Using railties 4.2.4
Using coffee-rails 4.1.1
Using concurrent-ruby 1.0.1
Installing orm_adapter 0.5.0
Installing responders 2.1.2
Installing warden 1.2.6
Installing devise 3.5.6
Using multi_json 1.11.2
Using jbuilder 2.4.1
Using jquery-rails 4.1.1
Using pg 0.18.4
Using sprockets 3.5.2
Using sprockets-rails 3.0.4
Using rails 4.2.4
Using rdoc 4.2.2
Using sass 3.4.22
Using tilt 2.0.2
Using sass-rails 5.0.4
Using sdoc 0.4.1
Using spring 1.6.4
Using turbolinks 2.5.3
Using uglifier 3.0.0
Using web-console 2.3.0
Bundle complete! 13 Gemfile dependencies, 60 gems now installed.
Use `bundle show [gemname]` to see where a bundled gem is installed.
```

**Setup initial devise configuration**

> publication-app$ rails generate devise:install

```
Running via Spring preloader in process 7688
      create  config/initializers/devise.rb
      create  config/locales/devise.en.yml
===============================================================================

Some setup you must do manually if you haven't yet:

  1. Ensure you have defined default url options in your environments files. Here
     is an example of default_url_options appropriate for a development environment
     in config/environments/development.rb:

       config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

     In production, :host should be set to the actual host of your application.

  2. Ensure you have defined root_url to *something* in your config/routes.rb.
     For example:

       root to: "home#index"

  3. Ensure you have flash messages in app/views/layouts/application.html.erb.
     For example:

       <p class="notice"><%= notice %></p>
       <p class="alert"><%= alert %></p>

  4. If you are deploying on Heroku with Rails 3.2 only, you may want to set:

       config.assets.initialize_on_precompile = false

     On config/application.rb forcing your application to not access the DB
     or load models when precompiling your assets.

  5. You can copy Devise views (for customization) to your app by running:

       rails g devise:views

===============================================================================
```

Following the instructions above, 

Step 1) 

Make changes to *publication-app/config/environments/development.rb*, as shown below, to resolve problems that ActionMailer would have when it attempts to send emails on the local server without any configuration. 

*publication-app/config/environments/development.rb*

```ruby
Rails.application.configure do
  # Settings specified here will take precedence over those in config/application.rb.
  config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }  <------
  # In the development environment your application's code is reloaded on
  # every request. This slows down response time but is perfect for development
  # since you don't have to restart the web server when you make code changes.
  config.cache_classes = false

  # Do not eager load code on boot.
  config.eager_load = false

  # Show full error reports and disable caching.
  config.consider_all_requests_local       = true
  config.action_controller.perform_caching = false

  # Don't care if the mailer can't send.
  config.action_mailer.raise_delivery_errors = false

  # Print deprecation notices to the Rails logger.
  config.active_support.deprecation = :log

  # Raise an error on page load if there are pending migrations.
  config.active_record.migration_error = :page_load

  # Debug mode disables concatenation and preprocessing of assets.
  # This option may cause significant delays in view rendering with a large
  # number of complex assets.
  config.assets.debug = true

  # Asset digests allow you to set far-future HTTP expiration dates on all assets,
  # yet still be able to expire them through the digest params.
  config.assets.digest = true

  # Adds additional error checking when serving assets at runtime.
  # Checks for improperly declared sprockets dependencies.
  # Raises helpful error messages.
  config.assets.raise_runtime_errors = true

  # Raises error for missing translations
  # config.action_view.raise_on_missing_translations = true
end
```

Step 2) 

Once devise finishes signing up or signing in a user, it automatically redirects to the root url, so add the following, to let devise invoke 'home' controller's action/method 'index'.

*publication-app/config/routes.rb*

```ruby
Rails.application.routes.draw do
  root to: "home#index"  <---------------------
  # The priority is based upon order of creation: first created -> highest priority.
  # See how all your routes lay out with "rake routes".

  # You can have the root of your site routed with "root"
  # root 'welcome#index'

  # Example of regular route:
  #   get 'products/:id' => 'catalog#view'

  # Example of named route that can be invoked with purchase_url(id: product.id)
  #   get 'products/:id/purchase' => 'catalog#purchase', as: :purchase

  # Example resource route (maps HTTP verbs to controller actions automatically):
  #   resources :products

  # Example resource route with options:
  #   resources :products do
  #     member do
  #       get 'short'
  #       post 'toggle'
  #     end
  #
  #     collection do
  #       get 'sold'
  #     end
  #   end

  # Example resource route with sub-resources:
  #   resources :products do
  #     resources :comments, :sales
  #     resource :seller
  #   end

  # Example resource route with more complex sub-resources:
  #   resources :products do
  #     resources :comments
  #     resources :sales do
  #       get 'recent', on: :collection
  #     end
  #   end

  # Example resource route with concerns:
  #   concern :toggleable do
  #     post 'toggle'
  #   end
  #   resources :posts, concerns: :toggleable
  #   resources :photos, concerns: :toggleable

  # Example resource route within a namespace:
  #   namespace :admin do
  #     # Directs /admin/products/* to Admin::ProductsController
  #     # (app/controllers/admin/products_controller.rb)
  #     resources :products
  #   end
end
```

**Create the controller and the view**

*publication-app/app/controllers/home_controller.rb*

```ruby
class HomeController < ApplicationController
	def index
	end
end
```

Create a folder 'home' in *publication-app/app/views* and a new file in it called 'index.html.erb'

*publication-app/app/views/home/index.html.erb*

```erb
<h1>Welcome to the index page</h1>
```

*Start server*

> publication-app$ rails server

```
=> Booting WEBrick
=> Rails 4.2.4 application starting in development on http://localhost:3000
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server
[2016-04-07 09:18:34] INFO  WEBrick 1.3.1
[2016-04-07 09:18:34] INFO  ruby 2.2.3 (2015-08-18) [x86_64-linux]
[2016-04-07 09:18:34] INFO  WEBrick::HTTPServer#start: pid=10568 port=3000
```

Make a request from the browser. The following is displayed on the console

```
Started GET "/" for 127.0.0.1 at 2016-04-07 09:18:35 -0400
Processing by HomeController#index as HTML
  Rendered home/index.html.erb within layouts/application (1.0ms)
Completed 200 OK in 1945ms (Views: 1928.0ms | ActiveRecord: 0.0ms)


Started GET "/assets/application.self-e80e8f2318043e8af94dddc2adad5a4f09739a8ebb323b3ab31cd71d45fd9113.css?body=1" for 127.0.0.1 at 2016-04-07 09:18:37 -0400


Started GET "/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1" for 127.0.0.1 at 2016-04-07 09:18:37 -0400


Started GET "/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1" for 127.0.0.1 at 2016-04-07 09:18:37 -0400


Started GET "/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1" for 127.0.0.1 at 2016-04-07 09:18:37 -0400


Started GET "/assets/application.self-3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819.js?body=1" for 127.0.0.1 at 2016-04-07 09:18:37 -0400
```

*snapshot*

![](_misc/browser%20snapshot.png)


Step 3)

Add flash messages to let the user know of a successful/unsuccessful signin messages.

*publication-app/app/views/layouts/application.html.erb*

```erb
<!DOCTYPE html>
<html>
<head>
  <title>PublicationApp</title>
  <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track' => true %>
  <%= javascript_include_tag 'application', 'data-turbolinks-track' => true %>
  <%= csrf_meta_tags %>
</head>
<body>
       <p class="notice"><%= notice %></p>   ---------
       <p class="alert"><%= alert %></p>
<%= yield %>

</body>
</html>
```

Step 5)

To customize devise provided views, copy the views first by 

> publication-app$ rails g devise:views

**Create a model and configure it with default Devise Modules**

> publication-app$ rails generate devise User

```
Running via Spring preloader in process 11058
      invoke  active_record
      create    db/migrate/20160407134119_devise_create_users.rb   
      create    app/models/user.rb
      invoke    test_unit
      create      test/models/user_test.rb
      create      test/fixtures/users.yml
      insert    app/models/user.rb
       route  devise_for :users
```

 'db/migrate/20160407134119_devise_create_users.rb' is a database migration file, which creates a table in the database.
 
 'app/models/user.rb' is the User module definition.
 
 'devise_for :users' is the routing section for Users in the routes file.
 
 **Add User to the database**
 
 > publication-app$ rake db:migrate
 
 ```
 == 20160407134119 DeviseCreateUsers: migrating ================================
-- create_table(:users)
   -> 0.2249s
-- add_index(:users, :email, {:unique=>true})
   -> 0.0336s
-- add_index(:users, :reset_password_token, {:unique=>true})
   -> 0.0340s
== 20160407134119 DeviseCreateUsers: migrated (0.2929s) =======================
 ```
 
 Look into the database to see the results of running the above steps
 
 ```
 droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ sudo su postgres
[sudo] password for droid: 
postgres@droidserver:/home/droid/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ psql
could not change directory to "/home/droid/onBB/Ruby-on-Rails-Sample-Apps/publication-app": Permission denied
psql (9.5.2)
Type "help" for help.
postgres-# \connect publication-app_development
You are now connected to database "publication-app_development" as user "postgres".
publication-app_development-# \dt
                  List of relations
 Schema |       Name        | Type  |      Owner      
--------+-------------------+-------+-----------------
 public | schema_migrations | table | publication-app
 public | users             | table | publication-app
(2 rows)

publication-app_development-# \d+ users
                                                               Table "public.users"
         Column         |            Type             |                     Modifiers                      | Storage  | Stats target | Description 
------------------------+-----------------------------+----------------------------------------------------+----------+--------------+-------------
 id                     | integer                     | not null default nextval('users_id_seq'::regclass) | plain    |              | 
 email                  | character varying           | not null default ''::character varying             | extended |              | 
 encrypted_password     | character varying           | not null default ''::character varying             | extended |              | 
 reset_password_token   | character varying           |                                                    | extended |              | 
 reset_password_sent_at | timestamp without time zone |                                                    | plain    |              | 
 remember_created_at    | timestamp without time zone |                                                    | plain    |              | 
 sign_in_count          | integer                     | not null default 0                                 | plain    |              | 
 current_sign_in_at     | timestamp without time zone |                                                    | plain    |              | 
 last_sign_in_at        | timestamp without time zone |                                                    | plain    |              | 
 current_sign_in_ip     | inet                        |                                                    | main     |              | 
 last_sign_in_ip        | inet                        |                                                    | main     |              | 
 created_at             | timestamp without time zone | not null                                           | plain    |              | 
 updated_at             | timestamp without time zone | not null                                           | plain    |              | 
Indexes:
    "users_pkey" PRIMARY KEY, btree (id)
    "index_users_on_email" UNIQUE, btree (email)
    "index_users_on_reset_password_token" UNIQUE, btree (reset_password_token)
```

Start the server

> publication-app$ rails server

```
=> Booting WEBrick
=> Rails 4.2.4 application starting in development on http://localhost:3000
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server
[2016-04-07 10:04:41] INFO  WEBrick 1.3.1
[2016-04-07 10:04:41] INFO  ruby 2.2.3 (2015-08-18) [x86_64-linux]
[2016-04-07 10:04:41] INFO  WEBrick::HTTPServer#start: pid=11430 port=3000
```

Request for /users/sign_in from the browser

Snapshot

![](_misc/users%20sign_in%20in%20browser.png)

```
Started GET "/users/sign_in" for 127.0.0.1 at 2016-04-07 10:04:46 -0400
  ActiveRecord::SchemaMigration Load (0.4ms)  SELECT "schema_migrations".* FROM "schema_migrations"
Processing by Devise::SessionsController#new as HTML
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/devise-3.5.6/app/views/devise/shared/_links.html.erb (3.9ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/devise-3.5.6/app/views/devise/sessions/new.html.erb within layouts/application (55.6ms)
Completed 200 OK in 312ms (Views: 285.1ms | ActiveRecord: 2.4ms)


Started GET "/assets/application.self-e80e8f2318043e8af94dddc2adad5a4f09739a8ebb323b3ab31cd71d45fd9113.css?body=1" for 127.0.0.1 at 2016-04-07 10:04:46 -0400


Started GET "/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1" for 127.0.0.1 at 2016-04-07 10:04:46 -0400


Started GET "/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1" for 127.0.0.1 at 2016-04-07 10:04:46 -0400


Started GET "/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1" for 127.0.0.1 at 2016-04-07 10:04:46 -0400


Started GET "/assets/application.self-3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819.js?body=1" for 127.0.0.1 at 2016-04-07 10:04:46 -0400
```

Request for /users/sign_up from the browser

Snapshot

![](_misc/users%20sign_up%20in%20browser.png)

```
Started GET "/users/sign_up" for 127.0.0.1 at 2016-04-07 10:16:05 -0400
Processing by Devise::RegistrationsController#new as HTML
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/devise-3.5.6/app/views/devise/shared/_links.html.erb (0.4ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/devise-3.5.6/app/views/devise/registrations/new.html.erb within layouts/application (4.3ms)
Completed 200 OK in 26ms (Views: 24.7ms | ActiveRecord: 0.0ms)
```

*Signing up*

Sign up with the email 'sample@gmail.com'. After signup, the browser is redirected to the "root" (as configured in *publication-app/config/routes.rb*), which displays the view that results from calling the HomeController's index method.

Snapshot after signing up

![](_misc/after%20signing%20up.png)


*Check the database to see if user is saved*

```
publication-app_development=# SELECT * FROM users;

 id |      email       |                      encrypted_password                      | reset_password_token | reset_password_sent_at | remember_created_at | sign_in_count |     current_sign_in_at     |      last_sign_in_at       | current_sign_in_ip | last_sign_in_ip |         created_at         |         updated_at         
----+------------------+--------------------------------------------------------------+----------------------+------------------------+---------------------+---------------+----------------------------+----------------------------+--------------------+-----------------+----------------------------+----------------------------
  1 | sample@gmail.com | $2a$10$TPL5nKsR.EO2j/SeM3IYOu8H7Q3hOn72zuq/f/wSVwdlk/6AkyJVK |                      |                        |                     |             3 | 2016-04-07 15:06:16.941589 | 2016-04-07 14:54:25.553537 | 127.0.0.1          | 127.0.0.1       | 2016-04-07 14:22:23.055446 | 2016-04-07 15:06:16.943684
(1 row)

```

### Adding a navbar

Add an application-wide navbar as a partial so it could be used anywhere it is needed, and include it in *publication-app/app/views/layouts/application.html.erb*

*publication-app/app/views/layouts/application.html.erb*

```erb
<!DOCTYPE html>
<html>
<head>
  <title>PublicationApp</title>
  <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track' => true %>
  <%= javascript_include_tag 'application', 'data-turbolinks-track' => true %>
  <%= csrf_meta_tags %>
</head>
<body>
	<%= render 'navbar' %>   ------

    <p class="notice"><%= notice %></p>
    <p class="alert"><%= alert %></p>
<%= yield %>

</body>
</html>
```

Run the server and check in the browser

![](_misc/navbar%20error%20in%20browser.png)

It could be noticed from the error that the partial is being looked for is home/_navbar or application/_navbar (Notice, the partial navbar is referred to as _navbar as all partials are prepended with an _) 

As I am adding an application-wide navbar, it's more appropriate to place it under application/

The navbar should contain buttons to let users sign in or sign up. If signed in, it should display the user email as a drop down with an option to sign out. On clicking the sign out button, the user should be signed out.

*publication-app/app/views/application/_navbar.html.erb*

```erb
<nav class="navbar navbar-default">
  <div class="container-fluid">
    <!-- Brand and toggle get grouped for better mobile display -->
    <div class="navbar-header">
      <a class="navbar-brand" href="#">Publications</a>
    </div>

    <!-- Collect the nav links, forms, and other content for toggling -->
    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
      <ul class="nav navbar-nav navbar-right">

      <% if user_signed_in? %>
          <div class="btn-group" role="group">
              <button type="button" class="btn btn-default navbar-btn dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                <%= current_user.email %>
                <span class="caret"></span>
              </button>
              <ul class="dropdown-menu">
                <li>
                  <%= link_to "Sign out", destroy_user_session_path, method: :delete %>
                </li>
              </ul>
          </div>            
      
       <% else %> 
          <%= link_to "Sign in", new_user_session_path, class: "btn btn-default navbar-btn" %>      
          <%= link_to "Sign up", new_user_registration_path, class: "btn btn-default navbar-btn" %>                
      <% end %>

      </ul>
    </div><!-- /.navbar-collapse -->

  </div><!-- /.container-fluid -->
</nav>
```

**Generated links for the buttons**

For the sign in and sign up buttons

![](_misc/generated%20links%20for%20sign%20in%20and%20sign%20up.png)

generated by the lines

```erb
          <%= link_to "Sign in", new_user_session_path, class: "btn btn-default navbar-btn" %>      
          <%= link_to "Sign up", new_user_registration_path, class: "btn btn-default navbar-btn" %>                
```

For the sign out button 

![](_misc/generated%20link%20for%20sign%20out.png)

generated by the line

```erb
<%= link_to "Sign out", destroy_user_session_path, method: :delete %>
```

**link_to method documentation**

<http://api.rubyonrails.org/classes/ActionView/Helpers/UrlHelper.html#method-i-link_to>

**Snapshots**

Sign in and Sign up buttons in the navbar

![](_misc/signin%20and%20signup%20options.png)

On clicking sign in

![](_misc/on%20clicking%20sign%20in.png)

After successfully signing in

![](_misc/after%20signing%20in%20successfully.png)

Sign out option

![](_misc/signout%20option.png)

**Including Bootstrap and necessary files**

The look of the webpage as shown in the snapshots above is possible only after including Bootstrap by.

The ways in which Bootstrap can be included in a Rails app is 
* Using Bootstrap files from CDN
* Placing Bootstrap files in a Rails project
* Installing Bootstrap's Sass gem

### Using Bootstrap files from CDN

Make the following changes

*publication-app/app/assets/stylesheets/application.css*

```css
/*
 * This is a manifest file that'll be compiled into application.css, which will include all the files
 * listed below.
 *
 * Any CSS and SCSS file within this directory, lib/assets/stylesheets, vendor/assets/stylesheets,
 * or any plugin's vendor/assets/stylesheets directory can be referenced here using a relative path.
 *
 * You're free to add application-wide styles to this file and they'll appear at the bottom of the
 * compiled file so the styles you add here take precedence over styles defined in any styles
 * defined in the other CSS/SCSS files in this directory. It is generally better to create a new
 * file per style scope.
 *
 *= require_tree .
 *= require_self
 */

 @import "https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css"  <-----
```

*publication-app/app/assets/javascripts/application.js*

```
<!DOCTYPE html>
<html>
<head>
  <title>PublicationApp</title>
  <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track' => true %>
  <%= javascript_include_tag 'application', 'data-turbolinks-track' => true %>
  <%= csrf_meta_tags %>
</head>
<body>
	<%= render 'navbar' %>

    <p class="notice"><%= notice %></p>
    <p class="alert"><%= alert %></p>

	<%= yield %>

	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>   --------
</body>
</html>
```

**Requests made by the browser**

On making a request in the browser, the browser requests for the following files

![]()

Requests made are

```
http://localhost:3000/

http://localhost:3000/assets/application.self-3bdba4a9db8458be2932495cce17e3cec3bba240b173cc5dae559d5e7129012b.css?body=1

http://localhost:3000/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1

http://localhost:3000/assets/application.self-3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819.js?body=1

https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js

http://localhost:3000/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1

http://localhost:3000/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1

https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css

https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/fonts/glyphicons-halflings-regular.woff2

http://localhost:3000/favicon.ico
```

On the server side,

```
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ rails server
=> Booting WEBrick
=> Rails 4.2.4 application starting in development on http://localhost:3000
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server
[2016-04-10 09:02:58] INFO  WEBrick 1.3.1
[2016-04-10 09:02:58] INFO  ruby 2.2.3 (2015-08-18) [x86_64-linux]
[2016-04-10 09:02:58] INFO  WEBrick::HTTPServer#start: pid=10076 port=3000


Started GET "/" for 127.0.0.1 at 2016-04-10 09:04:09 -0400
  ActiveRecord::SchemaMigration Load (18.1ms)  SELECT "schema_migrations".* FROM "schema_migrations"
Processing by HomeController#index as HTML
  Rendered home/index.html.erb within layouts/application (1.2ms)
  Rendered application/_navbar.html.erb (5.8ms)
Completed 200 OK in 412ms (Views: 392.1ms | ActiveRecord: 0.0ms)


Started GET "/assets/application.self-3bdba4a9db8458be2932495cce17e3cec3bba240b173cc5dae559d5e7129012b.css?body=1" for 127.0.0.1 at 2016-04-10 09:04:10 -0400


Started GET "/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1" for 127.0.0.1 at 2016-04-10 09:04:10 -0400


Started GET "/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1" for 127.0.0.1 at 2016-04-10 09:04:10 -0400


Started GET "/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1" for 127.0.0.1 at 2016-04-10 09:04:10 -0400


Started GET "/assets/application.self-3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819.js?body=1" for 127.0.0.1 at 2016-04-10 09:04:10 -0400
```

**More information on browser requests**

*http://localhost:3000/*

Request Headers

```
GET / HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/users/sign_in
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
```

Response Headers

```
HTTP/1.1 200 OK
X-Frame-Options: SAMEORIGIN
X-Xss-Protection: 1; mode=block
X-Content-Type-Options: nosniff
Content-Type: text/html; charset=utf-8
Etag: W/"5f5f965916c2959383565811631b3eef"
Cache-Control: max-age=0, private, must-revalidate
X-Request-Id: a7a042af-3bcb-4582-9c3c-3abdc3eb416c
X-Runtime: 0.808512
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 13:04:10 GMT
Content-Length: 2126
Connection: Keep-Alive
Set-Cookie: _publication-app_session=ci9YN2UyUnNMekJ4T3NVWHBYQ3kxMWZ6VnRzRWo5MFlpaWZCYzFZN2w3MlNiTGtYYy9OTFpXMDM3TFUzenpVWEE0TzkraTZJcCtlR2o1dm9hYWQ5dFFsSWtsaW8yeGQycFgwWVA1dllBb0xPSisxV1NJenJLSU1LWWNwUlhnWUs4dEVOaWRMcGo4SU9HMC9hZGZsbW53PT0tLUxTT2hzSFY2K2V4SnhRS0hFZGNBelE9PQ%3D%3D--76b3770b9bef3f4d3df6aad3cf29520a50068588; path=/; HttpOnly
```

Response

```
<!DOCTYPE html>
<html>
<head>
  <title>PublicationApp</title>
  <link rel="stylesheet" media="all" href="/assets/application.self-3bdba4a9db8458be2932495cce17e3cec3bba240b173cc5dae559d5e7129012b.css?body=1" data-turbolinks-track="true" />
  <script src="/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1" data-turbolinks-track="true"></script>
<script src="/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1" data-turbolinks-track="true"></script>
<script src="/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1" data-turbolinks-track="true"></script>
<script src="/assets/application.self-3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819.js?body=1" data-turbolinks-track="true"></script>
  <meta name="csrf-param" content="authenticity_token" />
<meta name="csrf-token" content="aMKIJ2qCI26NCMb1oOlOSxlg16oTH8vsJxy434vvV72USRlswbz6MIBj6y2HZ/KFihLVy4A26ihOlPcUSxNu8w==" />
</head>
<body>
	<nav class="navbar navbar-default">
  <div class="container-fluid">
    <!-- Brand and toggle get grouped for better mobile display -->
    <div class="navbar-header">
      <a class="navbar-brand" href="#">Publications</a>
    </div>

    <!-- Collect the nav links, forms, and other content for toggling -->
    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
      <ul class="nav navbar-nav navbar-right">
      <span class="glyphicon glyphicon-envelope"></span>
      <span class="glyphicon glyphicon-search"></span>
      <span class="glyphicon glyphicon-print"></span>
          <a class="btn btn-default navbar-btn" href="/users/sign_in">Sign in</a>      
          <a class="btn btn-default navbar-btn" href="/users/sign_up">Sign up</a>                

      </ul>
    </div><!-- /.navbar-collapse -->

  </div><!-- /.container-fluid -->
</nav>

    <p class="notice"></p>
    <p class="alert"></p>

	<h1>Welcome to the index page</h1>

	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
</body>
</html>
```

*http://localhost:3000/assets/application.self-3bdba4a9db8458be2932495cce17e3cec3bba240b173cc5dae559d5e7129012b.css?body=1*

Request Headers

```
GET /assets/application.self-3bdba4a9db8458be2932495cce17e3cec3bba240b173cc5dae559d5e7129012b.css?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/css,*/*;q=0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=ci9YN2UyUnNMekJ4T3NVWHBYQ3kxMWZ6VnRzRWo5MFlpaWZCYzFZN2w3MlNiTGtYYy9OTFpXMDM3TFUzenpVWEE0TzkraTZJcCtlR2o1dm9hYWQ5dFFsSWtsaW8yeGQycFgwWVA1dllBb0xPSisxV1NJenJLSU1LWWNwUlhnWUs4dEVOaWRMcGo4SU9HMC9hZGZsbW53PT0tLUxTT2hzSFY2K2V4SnhRS0hFZGNBelE9PQ%3D%3D--76b3770b9bef3f4d3df6aad3cf29520a50068588
```

Response Headers

```
HTTP/1.1 200 OK
Content-Length: 735
Content-Type: text/css; charset=utf-8
Cache-Control: public, max-age=31536000
Etag: "3bdba4a9db8458be2932495cce17e3cec3bba240b173cc5dae559d5e7129012b"
X-Request-Id: 1ee37e44-2d61-4ec4-ba54-344773a724c9
X-Runtime: 0.058796
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 13:04:10 GMT
Connection: Keep-Alive
```

Response

```
/*
 * This is a manifest file that'll be compiled into application.css, which will include all the files
 * listed below.
 *
 * Any CSS and SCSS file within this directory, lib/assets/stylesheets, vendor/assets/stylesheets,
 * or any plugin's vendor/assets/stylesheets directory can be referenced here using a relative path.
 *
 * You're free to add application-wide styles to this file and they'll appear at the bottom of the
 * compiled file so the styles you add here take precedence over styles defined in any styles
 * defined in the other CSS/SCSS files in this directory. It is generally better to create a new
 * file per style scope.
 *


 */


 @import "https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css"
```

*http://localhost:3000/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1*

Request Headers

```
GET /assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=ci9YN2UyUnNMekJ4T3NVWHBYQ3kxMWZ6VnRzRWo5MFlpaWZCYzFZN2w3MlNiTGtYYy9OTFpXMDM3TFUzenpVWEE0TzkraTZJcCtlR2o1dm9hYWQ5dFFsSWtsaW8yeGQycFgwWVA1dllBb0xPSisxV1NJenJLSU1LWWNwUlhnWUs4dEVOaWRMcGo4SU9HMC9hZGZsbW53PT0tLUxTT2hzSFY2K2V4SnhRS0hFZGNBelE9PQ%3D%3D--76b3770b9bef3f4d3df6aad3cf29520a50068588
```

Response Headers

```
HTTP/1.1 200 OK
Content-Length: 294200
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c"
X-Request-Id: c413b08f-c2b4-4810-a3ab-1c24689eda98
X-Runtime: 0.017262
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 13:04:10 GMT
Connection: Keep-Alive
```

Response

jQuery.js file

*http://localhost:3000/assets/application.self-3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819.js?body=1*

Request Headers

```
GET /assets/application.self-3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=ci9YN2UyUnNMekJ4T3NVWHBYQ3kxMWZ6VnRzRWo5MFlpaWZCYzFZN2w3MlNiTGtYYy9OTFpXMDM3TFUzenpVWEE0TzkraTZJcCtlR2o1dm9hYWQ5dFFsSWtsaW8yeGQycFgwWVA1dllBb0xPSisxV1NJenJLSU1LWWNwUlhnWUs4dEVOaWRMcGo4SU9HMC9hZGZsbW53PT0tLUxTT2hzSFY2K2V4SnhRS0hFZGNBelE9PQ%3D%3D--76b3770b9bef3f4d3df6aad3cf29520a50068588
```

Response Headers

```
HTTP/1.1 200 OK
Content-Length: 581
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "3b8dabdc891efe46b9a144b400ad69e37d7e5876bdc39dee783419a69d7ca819"
X-Request-Id: 88c3463a-8bc7-47ff-9ecb-60b91c5ad6cd
X-Runtime: 0.008359
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 13:04:10 GMT
Connection: Keep-Alive
```

Response

```
// This is a manifest file that'll be compiled into application.js, which will include all the files
// listed below.
//
// Any JavaScript/Coffee file within this directory, lib/assets/javascripts, vendor/assets/javascripts,
// or any plugin's vendor/assets/javascripts directory can be referenced here using a relative path.
//
// It's not advisable to add code directly here, but if you do, it'll appear at the bottom of the
// compiled file.
//
// Read Sprockets README (https://github.com/rails/sprockets#sprockets-directives) for details
// about supported directives.
//





```

*https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js*

Request Headers

```
GET /bootstrap/3.3.6/js/bootstrap.min.js HTTP/1.1
Host: maxcdn.bootstrapcdn.com
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
```

Response Headers

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2016 13:04:11 GMT
Content-Type: application/javascript
Transfer-Encoding: chunked
Connection: keep-alive
Last-Modified: Tue, 01 Dec 2015 17:30:57 GMT
ETag: W/"c5b5b2fa19bd66ff23211d9f844e0131"
Server: NetDNA-cache/2.2
Expires: Wed, 05 Apr 2017 13:04:11 GMT
Cache-Control: max-age=31104000
Vary: Accept-Encoding
Access-Control-Allow-Origin: *
X-Hello-Human: You should work for us! Email: jdorfman+theheader@maxcdn.com or @MaxCDNDeveloper on Twitter
X-Cache: HIT
Content-Encoding: gzip
```

Response

Minified bootstrap.js file

*http://localhost:3000/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1*

Request Headers

```
GET /assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=ci9YN2UyUnNMekJ4T3NVWHBYQ3kxMWZ6VnRzRWo5MFlpaWZCYzFZN2w3MlNiTGtYYy9OTFpXMDM3TFUzenpVWEE0TzkraTZJcCtlR2o1dm9hYWQ5dFFsSWtsaW8yeGQycFgwWVA1dllBb0xPSisxV1NJenJLSU1LWWNwUlhnWUs4dEVOaWRMcGo4SU9HMC9hZGZsbW53PT0tLUxTT2hzSFY2K2V4SnhRS0hFZGNBelE9PQ%3D%3D--76b3770b9bef3f4d3df6aad3cf29520a50068588
```

Response Headers

```
HTTP/1.1 200 OK
Content-Length: 24817
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff"
X-Request-Id: 8307c672-bfed-4650-b7ab-065f7aff8a62
X-Runtime: 0.008810
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 13:04:10 GMT
Connection: Keep-Alive
```

Response

turbolinks.js file shown below

*http://localhost:3000/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1*

Request Headers

```
GET /assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=ci9YN2UyUnNMekJ4T3NVWHBYQ3kxMWZ6VnRzRWo5MFlpaWZCYzFZN2w3MlNiTGtYYy9OTFpXMDM3TFUzenpVWEE0TzkraTZJcCtlR2o1dm9hYWQ5dFFsSWtsaW8yeGQycFgwWVA1dllBb0xPSisxV1NJenJLSU1LWWNwUlhnWUs4dEVOaWRMcGo4SU9HMC9hZGZsbW53PT0tLUxTT2hzSFY2K2V4SnhRS0hFZGNBelE9PQ%3D%3D--76b3770b9bef3f4d3df6aad3cf29520a50068588
```

Response Headers

```
HTTP/1.1 200 OK
Content-Length: 21648
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd"
X-Request-Id: 2eee9a62-3a32-4295-9685-cf9d534b40be
X-Runtime: 0.005958
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 13:04:10 GMT
Connection: Keep-Alive
```

Response

jQuery_ujs.js file as shown below

*https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css*

Request Headers

```
GET /bootstrap/3.3.6/css/bootstrap.min.css HTTP/1.1
Host: maxcdn.bootstrapcdn.com
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/css,*/*;q=0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
```

Response Headers

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2016 13:04:10 GMT
Content-Type: text/css
Transfer-Encoding: chunked
Connection: keep-alive
Last-Modified: Tue, 24 Nov 2015 19:49:46 GMT
ETag: W/"2f624089c65f12185e79925bc5a7fc42"
Server: NetDNA-cache/2.2
Expires: Wed, 05 Apr 2017 13:04:10 GMT
Cache-Control: max-age=31104000
Vary: Accept-Encoding
Access-Control-Allow-Origin: *
X-Hello-Human: You should work for us! Email: jdorfman+theheader@maxcdn.com or @MaxCDNDeveloper on Twitter
X-Cache: HIT
Content-Encoding: gzip
```

Response

Minified bootstrap.css file

*https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/fonts/glyphicons-halflings-regular.woff2*

Request Headers

```
GET /bootstrap/3.3.6/fonts/glyphicons-halflings-regular.woff2 HTTP/1.1
Host: maxcdn.bootstrapcdn.com
Connection: keep-alive
Cache-Control: max-age=0
Origin: http://localhost:3000
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Accept: */*
Referer: https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
```

Response Headers

```
HTTP/1.1 200 OK
Date: Sun, 10 Apr 2016 13:04:11 GMT
Content-Type: application/font-woff2
Content-Length: 18028
Connection: keep-alive
Last-Modified: Sat, 28 Nov 2015 18:26:59 GMT
ETag: "448c34a56d699c29117adc64c43affeb"
Server: NetDNA-cache/2.2
Expires: Wed, 05 Apr 2017 13:04:11 GMT
Cache-Control: max-age=31104000
Vary: Accept-Encoding
Access-Control-Allow-Origin: *
X-Hello-Human: You should work for us! Email: jdorfman+theheader@maxcdn.com or @MaxCDNDeveloper on Twitter
X-Cache: HIT
Accept-Ranges: bytes
```

Response

Shown below

*http://localhost:3000/favicon.ico*

Request Headers

```
GET /favicon.ico HTTP/1.1
Host: localhost:3000
Connection: keep-alive
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Accept: */*
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=ci9YN2UyUnNMekJ4T3NVWHBYQ3kxMWZ6VnRzRWo5MFlpaWZCYzFZN2w3MlNiTGtYYy9OTFpXMDM3TFUzenpVWEE0TzkraTZJcCtlR2o1dm9hYWQ5dFFsSWtsaW8yeGQycFgwWVA1dllBb0xPSisxV1NJenJLSU1LWWNwUlhnWUs4dEVOaWRMcGo4SU9HMC9hZGZsbW53PT0tLUxTT2hzSFY2K2V4SnhRS0hFZGNBelE9PQ%3D%3D--76b3770b9bef3f4d3df6aad3cf29520a50068588
```

Response Headers

```
HTTP/1.1 200 OK
Last-Modified: Wed, 06 Apr 2016 02:06:08 GMT
Content-Type: image/vnd.microsoft.icon
Content-Length: 0
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 13:04:11 GMT
Connection: Keep-Alive
```

### Placing Bootstrap files in a Rails project

1. Download bootstrap from <http://getbootstrap.com/>
2. Place \<Bootstrap\>/js/bootstrap.min.js under *publication-app/vendor/assets/javascripts*
3. Place \<Bootstrap\>/css/bootstrap.min.css under *publication-app/vendor/assets/stylesheets*
4. Place \<Bootstrap\>/fonts directory under *publication-app/vendor/assets*
5. Link the bootstrap CSS, JavaScript files in the Rails's app's CSS and JavaScript files respectively.

**Quick look at including bootstrap files in a Rails project**

![](_misc/including%20bootstrap%20files%20in%20a%20rails%20project.png)

To link bootstrap's JavaScript to the app, include the line "= require bootstrap.min" in *publication-app/app/assets/javascripts/application.js*, as shown below

*publication-app/app/assets/javascripts/application.js*

```javascript
// This is a manifest file that'll be compiled into application.js, which will include all the files
// listed below.
//
// Any JavaScript/Coffee file within this directory, lib/assets/javascripts, vendor/assets/javascripts,
// or any plugin's vendor/assets/javascripts directory can be referenced here using a relative path.
//
// It's not advisable to add code directly here, but if you do, it'll appear at the bottom of the
// compiled file.
//
// Read Sprockets README (https://github.com/rails/sprockets#sprockets-directives) for details
// about supported directives.
//
//= require jquery
//= require jquery_ujs
//= require bootstrap.min  <--------
//= require turbolinks
//= require_tree .
```

This line links the bootstrap's bootstrap.min.js. NOTE: This should be added after the jQuery lines as bootstrap.min.js depends on jQuery.

To link bootstrap's css to the app, include the line "= require bootstrap.min" in *publication-app/app/assets/stylesheets/application.css*, as shown below

```css
/*
 * This is a manifest file that'll be compiled into application.css, which will include all the files
 * listed below.
 *
 * Any CSS and SCSS file within this directory, lib/assets/stylesheets, vendor/assets/stylesheets,
 * or any plugin's vendor/assets/stylesheets directory can be referenced here using a relative path.
 *
 * You're free to add application-wide styles to this file and they'll appear at the bottom of the
 * compiled file so the styles you add here take precedence over styles defined in any styles
 * defined in the other CSS/SCSS files in this directory. It is generally better to create a new
 * file per style scope.
 *
 *= require_tree .
 *= require bootstrap.min
 *= require_self
 */

@font-face {  <---------
  font-family: 'Glyphicons Halflings';
  src: url('../assets/glyphicons-halflings-regular.eot');
  src: url('../assets/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'),        
       url('../assets/glyphicons-halflings-regular.woff2') format('woff2'),
       url('../assets/glyphicons-halflings-regular.woff') format('woff'), 
       url('../assets/glyphicons-halflings-regular.ttf') format('truetype'), 
       url('../assets/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
```

NOTE: removing .. from the url paths above also seems to work i.e. url('/assets/glyphicons-halflings-regular.eot');
whereas adding /fonts to the path does not work i.e. url('../assets/fonts/glyphicons-halflings-regular.eot');

# ~~~~~ How is this resolved?

@font-face is added to application.css, as shown above, to override the paths to the font files predefined in bootstrap.css. 

The definition of @font-face in bootstrap.min.css attempts to access the icons from the "fonts" directory, as can be noticed from below

A snippet from bootstrap.css

```css
@font-face {
  font-family: 'Glyphicons Halflings';

  src: url('../fonts/glyphicons-halflings-regular.eot');
  src: url('../fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), 
  	url('../fonts/glyphicons-halflings-regular.woff2') format('woff2'), 
  	url('../fonts/glyphicons-halflings-regular.woff') format('woff'), 
  	url('../fonts/glyphicons-halflings-regular.ttf') format('truetype'), 
  	url('../fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
```

**Confirming if the bootstrap files are being requested by the client**

To verify that the paths to the icons is configured properly, make the following changes to the partial to ensure that the client/browser requests for these icons and that the Rails app knows where to find these icons (if the earlier configuration is correct)

```erb
<nav class="navbar navbar-default">
  <div class="container-fluid">
    <!-- Brand and toggle get grouped for better mobile display -->
    <div class="navbar-header">
      <a class="navbar-brand" href="#">Publications</a>
    </div>

    <!-- Collect the nav links, forms, and other content for toggling -->
    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
      <ul class="nav navbar-nav navbar-right">
      <span class="glyphicon glyphicon-envelope"></span>   <--------
      <span class="glyphicon glyphicon-search"></span>
      <span class="glyphicon glyphicon-print"></span>
      <% if user_signed_in? %>
          <div class="btn-group" role="group">
              <button type="button" class="btn btn-default navbar-btn dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                <%= current_user.email %>
                <span class="caret"></span>
              </button>
              <ul class="dropdown-menu">
                <li>
                  <%= link_to "Sign out", destroy_user_session_path, method: :delete %>
                </li>
              </ul>
          </div>            
      
       <% else %>           
          <%= link_to "Sign in", new_user_session_path, class: "btn btn-default navbar-btn" %>      
          <%= link_to "Sign up", new_user_registration_path, class: "btn btn-default navbar-btn" %>                
      <% end %>

      </ul>
    </div><!-- /.navbar-collapse -->

  </div><!-- /.container-fluid -->
</nav>
```

**Requests made by the browser**

On making a request in the browser, the browser requests for the following files

![](_misc/bootstrap%20files%20request%20by%20browser.png)

Requests made are

```
http://localhost:3000/

http://localhost:3000/assets/bootstrap.min.self-66fe84b79c6d5db31355296a8c9627d232721fe3ac3c31f3554ccc7e999279b6.css?body=1

http://localhost:3000/assets/application.self-ca39df7438defaf3993fa4474e040dfae1e12491c6a53094db8619b44821f40e.css?body=1

http://localhost:3000/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1

http://localhost:3000/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1

http://localhost:3000/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1

http://localhost:3000/assets/bootstrap.min.self-d475868eedd65d9ab19f96e8574a2c8ce91ba7d64b8bbfa47cd55591a956ed67.js?body=1

http://localhost:3000/assets/application.self-f8806224e027f3e3f0138ea9ce99319e298dfdb323304d1f1be6eae8e8c74724.js?body=1

http://localhost:3000/assets/glyphicons-halflings-regular.woff2

http://localhost:3000/favicon.ico
```

On the server side, 

```
droid@droidserver:~/onBB/Ruby-on-Rails-Sample-Apps/publication-app$ rails server
=> Booting WEBrick
=> Rails 4.2.4 application starting in development on http://localhost:3000
=> Run `rails server -h` for more startup options
=> Ctrl-C to shutdown server
[2016-04-08 20:56:39] INFO  WEBrick 1.3.1
[2016-04-08 20:56:39] INFO  ruby 2.2.3 (2015-08-18) [x86_64-linux]
[2016-04-08 20:56:39] INFO  WEBrick::HTTPServer#start: pid=13121 port=3000


Started GET "/" for 127.0.0.1 at 2016-04-08 20:57:17 -0400
  ActiveRecord::SchemaMigration Load (0.6ms)  SELECT "schema_migrations".* FROM "schema_migrations"
Processing by HomeController#index as HTML
  Rendered home/index.html.erb within layouts/application (1.4ms)
  Rendered application/_navbar.html.erb (4.6ms)
Completed 200 OK in 311ms (Views: 301.3ms | ActiveRecord: 0.0ms)


Started GET "/assets/bootstrap.min.self-66fe84b79c6d5db31355296a8c9627d232721fe3ac3c31f3554ccc7e999279b6.css?body=1" for 127.0.0.1 at 2016-04-08 20:57:18 -0400


Started GET "/assets/application.self-ca39df7438defaf3993fa4474e040dfae1e12491c6a53094db8619b44821f40e.css?body=1" for 127.0.0.1 at 2016-04-08 20:57:18 -0400


Started GET "/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1" for 127.0.0.1 at 2016-04-08 20:57:18 -0400


Started GET "/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1" for 127.0.0.1 at 2016-04-08 20:57:18 -0400


Started GET "/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1" for 127.0.0.1 at 2016-04-08 20:57:18 -0400


Started GET "/assets/bootstrap.min.self-d475868eedd65d9ab19f96e8574a2c8ce91ba7d64b8bbfa47cd55591a956ed67.js?body=1" for 127.0.0.1 at 2016-04-08 20:57:18 -0400


Started GET "/assets/application.self-f8806224e027f3e3f0138ea9ce99319e298dfdb323304d1f1be6eae8e8c74724.js?body=1" for 127.0.0.1 at 2016-04-08 20:57:18 -0400


Started GET "/assets/bootstrap.min.css.map" for 127.0.0.1 at 2016-04-08 20:57:18 -0400

ActionController::RoutingError (No route matches [GET] "/assets/bootstrap.min.css.map"):
  actionpack (4.2.4) lib/action_dispatch/middleware/debug_exceptions.rb:21:in `call'
  web-console (2.3.0) lib/web_console/middleware.rb:28:in `block in call'
  web-console (2.3.0) lib/web_console/middleware.rb:18:in `catch'
  web-console (2.3.0) lib/web_console/middleware.rb:18:in `call'
  actionpack (4.2.4) lib/action_dispatch/middleware/show_exceptions.rb:30:in `call'
  railties (4.2.4) lib/rails/rack/logger.rb:38:in `call_app'
  railties (4.2.4) lib/rails/rack/logger.rb:20:in `block in call'
  activesupport (4.2.4) lib/active_support/tagged_logging.rb:68:in `block in tagged'
  activesupport (4.2.4) lib/active_support/tagged_logging.rb:26:in `tagged'
  activesupport (4.2.4) lib/active_support/tagged_logging.rb:68:in `tagged'
  railties (4.2.4) lib/rails/rack/logger.rb:20:in `call'
  actionpack (4.2.4) lib/action_dispatch/middleware/request_id.rb:21:in `call'
  rack (1.6.4) lib/rack/methodoverride.rb:22:in `call'
  rack (1.6.4) lib/rack/runtime.rb:18:in `call'
  activesupport (4.2.4) lib/active_support/cache/strategy/local_cache_middleware.rb:28:in `call'
  rack (1.6.4) lib/rack/lock.rb:17:in `call'
  actionpack (4.2.4) lib/action_dispatch/middleware/static.rb:116:in `call'
  rack (1.6.4) lib/rack/sendfile.rb:113:in `call'
  railties (4.2.4) lib/rails/engine.rb:518:in `call'
  railties (4.2.4) lib/rails/application.rb:165:in `call'
  rack (1.6.4) lib/rack/lock.rb:17:in `call'
  rack (1.6.4) lib/rack/content_length.rb:15:in `call'
  rack (1.6.4) lib/rack/handler/webrick.rb:88:in `service'
  /usr/local/lib/ruby/2.2.0/webrick/httpserver.rb:138:in `service'
  /usr/local/lib/ruby/2.2.0/webrick/httpserver.rb:94:in `run'
  /usr/local/lib/ruby/2.2.0/webrick/server.rb:294:in `block in start_thread'


  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/actionpack-4.2.4/lib/action_dispatch/middleware/templates/rescues/_trace.html.erb (2.6ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/actionpack-4.2.4/lib/action_dispatch/middleware/templates/routes/_route.html.erb (4.4ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/actionpack-4.2.4/lib/action_dispatch/middleware/templates/routes/_table.html.erb (22.1ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/actionpack-4.2.4/lib/action_dispatch/middleware/templates/rescues/_request_and_response.html.erb (3.0ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/actionpack-4.2.4/lib/action_dispatch/middleware/templates/rescues/routing_error.html.erb within rescues/layout (71.6ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/_markup.html.erb (1.1ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/_inner_console_markup.html.erb within layouts/inlined_string (1.4ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/_prompt_box_markup.html.erb within layouts/inlined_string (1.1ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/style.css.erb within layouts/inlined_string (2.6ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/console.js.erb within layouts/javascript (75.3ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/main.js.erb within layouts/javascript (0.6ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/error_page.js.erb within layouts/javascript (2.9ms)
  Rendered /usr/local/lib/ruby/gems/2.2.0/gems/web-console-2.3.0/lib/web_console/templates/index.html.erb (108.3ms)


Started GET "/assets/glyphicons-halflings-regular.woff2" for 127.0.0.1 at 2016-04-08 20:57:18 -0400
```

### More information on browser requests

*http://localhost:3000/*

Request headers

```
GET / HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/users/sign_in
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
```

Response headers

```
HTTP/1.1 200 OK
X-Frame-Options: SAMEORIGIN
X-Xss-Protection: 1; mode=block
X-Content-Type-Options: nosniff
Content-Type: text/html; charset=utf-8
Etag: W/"8ee74503f55f148a6271dac08903a226"
Cache-Control: max-age=0, private, must-revalidate
X-Request-Id: f9005c3b-284d-4a92-aaf8-3f9e2b5e2957
X-Runtime: 0.374671
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Content-Length: 2363
Connection: Keep-Alive
Set-Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04; path=/; HttpOnly
```

Reponse

```html
<!DOCTYPE html>
<html>
<head>
  <title>PublicationApp</title>
  <link rel="stylesheet" media="all" href="/assets/bootstrap.min.self-66fe84b79c6d5db31355296a8c9627d232721fe3ac3c31f3554ccc7e999279b6.css?body=1" data-turbolinks-track="true" />
<link rel="stylesheet" media="all" href="/assets/application.self-43d915a97a2982600a73d0dc761c4604e7a8d12d02297a1fe6d4f4156874ce6b.css?body=1" data-turbolinks-track="true" />
  <script src="/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1" data-turbolinks-track="true"></script>
<script src="/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1" data-turbolinks-track="true"></script>
<script src="/assets/bootstrap.min.self-d475868eedd65d9ab19f96e8574a2c8ce91ba7d64b8bbfa47cd55591a956ed67.js?body=1" data-turbolinks-track="true"></script>
<script src="/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1" data-turbolinks-track="true"></script>
<script src="/assets/application.self-f8806224e027f3e3f0138ea9ce99319e298dfdb323304d1f1be6eae8e8c74724.js?body=1" data-turbolinks-track="true"></script>
  <meta name="csrf-param" content="authenticity_token" />
<meta name="csrf-token" content="MZWAXIzvY7zvIwABmzc31HgDHr/Cx8OaefvVJxu0fb8eCFv2PrR8zoA6ktO/ANpLdDErLsZlobUWTVva4FJk5w==" />
</head>
<body>
	<nav class="navbar navbar-default">
  <div class="container-fluid">
    <!-- Brand and toggle get grouped for better mobile display -->
    <div class="navbar-header">
      <a class="navbar-brand" href="#">Publications</a>
    </div>

    <!-- Collect the nav links, forms, and other content for toggling -->
    <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
      <ul class="nav navbar-nav navbar-right">
          <a class="btn btn-default navbar-btn" href="/users/sign_in">Sign in</a>      
          <a class="btn btn-default navbar-btn" href="/users/sign_up">Sign up</a>                

      </ul>
    </div><!-- /.navbar-collapse -->

  </div><!-- /.container-fluid -->
</nav>

    <p class="notice"></p>
    <p class="alert"></p>
<h1>Welcome to the index page</h1>

</body>
</html>
```

*http://localhost:3000/assets/bootstrap.min.self-66fe84b79c6d5db31355296a8c9627d232721fe3ac3c31f3554ccc7e999279b6.css?body=1*

Request headers

```
GET /assets/bootstrap.min.self-66fe84b79c6d5db31355296a8c9627d232721fe3ac3c31f3554ccc7e999279b6.css?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/css,*/*;q=0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 121262
Content-Type: text/css; charset=utf-8
Cache-Control: public, max-age=31536000
Etag: "66fe84b79c6d5db31355296a8c9627d232721fe3ac3c31f3554ccc7e999279b6"
X-Request-Id: 515d5ef9-9140-43d1-ad4e-e1dab7ed1cee
X-Runtime: 0.062489
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

Response

minified bootstrap.css file

*http://localhost:3000/assets/application.self-ca39df7438defaf3993fa4474e040dfae1e12491c6a53094db8619b44821f40e.css?body=1*

Request headers

```
GET /assets/application.self-ca39df7438defaf3993fa4474e040dfae1e12491c6a53094db8619b44821f40e.css?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/css,*/*;q=0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 1185
Content-Type: text/css; charset=utf-8
Cache-Control: public, max-age=31536000
Etag: "ca39df7438defaf3993fa4474e040dfae1e12491c6a53094db8619b44821f40e"
X-Request-Id: 9a79929c-cef1-414e-9db3-c337fbff7726
X-Runtime: 0.015169
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

Response

```css
/*
 * This is a manifest file that'll be compiled into application.css, which will include all the files
 * listed below.
 *
 * Any CSS and SCSS file within this directory, lib/assets/stylesheets, vendor/assets/stylesheets,
 * or any plugin's vendor/assets/stylesheets directory can be referenced here using a relative path.
 *
 * You're free to add application-wide styles to this file and they'll appear at the bottom of the
 * compiled file so the styles you add here take precedence over styles defined in any styles
 * defined in the other CSS/SCSS files in this directory. It is generally better to create a new
 * file per style scope.
 *



 */


@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../assets/glyphicons-halflings-regular.eot');
  src: url('../assets/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'),        
       url('../assets/glyphicons-halflings-regular.woff2') format('woff2'),
       url('../assets/glyphicons-halflings-regular.woff') format('woff'), 
       url('../assets/glyphicons-halflings-regular.ttf') format('truetype'), 
       url('../assets/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
```

*http://localhost:3000/assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1*

Request headers

```
GET /assets/jquery.self-660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 294200
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "660adc51e0224b731d29f575a6f1ec167ba08ad06ed5deca4f1e8654c135bf4c"
X-Request-Id: 2ee33426-7eb7-48a7-ae18-becfb152f16a
X-Runtime: 0.013008
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

Response

jQuery.js file

*http://localhost:3000/assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1*

Request headers

```
GET /assets/jquery_ujs.self-e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 21648
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "e87806d0cf4489aeb1bb7288016024e8de67fd18db693fe026fe3907581e53cd"
X-Request-Id: b00e1a9e-ffef-466a-b116-7c0aacff9068
X-Runtime: 0.007010
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

Response

```javascript
(function($, undefined) {

/**
 * Unobtrusive scripting adapter for jQuery
 * https://github.com/rails/jquery-ujs
 *
 * Requires jQuery 1.8.0 or later.
 *
 * Released under the MIT license
 *
 */

  // Cut down on the number of issues from people inadvertently including jquery_ujs twice
  // by detecting and raising an error when it happens.
  'use strict';

  if ( $.rails !== undefined ) {
    $.error('jquery-ujs has already been loaded!');
  }

  // Shorthand to make it a little easier to call public rails functions from within rails.js
  var rails;
  var $document = $(document);

  $.rails = rails = {
    // Link elements bound by jquery-ujs
    linkClickSelector: 'a[data-confirm], a[data-method], a[data-remote]:not([disabled]), a[data-disable-with], a[data-disable]',

    // Button elements bound by jquery-ujs
    buttonClickSelector: 'button[data-remote]:not([form]):not(form button), button[data-confirm]:not([form]):not(form button)',

    // Select elements bound by jquery-ujs
    inputChangeSelector: 'select[data-remote], input[data-remote], textarea[data-remote]',

    // Form elements bound by jquery-ujs
    formSubmitSelector: 'form',

    // Form input elements bound by jquery-ujs
    formInputClickSelector: 'form input[type=submit], form input[type=image], form button[type=submit], form button:not([type]), input[type=submit][form], input[type=image][form], button[type=submit][form], button[form]:not([type])',

    // Form input elements disabled during form submission
    disableSelector: 'input[data-disable-with]:enabled, button[data-disable-with]:enabled, textarea[data-disable-with]:enabled, input[data-disable]:enabled, button[data-disable]:enabled, textarea[data-disable]:enabled',

    // Form input elements re-enabled after form submission
    enableSelector: 'input[data-disable-with]:disabled, button[data-disable-with]:disabled, textarea[data-disable-with]:disabled, input[data-disable]:disabled, button[data-disable]:disabled, textarea[data-disable]:disabled',

    // Form required input elements
    requiredInputSelector: 'input[name][required]:not([disabled]), textarea[name][required]:not([disabled])',

    // Form file input elements
    fileInputSelector: 'input[type=file]:not([disabled])',

    // Link onClick disable selector with possible reenable after remote submission
    linkDisableSelector: 'a[data-disable-with], a[data-disable]',

    // Button onClick disable selector with possible reenable after remote submission
    buttonDisableSelector: 'button[data-remote][data-disable-with], button[data-remote][data-disable]',

    // Up-to-date Cross-Site Request Forgery token
    csrfToken: function() {
     return $('meta[name=csrf-token]').attr('content');
    },

    // URL param that must contain the CSRF token
    csrfParam: function() {
     return $('meta[name=csrf-param]').attr('content');
    },

    // Make sure that every Ajax request sends the CSRF token
    CSRFProtection: function(xhr) {
      var token = rails.csrfToken();
      if (token) xhr.setRequestHeader('X-CSRF-Token', token);
    },

    // Make sure that all forms have actual up-to-date tokens (cached forms contain old ones)
    refreshCSRFTokens: function(){
      $('form input[name="' + rails.csrfParam() + '"]').val(rails.csrfToken());
    },

    // Triggers an event on an element and returns false if the event result is false
    fire: function(obj, name, data) {
      var event = $.Event(name);
      obj.trigger(event, data);
      return event.result !== false;
    },

    // Default confirm dialog, may be overridden with custom confirm dialog in $.rails.confirm
    confirm: function(message) {
      return confirm(message);
    },

    // Default ajax function, may be overridden with custom function in $.rails.ajax
    ajax: function(options) {
      return $.ajax(options);
    },

    // Default way to get an element's href. May be overridden at $.rails.href.
    href: function(element) {
      return element[0].href;
    },

    // Checks "data-remote" if true to handle the request through a XHR request.
    isRemote: function(element) {
      return element.data('remote') !== undefined && element.data('remote') !== false;
    },

    // Submits "remote" forms and links with ajax
    handleRemote: function(element) {
      var method, url, data, withCredentials, dataType, options;

      if (rails.fire(element, 'ajax:before')) {
        withCredentials = element.data('with-credentials') || null;
        dataType = element.data('type') || ($.ajaxSettings && $.ajaxSettings.dataType);

        if (element.is('form')) {
          method = element.data('ujs:submit-button-formmethod') || element.attr('method');
          url = element.data('ujs:submit-button-formaction') || element.attr('action');
          data = $(element[0]).serializeArray();
          // memoized value from clicked submit button
          var button = element.data('ujs:submit-button');
          if (button) {
            data.push(button);
            element.data('ujs:submit-button', null);
          }
          element.data('ujs:submit-button-formmethod', null);
          element.data('ujs:submit-button-formaction', null);
        } else if (element.is(rails.inputChangeSelector)) {
          method = element.data('method');
          url = element.data('url');
          data = element.serialize();
          if (element.data('params')) data = data + '&' + element.data('params');
        } else if (element.is(rails.buttonClickSelector)) {
          method = element.data('method') || 'get';
          url = element.data('url');
          data = element.serialize();
          if (element.data('params')) data = data + '&' + element.data('params');
        } else {
          method = element.data('method');
          url = rails.href(element);
          data = element.data('params') || null;
        }

        options = {
          type: method || 'GET', data: data, dataType: dataType,
          // stopping the "ajax:beforeSend" event will cancel the ajax request
          beforeSend: function(xhr, settings) {
            if (settings.dataType === undefined) {
              xhr.setRequestHeader('accept', '*/*;q=0.5, ' + settings.accepts.script);
            }
            if (rails.fire(element, 'ajax:beforeSend', [xhr, settings])) {
              element.trigger('ajax:send', xhr);
            } else {
              return false;
            }
          },
          success: function(data, status, xhr) {
            element.trigger('ajax:success', [data, status, xhr]);
          },
          complete: function(xhr, status) {
            element.trigger('ajax:complete', [xhr, status]);
          },
          error: function(xhr, status, error) {
            element.trigger('ajax:error', [xhr, status, error]);
          },
          crossDomain: rails.isCrossDomain(url)
        };

        // There is no withCredentials for IE6-8 when
        // "Enable native XMLHTTP support" is disabled
        if (withCredentials) {
          options.xhrFields = {
            withCredentials: withCredentials
          };
        }

        // Only pass url to `ajax` options if not blank
        if (url) { options.url = url; }

        return rails.ajax(options);
      } else {
        return false;
      }
    },

    // Determines if the request is a cross domain request.
    isCrossDomain: function(url) {
      var originAnchor = document.createElement('a');
      originAnchor.href = location.href;
      var urlAnchor = document.createElement('a');

      try {
        urlAnchor.href = url;
        // This is a workaround to a IE bug.
        urlAnchor.href = urlAnchor.href;

        // If URL protocol is false or is a string containing a single colon
        // *and* host are false, assume it is not a cross-domain request
        // (should only be the case for IE7 and IE compatibility mode).
        // Otherwise, evaluate protocol and host of the URL against the origin
        // protocol and host.
        return !(((!urlAnchor.protocol || urlAnchor.protocol === ':') && !urlAnchor.host) ||
          (originAnchor.protocol + '//' + originAnchor.host ===
            urlAnchor.protocol + '//' + urlAnchor.host));
      } catch (e) {
        // If there is an error parsing the URL, assume it is crossDomain.
        return true;
      }
    },

    // Handles "data-method" on links such as:
    // <a href="/users/5" data-method="delete" rel="nofollow" data-confirm="Are you sure?">Delete</a>
    handleMethod: function(link) {
      var href = rails.href(link),
        method = link.data('method'),
        target = link.attr('target'),
        csrfToken = rails.csrfToken(),
        csrfParam = rails.csrfParam(),
        form = $('<form method="post" action="' + href + '"></form>'),
        metadataInput = '<input name="_method" value="' + method + '" type="hidden" />';

      if (csrfParam !== undefined && csrfToken !== undefined && !rails.isCrossDomain(href)) {
        metadataInput += '<input name="' + csrfParam + '" value="' + csrfToken + '" type="hidden" />';
      }

      if (target) { form.attr('target', target); }

      form.hide().append(metadataInput).appendTo('body');
      form.submit();
    },

    // Helper function that returns form elements that match the specified CSS selector
    // If form is actually a "form" element this will return associated elements outside the from that have
    // the html form attribute set
    formElements: function(form, selector) {
      return form.is('form') ? $(form[0].elements).filter(selector) : form.find(selector);
    },

    /* Disables form elements:
      - Caches element value in 'ujs:enable-with' data store
      - Replaces element text with value of 'data-disable-with' attribute
      - Sets disabled property to true
    */
    disableFormElements: function(form) {
      rails.formElements(form, rails.disableSelector).each(function() {
        rails.disableFormElement($(this));
      });
    },

    disableFormElement: function(element) {
      var method, replacement;

      method = element.is('button') ? 'html' : 'val';
      replacement = element.data('disable-with');

      if (replacement !== undefined) {
        element.data('ujs:enable-with', element[method]());
        element[method](replacement);
      }

      element.prop('disabled', true);
      element.data('ujs:disabled', true);
    },

    /* Re-enables disabled form elements:
      - Replaces element text with cached value from 'ujs:enable-with' data store (created in `disableFormElements`)
      - Sets disabled property to false
    */
    enableFormElements: function(form) {
      rails.formElements(form, rails.enableSelector).each(function() {
        rails.enableFormElement($(this));
      });
    },

    enableFormElement: function(element) {
      var method = element.is('button') ? 'html' : 'val';
      if (element.data('ujs:enable-with') !== undefined) {
        element[method](element.data('ujs:enable-with'));
        element.removeData('ujs:enable-with'); // clean up cache
      }
      element.prop('disabled', false);
      element.removeData('ujs:disabled');
    },

   /* For 'data-confirm' attribute:
      - Fires `confirm` event
      - Shows the confirmation dialog
      - Fires the `confirm:complete` event

      Returns `true` if no function stops the chain and user chose yes; `false` otherwise.
      Attaching a handler to the element's `confirm` event that returns a `falsy` value cancels the confirmation dialog.
      Attaching a handler to the element's `confirm:complete` event that returns a `falsy` value makes this function
      return false. The `confirm:complete` event is fired whether or not the user answered true or false to the dialog.
   */
    allowAction: function(element) {
      var message = element.data('confirm'),
          answer = false, callback;
      if (!message) { return true; }

      if (rails.fire(element, 'confirm')) {
        try {
          answer = rails.confirm(message);
        } catch (e) {
          (console.error || console.log).call(console, e.stack || e);
        }
        callback = rails.fire(element, 'confirm:complete', [answer]);
      }
      return answer && callback;
    },

    // Helper function which checks for blank inputs in a form that match the specified CSS selector
    blankInputs: function(form, specifiedSelector, nonBlank) {
      var foundInputs = $(),
        input,
        valueToCheck,
        radiosForNameWithNoneSelected,
        radioName,
        selector = specifiedSelector || 'input,textarea',
        requiredInputs = form.find(selector),
        checkedRadioButtonNames = {};

      requiredInputs.each(function() {
        input = $(this);
        if (input.is('input[type=radio]')) {

          // Don't count unchecked required radio as blank if other radio with same name is checked,
          // regardless of whether same-name radio input has required attribute or not. The spec
          // states https://www.w3.org/TR/html5/forms.html#the-required-attribute
          radioName = input.attr('name');

          // Skip if we've already seen the radio with this name.
          if (!checkedRadioButtonNames[radioName]) {

            // If none checked
            if (form.find('input[type=radio]:checked[name="' + radioName + '"]').length === 0) {
              radiosForNameWithNoneSelected = form.find(
                'input[type=radio][name="' + radioName + '"]');
              foundInputs = foundInputs.add(radiosForNameWithNoneSelected);
            }

            // We only need to check each name once.
            checkedRadioButtonNames[radioName] = radioName;
          }
        } else {
          valueToCheck = input.is('input[type=checkbox],input[type=radio]') ? input.is(':checked') : !!input.val();
          if (valueToCheck === nonBlank) {
            foundInputs = foundInputs.add(input);
          }
        }
      });
      return foundInputs.length ? foundInputs : false;
    },

    // Helper function which checks for non-blank inputs in a form that match the specified CSS selector
    nonBlankInputs: function(form, specifiedSelector) {
      return rails.blankInputs(form, specifiedSelector, true); // true specifies nonBlank
    },

    // Helper function, needed to provide consistent behavior in IE
    stopEverything: function(e) {
      $(e.target).trigger('ujs:everythingStopped');
      e.stopImmediatePropagation();
      return false;
    },

    //  Replace element's html with the 'data-disable-with' after storing original html
    //  and prevent clicking on it
    disableElement: function(element) {
      var replacement = element.data('disable-with');

      if (replacement !== undefined) {
        element.data('ujs:enable-with', element.html()); // store enabled state
        element.html(replacement);
      }

      element.bind('click.railsDisable', function(e) { // prevent further clicking
        return rails.stopEverything(e);
      });
      element.data('ujs:disabled', true);
    },

    // Restore element to its original state which was disabled by 'disableElement' above
    enableElement: function(element) {
      if (element.data('ujs:enable-with') !== undefined) {
        element.html(element.data('ujs:enable-with')); // set to old enabled state
        element.removeData('ujs:enable-with'); // clean up cache
      }
      element.unbind('click.railsDisable'); // enable element
      element.removeData('ujs:disabled');
    }
  };

  if (rails.fire($document, 'rails:attachBindings')) {

    $.ajaxPrefilter(function(options, originalOptions, xhr){ if ( !options.crossDomain ) { rails.CSRFProtection(xhr); }});

    // This event works the same as the load event, except that it fires every
    // time the page is loaded.
    //
    // See https://github.com/rails/jquery-ujs/issues/357
    // See https://developer.mozilla.org/en-US/docs/Using_Firefox_1.5_caching
    $(window).on('pageshow.rails', function () {
      $($.rails.enableSelector).each(function () {
        var element = $(this);

        if (element.data('ujs:disabled')) {
          $.rails.enableFormElement(element);
        }
      });

      $($.rails.linkDisableSelector).each(function () {
        var element = $(this);

        if (element.data('ujs:disabled')) {
          $.rails.enableElement(element);
        }
      });
    });

    $document.delegate(rails.linkDisableSelector, 'ajax:complete', function() {
        rails.enableElement($(this));
    });

    $document.delegate(rails.buttonDisableSelector, 'ajax:complete', function() {
        rails.enableFormElement($(this));
    });

    $document.delegate(rails.linkClickSelector, 'click.rails', function(e) {
      var link = $(this), method = link.data('method'), data = link.data('params'), metaClick = e.metaKey || e.ctrlKey;
      if (!rails.allowAction(link)) return rails.stopEverything(e);

      if (!metaClick && link.is(rails.linkDisableSelector)) rails.disableElement(link);

      if (rails.isRemote(link)) {
        if (metaClick && (!method || method === 'GET') && !data) { return true; }

        var handleRemote = rails.handleRemote(link);
        // Response from rails.handleRemote() will either be false or a deferred object promise.
        if (handleRemote === false) {
          rails.enableElement(link);
        } else {
          handleRemote.fail( function() { rails.enableElement(link); } );
        }
        return false;

      } else if (method) {
        rails.handleMethod(link);
        return false;
      }
    });

    $document.delegate(rails.buttonClickSelector, 'click.rails', function(e) {
      var button = $(this);

      if (!rails.allowAction(button) || !rails.isRemote(button)) return rails.stopEverything(e);

      if (button.is(rails.buttonDisableSelector)) rails.disableFormElement(button);

      var handleRemote = rails.handleRemote(button);
      // Response from rails.handleRemote() will either be false or a deferred object promise.
      if (handleRemote === false) {
        rails.enableFormElement(button);
      } else {
        handleRemote.fail( function() { rails.enableFormElement(button); } );
      }
      return false;
    });

    $document.delegate(rails.inputChangeSelector, 'change.rails', function(e) {
      var link = $(this);
      if (!rails.allowAction(link) || !rails.isRemote(link)) return rails.stopEverything(e);

      rails.handleRemote(link);
      return false;
    });

    $document.delegate(rails.formSubmitSelector, 'submit.rails', function(e) {
      var form = $(this),
        remote = rails.isRemote(form),
        blankRequiredInputs,
        nonBlankFileInputs;

      if (!rails.allowAction(form)) return rails.stopEverything(e);

      // Skip other logic when required values are missing or file upload is present
      if (form.attr('novalidate') === undefined) {
        if (form.data('ujs:formnovalidate-button') === undefined) {
          blankRequiredInputs = rails.blankInputs(form, rails.requiredInputSelector, false);
          if (blankRequiredInputs && rails.fire(form, 'ajax:aborted:required', [blankRequiredInputs])) {
            return rails.stopEverything(e);
          }
        } else {
          // Clear the formnovalidate in case the next button click is not on a formnovalidate button
          // Not strictly necessary to do here, since it is also reset on each button click, but just to be certain
          form.data('ujs:formnovalidate-button', undefined);
        }
      }

      if (remote) {
        nonBlankFileInputs = rails.nonBlankInputs(form, rails.fileInputSelector);
        if (nonBlankFileInputs) {
          // Slight timeout so that the submit button gets properly serialized
          // (make it easy for event handler to serialize form without disabled values)
          setTimeout(function(){ rails.disableFormElements(form); }, 13);
          var aborted = rails.fire(form, 'ajax:aborted:file', [nonBlankFileInputs]);

          // Re-enable form elements if event bindings return false (canceling normal form submission)
          if (!aborted) { setTimeout(function(){ rails.enableFormElements(form); }, 13); }

          return aborted;
        }

        rails.handleRemote(form);
        return false;

      } else {
        // Slight timeout so that the submit button gets properly serialized
        setTimeout(function(){ rails.disableFormElements(form); }, 13);
      }
    });

    $document.delegate(rails.formInputClickSelector, 'click.rails', function(event) {
      var button = $(this);

      if (!rails.allowAction(button)) return rails.stopEverything(event);

      // Register the pressed submit button
      var name = button.attr('name'),
        data = name ? {name:name, value:button.val()} : null;

      var form = button.closest('form');
      if (form.length === 0) {
        form = $('#' + button.attr('form'));
      }
      form.data('ujs:submit-button', data);

      // Save attributes from button
      form.data('ujs:formnovalidate-button', button.attr('formnovalidate'));
      form.data('ujs:submit-button-formaction', button.attr('formaction'));
      form.data('ujs:submit-button-formmethod', button.attr('formmethod'));
    });

    $document.delegate(rails.formSubmitSelector, 'ajax:send.rails', function(event) {
      if (this === event.target) rails.disableFormElements($(this));
    });

    $document.delegate(rails.formSubmitSelector, 'ajax:complete.rails', function(event) {
      if (this === event.target) rails.enableFormElements($(this));
    });

    $(function(){
      rails.refreshCSRFTokens();
    });
  }

})( jQuery );
```

*http://localhost:3000/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1*

Request headers

```
GET /assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 24817
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff"
X-Request-Id: 3d07b160-f992-412f-a5bb-a3b69bfbf484
X-Runtime: 0.005308
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

*http://localhost:3000/assets/bootstrap.min.self-d475868eedd65d9ab19f96e8574a2c8ce91ba7d64b8bbfa47cd55591a956ed67.js?body=1*

Request headers

```
GET /assets/bootstrap.min.self-d475868eedd65d9ab19f96e8574a2c8ce91ba7d64b8bbfa47cd55591a956ed67.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 36870
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "d475868eedd65d9ab19f96e8574a2c8ce91ba7d64b8bbfa47cd55591a956ed67"
X-Request-Id: e100cb02-38a2-4a61-9afa-741882a405a5
X-Runtime: 0.005013
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

Response

Minified bootstrap.js file

*http://localhost:3000/assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1*

Request headers

```
GET /assets/turbolinks.self-c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
If-None-Match: "c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff"
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 304 Not Modified
Cache-Control: public, max-age=31536000
Etag: "c37727e9bd6b2735da5c311aa83fead54ed0be6cc8bd9a65309e9c5abe2cbfff"
X-Request-Id: c0b3fed7-a443-4e51-80b3-4dce7fab1764
X-Runtime: 0.003196
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sun, 10 Apr 2016 03:02:47 GMT
Connection: Keep-Alive
```

Response

```javascript
(function() {
  var CSRFToken, Click, ComponentUrl, EVENTS, Link, ProgressBar, browserIsntBuggy, browserSupportsCustomEvents, browserSupportsPushState, browserSupportsTurbolinks, bypassOnLoadPopstate, cacheCurrentPage, cacheSize, changePage, clone, constrainPageCacheTo, createDocument, crossOriginRedirect, currentState, enableProgressBar, enableTransitionCache, executeScriptTags, extractTitleAndBody, fetch, fetchHistory, fetchReplacement, historyStateIsDefined, initializeTurbolinks, installDocumentReadyPageEventTriggers, installHistoryChangeHandler, installJqueryAjaxSuccessPageUpdateTrigger, loadedAssets, manuallyTriggerHashChangeForFirefox, pageCache, pageChangePrevented, pagesCached, popCookie, processResponse, progressBar, recallScrollPosition, ref, referer, reflectNewUrl, reflectRedirectedUrl, rememberCurrentState, rememberCurrentUrl, rememberReferer, removeNoscriptTags, requestMethodIsSafe, resetScrollPosition, setAutofocusElement, transitionCacheEnabled, transitionCacheFor, triggerEvent, visit, xhr,
    indexOf = [].indexOf || function(item) { for (var i = 0, l = this.length; i < l; i++) { if (i in this && this[i] === item) return i; } return -1; },
    extend = function(child, parent) { for (var key in parent) { if (hasProp.call(parent, key)) child[key] = parent[key]; } function ctor() { this.constructor = child; } ctor.prototype = parent.prototype; child.prototype = new ctor(); child.__super__ = parent.prototype; return child; },
    hasProp = {}.hasOwnProperty,
    slice = [].slice,
    bind = function(fn, me){ return function(){ return fn.apply(me, arguments); }; };

  pageCache = {};

  cacheSize = 10;

  transitionCacheEnabled = false;

  progressBar = null;

  currentState = null;

  loadedAssets = null;

  referer = null;

  xhr = null;

  EVENTS = {
    BEFORE_CHANGE: 'page:before-change',
    FETCH: 'page:fetch',
    RECEIVE: 'page:receive',
    CHANGE: 'page:change',
    UPDATE: 'page:update',
    LOAD: 'page:load',
    RESTORE: 'page:restore',
    BEFORE_UNLOAD: 'page:before-unload',
    EXPIRE: 'page:expire'
  };

  fetch = function(url) {
    var cachedPage;
    url = new ComponentUrl(url);
    rememberReferer();
    cacheCurrentPage();
    if (progressBar != null) {
      progressBar.start();
    }
    if (transitionCacheEnabled && (cachedPage = transitionCacheFor(url.absolute))) {
      fetchHistory(cachedPage);
      return fetchReplacement(url, null, false);
    } else {
      return fetchReplacement(url, resetScrollPosition);
    }
  };

  transitionCacheFor = function(url) {
    var cachedPage;
    cachedPage = pageCache[url];
    if (cachedPage && !cachedPage.transitionCacheDisabled) {
      return cachedPage;
    }
  };

  enableTransitionCache = function(enable) {
    if (enable == null) {
      enable = true;
    }
    return transitionCacheEnabled = enable;
  };

  enableProgressBar = function(enable) {
    if (enable == null) {
      enable = true;
    }
    if (!browserSupportsTurbolinks) {
      return;
    }
    if (enable) {
      return progressBar != null ? progressBar : progressBar = new ProgressBar('html');
    } else {
      if (progressBar != null) {
        progressBar.uninstall();
      }
      return progressBar = null;
    }
  };

  fetchReplacement = function(url, onLoadFunction, showProgressBar) {
    if (showProgressBar == null) {
      showProgressBar = true;
    }
    triggerEvent(EVENTS.FETCH, {
      url: url.absolute
    });
    if (xhr != null) {
      xhr.abort();
    }
    xhr = new XMLHttpRequest;
    xhr.open('GET', url.withoutHashForIE10compatibility(), true);
    xhr.setRequestHeader('Accept', 'text/html, application/xhtml+xml, application/xml');
    xhr.setRequestHeader('X-XHR-Referer', referer);
    xhr.onload = function() {
      var doc;
      triggerEvent(EVENTS.RECEIVE, {
        url: url.absolute
      });
      if (doc = processResponse()) {
        reflectNewUrl(url);
        reflectRedirectedUrl();
        changePage.apply(null, extractTitleAndBody(doc));
        manuallyTriggerHashChangeForFirefox();
        if (typeof onLoadFunction === "function") {
          onLoadFunction();
        }
        return triggerEvent(EVENTS.LOAD);
      } else {
        return document.location.href = crossOriginRedirect() || url.absolute;
      }
    };
    if (progressBar && showProgressBar) {
      xhr.onprogress = (function(_this) {
        return function(event) {
          var percent;
          percent = event.lengthComputable ? event.loaded / event.total * 100 : progressBar.value + (100 - progressBar.value) / 10;
          return progressBar.advanceTo(percent);
        };
      })(this);
    }
    xhr.onloadend = function() {
      return xhr = null;
    };
    xhr.onerror = function() {
      return document.location.href = url.absolute;
    };
    return xhr.send();
  };

  fetchHistory = function(cachedPage) {
    if (xhr != null) {
      xhr.abort();
    }
    changePage(cachedPage.title, cachedPage.body);
    recallScrollPosition(cachedPage);
    return triggerEvent(EVENTS.RESTORE);
  };

  cacheCurrentPage = function() {
    var currentStateUrl;
    currentStateUrl = new ComponentUrl(currentState.url);
    pageCache[currentStateUrl.absolute] = {
      url: currentStateUrl.relative,
      body: document.body,
      title: document.title,
      positionY: window.pageYOffset,
      positionX: window.pageXOffset,
      cachedAt: new Date().getTime(),
      transitionCacheDisabled: document.querySelector('[data-no-transition-cache]') != null
    };
    return constrainPageCacheTo(cacheSize);
  };

  pagesCached = function(size) {
    if (size == null) {
      size = cacheSize;
    }
    if (/^[\d]+$/.test(size)) {
      return cacheSize = parseInt(size);
    }
  };

  constrainPageCacheTo = function(limit) {
    var cacheTimesRecentFirst, i, key, len, pageCacheKeys, results;
    pageCacheKeys = Object.keys(pageCache);
    cacheTimesRecentFirst = pageCacheKeys.map(function(url) {
      return pageCache[url].cachedAt;
    }).sort(function(a, b) {
      return b - a;
    });
    results = [];
    for (i = 0, len = pageCacheKeys.length; i < len; i++) {
      key = pageCacheKeys[i];
      if (!(pageCache[key].cachedAt <= cacheTimesRecentFirst[limit])) {
        continue;
      }
      triggerEvent(EVENTS.EXPIRE, pageCache[key]);
      results.push(delete pageCache[key]);
    }
    return results;
  };

  changePage = function(title, body, csrfToken, runScripts) {
    triggerEvent(EVENTS.BEFORE_UNLOAD);
    document.title = title;
    document.documentElement.replaceChild(body, document.body);
    if (csrfToken != null) {
      CSRFToken.update(csrfToken);
    }
    setAutofocusElement();
    if (runScripts) {
      executeScriptTags();
    }
    currentState = window.history.state;
    if (progressBar != null) {
      progressBar.done();
    }
    triggerEvent(EVENTS.CHANGE);
    return triggerEvent(EVENTS.UPDATE);
  };

  executeScriptTags = function() {
    var attr, copy, i, j, len, len1, nextSibling, parentNode, ref, ref1, script, scripts;
    scripts = Array.prototype.slice.call(document.body.querySelectorAll('script:not([data-turbolinks-eval="false"])'));
    for (i = 0, len = scripts.length; i < len; i++) {
      script = scripts[i];
      if (!((ref = script.type) === '' || ref === 'text/javascript')) {
        continue;
      }
      copy = document.createElement('script');
      ref1 = script.attributes;
      for (j = 0, len1 = ref1.length; j < len1; j++) {
        attr = ref1[j];
        copy.setAttribute(attr.name, attr.value);
      }
      if (!script.hasAttribute('async')) {
        copy.async = false;
      }
      copy.appendChild(document.createTextNode(script.innerHTML));
      parentNode = script.parentNode, nextSibling = script.nextSibling;
      parentNode.removeChild(script);
      parentNode.insertBefore(copy, nextSibling);
    }
  };

  removeNoscriptTags = function(node) {
    node.innerHTML = node.innerHTML.replace(/<noscript[\S\s]*?<\/noscript>/ig, '');
    return node;
  };

  setAutofocusElement = function() {
    var autofocusElement, list;
    autofocusElement = (list = document.querySelectorAll('input[autofocus], textarea[autofocus]'))[list.length - 1];
    if (autofocusElement && document.activeElement !== autofocusElement) {
      return autofocusElement.focus();
    }
  };

  reflectNewUrl = function(url) {
    if ((url = new ComponentUrl(url)).absolute !== referer) {
      return window.history.pushState({
        turbolinks: true,
        url: url.absolute
      }, '', url.absolute);
    }
  };

  reflectRedirectedUrl = function() {
    var location, preservedHash;
    if (location = xhr.getResponseHeader('X-XHR-Redirected-To')) {
      location = new ComponentUrl(location);
      preservedHash = location.hasNoHash() ? document.location.hash : '';
      return window.history.replaceState(window.history.state, '', location.href + preservedHash);
    }
  };

  crossOriginRedirect = function() {
    var redirect;
    if (((redirect = xhr.getResponseHeader('Location')) != null) && (new ComponentUrl(redirect)).crossOrigin()) {
      return redirect;
    }
  };

  rememberReferer = function() {
    return referer = document.location.href;
  };

  rememberCurrentUrl = function() {
    return window.history.replaceState({
      turbolinks: true,
      url: document.location.href
    }, '', document.location.href);
  };

  rememberCurrentState = function() {
    return currentState = window.history.state;
  };

  manuallyTriggerHashChangeForFirefox = function() {
    var url;
    if (navigator.userAgent.match(/Firefox/) && !(url = new ComponentUrl).hasNoHash()) {
      window.history.replaceState(currentState, '', url.withoutHash());
      return document.location.hash = url.hash;
    }
  };

  recallScrollPosition = function(page) {
    return window.scrollTo(page.positionX, page.positionY);
  };

  resetScrollPosition = function() {
    if (document.location.hash) {
      return document.location.href = document.location.href;
    } else {
      return window.scrollTo(0, 0);
    }
  };

  clone = function(original) {
    var copy, key, value;
    if ((original == null) || typeof original !== 'object') {
      return original;
    }
    copy = new original.constructor();
    for (key in original) {
      value = original[key];
      copy[key] = clone(value);
    }
    return copy;
  };

  popCookie = function(name) {
    var ref, value;
    value = ((ref = document.cookie.match(new RegExp(name + "=(\\w+)"))) != null ? ref[1].toUpperCase() : void 0) || '';
    document.cookie = name + '=; expires=Thu, 01-Jan-70 00:00:01 GMT; path=/';
    return value;
  };

  triggerEvent = function(name, data) {
    var event;
    if (typeof Prototype !== 'undefined') {
      Event.fire(document, name, data, true);
    }
    event = document.createEvent('Events');
    if (data) {
      event.data = data;
    }
    event.initEvent(name, true, true);
    return document.dispatchEvent(event);
  };

  pageChangePrevented = function(url) {
    return !triggerEvent(EVENTS.BEFORE_CHANGE, {
      url: url
    });
  };

  processResponse = function() {
    var assetsChanged, clientOrServerError, doc, extractTrackAssets, intersection, validContent;
    clientOrServerError = function() {
      var ref;
      return (400 <= (ref = xhr.status) && ref < 600);
    };
    validContent = function() {
      var contentType;
      return ((contentType = xhr.getResponseHeader('Content-Type')) != null) && contentType.match(/^(?:text\/html|application\/xhtml\+xml|application\/xml)(?:;|$)/);
    };
    extractTrackAssets = function(doc) {
      var i, len, node, ref, results;
      ref = doc.querySelector('head').childNodes;
      results = [];
      for (i = 0, len = ref.length; i < len; i++) {
        node = ref[i];
        if ((typeof node.getAttribute === "function" ? node.getAttribute('data-turbolinks-track') : void 0) != null) {
          results.push(node.getAttribute('src') || node.getAttribute('href'));
        }
      }
      return results;
    };
    assetsChanged = function(doc) {
      var fetchedAssets;
      loadedAssets || (loadedAssets = extractTrackAssets(document));
      fetchedAssets = extractTrackAssets(doc);
      return fetchedAssets.length !== loadedAssets.length || intersection(fetchedAssets, loadedAssets).length !== loadedAssets.length;
    };
    intersection = function(a, b) {
      var i, len, ref, results, value;
      if (a.length > b.length) {
        ref = [b, a], a = ref[0], b = ref[1];
      }
      results = [];
      for (i = 0, len = a.length; i < len; i++) {
        value = a[i];
        if (indexOf.call(b, value) >= 0) {
          results.push(value);
        }
      }
      return results;
    };
    if (!clientOrServerError() && validContent()) {
      doc = createDocument(xhr.responseText);
      if (doc && !assetsChanged(doc)) {
        return doc;
      }
    }
  };

  extractTitleAndBody = function(doc) {
    var title;
    title = doc.querySelector('title');
    return [title != null ? title.textContent : void 0, removeNoscriptTags(doc.querySelector('body')), CSRFToken.get(doc).token, 'runScripts'];
  };

  CSRFToken = {
    get: function(doc) {
      var tag;
      if (doc == null) {
        doc = document;
      }
      return {
        node: tag = doc.querySelector('meta[name="csrf-token"]'),
        token: tag != null ? typeof tag.getAttribute === "function" ? tag.getAttribute('content') : void 0 : void 0
      };
    },
    update: function(latest) {
      var current;
      current = this.get();
      if ((current.token != null) && (latest != null) && current.token !== latest) {
        return current.node.setAttribute('content', latest);
      }
    }
  };

  createDocument = function(html) {
    var doc;
    doc = document.documentElement.cloneNode();
    doc.innerHTML = html;
    doc.head = doc.querySelector('head');
    doc.body = doc.querySelector('body');
    return doc;
  };

  ComponentUrl = (function() {
    function ComponentUrl(original1) {
      this.original = original1 != null ? original1 : document.location.href;
      if (this.original.constructor === ComponentUrl) {
        return this.original;
      }
      this._parse();
    }

    ComponentUrl.prototype.withoutHash = function() {
      return this.href.replace(this.hash, '').replace('#', '');
    };

    ComponentUrl.prototype.withoutHashForIE10compatibility = function() {
      return this.withoutHash();
    };

    ComponentUrl.prototype.hasNoHash = function() {
      return this.hash.length === 0;
    };

    ComponentUrl.prototype.crossOrigin = function() {
      return this.origin !== (new ComponentUrl).origin;
    };

    ComponentUrl.prototype._parse = function() {
      var ref;
      (this.link != null ? this.link : this.link = document.createElement('a')).href = this.original;
      ref = this.link, this.href = ref.href, this.protocol = ref.protocol, this.host = ref.host, this.hostname = ref.hostname, this.port = ref.port, this.pathname = ref.pathname, this.search = ref.search, this.hash = ref.hash;
      this.origin = [this.protocol, '//', this.hostname].join('');
      if (this.port.length !== 0) {
        this.origin += ":" + this.port;
      }
      this.relative = [this.pathname, this.search, this.hash].join('');
      return this.absolute = this.href;
    };

    return ComponentUrl;

  })();

  Link = (function(superClass) {
    extend(Link, superClass);

    Link.HTML_EXTENSIONS = ['html'];

    Link.allowExtensions = function() {
      var extension, extensions, i, len;
      extensions = 1 <= arguments.length ? slice.call(arguments, 0) : [];
      for (i = 0, len = extensions.length; i < len; i++) {
        extension = extensions[i];
        Link.HTML_EXTENSIONS.push(extension);
      }
      return Link.HTML_EXTENSIONS;
    };

    function Link(link1) {
      this.link = link1;
      if (this.link.constructor === Link) {
        return this.link;
      }
      this.original = this.link.href;
      this.originalElement = this.link;
      this.link = this.link.cloneNode(false);
      Link.__super__.constructor.apply(this, arguments);
    }

    Link.prototype.shouldIgnore = function() {
      return this.crossOrigin() || this._anchored() || this._nonHtml() || this._optOut() || this._target();
    };

    Link.prototype._anchored = function() {
      return (this.hash.length > 0 || this.href.charAt(this.href.length - 1) === '#') && (this.withoutHash() === (new ComponentUrl).withoutHash());
    };

    Link.prototype._nonHtml = function() {
      return this.pathname.match(/\.[a-z]+$/g) && !this.pathname.match(new RegExp("\\.(?:" + (Link.HTML_EXTENSIONS.join('|')) + ")?$", 'g'));
    };

    Link.prototype._optOut = function() {
      var ignore, link;
      link = this.originalElement;
      while (!(ignore || link === document)) {
        ignore = link.getAttribute('data-no-turbolink') != null;
        link = link.parentNode;
      }
      return ignore;
    };

    Link.prototype._target = function() {
      return this.link.target.length !== 0;
    };

    return Link;

  })(ComponentUrl);

  Click = (function() {
    Click.installHandlerLast = function(event) {
      if (!event.defaultPrevented) {
        document.removeEventListener('click', Click.handle, false);
        return document.addEventListener('click', Click.handle, false);
      }
    };

    Click.handle = function(event) {
      return new Click(event);
    };

    function Click(event1) {
      this.event = event1;
      if (this.event.defaultPrevented) {
        return;
      }
      this._extractLink();
      if (this._validForTurbolinks()) {
        if (!pageChangePrevented(this.link.absolute)) {
          visit(this.link.href);
        }
        this.event.preventDefault();
      }
    }

    Click.prototype._extractLink = function() {
      var link;
      link = this.event.target;
      while (!(!link.parentNode || link.nodeName === 'A')) {
        link = link.parentNode;
      }
      if (link.nodeName === 'A' && link.href.length !== 0) {
        return this.link = new Link(link);
      }
    };

    Click.prototype._validForTurbolinks = function() {
      return (this.link != null) && !(this.link.shouldIgnore() || this._nonStandardClick());
    };

    Click.prototype._nonStandardClick = function() {
      return this.event.which > 1 || this.event.metaKey || this.event.ctrlKey || this.event.shiftKey || this.event.altKey;
    };

    return Click;

  })();

  ProgressBar = (function() {
    var className;

    className = 'turbolinks-progress-bar';

    function ProgressBar(elementSelector) {
      this.elementSelector = elementSelector;
      this._trickle = bind(this._trickle, this);
      this.value = 0;
      this.content = '';
      this.speed = 300;
      this.opacity = 0.99;
      this.install();
    }

    ProgressBar.prototype.install = function() {
      this.element = document.querySelector(this.elementSelector);
      this.element.classList.add(className);
      this.styleElement = document.createElement('style');
      document.head.appendChild(this.styleElement);
      return this._updateStyle();
    };

    ProgressBar.prototype.uninstall = function() {
      this.element.classList.remove(className);
      return document.head.removeChild(this.styleElement);
    };

    ProgressBar.prototype.start = function() {
      return this.advanceTo(5);
    };

    ProgressBar.prototype.advanceTo = function(value) {
      var ref;
      if ((value > (ref = this.value) && ref <= 100)) {
        this.value = value;
        this._updateStyle();
        if (this.value === 100) {
          return this._stopTrickle();
        } else if (this.value > 0) {
          return this._startTrickle();
        }
      }
    };

    ProgressBar.prototype.done = function() {
      if (this.value > 0) {
        this.advanceTo(100);
        return this._reset();
      }
    };

    ProgressBar.prototype._reset = function() {
      var originalOpacity;
      originalOpacity = this.opacity;
      setTimeout((function(_this) {
        return function() {
          _this.opacity = 0;
          return _this._updateStyle();
        };
      })(this), this.speed / 2);
      return setTimeout((function(_this) {
        return function() {
          _this.value = 0;
          _this.opacity = originalOpacity;
          return _this._withSpeed(0, function() {
            return _this._updateStyle(true);
          });
        };
      })(this), this.speed);
    };

    ProgressBar.prototype._startTrickle = function() {
      if (this.trickling) {
        return;
      }
      this.trickling = true;
      return setTimeout(this._trickle, this.speed);
    };

    ProgressBar.prototype._stopTrickle = function() {
      return delete this.trickling;
    };

    ProgressBar.prototype._trickle = function() {
      if (!this.trickling) {
        return;
      }
      this.advanceTo(this.value + Math.random() / 2);
      return setTimeout(this._trickle, this.speed);
    };

    ProgressBar.prototype._withSpeed = function(speed, fn) {
      var originalSpeed, result;
      originalSpeed = this.speed;
      this.speed = speed;
      result = fn();
      this.speed = originalSpeed;
      return result;
    };

    ProgressBar.prototype._updateStyle = function(forceRepaint) {
      if (forceRepaint == null) {
        forceRepaint = false;
      }
      if (forceRepaint) {
        this._changeContentToForceRepaint();
      }
      return this.styleElement.textContent = this._createCSSRule();
    };

    ProgressBar.prototype._changeContentToForceRepaint = function() {
      return this.content = this.content === '' ? ' ' : '';
    };

    ProgressBar.prototype._createCSSRule = function() {
      return this.elementSelector + "." + className + "::before {\n  content: '" + this.content + "';\n  position: fixed;\n  top: 0;\n  left: 0;\n  z-index: 2000;\n  background-color: #0076ff;\n  height: 3px;\n  opacity: " + this.opacity + ";\n  width: " + this.value + "%;\n  transition: width " + this.speed + "ms ease-out, opacity " + (this.speed / 2) + "ms ease-in;\n  transform: translate3d(0,0,0);\n}";
    };

    return ProgressBar;

  })();

  bypassOnLoadPopstate = function(fn) {
    return setTimeout(fn, 500);
  };

  installDocumentReadyPageEventTriggers = function() {
    return document.addEventListener('DOMContentLoaded', (function() {
      triggerEvent(EVENTS.CHANGE);
      return triggerEvent(EVENTS.UPDATE);
    }), true);
  };

  installJqueryAjaxSuccessPageUpdateTrigger = function() {
    if (typeof jQuery !== 'undefined') {
      return jQuery(document).on('ajaxSuccess', function(event, xhr, settings) {
        if (!jQuery.trim(xhr.responseText)) {
          return;
        }
        return triggerEvent(EVENTS.UPDATE);
      });
    }
  };

  installHistoryChangeHandler = function(event) {
    var cachedPage, ref;
    if ((ref = event.state) != null ? ref.turbolinks : void 0) {
      if (cachedPage = pageCache[(new ComponentUrl(event.state.url)).absolute]) {
        cacheCurrentPage();
        return fetchHistory(cachedPage);
      } else {
        return visit(event.target.location.href);
      }
    }
  };

  initializeTurbolinks = function() {
    rememberCurrentUrl();
    rememberCurrentState();
    document.addEventListener('click', Click.installHandlerLast, true);
    window.addEventListener('hashchange', function(event) {
      rememberCurrentUrl();
      return rememberCurrentState();
    }, false);
    return bypassOnLoadPopstate(function() {
      return window.addEventListener('popstate', installHistoryChangeHandler, false);
    });
  };

  historyStateIsDefined = window.history.state !== void 0 || navigator.userAgent.match(/Firefox\/2[6|7]/);

  browserSupportsPushState = window.history && window.history.pushState && window.history.replaceState && historyStateIsDefined;

  browserIsntBuggy = !navigator.userAgent.match(/CriOS\//);

  requestMethodIsSafe = (ref = popCookie('request_method')) === 'GET' || ref === '';

  browserSupportsTurbolinks = browserSupportsPushState && browserIsntBuggy && requestMethodIsSafe;

  browserSupportsCustomEvents = document.addEventListener && document.createEvent;

  if (browserSupportsCustomEvents) {
    installDocumentReadyPageEventTriggers();
    installJqueryAjaxSuccessPageUpdateTrigger();
  }

  if (browserSupportsTurbolinks) {
    visit = fetch;
    initializeTurbolinks();
  } else {
    visit = function(url) {
      return document.location.href = url;
    };
  }

  this.Turbolinks = {
    visit: visit,
    pagesCached: pagesCached,
    enableTransitionCache: enableTransitionCache,
    enableProgressBar: enableProgressBar,
    allowLinkExtensions: Link.allowExtensions,
    supported: browserSupportsTurbolinks,
    EVENTS: clone(EVENTS)
  };

}).call(this);
```

*http://localhost:3000/assets/application.self-f8806224e027f3e3f0138ea9ce99319e298dfdb323304d1f1be6eae8e8c74724.js?body=1*

Request headers

```
GET /assets/application.self-f8806224e027f3e3f0138ea9ce99319e298dfdb323304d1f1be6eae8e8c74724.js?body=1 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Accept: */*
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 582
Content-Type: application/javascript
Cache-Control: public, max-age=31536000
Etag: "f8806224e027f3e3f0138ea9ce99319e298dfdb323304d1f1be6eae8e8c74724"
X-Request-Id: 418fc53a-24ca-410a-9a1b-55a8d4a14025
X-Runtime: 0.008508
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

Response

```javascript
// This is a manifest file that'll be compiled into application.js, which will include all the files
// listed below.
//
// Any JavaScript/Coffee file within this directory, lib/assets/javascripts, vendor/assets/javascripts,
// or any plugin's vendor/assets/javascripts directory can be referenced here using a relative path.
//
// It's not advisable to add code directly here, but if you do, it'll appear at the bottom of the
// compiled file.
//
// Read Sprockets README (https://github.com/rails/sprockets#sprockets-directives) for details
// about supported directives.
//






```

*http://localhost:3000/assets/glyphicons-halflings-regular.woff2*

Request headers

```
GET /assets/glyphicons-halflings-regular.woff2 HTTP/1.1
Host: localhost:3000
Connection: keep-alive
Cache-Control: max-age=0
Origin: http://localhost:3000
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Accept: */*
Referer: http://localhost:3000/assets/application.self-ca39df7438defaf3993fa4474e040dfae1e12491c6a53094db8619b44821f40e.css?body=1
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Content-Length: 18028
Cache-Control: public, must-revalidate
Etag: "fe185d11a49676890d47bb783312a0cda5a44c4039214094e7957b4c040ef11c"
Vary: Accept-Encoding
X-Request-Id: 6a62feb1-a773-48a4-aaf7-94cc6d298515
X-Runtime: 0.009014
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```

Response

```
data:application/octet-stream;base64,d09GMgABAAAAAEZsAA8AAAAAsVwAAEYJAAECTQAAAAAAAAAAAAAAAAAAAAAAAAAAP0ZGVE0cGiAGYACMcggEEQgKgqkkgeVlATYCJAOGdAuEMAAEIAWHIgeVUT93ZWJmBhtljDXsmI+A80Cgwj/+vggK2vaIIBusdPb/n5SghozBk8fY3CwzKw8ycQ3LRhauWU8b7AQmPrHpsWLSbaQ1gVqO5kgksapZihmcvXvsSAlqZIYL1YkM/LIl97nZp395IqcEA/f21yuNQLmMXb2rZZ/7e/rS+3aQoE5jiykOu275k8k/fj/okKRo8gD/nl/nJmkfxsrIHdGdBcGkiz+6PvzlXksg+3a0LRtj240x7fSAEokyS6Dhebf1LCdu5KvgAAco8DNFd2ngQgUXgqAmqf8L6c5UtGxo2DBNGtLY2tKGZOVZ2HLx77Kss250ad5d3Xl1cpW0vK77me4TVlhzag6hop7lZ01uGarTmUiBV5Wpw9QIIHIy9D5pVGBWN7jNUiixqMnPGuD/K6BvNvMnY8XIQrCP5gbrNOe31s653X+Hg4vjv5quVAldYVtRZDwzd3E4LI6F7nJUSRahOOESHI4wPkW4P/kqRajnl6aVI8/6NyeN7N39hlMJDAtvY/vKt+1fizcmIyrRKym9s6DQKzRhAbBBNrZjjOd5sdmjhmYoYhlG6ebk/+m0JDt7IFlBwzF2UC10R/j/jOHAsRXNIvuwldsBQ8JmLSBXgveuAprUmc51S9awSwjjI63tDuSs1ipLhjzb/AQgKNHf69T31/9a/mDZqwzltVuXJepZBVSKrHslr8mKJIitEKBze2/v7RmcF/KIgxjVu+92dCJw4Jw0YMjq36mKz6R9bwxg47PdFPonbhRl3D4K5EceNXMAevNfTvMKklBL06Z2bVXeC8m+e3q93PLu8/+fGfh/+IyHIjNgbA2SHAOWVyPUkL1eGEArjSwHY7nJa2+pjUFPG3AVbnW1p9R685Z6Sin13M6lHveY2zHHfeHh/0893n+ttoB4vlLGxGDBSolgp3GDFaWCVXMvvyv4a9J2xzF4bBrd3+dqEmwFlkVs7FxuRIzIw8a2r1aGseb/0Gpnm3taZOWJCHo3jwsUNf/fIQR4bcI1b8JbBxy9v3Xv+ya3rzHagkgQQmtB4uwIcXLqzlKQxA2jt7AWjyhcZ2j0EBTIN4ns0op5jz2GSLVa81VQaOnQJDgQUmfTBcQYgHrCZ82tyU46i+AAMXWsJNyFr6Shnj5S/V3l+hSXDqasIp/0Zje8lwv1S69efyeYquu9M5MrRS+8xF6JWVU1XahOQhcu3sqLpdI438Urzs2POI/5LHyJe018jEGKEeV1YXzQYYiSf+yO1d7LhdWdJQAKf2xLR6JQ7SwXTnUU5tzUa/5j7zhtWEDa02T/F8yYP3/x/NrzoudZ0ybP/nvq9pT4s8fPDj/bUNworhRHil22v8/G5K/kT+SP5Lfk1+SX5AZyLbmSXExGyQg5lywmp5N55DhyrPu0+zP3H9yfuD9wv+8+6n7b/br7FXPo5P8Fi54S0BCi00THCKR68zH6oT8SXFU1FnE9rdl00XrUkg6GJlqQbmqiJeltTbQifbyJ1nRr3kQbundooi09/22iHb1CE+3p9Tc28fSugyY60rvJcXQiC9YxOpMVrOvQlaypdTv0IktfoS9KZNZjMJZssvUcMB2yxSdeAxZCtvk4VkO21XpnsAayvawPBlsgO8r6ZOwK2VnWF2J/yIN1HQ6HvKl1O5xAnip9AQZ5iXwMLqmsJ0M+E1xnPRvyOeBW68WQrwG3W2+GfGfwoPVekB8MnrY+ivxkvAo5rc/H++QX7tjF+JQKKkV8QaUOj+MbKk2tW+NbKm1P3A7fUel6HD9Q6W7dGz9SKVmPwW9UJlvPAVUqi5U1EMBT2QxNQgv+7AShpfBbsxMKrYTfb1lEaK0Y1Xvs0Sx9MTxmjSYCNmikGIYnj4F/B8qlVSNWqAjeEa28H6GlRftEfyJUwaXeqdAGokFEOYP/ZUK5OqkHBhXEJQ8CT5zBINLQBBPxgofYRhJ1im4gFjc/JVIDRzQihLhmqWfHwUbquoEgDmE9gpEts9VRl+G9eStCvSzE+NAyw8sT1oU1opWH8JmEjHhuoQUVzqoEZiohobPm62zifEdYUfgg3oNVcJTkCsVFdSDCQJ4Bj6blLfCABB9Eby42WVr2gi0mYT5mEj+bAKuTTo9OnKIJXdRPL147XNoOwkrKDc9CBsdFc0pyGQSqkBkBoMSa9cYPFCfyhWcSL+Pj0UIXJZ+hHm8gH0P16rpulTeL3DoFfPV5g0t0sib3JKfYc698ufV3UIj5xFxpXb4kWhJAKwHNDLa21YA5MHhdu3K4rSW+yNUr9gdSVaxFbYcrFtywqqM7d6B1rMA5L0m8BdQ3yDfVprlR/mx1XKZ50A5XixBOKes4idywdlnuKnW0bQKUobG/6eKp4gS6bSgJZgbKRb3y/0c4sgyiaiNJrL1SjswX+XoMI3G437ffAQYJhClZoNckiwvh0JuGY18lv20teyEwLWALO+HlhazxFGh5VvXkwV1IdiEJzx90HGG9XEvvxRAeBqVbzDF7GgMi52ogNkDsljNUMCWlE78P6c6YIsfUmcZaSYZH5AabU5P3jYIusxHEzqNwB4HG06xTxjFl6fvZk8TYm535DFnBHv92uzgaCGSxXLFCoRdsoVP7/lIpBtIT04bn+a+WroALewJJitOG9NIlnZSvPvsw0I7aprNc8CeUY2e9MiU0oFGORKEKMM2SM0KyIslNjtWOJoDbimhJFcfC2qfSUmcQt01FpKGpobaaDUm9zigHqd7VNVWWRF0MffIdmQdi7Tgkl4fsOKg+8+FYIAGyB2iVImwetc6A4mocnS4liNuAGEhIxy0LSZqm3bgjMZIdQwE09d5Z3gE3hO3urhLtWd2WoVYMbwgaPlDKXaE2v7cHmPaZTzT/N2YaDb1+ABgeQUpkWUbVwoDKLpbeb/XD/nkpCcY4bMYLtjIyjmWKnB+m0jFIG6FbAXSJsEAhyIUMMlyAQLgINQbE2ZPKJVrX7vzba96SCAZh9Z2u3ED6LmBuqDPKT0aMohBSKPOFpbb3/71aAWtMawVGIO1IV2pZHw1JpOo11+cqE/E22s5ltVNiay6kvDVGLBfsLpUCTjDf1JmSuYB8lIZWpoB8fH4FTvSHKAkgNLed7NpdLOwaSnB8fvl4ZdPJQajUHKGvNYiIL7vau1Ok/QTk9JTQdvLX3Hk/m/myJ192fHLqhMtY3Ab47kjpUcoFsLUVBcSTQkA9C91YrN/6rEITGDnLNLOYq8NUqdhCiUKpY6CtwRirSJFQo84rgvKJgV+Tk9VZSNkjrCSqy8pgoOxG+KPxQjvjtcIr2xGUhUJQUrA0zLwgdAStOnQI9SJaE0W6Sl4hWMLHk+CscTRfZFRXKDXk3IAEp+X/5B+42kmxlFXFh9JBzXr+QFU2/24uV0dY/cDBBehI7FJLwBbbGiYIJ3N3TbFqisqOmIuxPJ+UsZgzpimAlp1gI0ZAEgwYDEYg1KLgCP7Ydo1vzWIkeAwH7yuy4Lx1+ya0fYl8ylgYJlvZqpA4RostuUUmLz6KLxfRR8UuYep6XoreL4PU/n0pnBGyE5LzJ5N4qZEkTz08AcfCepmkb+Sn4UE5TR/YnSYd8n7uoZm5MxlytQUzZ5+cpie/ONKjXLAttk1EesjoEZj4a7rNNYb5sbRBCt3C/apHOankfDEt2CEgxzg3+xBbnH/0pCxtUu51fKY1N64KHD1Y/pGkLJhhSqfZGxabuF50tE6bNNPYXGYQ0IRdQXobSF4CN7eqRpXoHP6VmYQmayIbTFU+few+53JC5Vgo24Kq64ICVJolv6sLSqoIv4StZGhLxB+U87ZQk7JLwR5URmFBhzNISIZDW3I7YZvAtmQCt5kXhxqVNTTIzAyJl2xMhGsDakcPGnuh7DifaH7kjwcNZlJAA9Ds/B45d+BCqKTg0DDrC3pT9fSw4v8nl6AUAmE3A4JA3UBOm7GK3ca5bJFiGGozD2hOBBPuslj2i0Yvye1lonOj2Sf6ikRzUavxPP5rXtPtHfLXvLL9iFpBU0+oaRdkulNK43gcTjREvbPAS9MhtLnU+Qkh2at2iaxoQWDbRZa3WBCQlQACvMotDaJQDe3EOp+C29GkG39D6jrCwlfNelO9c8RkTww6CBC2X7+r1Mtgijp0wWHOt9CRCx6lhrLN2LP6ohaBrg28SVnwBDTHDCMgEJD4KtIczSs8A+pxAG6wb9QAuHUKVQgEzGN3d4/zeCRktbPwG8a/Dp19z4H71sE5NMz9mu38AzlwrCpUOvolRxVR5oVeYZ+LFYcQ5APdyyeo52WDHvRi9qgEFBSKbC3V3CpY3UznJSrFuggZuC6F2orIXIpAcFIkVOUqS9YYzQW9CLhocIfAiMjowYLf46Zt+sEbkeItL5NvU9ozjt/CRY3gz850b3+4B55959C2Vodv9QdlSgtgPJkk9tl07dgSvd/8HwmqXWcq31qbD4S1NnGwwPlskgT4fhv3Ra+rCoZT+rgvipL5aaPEVMZ0zWuCx67gslfdw74M3D0/arkAR6LSzNRVVQVBSsb1Dv2bAhxghtJi1MuRl4NHwoj1Uc1Bz6upgfHDls4VxtrsY4P76r1Xy++pFegDV1NtCN3ArWezutpGy/GqkSapXhb1+tiY1KGINjtDMTo924hQieS6FNVgytqckFZW/5Md1EWdxjUitGhPq1jgfhQbq97YTjNfNdOBXbp6Lf6t5JJDV9PddNSljYLTiLTQGMtl3F2wXLaUqb8dVq8ZE5aL/2PUIx1tW8Zrdd6XrV/KsSKpyfZzjUizf/Q8fXjvsQKFbTBi5XgBSNNxYh+RYTN0ZudNVNvRzypdSbsYHAoV3n3XKBz6vpwsTZSEjZY9igndQIxKQdvG0GSJkKCsyz/CpzZQVrH2Ww1kVuN29OY0ap7S35uRbEhc4vfUFozF6HuY2PICTfTlvciYXLqdjeUBWf7cgYAcHYFgOU3DYEQTYoc8wQUSO2EjevKGkTyKeCIG8yyoZIJnQ2m/YJFjkpsWOsEBBcjiSbTiPmp3t8x9SgXIyXqnjV46Vi4d/TrX/tqLE3u/zbwGKMiyQvfmyxzJpgOSyfN4jjwYHkRiIyJTo6F79JJQ+Uh1vU6BLxPre3I2BTt3VbYT5tDyEnPWUBfQnpM8pOdYwOBZ4nPUxPfeTXh1sIcUXJpiAJHac7gkEY6YEXiOyiiiiS9efANeKhgwan5t4Kw7I7clSoTeTTSdx3CYUU3XrPA6OhpiXEMyZ2YBsLBdvXrSUDhUmSBVqpNRYtbodLqDHUMcvVSfPgpwoDgrNmdfMpZszqE2p0jyEQgg2s4Ax4YPSJ069w1kmzzmQ83pNrOv2KTqL6u/Nn/jRTrCS4uUIstga0qpPJvPxqLkPQj5dp43hKXiTjW3tWCw8pu2SnSLEtlcark2zYUlAw7Lnjf0KqUnD6UQlVWV2TSxOuIbWCsN5FwCYgD8kkUKEeTs9N5hZq6KeIwfk33BiTErcJmLQqXLMO428hfilOX9njNy9UEkG04Umn62EvQjs2SqfQjH16SfUDdo90g3YqNGqp7Cp4WCrDjwEQ0es1A++EJ0GR5HTtAUFY6i8G3kAYJ49ECPagmFkbh8e8BzORIZ4Ls9D/53UtkvratvREpzNRZ6PpM7iid43fFFBtBxFV4GculePUcaP72FOUHqoQZ/5pbHQeRfl6MG7UsltUTJrjp1aWtqa+5JGGXJ5r0arEf61Z0jKqGGKbVqbQaR4Xy9dKO5fWABSuapWtiI6db3FwcDSA89NO6de2ffgaK+KaFxWIhNQSwXmkj4jDcY+zGJ61YipdkUD28s51kjaBL9/PfdqFMX8l/qO4vNYV/Ul1peY240oq0QjaCCSLhFq64/iauwEX3RCsidobut3O682aQ9fUKeV3beqlVl8OVomheD2gBHHYqTRpCFiZHmO51AMlOl2AGcgEDLZiAF/sLL/G7N4jLQI42O5h658RNm3Vk6Xb9KeeUISF0arZUtt5hH14x3Z3YnoQcE4nyIxDBl8QrDXzeI8NKQq24rZh7f2bji4Fk8q+cozQqqP/bskhCpkXny+aEld22sK2oOgyYmIeiiY5NeoXUnnWL8JvFon202EATCpJrO+7kqMgw/HLRBx0kcq7bGsjVGBle+2Jlb4sacBqhC9VV670nORZSTIZJtOovS+5x4aNRll93Hrm68enxdJQyNkG0R2XLBVbhGjdqvkAWU+RF/rjHGCx2JfTshD24gRr4moGfy2vH/UImG3QGvrxsbOybX9qmc+O8YJCS4GulGqykaLnSbQu1RqDOmjr0VKJ5DPfq30+SmWMDO2GVz1Dvdafurtq3ZikC80Qh+/E7tyRsbzqFFAX/rCdRTUosUBBShiGidXOnoo/rBQmXxbxi6hr2coLS5zgFiVNEWhAZuzpIRanUCub7AGwkHZ0Dk9ycEcVHrlI5ueC51NmJWVSbUDJtduTvb76oVIUNfDIQWBgsIno01xireerkdybr7bYBSUXWRqnGCkuAWprFQ/NpaMIO2fW3xvKHMBsr1br2mXm7VT3LJVKbiwZG1zjqfVeMn12jA5qcwbg9aoXBeGVLpfERGql9iXPJAltZtgYLoREXrOIEAxntv6B5HTYnhoJwBcbjdzwZ93O5TZCAWFK4PQywb+wRpwNyaReodEorpL7Dew4tbGGQ4XY7XLE1DSZrO0PNfdZcsXVaZgWPxIpfkpHAYsAZnHUDsYCJ5KYssO0KzXmWtnmwQ2ggEoaoyJ4AuKJ3N0MSY4nk+4C0afM5orRjcE9PEd5r6/uo7qWrlpegdku3VjRjR0mnUvbHkr+pfGQhvfCFA9inJot0eqsQ9f9nMjFNQep2X6R0fiCohen0pvHzGp1R9vWoYkYZFo3RDrFrloW6MjRe9f8O9nCrVnvXJNNuG171buamxC745GrvQrgWojuiIF5EGkt2T9Yx6YFcIbRRl9G+Ci3xqOGqt7zXhGJA5vPa1QC76mkW/GFbML8xaVwVAF3yXgWZf5xBcIiQde+EFnJF2EKHg8oPznMDIL7gG8rY7YdcWHDpTZaZpM1TkR8sQKuvO/YNduMahL8xoFMAyHUMzMiS/0wEO9L/8MX2/jESkzU5Yyfj+dOw/Rs+d7X5uLFBqOQ8u7pY+16P8qM17Cjn9f8lFTi12fDNohhTykUPF0LhFlJWHIFhU4OLLO1CWJMM9jUrWLQ/d1Wfdlf35aWd6fnGXKEHpPDpoEzGxObMz4U7szL31UYmL48d9Q0zYf5BX+d+nwteO3H6DEhvhDRLaYpmlIoaBh818xzR1fe7wrdcB2WOZeYAE4IvINrChMv9bIKXY1lxkuCy10o7Vs2KBEWv5pMxE5eS+JTBU3Hitrns9O/bUt4uGASiEaQiHC43YTFO3+BPfMb2Y+P2p0TP/Ts9oL6Q2P+YnRV72fv/G1FCuf3tzWuwbmVrTS5TEnhNCe5JEzHT4Jom91HqS0/cptRdVb2H5NVGmM4+RyJeIcn6/jpG+CqYB9Nn5Rl0RoCS6POgE+nRtKJp9DPvDz01CQIeeW5xHeOwIzkbTBWgQOACbI32I9CyjI8CYdQv9TGF6KN5RaLE0JdN4AW0EYFUT4JXVuS5FEajjdjFhkp40Dl8nL1uoZLF7RnioSco1OZ6MDINE9RE86uwmkDhWiEXzRmfJyNkL6IqYI/VJkeSfjTJTss3u/18GD+OpXVFxQROabojRX/BRGecHEj5i3pg0Z6EZqK0TsS2uATAmB0UjY6bcaTi/CXZSL9U0/xhynorrCJpQN5WjSwNzT1cFtU4z1Y8edkVcYnGGf/tR3zUYEo1audq9Vnk1B12NE73W9uBoLwlpKcX7naaOLS+0sOOha7VOrNGOvsjEHBMjZewpIlAX7fH8CAl7/UtTUZB4ibK4naY+YeMmte22jjxhLOumjBdIRUjP8vOJDQIcXZQlLGVEnrNVfle7bP0XjwPam6s7Y77hmJP3B2D+nT8gob5wkU0Nsgts6+ouglCyVzf1BqHZo8guGi/0V5wjO1f1ZCqWOno7RTKGqJ/u9uP6aqEH+DkTecncQcdTkFM46HXAjLbgrDtmWTi7bSBL0a/o7NSE1LaJzaE+LIQXoA4NX+hnpbTxLW3hYzzXGG5d0KctFK41kTJjqLmhrvF6Daw3ZCBQnHrzE+UBtRng8vCyVoT2k/ulTx1Qdma8Uv4MUqTTxuCwkzmGWg0tn8Ee3mQShveumoi/Q5ua8fPHYCz2YXTBPRMUh2s/dqLtNCNQDeikQswWCKGa2KW4L1sX9QZzLjxhFTBlxnuPtCaOonb+EPKhYX4BHWUBCNDzOIvoKWbksRwX224UeQaS6gJm5EJQHEz5dfGzSXmySBg9U/gy9tEdlNIiW8PIKNnCvE9A7XoqSbi6QMX2MJfkqiOY49zgLBrQAAKt9MVJJFGhz3kNDWP00Z5GDethj9+eA3Yisu8OfFLH3JgJJ1ecE0agDHg/Ef4rYU6DTfauj0vOYMZEBd4DL+i3bmY6WLhJODpICbFJUm1dm0v0ujZpDiD8QFUSz0gqTu3QbwhGrOD9O5axqZvhh48iAledcaO+ZFyT74qIiZHQjSpDPSPjMs82eJQ37DxUz9UbCjd5iNRyVT4tYkgpERHJunrvICd9tte23e53nCEEF3LBWM4RWoq1CbQuOpJWbtcTO+4t7j6KOuEKHQI2AeBy/72HDh1VwWNz1TRrrBFWV6x7kvqJ8COtD5g135EwwULd4+zHYNyd/zB1mtEiLlHKxh+sm2RCtJgwo5Qd9ZhDntBy9R5d7e/gI+26UTkIbHGc4AJOXvTWs42v6fRofqBOVVy0ILwxNpoKfunoFZMc4ZRTkW6HVPIEbKKRXP5USNKy2pst2cl+qkd+KSSFb1E3Hi3rr0PvEbDMAcjsfXESJS8cYZmms3ZPsKp8W3E0loKKkrN+QmMtJE7cGzc8VhiFSEWAH2ktmZwX6FLIRpMMR05N4HvQIjOVkAz7NDmHWxWEajygkOG4HaxX060LyuNo1fiYAr9skW7bBsMg/MjYUdKo2olHB2NxqO9Ad68vZSBx/6PMFeYBZ84crsg8iKPNxhAPOiCg6uFh6ZK3opF1rxDqzfGUlV9Qi2AM3flie0XrHOGmSSgWz9lPV0fdHOarZkV5wNzpQUJhX57fO08IXo5EUaPiJ+i1c/Pl5wzu0OzzYETuI9Gaaa86GNG02yvfFlkBe6l70nDlJrbFXN8aUmGemsDBl2cQ/s+eMP/BH2f671T5TM5pPCefN/YPpj/ABdII51gxucDPQ+/WCmGlv+nubjBvuXIx0QyZHhcvVa2liZ0F9QvOb48vDz/pleKZr2H501+scBXqj0jWsQ1H9ey0oKbCOJ/doz8zRokw8AeYgNlgJcP3z5HE0zyNCkeaXdS9nBk4YmzNjyUtLMIpfSWeA0qUOha5WQKt0mrQGxBUzTvQq8i2NcWSPp42HL2fkHfSew+cVumkgy4mE6P2KIYOb7mpKvVuPKfYbjkGoQbBSpYKImGHB6kL0JQIzd0roYYLYcovu/26uvA7N3pE2FrOtxF713SPTQlNcJejCWnYmmu8TlB3iNiRzbrwSGBUDfYkMjMbloZmHtP2wNDaMJp6H8bIO62hpp7nIvBdjPKqgiqOWbKk6RAs5FGhV4HYG+AO9LhsU+m1xsVPjnJXJDUGXUuhVtm7QuIWhdyahUm4GIoYa9p83z2yJsFb1Ojq3tHexTU4RdNSpDDei0drq3MbU+7xwW7j8m4RbnXj+vFFeEuN0H9y9KKsjH2Hfm0f8dlgEI5HNAJ1e9DR8T1dNmakAPfiCNeoCkJv1h4mPA2Zw7FjOzKgrhBQJMPHg3ttV19jG571wqonQjbQij8kvV56W49DA5cdWbndrZnppWrQTvN+C/6m264wBb67m/p0oq8G+rDb4oQ2LyktiTF/OnAkROqlhciXCq4QGg4KLCezhvx54PWx+MF2mMQghW6ci0azVNfRgZlbBCdhpk1izkpduyWQJsOuEKxsYzYCJsLoSXBG5ZDEDajcb/CMaYMGqsTJ/uMVNbGg+CdyqOTL5XKRKHG87+iQ+q7r7r56NsGw9p7uySg189DhRQ704Mmi1Z9sE1wdhUzxnWu6N6uwMcVZNF4pAmLZl8KmOPm8efjGj6rk2wpOntg9g5s5elSWXltUJIdka8IZnA1R4mlLJeGINo61kPxxtenn9czuZk98A+Da4GPQOCSVamledhsEcv4CLlFRUiLiWeFyxIrj4vW4DajDa/iSpd5yn7q8Sw6IorU8UUmJIhG3QLTv6lIQFDkN9sAPL72rGFwmN1l9bYln0oo3u5wceja4LU35dT2CwOks9f5OM09cujaMw2FEQY673q7wTGRecuvJLy6uPvug5ugKTrdl7c8IUmkT+zSmvtUhM1L5oroVkCKNNKaIyPH6mm6ZYuFtyS15W1impv/P8S4ixvQZIZT43FFLr+VFXAdOj+u1NGfVoNed+AWnv6aD77FhTqZwgg0+ayk5wcEwiEKNWurMQnMK9qV5ihlyjpplcqspdq+irkTz63TocnaBXPt2+Vut/D7zcrVKbZyBApYKYZzyq7XMvJt+dd0X6urVj7o+tXJNWpywmGPtQjz44w9gKVx513R8243v/3InPIYYGgb0mOA++dfW/uNb5sOOl++t6Gg36/qt/lrFEASMOH9jYUmBIbkNtHDiop/NzK4ALLYPR8PtC7trB6A1QMjZ9PcIG/9g9Mlpdw2I0m7Qnh04cJ92vyDnyRPpKo+dssInTwoL3R3U/IqyFKDdQVvILqGkco8WaPNUDXBSPys7y//zXBEqSItzTHHe5utVmrlmluI6cWwtxIekDPEqNiGFaOcry6wEAHtot4n2LSBqZ7FryU1NyddQI+O25Dq8fZGxuHsv3evuVsvfxbZDXeyYmeq3JluzVyTaqwEDXt8j4Pu4tjRmHVdhXA2LBcE17PDourpNWzaevRwpVKczl5UbFZt+/Nodzg6tyRLUwArjOi4gWpSmvAKoYHPeaSjNUvSpUYW8ssx8L/pg+QppbM9esEwjoKf3HfJmpC3x1zstQzsTX9ze+Sr5e0BFTUNvb8OCX6ScxsP1Nxe+VPbjcnF63Ea1JRfXr3yZmlU8WqTcb8ETW1RBPY6EBNAnRFBKXbQ7LFU5Ga+1ylGbsdNwip5rBvE0foAd6uEGweIGXwWNQ6pemXFFosWukJxiDYFTR3Pa+N/tf1mFnTJOlkEOrtJ17a4fJfDwU0SEgiDXaGoJCv95Ozkk37RJQajVaOQERU+PzBGE4bLLfQqoFmeJs6yFFJcvKyD51YOT7zWdSlnKIEDkB0f6+I2N/L6C6q5mMhSQorQEl1mgxOcvuMLfvJl/ZYTft7mxfHbeLxYfuCLe/9Vw5YDYfuWIi/FU4/Q4Hk9L83Iq0g+e3SoNhoMdwBM0aGngQFGbmTNnIh/RBmqynxw69CT7lTsdOpT9pGbgzfyW94wsZL2urnrNyMia2cbUjOq6swOwqxp1Jeegy6N9T/Ums76CaRkyD1XoLAtAAs1r6moPJXU/2xrjNKdOnEtt9t750GQ/NcndkzvKMJlZ753a/GV9c1r0gBuHqj5FxqtVc14U3Zx2e6B/6wSkpmZRPMSQoYlWUPzvw8pUDmbNpu4/pZD1bdhw2VAqAMgmAab30FGHR4n5e2OcA0rv8UVQGGUyKY54UL0wBUEG0d/NAftNyapaSLZqlSIR17si2UEFrNBDK3pxiW0EVhF64ZaeBfNVJdhDtQA6FkAxDubj8Fe5igzuWxF5Kc5KQPdvsWIlDPdqlBVBPilOD9LHgNRpf+e8JJJB84jA7HRgPsw/ZjBnAP9IMzZw6DbhzER8+wRNm+QM4fYQNE6NobAKnJIgNEq9StqDHq8KtWoHpJ6YxocBtPNcDe1woDPTGfgcjqM4jcCmqtHjltCv75QTu602cK4R+VY/OqwkgnNE+cBO+hK1Dsa5kTLvkm6SLLaESN1PXIJbuPjVuJv2S9ktKZ2rV365aeltmT8Y/66DVNA6sMzw3rpV1mVZjNPjii0jZEplKa+x2s9aqtU1lD/4JLvmDqFcZKlXGTy3ubksyYZ/hpo7r9i3uMM1zc3yU7jVuK+8GpdUq1SW8ZrOCMyEZiiBUFkOsHY9UQ1+RFh/Kge83w/dOPjovqlzLQnCCAXLqK7OgAU1NQIMrQ1YolKlbCBRQ88IGOEZpM4M4ZP4A9HAbHzy/TXOe/vTplRcdOq8lSvp76Nlu27F27iLksJQc9PoH2z7MxWZnflVT6lb/Nvux1q7yVMz5cCd7p+dKujsLJiqht86w5taH/6+xtRMiZushtUFU52d9BUnzLXm4yoH9fKMKkCo+BmdH8Sxfnhnbm8ysbkZ4RaI4i0KhYwgs1ezFIqrvVYcADvkcFrlBDmNPxN+hBirJKs2nzyUtVFygmJROCbzFHNlG5XJRWKv2lEULLf+XnxCsrXv56KY71ZkrFYttijcXeMgLu/oy444HxIvcWhWoRtuUq7zrlHIRIkq+VUoKjFo5zEUw2DYnVFMEnsHhYFVagsLYBfg0iKabx4zANy75plWqAJsBYW1OhwJ0e3qwtjADWphBEZh4BCeRa22zJ5aiItnMbG3evywzDLWoNU6BM1BddlaSWY2loMBMtV0dysIiomJF2YZgadEj4se78noEaqpEUNMLX0UZ7u1WhizMD7ShPN4SqL9/8U+XO6QwetRibhB2l9DtmmCaN/SYg9sXQ0FGoc23tXeHdw0HioOmkHLrxbJsPxxWImkBDeEG7sUWfJYLoAtvora1biVYcmHw1biaBeslmlLZ5XUz3FOs1LEhk4ochEnwV284CXZmISPha30jYhAM9TNgM7CgWqnFlqs90qGLh87/ONubd36r9XOLFP7+9gEMHivs8MfAfX42M27o09GBzMzrdKntoWrPCQn2w67uEeXRSu02n2lpc7z+vOnhScx8GYzm8b90nnQNd0vJqRanFwaUkL0N2Rt7fRd5rw4p6fCXM39AYQz34KEyKqYQPfsb7/7VOm/M2V1XhIdt1dAiqoV/JSWjqZlN2yWHgchQuMswHOC5OYx3M3fJJrkG/Kv21qn4ybZFJLnPwOv4mRD6eEgnShZ0KZTbT6CSiImcHTe3IiqUOOHhANCGwFGrBT4tJ3aBLHg2fg0jEfhNZwJdF4dxIYkr97yai1h46CNZxpewQ7KkEOkEpaFg0ECc9ZUPWuhVFMsfA6AcuDlD5o5SbcPvULPmAfQrIb2JwHC7HZHAEG2zhFAkM10BBDAzGhR1U5qhiYYgAXlVD3OA3h0OzJdrxJQoXxULQcJTMOeg5LJ57/xZTEU4929BFfDWsWaKk1ySDU/hPGCPeAA/dFvsAOsIuvGOdFLNc74Pasna8ktKgeVhOhBphIPFkV8Cf4g3iBx0pQTkV8/XKM3JR72jnxNNrBmqiuTkyuSUyp951cAX9xdM6qo+rZmbdyu2NLLs9LcbSB3IZaX7vflLttSI4nprKo7xu0f+qaxcaBx8zcxigHW5CTCld2Z1a9fGcDzaUvgJuxKqc6sTa6KrPbeGsdlbRLlVsQ1UH/PMD4Uvr4gUZ0V57U1qoZXlalIrUlo1xrl+Sb5NNKNSWzTRTd94nPI6cRtW2PIvuwBooR8jWReCaLs9yVVdukBMQ+mRAeTsj6TLuhUrNIbNyrpPXSDWrhfp+OfvjHQpTo9MHBa+5oGNtKLik4EhHQXFAAo5Rd17Q4exp2tOyDHQtJds5EkgGuh2oyAwi7ze6pGxCoDEi9VHVqSH8ZOCPwS56CmfG9xisoVS5dHO17W5L6eOU6n+2Uf/+14S4sMkqGoXId3aP748X6h8vJaAnBI1GKREovN5Im4Hgy7iNtba7Y44snNzGv34i5iWA8uUb5YcAK4eA5ZYV61GALQIpjRI+ufGJnjQrMQd25ipL8R8+WQddPwoOltNZ5Gsg+9fj7H0DgfBYCtwWL9+o7kTjrdcBs0C7UBW2d2XgpCvdNG0FV6+yk/nLw2MI/QRsnJBziYggDCLwQyoIxDCDiojK4+GJ1OOEfuj80lEGzzJegf3TW6RkiYezSENmgcBKeO77g0jiXGASMNN7jomx3xjs36y3gM82+63E4gdKpclSffyKgPDagg+uZFo42O5r0wI4MS72q4TsOjVu/TuWTgP1dsY1eQgdfwiwvE7QrFvr3WtbV1+y2TBrt9DzKEMqi2pUVOkL99I4fktbUySF5hM/D1uxmlcrvBcXOnpLCIhC2PUzMmyAQU7/SEZrTth6MOzOvOZndsLpo9V/g45YQs9eDSY0gD4a5qnmNU6rFXrg6R16AFc4E5DvIwnu6UWuBEzk0Rk/q+QzKSWk2Sjd37kGRqtYx0nxYiOMA6Z+17LsaxsNAxRmI2gzHHOCIGedSmPpj1vwySrVfAOaPrINNWmhqKivYLr2DXEmq//a4Wmo+/VPKUlJGRgDxJEaO9TdSxVyclrWYbJrhceeRa62RrAc206PlSBHnRaneY5gUVffmI0IDP31s4whfUjQKGu6PHYkLtIKknZCdt/G/7Eic8nRH4fEXUys016vU6FbO52otvvJqpyT6ytXIsboOpacCtwQ0NPFSquFO5uZ8+pRZks4Ug//TpcU6nqt0MLmcEKyDvUwfCGuu8DVH6+beBvusPCQ2B4UsCYUIIAb6M2+A/X+2L21GNRSCHk7VyuIb/aqTugmg+9JVFppDTmzsTj0Od1603f4WLHLdeca8KxmBVr2X6Iy2fmBi3O29KmMSL49LmjtSdPikLx/2CO0pn7aPPf9etOVI7T2ftoh/F/WlJN/p9l+I4S6GSnB/bgQRxpmqPudFl2JOjK9mXJ27xz7drM4vBrbsH/GVGz4ED+wWe7A6FMLGa8q/fViOp7cZwpU1BemJeUI73Vs91pNt+3jF1upfSk5V3Hm7ICV6bLklJl6GKXxzGzNp2ZFeuyPaP885bUSzN3ugrTA8EvmKCFu2+yQKl5YTGxIdxvP4NOatWHH3vCZTOj1bRdzRxVeQzJmrbxLFIWWK8IPy5iAsVv3QVdI1UnPWIN8+B8pKr2WEWckJ3UDk/Kdt1lemLVC/ZYaOVjkExOZYRsWuqTQpc0+RQ3d9zmzzYVGGejdDjQII8P03iCygQf+oIvC6hLCclPyzHJYFhHH5lzgXrEo7AnY5V4ZYwtc0velHV9ijRuP2T96RhmayqcDouNqtqwv9kRkBcVq40psl/e9NSaez+GQuIzTjpr8mqBm51/a5G75hNX4anPaa99Vo44aQDSOPuimyHc3k1ayX1zHwXKPBpOQILItk25Lp91It+V0uE258EkWhZqWuKyvYXpBOXXOD712yTUm0Pjru0JtINuh3mpvHY8jC+78Fi+11nyhOUtb4iwufegERe/bLmvt6MqGr/sRVKKimemjYDqLUYiy1ZYtlo1uD38ukKWv2v6d89BN6RpkEsjsoojp1LI9AJDZayT2bISgIbOu47vkmGvschNgFZaSb7ZNng1iVtrjg2I6r2mVGBtdLUzFdfkRUb9kGbdn0/K+hH4ZrK+gljYw4qEP9t+/SSZ2DSPoUO9XGx2Csc+6M92Vs1xM2Ut7bW1z+yOaNXwMkrXv1vr15F4OM4c4Ep5Y9m5wuXMmH05gEWrVGfBXgBGn+kF7dph+kmCU5FPiJeTmHkYZ87ZorZzDldTkUmCXQYXrDAQ0waeifiZYU4WlLxB3MmNt4CsjdfAB/8w6NjeUqekTEaDcT+QFRasD9TAEQy+woah3zUUPXUy0/TjOlcZKoaUu/e8Ps3ekjV+IPusTlpyAMAi1Ejtb+2gnpys/NjLvI09oZH/VKdEzTOyHF4pvC+PDJ+WJJotfduCOEZ4xngqbOoBsUyiGF1Qq1OQ9EAK5uia5dY8zAO0Q0YE2FqNW4DPt6JqPWyEmUz9gcRdt6nF9P06TylPoGwX7KfkKAH2wx1SDqgBJBYUp3/JX454QQhNPb8b9EP0bym6BwCADOFuuKUOD+2giDOHzEBZBoj79TR/ByWmkEmi4SEe0EhaTYLi4zt3C9YYZ2foxrhBeOHpD0SVxaJO3zvBPDkGimBINBnFr5+ow0/Kr7mgr3DIH2/49qniEsRdMw+NXytRY610O7R3NUup/30QQf7mgtR8Tb8+g0CB7KAvig2GgoKNtGUxjcAltr3PDn5+V/wlUPBDGYxDxn+69CO6Wk4FQa+robluywNVrs0JMCfdXTJ+Jz4o8ZpwSwuYHY2cgnio/KOUA2vGr1nRkKQyY7HCnQb8sPn2g1DATO9O5gMHwQYLLxvw4KT5uOceHwJCi9L801wqTFTX76RWC5m91aNqoYjvFU+yJLI9YgjQvbxXbUNQRUdj5FJVm/AzNCGz7XAkRQVv/xHVFYxbnIro85PWMJTlSULi5sEwrO2mWanT1pb21/9OZz7EZFQrd+w9yAPe0dsEW6RBSXfI9rbaMBkd79IoPk9hn8guHmpZS/tqle8GbO0tj5/0izT9qywSVAsKk1WlfCEfsK6SybjZRWixIu7+00G7L2jPfIpFotxRr+gU7bfCBsFtCLJR9HrVJpGmY0quUxYLGiKW5e0upOnd453tO1l8VdRRdl42uu6DD/h6JN7EF7ahkWOeO9ou51p/bsFoteCjxKESpSzw8BIjwelfPNe2c2TioXJZSpeidCvLuN12nhFmejry2Ij7jubkvTUnTxdel1c7YPXAoGof3faTrtob7xjaHG4RZijPR665+ITNFExH7g3Dv3d51f8vcyTbMOVNo/hp78UrRJIRV/Mo6D5cXn/iR7hC1kGUo6k26saPHg91GNT31gVeSE9MPs4x5fzeNYMmJ30/j8fsXt9ov/A7t9GX4T84cegmXr4r4lrdKnJsfCIN7PK2oJ8dPunK2Gubbg8eAdlJILpZZaP48mNqtc8Wxy5VPem/49YWxz+4ZobC55/+AOj2fYAG79zux1Ww8yLq96nVZ7JKhGz4Yxol1OpSz1GZctzdyB1Welvzd/Zr25RqxezPU4bRTpb0ih/F3Rd5Q1r13znQJHZv3VaXDl7aIGxj3YQfxiAFNrcldOGLtqh+nNhg4kkdSufcbkZdzoj4x/mP+Vl+lSJMz3QFKwH0LvQIbVw7FBMYM06hZPd0FIDOwzYZwjKrgudBkZoYZ3OkDuvFAcTzBOGNUlloCsYltvY9bsODJ3XYnQwNkFXNDBUzWhKY2M8JgPAbUpjY+AKuBAMjQfzoU8cG0Nuq1c//PlOB8Jp/u6+b10oWNCE+59790x67Jj02Tu/8NjxZ7nvfMeP5z4Y5Dl+bDRz5lZ5+a2ZYIrXVd+bLPmf/vHXxSNfynW0+StEZerq7Zng6U3Z/KJ+A2izcarrsoeStyNZ+srm8Xr8JDvbDDXNrzkktcsgerIdPv8Kvipq9U+fjfiM8dsknNAkTy+vwA8Vw3hS7b2DwnT9Zi19Kp5v78mm+NnMfDOGTTsVeN6or1WUlbVsLy4U8X5Yx46vWeG8NJl4Mybm69d4riI7pCSNS0n2kjXbZNqtDL3K4fz6i353W8rUTRkfOU/Y4yU00uFRqBx96RlTXp7sdJad6EDRy+YOd1ubWTst3fb/jcC6czuiYr7Nd0gtKgUM75aWw2ltvbZJyggtth9/MWUvlX74qFROTq4u8nCy3/ApSCT766tX799+j87wA5C1ycam7bxPCiig6TnohizZDV1nTTZyHeorhCO7ByWD4C9z/HevQRicJBH1jHHGNMsRB08+CmQ5ffedEyvw0SSMc/Sas/0/AzCjmRRhLD6deYu52ohzPPD+PYYs8ItjXypc4oNE7bzcfcgyGU3tsM3MVDgXLxLtNOZn5ifapp6d4jgn+30ii0PiAyqEXDm9I1mPHz56JI7m9tQ3Y1tzk3wiJH27CXltzBbv1cCrelF4IDW3JeWgb/nlkyRqhmvQznASKfF4vcT7LTq6htCYfD+dmG/j+Ganh2dGcsCe3zIVGopTkcda94wCEXF9cYiKtQmFb4AdHyx3ecVPoWfKE5BDRjHWbJjnnycG7Uw1VDP18jP70fB5qqZNiTnaMiJzlJjyNRR1G0SVizbA1C1K7IlVCIZiBXO6zxgKq08pg8wWd7hSDS0y5i81Ztw8qkJRzDQWa4yY6pCtnUe5CRMfKSXfvA7jPGQexuDEqsSe7bwBM8gyC2COHBphAhLYw12pqlN7o0sl9FxdpjMIJoGKcBKEk66uG9q42huIlEPVuKIM/Zyp64a2kyz3wA3a+V7pVNDZ2ze/aLw1mXX7bETAo3jat7Yfl/EDTCdEtgbwhBhywzYd+nYMGdW3ZmNc/qP9p7VnQeoFkcKds6CGskAAP7a9nsLYf8GRCZyVR0bmwVYRQbdsLLa1xDqnvqCVaSN+TlX75pNEVn43vo9rt0tgGiGIUByW7E1Ys/xSzcYkI+5UaWloqJ6ub23VmMU8LjhVbcc8ks4z79PpGEVT5DQM3Kud+p9WHjmy8ie9mWJ20nu/ofg/7lZW3v2jM53XO5RVJ9askQLAtTFS2Vbpe0LH9MbuaZ8H67ofNEMLUmjc6YpyNn6YH9OWkEqUpR9Q4M2O1fdNH4cMCwQ3R4zQAC0sEE5Mb7z0PJ+yttGjeuf3lZUySCYSfBYks7KSvDx7DQam2pyTS+RfnObW/21tU4wpPn9yks+bZkAHHz2a4kJGmYvvQ0IAsamJiYOHJieHRn0ZQKkm08j/GQSEedd1YuLQwcnJQz8nqx7q5fHnGFMB5jQ5K5fDk+SxQ/ius+1Jw67wpNkfjCvX55jrZgUvUqsGVeoNzBLuQwuwAUZ1OhRDESqjfQyGVDofurZ9e8Lc3b0B4rK31HWqztcX+JWsZVshrpY++j8Li8QP5f3auLgix00KOGd6g/QwXEhrg9QGWrM6xGjlAq0bfpkDQBOqKx30I6tOneoM1mZqvucYebXu5Ytpb8AhhEL3Cf7x9LeTsVInqTU+2hMDYNryWyEawsRUGIhgbR9DAZqdC0mF0Z3DfbhuCo8+V98Q9AEhTX0YVcthdvW2ATSQgDMpIRAEpwEOaxtjyIIasvNt/j+Sjgnd5WTvGHeV43YXqyHXlDtYz6HbqH29HTjtdnSV69Ai07wjDGvCdhdYikoXmbFbk2ydtlta3ZlNw4Cn8cMWWEMHM2zqllsNw1RhvFZqi6GF2sq7peUYAYzRrCLFkxfR8gt0OhWCKJ7q4KbIwTy+CAZjWvN2ZZf9UZvH7lSFn6BxSOGRaXug0umKgFHln5MnwZPDlruTaaD2UNj277+t6PzIA6/h7W1LykHnSYr1pBmPkEJGgwqjFQU9iYm1B+LWB1Thhb224CjiD5wmVFMQnz8v79iBQTrWtx6su9CeVqco+PdAd+8PRgdhXuOmXYWMteRvXSrT8Tk5FhasUr9pDuHxX9TymMCZ/s7LMnZNk4DYYFCnk/RmA6a0BntRBlnPFqvtSH8jVjd2xTfM0rCgcT5A4POrGH51yZjXhkF4sMMvgwKreNkIsEL+4DOjxKDZ9ImddIPKwXkdhmIwjJ4WbkdgBMEMGPIERdoEROzZjRrkQZLUOgzGUNgQBXdJH9M3z+wQblfT9zJFRDxoGESQJlqYiMMJzqA3zTPhJvrNHOspTETLNDvcN+jm0bQ/JK3uy2tA2QMi9r8iTCZ+p/n2MR3KumarMTSKyrF87trZN09zjx7NffrGTDE76d0/wnsxJJAXgwOvdymZgDEYfdDgMOh+N4TaIwgLRRA1iqpgHdJxJm8Nx2933s0Ly9Nfk4XptIqq1DhRMdsaj0fzu7vz6/nTyYr56vkwGTjl1wJouORXv2WgmCu6slzq5RPUiYZSi9TKF5PDVT93ruBl2fTvT9kZj91TeBKBFkFV1syefzOYfAk9V0G1zd3FUp0OClDxsHRPJVEiMVnXlB0ZIXNvJSWtXp0Uev9faG4sBP17P9TcBR/4IkwcrBc1sV9ENqnu7AQr6u/Ky1MYYsY8geCnzGdmSsv0pTDkYuxf56HReNQtG+0Loxg7iUir4uPi4leROkeYTfBpxEVlzEl1qq52Sl1+bcjZ39hRSExLa+y7ymhinkE+fS4oaJXcIoLz41VdojlJ7Whf7lavQIebR1oQMEMK3HAVE2IN8xs645lMDDONoXROKqpODL0yv9MhvDOMjQ1DYRizl3luLpXK3cmLf1fiYMyz3H0YsVFCG8xDj6rDaSDBoTgqCALD73s1N4m57AVPI2FUossdQr2fgr1V7W/+aacw5w3zX8vw0fleCkNoclV9fnLITBkgMfJ6/z4uLvY9HCUWR8Gam0eMowvr/G8gmZCHDBiMRel1kVCzBVBz2JjeuOjzOK3wA/wF/lCon3UmO+bKKozr+XxpJqT/UGLbyJuwspho0ju0W5eAfBh5KmODVppohtK80ij/lH7OFl9BlXFVMre9//RHSVHHM2CuXsp2/j3uQKwP3EsnpLXQh+jLWiMINHNKAj0PuqQ6c1kFqegJFHPapWLCeWoMr+u3G1MfX0XcgyKOqouKQJ5+gp/nuQg+rTg2uvEjznmx2uTlW+/oY/JT74Sl2cWslpCU8vIjrVNKlEda+655GXZ2Et3fU/nRjxrmiZ1wuHdhVJqez/XFLxMsHxQKOSdKa3YlJS6Gfm/yW8zznyDooaf8HJwTwlKxQmqin1PoyIAqJCf46IWBCKlww6dTpXUAC+Ar5wc5GFys7V9mK+Xy/Pk49RB1XCy2yhSP03Tm5fBwntGN0B5r2K4TSjBo8yhdGE4RhFHIdvOzVx+sgcfMN/MMlTirgzY63Nbdo8/iC7fxV2OTr1lfaT76rIzdIpHfUqEQ5/WS4oEo02UYXd42+LmqBFJBJVWXNia0Rl2UvTdAzLNrM1gNaIE/jMFL7+ATrgTeAB5RpDKZQghrvls8b6UtWw0RAHN+nxzuMK+NXVScsMMywc3kr2jK8d1KxnHuS7l2p6ufKDMySha6/hrtLy9XCIUavCzjrBnDztt67wsRj2QkMtFjQbRrUJQPuQGXCaeUS/8rgO6tRWOlC9vCAdwH4FtRnvng8/T5+2n6lxZFZBpWHMP1eFI4GZrkQtA12swWxGEXPTqigUtRmLadA+fTHFygsEDGVrteO0tyzAmXTRh7/PcT8cZ7fyP+80OPd30Te14s7RunJDBSY/9cb76rUb3RvMHXpVD8yiTpAYYbWcp2cOCuPj8PLv8fgMMuS6HIS0Fijsx/Nv3exBQfNb9/t2vykmWOK12yRhY8SMtlIqo7e3dOiXl4L8bX5QcmZuaqhC9YWhhbn6Q3u5q2YyXfxYA1vWSVWV+feSLQq9+eozJcMzfXCpYLGmtcxOudsnxGAk8gipIPtDY4iqjx8IWRnJzD7/y9F4SN/25L8Bd6UiKPDhmD/Yeglp8/LzfQMzKaOtCw4T6OsGX2V0gEqVXyq/sHME/d16e+NYW0+P8NpPru5GUzSIeuY2/HPmwWXTC2MrGIY/25h91Iyjmae1oNe3NP9QSWIaVBLP43hj/FtzMAd+S/jkEcCuBGatr/uDi4QhbtJjhVJAYRR4WhwgC12d/pJBu1WTWYghiGDw5G4hFMhTVux+yy2PIxlpQ+Agxx87oyo6MuqzaTA2WX6QruDey82vWXnCuYlkAvrKLwmbVr7WJ74Pcoj8U3B9BpPRulyXtszY2s3YKt4s7mv6bvGaA4qwOFMWedKAO7/BPoJc4C02gv60Vmtk250o3ddJ8ANQ8fFL2fGsy8dme9bwPaIOp+AeCpm1dLaeeItlUHq9/Yo92WrXesUlOCRexG7d9UH6yyJaoNYD3tFxiL+HwqPTGC8iqO+RYfu/23U6dY9qyAHrfYXury03cpbB+Ww9ZmUZ1I4/qMKBRZU/70hFPLjEuPt+Yx3tji7VddtWaZn7ewN9eas14mD/1w9EBUJy7swCUzjbOVhMMNmp2vtN/e8rsR+TXPemFUZjbR66lBNdwZTJXzWMyh5rfBfPEITLh/LZ/lls63B+rEGlQDFtdne0Epqu6trkbRFZUuIhRo/BiT+WqioEE7EC7w4n7C/qCFb94lsOgM/UcjGtF9Jl0CGt7XvmPcYA9Du2hIOXhuToa3WSDOEhds8LJj3hQDpFwrdlxFn6WrxqcxpkQ5S7dY4SkyYgEuv/Otk070B9oX/Veip47cUdepJKUvBaOUEHw2dMOwmcMzMhTUm6O0N6GhF6YAljK40dvQuHl1/DBl1/GAKZJO2HVoJ2SctsPuhPWBH354WYnJCx4AkJG0PsTaIwxiiCJrM9MO8MIMA7yDrsw6E6A5v7qidhMPiPoGJNCfQ906FMopSLnLPgnVppp6x9scO2WTZFxqF20aZp/kGE/PYSXyOZqRiARjS5t409AP26XFIWupJUiB3kRukxB//HtZ3CKTF3tuX9Z9Ct8pOYM9DV8v+x6HWs4o6fk+Fmz6tq33WZ4Gn9ZW94sbBmdRI6ffrTpRxAGVF8hidweDx/fVJL4benex8NmuiyO/u+N/VRSYP3zF8O9HCNTOBYRowR5/evx7+W+6JHfx18+cnbS6BBwpfFZoido/u4wNFFpWjze+JZ/8R/tvL6PXhof06UXPIrlL07KFoOwVtQhsBqVwNzbOAB8teg0hwWyANBduPpS8JFzh13pWP3N6+3FlauxR5+vpXW2LmwTmXuY9XrUN5KftraUhoLK6bIX0SEI0c0wLaTl93h0yol7X/UvQNQTFT0L6KejtTw2t53ZefqoS6rX9792AeKaTcm1cHkvaJkde0Ac1j0Pn0BBMG7x9Jka68pTAy+KoQl1LhhShbjOGhnzNc0dqeRrwFmv+T6+1Ftpi5XPcveZhVz9SNvASobeyvkqQwsdmaOPaMgkMxMpsQlMcp1w9omrV1VaXHsoqlB/0WaaTFF6iosGZBITLul4aRSkH1egqlANcvZ8EoAoDwhSCctRyKGGiHUD4BRYIhDZu1IwUoz+lfdpkTLCpFx6mgRaaZ6IOSR12cdhOY9DHYY2Rxq5rjM33bUyM9n9jwUEhpLFoZLijsVbr8LW5zvJ3YwM9oqbmhpbh5haW1XNf0jqK/9KXlaJzTB/L7aNnPpGclzHcKjQtJfATJsv1MBEIVWIWgylF3KyNhioZYrjU1gY1MZfE74TnCeQr6Cs7mI48hauGkmAhcbBmzRrOTfkqxixbL0dLKxMHexcEwxKXro0sPkPiTBOBjBsB851SJSVjjLPCxsN+kZInRUePhkGJrke6wj2HaMIS5J+UjrA4HDpJROxOAinFV8y74UFGKXVjdydxaM1YH8OoskxAYYS+fow2zFBjMkzjIqVBCIUyYuzIVQmZwCaME4CL/wyvOfZBI9NRTE8HBKw6gUUUgDlrp6mSkcYaZt5LRpViOTN0ukwkY4nLrHD/THr/oL811GQS2nAIov7w+duwPiRgnC7376sdfljzBz22FwCh4z+EoBhOkBTNsBwvEIrEEqlMrlCq1BqtTm8wmswWq83ucLrcHq/PDyCCYjhBUjTDcrwgSrKiar99+J/QDdOyHdfzgzCKkzTLi7Kqm7brh3Gal3Xbj/O6n/f7QQhGUAwnSIpmWI4XRElWVE03TMt2XM8PwihO0iwvyqpu2q4fxmle1m0/zut+3u/3hxEUwwmSohmW4wVRkhVV0w3Tsh3X84MwipM0y4uyqpu264dxmpd124/zup/39/8AYiScq3RWJmeuz5btf8FyPr882Xnz5T+PkhmTmI37Zv57nee0t52jAIm1EZueJe6178fMft9a+/5hxXpXvr+899z13TKfHbVzdpDvwMzyHZCZ2WVXHasAibWR4AIAAAAAQEREREQkIiIiImJmZmZm1n0DkFgbCQ7TTwGEMMYYY0RERERErLXWWps2V/IwOELW5xBJG6UPAAAAAAAAAACQEwAAAIMuAUisjQRXCAAAAAAAAAqi34gTx9A5oACJdYQqpZRSKkpefYAeFMQ6TZS0JEmSJEnSDkaCi5mZmZl50Z+e+97zwF9Xzcb9PEc8/gMAAA==
```

*http://localhost:3000/favicon.ico*

Request headers

```
GET /favicon.ico HTTP/1.1
Host: localhost:3000
Connection: keep-alive
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/49.0.2623.110 Safari/537.36
Accept: */*
Referer: http://localhost:3000/
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-GB,en-US;q=0.8,en;q=0.6
Cookie: _publication-app_session=WHczaS8yWDFXZ214ODZBcDc0UG05RkR5ZUdmV0JpYWVWbmZabUlzQ2s3WjFIMTZ2eVdTdkFFempJLzlhSVJSOHgzNWVRdUt0M2Mva2RhTFFVcUF6dXhxbUtxeTl2S0E5V2NMOGpsL3hpRnhoMGs2NFRjNUEvVXZmYm5iakNKRDlKRlNrbUoyUkNQVU14YnJNNlRYZHRRPT0tLVJCRkJtTFJBVHZGc2pjQkdIZUdWeUE9PQ%3D%3D--b436093ddc5f8f6fbf5099b9fd8d2c741c944b04
```

Response headers

```
HTTP/1.1 200 OK
Last-Modified: Wed, 06 Apr 2016 02:06:08 GMT
Content-Type: image/vnd.microsoft.icon
Content-Length: 0
Server: WEBrick/1.3.1 (Ruby/2.2.3/2015-08-18)
Date: Sat, 09 Apr 2016 00:57:18 GMT
Connection: Keep-Alive
```
