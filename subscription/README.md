# Commands 

### Creating an application

> rails new \<name of the application\>

> rails new subscription

>     create  
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
	Fetching gem metadata from https://rubygems.org/............
	Fetching version metadata from https://rubygems.org/...
	Fetching dependency metadata from https://rubygems.org/..
	Resolving dependencies.......
	Using rake 10.4.2
	Using i18n 0.7.0
	Using json 1.8.3
	Using minitest 5.8.2
	Using thread_safe 0.3.5
	Using tzinfo 1.2.2
	Using activesupport 4.2.4
	Using builder 3.2.2
	Using erubis 2.7.0
	Using mini_portile 0.6.2
	Using nokogiri 1.6.6.2
	Using rails-deprecated_sanitizer 1.0.3
	Using rails-dom-testing 1.0.7
	Using loofah 2.0.3
	Using rails-html-sanitizer 1.0.2
	Using actionview 4.2.4
	Using rack 1.6.4
	Using rack-test 0.6.3
	Using actionpack 4.2.4
	Using globalid 0.3.6
	Using activejob 4.2.4
	Using mime-types 2.6.2
	Using mail 2.6.3
	Using actionmailer 4.2.4
	Using activemodel 4.2.4
	Using arel 6.0.3
	Using activerecord 4.2.4
	Using debug_inspector 0.0.2
	Using binding_of_caller 0.7.2
	Using bundler 1.10.6
	Using byebug 8.0.1
	Using coffee-script-source 1.9.1.1
	Using execjs 2.6.0
	Using coffee-script 2.4.1
	Using thor 0.19.1
	Using railties 4.2.4
	Using coffee-rails 4.1.0
	Using multi_json 1.11.2
	Using jbuilder 2.3.2
	Using jquery-rails 4.0.5
	Using sprockets 3.4.0
	Using sprockets-rails 2.3.3
	Using rails 4.2.4
	Using rdoc 4.2.0
	Using sass 3.4.19
	Using tilt 2.0.1
	Using sass-rails 5.0.4
	Using sdoc 0.4.1
	Using spring 1.4.0
	Using sqlite3 1.3.11
	Using turbolinks 2.5.3
	Using uglifier 2.7.2
	Using web-console 2.2.1
	Bundle complete! 12 Gemfile dependencies, 53 gems now installed.
	Use `bundle show [gemname]` to see where a bundled gem is installed.
	         run  bundle exec spring binstub --all
	* bin/rake: spring inserted
	* bin/rails: spring inserted


NOTE: Attempting to create an application with a name that is a reserved word in Ruby or Rails would 
result in an error.

### Starting the application

Change to the application directory and start the server included in the Ruby standard library known as WEBrick

> rails server (or) rails s

### Generating a specific part of an application

To generate a specific part of an application, pass *generate* as an argument to the rails command.

> rails generate \<what has to be generated\> 

> rails g \<what has to be generated\> 

### Removing a specific part of an application

If an error was made when generating a scaffold, it could be destroyed by the following command

> rails destroy \<what was generated\> 

> rails d \<what was generated\>

### Scaffolding

Scaffolds can be used to quickly generate temporary structures that could be experimented with. 

The scaffold command generates a model, a controller, views and tests. 

> rails generate scaffold <name of the table> <attribute:type> <attribute:type> ..

> rails generate scaffold student name:string grade:integer

>     invoke  active_record
      create    db/migrate/20151109002659_create_students.rb
      create    app/models/student.rb
      invoke    test_unit
      create      test/models/student_test.rb
      create      test/fixtures/students.yml
      invoke  resource_route
       route    resources :students
      invoke  scaffold_controller
      create    app/controllers/students_controller.rb
      invoke    erb
      create      app/views/students
      create      app/views/students/index.html.erb
      create      app/views/students/edit.html.erb
      create      app/views/students/show.html.erb
      create      app/views/students/new.html.erb
      create      app/views/students/_form.html.erb
      invoke    test_unit
      create      test/controllers/students_controller_test.rb
      invoke    helper
      create      app/helpers/students_helper.rb
      invoke      test_unit
      invoke    jbuilder
      create      app/views/students/index.json.jbuilder
      create      app/views/students/show.json.jbuilder
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/students.coffee
      invoke    scss
      create      app/assets/stylesheets/students.scss
      invoke  scss
      create    app/assets/stylesheets/scaffolds.scss

Running the application now in the server causes the following error:

*Migrations are pending. To resolve this issue, run: bin/rake db:migrate RAILS_ENV=development*

This is because the migration has not yet been run.

If an error is made while creating the scaffold, it could be destroyed

> rails destroy scaffold student

### Creating the database

One of the files that the scaffold created was db/migrate/20151109002659_create_students.rb. 

```ruby
class CreateStudents < ActiveRecord::Migration
  def change
    create_table :students do |t|
      t.string :name
      t.integer :grade

      t.timestamps null: false
    end
  end
end
```

It is a Ruby class called Migration which is used as a version control for the database and allows implementing incremental changes to the database schema. Notice the timestamp associated with the filename. 

A Migration class inherits from *ActiveRecord::Migration*

The class CreateStudents contains table creation logic in its change method. It contains fields that were declared at the time of scaffold generation as well as two timestamp fields, created_at and updated_at which contains the time when the records are created and updated respectively. 

#### Running the migration forward

The following creates an SQLite3 database in a new file at db/development.sqlite3 and runs the change method from the latest migration to create the students table in the database. 

> bundle exec rake db:migrate

In addition to running the change method from the latest migration, this method also runs any migrations that have not been run yet. Mutiple migrations are run in a sequential manner.  

#### Rolling back the migration

To roll back the latest migration, run the following command which reverses the operations performed in the change method. If the migrations performed in the change method are complex and cannot be automatically rolled back, the migration should be defined in *up* and *down* methods. In such a case, rolling back with the following command calls the down method.

> bundle exec rake db:rollback

The following method rolls back more than one migration which is specified by the STEP argument

> bundle exec rake db:rollback STEP=\<number of migrations to rollback\>

> bundle exec rake db:rollback STEP=2
