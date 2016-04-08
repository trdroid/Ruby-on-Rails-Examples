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

Including a partial and link to bootstrap as explained in <http://getbootstrap.com/getting-started/>

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

<http://api.rubyonrails.org/classes/ActionView/Helpers/UrlHelper.html#method-i-link_to>

*Including Bootstrap and necessary files*



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
