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


