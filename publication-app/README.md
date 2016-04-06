# Prerequisites

**Installing PostgreSQL**

<http://www.postgresql.org/download/linux/ubuntu/>

>    sudo apt-get install postgresql postgresql-contrib libpq-dev python-dev

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

