<i>Creating the application</i>

    $ rails --version
    Rails 4.2.4
    
    $ bin/rails --version
    Rails 4.2.4

Use the <i>rails new</i> command to create a new rails application

> rails new document_management
  
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
    Resolving dependencies............................................
    Using rake 10.5.0
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
    Using mime-types 2.99
    Using mail 2.6.3
    Using actionmailer 4.2.4
    Using activemodel 4.2.4
    Using arel 6.0.3
    Using activerecord 4.2.4
    Using debug_inspector 0.0.2
    Using binding_of_caller 0.7.2
    Using bundler 1.10.6
    Using byebug 8.2.1
    Using coffee-script-source 1.10.0
    Using execjs 2.6.0
    Using coffee-script 2.4.1
    Using thor 0.19.1
    Using railties 4.2.4
    Using coffee-rails 4.1.1
    Using concurrent-ruby 1.0.0
    Using multi_json 1.11.2
    Using jbuilder 2.4.0
    Using jquery-rails 4.1.0
    Using sprockets 3.5.2
    Using sprockets-rails 3.0.1
    Using rails 4.2.4
    Using rdoc 4.2.1
    Using sass 3.4.21
    Using tilt 2.0.2
    Using sass-rails 5.0.4
    Using sdoc 0.4.1
    Using spring 1.6.2
    Using sqlite3 1.3.11
    Using turbolinks 2.5.3
    Using uglifier 2.7.2
    Using web-console 2.3.0
    Bundle complete! 12 Gemfile dependencies, 54 gems now installed.
    Use `bundle show [gemname]` to see where a bundled gem is installed.
             run  bundle exec spring binstub --all
    * bin/rake: spring inserted
    * bin/rails: spring inserted

<hr>

<b>The following app files and app structure is created by the <i>rails new</i> command.</b>

<i>Contents of the Rails Application</i>

> $ cd document_management

> $ ls
  
    app  bin  config  config.ru  db  Gemfile  Gemfile.lock  lib  log  public  Rakefile  README.rdoc  test  tmp  vendor

> $ ls bin
  
    bundle  rails  rake  setup  spring

<hr>

<i>Contents of the Gemfile</i>

The Gemfile is also created by the <i>rails new</i> command

>   $ cat Gemfile

    source 'https://rubygems.org'


    # Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
    gem 'rails', '4.2.4'
    # Use sqlite3 as the database for Active Record
    gem 'sqlite3'
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


<hr>

<i> Installing gems and dependencies </i>

The <i>rails new</i> command automatically runs the following bundle command to install gems and their dependencies.

> bin/bundle install

The bundle command stores the version numbers of gems and their dependencies in <i>Gemfile.lock</i>

<i> Contents of Gemfile.lock</i>

> $ cat Gemfile.lock

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
        byebug (8.2.1)
        coffee-rails (4.1.1)
          coffee-script (>= 2.2.0)
          railties (>= 4.0.0, < 5.1.x)
        coffee-script (2.4.1)
          coffee-script-source
          execjs
        coffee-script-source (1.10.0)
        concurrent-ruby (1.0.0)
        debug_inspector (0.0.2)
        erubis (2.7.0)
        execjs (2.6.0)
        globalid (0.3.6)
          activesupport (>= 4.1.0)
        i18n (0.7.0)
        jbuilder (2.4.0)
          activesupport (>= 3.0.0, < 5.1)
          multi_json (~> 1.2)
        jquery-rails (4.1.0)
          rails-dom-testing (~> 1.0)
          railties (>= 4.2.0)
          thor (>= 0.14, < 2.0)
        json (1.8.3)
        loofah (2.0.3)
          nokogiri (>= 1.5.9)
        mail (2.6.3)
          mime-types (>= 1.16, < 3)
        mime-types (2.99)
        mini_portile2 (2.0.0)
        minitest (5.8.4)
        multi_json (1.11.2)
        nokogiri (1.6.7.2)
          mini_portile2 (~> 2.0.0.rc2)
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
        rake (10.5.0)
        rdoc (4.2.1)
          json (~> 1.4)
        sass (3.4.21)
        sass-rails (5.0.4)
          railties (>= 4.0.0, < 5.0)
          sass (~> 3.1)
          sprockets (>= 2.8, < 4.0)
          sprockets-rails (>= 2.0, < 4.0)
          tilt (>= 1.1, < 3)
        sdoc (0.4.1)
          json (~> 1.7, >= 1.7.7)
          rdoc (~> 4.0)
        spring (1.6.2)
        sprockets (3.5.2)
          concurrent-ruby (~> 1.0)
          rack (> 1, < 3)
        sprockets-rails (3.0.1)
          actionpack (>= 4.0)
          activesupport (>= 4.0)
          sprockets (>= 3.0.0)
        sqlite3 (1.3.11)
        thor (0.19.1)
        thread_safe (0.3.5)
        tilt (2.0.2)
        turbolinks (2.5.3)
          coffee-rails
        tzinfo (1.2.2)
          thread_safe (~> 0.1)
        uglifier (2.7.2)
          execjs (>= 0.3.0)
          json (>= 1.8.0)
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
      rails (= 4.2.4)
      sass-rails (~> 5.0)
      sdoc (~> 0.4.0)
      spring
      sqlite3
      turbolinks
      uglifier (>= 1.3.0)
      web-console (~> 2.0)
    
    BUNDLED WITH
       1.10.6

<hr>

<i>List all gems with their versions</i>

> bin/bundle list

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
    * byebug (8.2.1)
    * coffee-rails (4.1.1)
    * coffee-script (2.4.1)
    * coffee-script-source (1.10.0)
    * concurrent-ruby (1.0.0)
    * debug_inspector (0.0.2)
    * erubis (2.7.0)
    * execjs (2.6.0)
    * globalid (0.3.6)
    * i18n (0.7.0)
    * jbuilder (2.4.0)
    * jquery-rails (4.1.0)
    * json (1.8.3)
    * loofah (2.0.3)
    * mail (2.6.3)
    * mime-types (2.99)
    * mini_portile2 (2.0.0)
    * minitest (5.8.4)
    * multi_json (1.11.2)
    * nokogiri (1.6.7.2)
    * rack (1.6.4)
    * rack-test (0.6.3)
    * rails (4.2.4)
    * rails-deprecated_sanitizer (1.0.3)
    * rails-dom-testing (1.0.7)
    * rails-html-sanitizer (1.0.3)
    * railties (4.2.4)
    * rake (10.5.0)
    * rdoc (4.2.1)
    * sass (3.4.21)
    * sass-rails (5.0.4)
    * sdoc (0.4.1)
    * spring (1.6.2)
    * sprockets (3.5.2)
    * sprockets-rails (3.0.1)
    * sqlite3 (1.3.11)
    * thor (0.19.1)
    * thread_safe (0.3.5)
    * tilt (2.0.2)
    * turbolinks (2.5.3)
    * tzinfo (1.2.2)
    * uglifier (2.7.2)
    * web-console (2.3.0)

<hr>

<i>Explore tasks in the application</i>

> bin/rake --tasks

    Running via Spring preloader in process 3965
    rake about                              # List versions of all Rails frameworks and the environment
    rake assets:clean[keep]                 # Remove old compiled assets
    rake assets:clobber                     # Remove compiled assets
    rake assets:environment                 # Load asset compile environment
    rake assets:precompile                  # Compile all the assets named in config.assets.precompile
    rake cache_digests:dependencies         # Lookup first-level dependencies for TEMPLATE (like messages/show or comments/_comment.html)
    rake cache_digests:nested_dependencies  # Lookup nested dependencies for TEMPLATE (like messages/show or comments/_comment.html)
    rake db:create                          # Creates the database from DATABASE_URL or config/database.yml for the current RAILS_ENV (use db:create:all to create all databases in the config)
    rake db:drop                            # Drops the database from DATABASE_URL or config/database.yml for the current RAILS_ENV (use db:drop:all to drop all databases in the config)
    rake db:fixtures:load                   # Load fixtures into the current environment's database
    rake db:migrate                         # Migrate the database (options: VERSION=x, VERBOSE=false, SCOPE=blog)
    rake db:migrate:status                  # Display status of migrations
    rake db:rollback                        # Rolls the schema back to the previous version (specify steps w/ STEP=n)
    rake db:schema:cache:clear              # Clear a db/schema_cache.dump file
    rake db:schema:cache:dump               # Create a db/schema_cache.dump file
    rake db:schema:dump                     # Create a db/schema.rb file that is portable against any DB supported by AR
    rake db:schema:load                     # Load a schema.rb file into the database
    rake db:seed                            # Load the seed data from db/seeds.rb
    rake db:setup                           # Create the database, load the schema, and initialize with the seed data (use db:reset to also drop the database first)
    rake db:structure:dump                  # Dump the database structure to db/structure.sql
    rake db:structure:load                  # Recreate the databases from the structure.sql file
    rake db:version                         # Retrieves the current schema version number
    rake doc:app                            # Generate docs for the app -- also available doc:rails, doc:guides (options: TEMPLATE=/rdoc-template.rb, TITLE="Custom Title")
    rake log:clear                          # Truncates all *.log files in log/ to zero bytes (specify which logs with LOGS=test,development)
    rake middleware                         # Prints out your Rack middleware stack
    rake notes                              # Enumerate all annotations (use notes:optimize, :fixme, :todo for focus)
    rake notes:custom                       # Enumerate a custom annotation, specify with ANNOTATION=CUSTOM
    rake rails:template                     # Applies the template supplied by LOCATION=(/path/to/template) or URL
    rake rails:update                       # Update configs and some other initially generated files (or use just update:configs or update:bin)
    rake routes                             # Print out all defined routes in match order, with names
    rake secret                             # Generate a cryptographically secure secret key (this is typically used to generate a secret for cookie sessions)
    rake stats                              # Report code statistics (KLOCs, etc) from the application or engine
    rake test                               # Runs all tests in test folder
    rake test:all                           # Run tests quickly by merging all types and not resetting db
    rake test:all:db                        # Run tests quickly, but also reset db
    rake test:db                            # Run tests quickly, but also reset db
    rake time:zones:all                     # Displays all time zones, also available: time:zones:us, time:zones:local -- filter with OFFSET parameter, e.g., OFFSET=-6
    rake tmp:clear                          # Clear session, cache, and socket files from tmp/ (narrow w/ tmp:sessions:clear, tmp:cache:clear, tmp:sockets:clear)
    rake tmp:create                         # Creates tmp directories for sessions, cache, sockets, and pids

These tasks are added by some of the gems. Custom tasks can also be added to the application by writing Ruby scripts and saving them under lib/tasks

<hr>

<i>Start WEBrick server</i>

> $ bin/rails server

Visit localhost:3000 in the browser

<hr>

<i> Create a scaffold </i>

Create a scaffold for a Document. The following command specifies that a Document has a name and content.

The name would be a string in the database where as the content is a text field. 

> $ bin/rails generate scaffold Document name:string content:text

    Running via Spring preloader in process 1544
      invoke  active_record
      create    db/migrate/20160129144122_create_documents.rb
      create    app/models/document.rb
      invoke    test_unit
      create      test/models/document_test.rb
      create      test/fixtures/documents.yml
      invoke  resource_route
       route    resources :documents
      invoke  scaffold_controller
      create    app/controllers/documents_controller.rb
      invoke    erb
      create      app/views/documents
      create      app/views/documents/index.html.erb
      create      app/views/documents/edit.html.erb
      create      app/views/documents/show.html.erb
      create      app/views/documents/new.html.erb
      create      app/views/documents/_form.html.erb
      invoke    test_unit
      create      test/controllers/documents_controller_test.rb
      invoke    helper
      create      app/helpers/documents_helper.rb
      invoke      test_unit
      invoke    jbuilder
      create      app/views/documents/index.json.jbuilder
      create      app/views/documents/show.json.jbuilder
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/documents.coffee
      invoke    scss
      create      app/assets/stylesheets/documents.scss
      invoke  scss
      create    app/assets/stylesheets/scaffolds.scss

The scaffold generatator generates a file for migration (under app/db/migrate directory) along with other required files. Migration file names begin with a timestamp, which indicate the time they are created.

Database Migrations are used when changes have to be made to the structure of the database. A complete record of changes done to the database as the application is built is stored in Database Migrations. 

> $ cat db/migrate/20160129144122_create_documents.rb

```ruby
class CreateDocuments < ActiveRecord::Migration
  def change
    create_table :documents do |t|
      t.string :name
      t.text :content

      t.timestamps null: false
    end
  end
end
```

The <i>change</i> method as shown above would create a table named <i>documents</i> with the fields: 
* id
* name
* content
* created_at
* updated_at

<b>id</b> is a unique and auto-incrementing integer that identifies each row uniquely.

name, content fields are to hold the name and content of <i>a document</i>

<b>created_at and updated_at</b> are fields that the framework deals with. They are used to track the creation and last updated timestamps. 

Run the migration task db:migrate using rake to run all the pending database migrations. Rails keeps track of which migrations have been run by storing the timestamps of the executed migrations in a database table called <i>schema_migrations</i>.

Running a migration executes the <i>change</i> method, which in this case, as shown above, creates a table called <i>documents</i>

Run the rollback task db:rollback to undo a database migration with a mistake in it. 

> $ bin/rake db:migrate

    Running via Spring preloader in process 2763
    == 20160129144122 CreateDocuments: migrating ==================================
    -- create_table(:documents)
       -> 0.0019s
    == 20160129144122 CreateDocuments: migrated (0.0021s) =========================

Rails stores the current state of the database in the file db/schema.rb. This file is updated everytime a database migration is run and hence should not be edited manually. 

> $ cat db/schema.rb

```ruby
ActiveRecord::Schema.define(version: 20160129144122) do

  create_table "documents", force: :cascade do |t|
    t.string   "name"
    t.text     "content"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

end
```

To setup a new, empty database for an application, or to remove all the data and reset the database structure, run the db:schema:load task, instead of running individual migrations.

# Model

<i>app/models/document.rb</i>

Models inherit from the ActiveRecord class, which provides methods for database operations. 

```ruby
class Document < ActiveRecord::Base
end
```

<hr>

### Performing CRUD operations

http://guides.rubyonrails.org/active_record_basics.html

http://api.rubyonrails.org/

<b> The methods that will be discussed are implemented in the ActiveRecord class. </b>

The <i>Document</i> class is associated with the <i>Documents</i> table in the database.

Each row of the <i>Documents</i> table is represented by an instance of the <i>Document</i> class and each column is represented by an attribute of that object. The value associated with a particular column can be retrieved by calling the attribute method on that object.

<i>Start the Rails console</i>

> bin/rails console

    Running via Spring preloader in process 5433
    Loading development environment (Rails 4.2.4)
    irb(main):001:0> 


Starting the Rails console from the application's root loads the application's environment

<b><i>Creating a record</i></b>

A document record can be created by 
* creating an instance of the Document class
* assigning values to the attributes and 
* calling the <i>save</i> method on the instance to commit the record to the database

The following are the steps:

    irb(main):026:0> doc2 = Document.new
    => #<Document id: nil, name: nil, content: nil, created_at: nil, updated_at: nil>
    irb(main):027:0> doc2.name="Doc2"
    => "Doc2"
    irb(main):028:0> doc2.content="This is document2!"
    => "This is document2!"
    irb(main):029:0> doc2.save
       (0.3ms)  begin transaction
      SQL (0.4ms)  INSERT INTO "documents" ("name", "content", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["name", "Doc2"], ["content", "This is document2!"], ["created_at", "2016-01-30 03:24:39.102758"], ["updated_at", "2016-01-30 03:24:39.102758"]]
       (118.2ms)  commit transaction
    => true


The create method accepts a hash of attribute-value pairs and inserts a row in a corresponding table.

    irb(main):001:0> Document.create(name: "Doc1", content: "Hello World!")
      (0.2ms)  begin transaction
      SQL (16.0ms)  INSERT INTO "documents" ("name", "content", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["name", "Doc1"], ["content", "Hello World!"], ["created_at", "2016-01-30 00:04:22.842437"], ["updated_at", "2016-01-30 00:04:22.842437"]]
       (102.1ms)  commit transaction
    => #<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">

The create method can also be passed a block.

    irb(main):006:0> doc3 = Document.new do |doc|
    irb(main):007:1* doc.name="doc3"
    irb(main):008:1> doc.content="This is document3"
    irb(main):009:1> end
    => #<Document id: nil, name: "doc3", content: "This is document3", created_at: nil, updated_at: nil>
    irb(main):010:0> doc3.save
       (0.3ms)  begin transaction
      SQL (0.7ms)  INSERT INTO "documents" ("name", "content", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["name", "doc3"], ["content", "This is document3"], ["created_at", "2016-01-30 00:27:48.229196"], ["updated_at", "2016-01-30 00:27:48.229196"]]
       (102.6ms)  commit transaction
    => true

<b><i>Read</i></b>

To return all the rows, call <i>all</i> method on the Document class

    irb(main):013:0> Document.all
      Document Load (0.4ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">, #<Document id: 2, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 00:17:04", updated_at: "2016-01-30 00:17:04">, #<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">]>

The <i>all</i> method returns an <i>Active Record Relation</i> which contains an array of all documents.

Store the <i>Active Record Relation</i> instance, which represents an array of all documents, in a variable. <i>first</i> and <i>last</i> methods can be invoked on an Action Record Relation instance, which returns the first and last entries in the array respectively.

    irb(main):003:0> docs = Document.all
      Document Load (0.4ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">, #<Document id: 2, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 00:17:04", updated_at: "2016-01-30 00:17:04">, #<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">]>


      irb(main):004:0> docs.first
    => #<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">
    irb(main):005:0> docs.last
    => #<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">


To return the first and last records in the documents table, instead of fetching all the records and calling <i>first</i> and <i>last</i> method on an <i>ActiveRecord::Relation</i> instance, call the <i>first</i> method on the Document class

    irb(main):011:0> Document.first
      Document Load (0.4ms)  SELECT  "documents".* FROM "documents"  ORDER BY "documents"."id" ASC LIMIT 1
    => #<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">
    irb(main):012:0> Document.last
      Document Load (0.5ms)  SELECT  "documents".* FROM "documents"  ORDER BY "documents"."id" DESC LIMIT 1
    => #<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">

To retrieve a record by id, call <i>find</i> method on the Document class and pass the id of the record that has to be fetched

    irb(main):014:0> Document.find 2
      Document Load (0.6ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 2]]
    => #<Document id: 2, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 00:17:04", updated_at: "2016-01-30 00:17:04">

Attempting to find by an id that does not exist results in an ActiveRecord::RecordNotFound exception

    irb(main):015:0> Document.find 10
      Document Load (0.3ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 10]]
    ActiveRecord::RecordNotFound: Couldn't find Document with 'id'=10
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activerecord-4.2.4/lib/active_record/core.rb:155:in `find'
    	from (irb):15
    	from /usr/local/lib/ruby/gems/2.2.0/gems/railties-4.2.4/lib/rails/commands/console.rb:110:in `start'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/railties-4.2.4/lib/rails/commands/console.rb:9:in `start'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/railties-4.2.4/lib/rails/commands/commands_tasks.rb:68:in `console'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/railties-4.2.4/lib/rails/commands/commands_tasks.rb:39:in `run_command!'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/railties-4.2.4/lib/rails/commands.rb:17:in `<top (required)>'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:274:in `require'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:274:in `block in require'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:240:in `load_dependency'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:274:in `require'
    	from /home/droid/onGit/Ruby-on-Rails/document_management/bin/rails:9:in `<top (required)>'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:268:in `load'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:268:in `block in load'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:240:in `load_dependency'
    	from /usr/local/lib/ruby/gems/2.2.0/gems/activesupport-4.2.4/lib/active_support/dependencies.rb:268:in `load'
    	from /usr/local/lib/ruby/2.2.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from /usr/local/lib/ruby/2.2.0/rubygems/core_ext/kernel_require.rb:54:in `require'
    	from -e:1:in `<main>'

To find a record by any other field, use the <i>where</i> method on the Document class. The where method returns an <i>ActiveRecord::Relation</i> instance which implies the possibility of more than one row being returned and that the methods of <i>ActiveRecord::Relation</i> can be chained with the <i>where</i> call. 

    irb(main):034:0> Document.where(name:"Doc1").class.name
    => "ActiveRecord::Relation"

Chaining the first, last, and all methods with the <i>where</i> method respectively returns the first, last and all rows of the returned matching rows.

    irb(main):005:0> Document.where(name:"Doc1").first
      Document Load (0.3ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."name" = ?  ORDER BY "documents"."id" ASC LIMIT 1  [["name", "Doc1"]]
    => #<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">
    irb(main):006:0> Document.where(name:"Doc1").last
      Document Load (0.4ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."name" = ?  ORDER BY "documents"."id" DESC LIMIT 1  [["name", "Doc1"]]
    => #<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">
    irb(main):007:0> Document.where(name:"Doc1").all
      Document Load (0.5ms)  SELECT "documents".* FROM "documents" WHERE "documents"."name" = ?  [["name", "Doc1"]]
    => #<ActiveRecord::Relation [#<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">]>


The call <i>first</i> on an <i>ActiveRecord::Relation</i> instance returns the Model (Document) class's instance.

    irb(main):033:0> Document.where(name:"Doc1").first.class.name
      Document Load (0.4ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."name" = ?  ORDER BY "documents"."id" ASC LIMIT 1  [["name", "Doc1"]]
    => "Document"

The <i>to_sql</i> method on an <i>ActiveRecord::Relation</i> instance returns the sql query in string

    irb(main):044:0> Document.where(name:"Doc1").to_sql
    => "SELECT \"documents\".* FROM \"documents\" WHERE \"documents\".\"name\" = 'Doc1'"

<i>find_by methods</i>

Active Record generates <i>find_by</i> methods based on the column names. They are short for the chaining of first method with where eg. <i>Document.where(name:"Doc1").first</i>

    irb(main):049:0> Document.find_by_name("Doc2")
      Document Load (0.1ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."name" = ? LIMIT 1  [["name", "Doc2"]]
    => #<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">


<i>Limiting Search Results</i>

To limit the number of rows returned, call the <i>limit</i> method on the Model (Document) class. It returns an <i>ActiveRecord::Relation</i> instance.

    irb(main):009:0> Document.limit(2)
      Document Load (0.2ms)  SELECT  "documents".* FROM "documents" LIMIT 2
    => #<ActiveRecord::Relation [#<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">, #<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">]>
    irb(main):010:0> Document.limit(3)

The order the returned results, chain the <i>order</i> method of <i>ActiveRecord::Relation</i> with the <i>limit</i> method.

    irb(main):011:0> Document.limit(2).order "created_at ASC"
      Document Load (0.5ms)  SELECT  "documents".* FROM "documents"  ORDER BY created_at ASC LIMIT 2
    => #<ActiveRecord::Relation [#<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">, #<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">]>

To skip the first x records, use the <i>offset</i> method on the <i>ActiveRecord::Relation</i> instance returned by the <i>limit</i> method called on the Model (Document) class.

In the following example, the first record is skipped 

    irb(main):012:0> Document.limit(2).offset(1)
      Document Load (0.5ms)  SELECT  "documents".* FROM "documents" LIMIT 2 OFFSET 1
    => #<ActiveRecord::Relation [#<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">, #<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">]>

Skipping more than existing number of rows, returns an empty <i>ActiveRecord::Relation</i> instance

    irb(main):013:0> Document.limit(2).offset(5)
      Document Load (0.4ms)  SELECT  "documents".* FROM "documents" LIMIT 2 OFFSET 5
    => #<ActiveRecord::Relation []>


<b><i>Update</i></b>

Updating a record is equivalent to 
* reading a record into a variable
* updating values and 
* calling <i>save</i> method to save it back to the table

Updating a record using <i>save</i> method

    irb(main):050:0> Document.all
      Document Load (0.5ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">, #<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">]>
    irb(main):051:0> doc = Document.find 3
      Document Load (0.4ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 3]]
    => #<Document id: 3, name: "doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-01-30 00:27:48">
    irb(main):052:0> doc.name = "Doc3"
    => "Doc3"
    irb(main):053:0> doc.save
       (0.2ms)  begin transaction
      SQL (0.6ms)  UPDATE "documents" SET "name" = ?, "updated_at" = ? WHERE "documents"."id" = ?  [["name", "Doc3"], ["updated_at", "2016-02-02 00:47:20.647125"], ["id", 3]]
       (102.7ms)  commit transaction
    => true
    irb(main):054:0> Document.find 3
      Document Load (0.4ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 3]]
    => #<Document id: 3, name: "Doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-02-02 00:47:20">

Note: The <i>save</i> method returns true when the record is successfully saved.

Updating a record can also be done by
* reading a record into a variable
* calling <i>update</i> method by passing it a hash of attribute-value pairs which updates the values and saves the updated record back to the table 

Updating a record using <i>update</i> method

    irb(main):055:0> Document.all
      Document Load (0.3ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 3, name: "Doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-02-02 00:47:20">, #<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">]>
    irb(main):056:0> doc = Document.find 3
      Document Load (0.2ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 3]]
    => #<Document id: 3, name: "Doc3", content: "This is document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-02-02 00:47:20">
    irb(main):057:0> doc.update content: "This is Document3"
       (0.1ms)  begin transaction
      SQL (0.4ms)  UPDATE "documents" SET "content" = ?, "updated_at" = ? WHERE "documents"."id" = ?  [["content", "This is Document3"], ["updated_at", "2016-02-02 01:13:25.438584"], ["id", 3]]
       (213.2ms)  commit transaction
    => true
    irb(main):058:0> Document.find 3
      Document Load (0.1ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 3]]
    => #<Document id: 3, name: "Doc3", content: "This is Document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-02-02 01:13:25">


<b><i>Delete</i></b>

Using the <i>destroy_all</i> method on an <i>ActiveRecord::Relation</i> instance

    irb(main):046:0> Document.where(name: "Doc1").destroy_all
      Document Load (0.1ms)  SELECT "documents".* FROM "documents" WHERE "documents"."name" = ?  [["name", "Doc1"]]
       (0.1ms)  begin transaction
      SQL (0.3ms)  DELETE FROM "documents" WHERE "documents"."id" = ?  [["id", 1]]
       (108.6ms)  commit transaction
       (0.2ms)  begin transaction
      SQL (0.3ms)  DELETE FROM "documents" WHERE "documents"."id" = ?  [["id", 5]]
       (87.2ms)  commit transaction
    => [#<Document id: 1, name: "Doc1", content: "Hello World!", created_at: "2016-01-30 00:04:22", updated_at: "2016-01-30 00:04:22">, #<Document id: 5, name: "Doc1", content: "Hello World!", created_at: "2016-02-02 00:05:27", updated_at: "2016-02-02 00:05:27">]

Using the <i>destroy</i> method on the Model (Document) class

    irb(main):059:0> Document.all
      Document Load (0.5ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 3, name: "Doc3", content: "This is Document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-02-02 01:13:25">, #<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">]>
    irb(main):060:0> Document.destroy 3
      Document Load (0.1ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 3]]
       (0.2ms)  begin transaction
      SQL (0.2ms)  DELETE FROM "documents" WHERE "documents"."id" = ?  [["id", 3]]
       (100.9ms)  commit transaction
    => #<Document id: 3, name: "Doc3", content: "This is Document3", created_at: "2016-01-30 00:27:48", updated_at: "2016-02-02 01:13:25">
    irb(main):061:0> Document.all
      Document Load (0.2ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">]>

Another way to destroy is to find the record and save the reference in a variable and call the <i>destroy</i> method on the variable

    irb(main):062:0> Document.all
      Document Load (0.3ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">]>
    irb(main):063:0> doc = Document.find 4
      Document Load (0.2ms)  SELECT  "documents".* FROM "documents" WHERE "documents"."id" = ? LIMIT 1  [["id", 4]]
    => #<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">
    irb(main):064:0> doc.destroy
       (0.1ms)  begin transaction
      SQL (0.2ms)  DELETE FROM "documents" WHERE "documents"."id" = ?  [["id", 4]]
       (96.6ms)  commit transaction
    => #<Document id: 4, name: "Doc2", content: "This is document2!", created_at: "2016-01-30 03:24:39", updated_at: "2016-01-30 03:24:39">
    irb(main):065:0> Document.all
      Document Load (0.5ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation []>

<i>Other methods</i>

The following shows the usage of <i>minimum</i>, <i>maximum</i> and <i>count</i> methods.

    irb(main):072:0* Document.all
      Document Load (0.5ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 6, name: "Doc1", content: "Hello World!", created_at: "2016-02-02 02:01:22", updated_at: "2016-02-02 02:01:22">, #<Document id: 7, name: "Doc2", content: "Hello World in Doc2!", created_at: "2016-02-02 02:01:33", updated_at: "2016-02-02 02:01:33">, #<Document id: 8, name: "Doc3", content: "Hello World in Doc3!", created_at: "2016-02-02 02:01:41", updated_at: "2016-02-02 02:01:41">]>
    irb(main):073:0> Document.minimum :created_at
       (0.5ms)  SELECT MIN("documents"."created_at") FROM "documents"
    => Tue, 02 Feb 2016 02:01:22 UTC +00:00
    irb(main):074:0> Document.maximum :created_at
       (0.6ms)  SELECT MAX("documents"."created_at") FROM "documents"
    => Tue, 02 Feb 2016 02:01:41 UTC +00:00
    irb(main):075:0> Document.count
       (1.0ms)  SELECT COUNT(*) FROM "documents"
    => 3

<i>To exit the Rails console</i>

     irb(main):001:0\> exit

<hr>

### Adding columns to an existing table

Add a column called "author" to the documents table.

To do this, the <i>generate(g)</i> sub-command of the <i>rails</i> command can be used by passing it the name of the migration and its name and type as shown below.

> $ bin/rails g migration add_author_to_documents author:string

    Running via Spring preloader in process 25461
      invoke  active_record
      create    db/migrate/20160202170445_add_author_to_documents.rb

> $ bin/rake db:migrate

        Running via Spring preloader in process 25688
        == 20160202170445 AddAuthorToDocuments: migrating =============================
        -- add_column(:documents, :author, :string)
           -> 0.0007s
        == 20160202170445 AddAuthorToDocuments: migrated (0.0008s) ====================

The migration follows the convention add_ColumnName_to_TableName (Remember! Convention over Configuration)

Rails parses the migration name add_author_to_documents and knows to add a column name <i>author</i> to the table <i>documents</i> and its type is specified by <i>author:string</i> parameter.

A custom migration name that does not follow the convention can also be used, except that it requires the migration to be edited manually. 

Finally, the rake task has to be run to add the column to the table.

The following file is created as a result

$ cat db/20160202170445_add_author_to_documents.rb

```ruby
class AddAuthorToDocuments < ActiveRecord::Migration
  def change
    add_column :documents, :author, :string
  end
end
```

Adding another column "publisher", but this time let's not follow the convention:

> $ bin/rails g migration addingWhoPublishedThisDocumentToDocuments pub:string

    Running via Spring preloader in process 26111
          invoke  active_record
          create    db/migrate/20160202175612_adding_who_published_this_document_to_documents.rb

> $ cat 20160202175612_adding_who_published_this_document_to_documents.rb

```ruby
class AddingWhoPublishedThisDocumentToDocuments < ActiveRecord::Migration
  def change
  end
end
```

Before the migration task is run, the code to add a column to the table has to be added to the change method.

```ruby
class AddingWhoPublishedThisDocumentToDocuments < ActiveRecord::Migration
  def change
  	add_column :documents, :publisher, :string
  end
end
```

Active Record <i>migrations</i> provides the add_column method which expects the name of the table, the column name and its type as arguments. 

Other methods provided are remove_column, rename_column, change_column for changing options related to a column like its type, default value etc.

> $ bin/rake db:migrate

    Running via Spring preloader in process 26282
    == 20160202175612 AddingWhoPublishedThisDocumentToDocuments: migrating ========
    -- add_column(:documents, :publisher, :string)
       -> 0.0011s
    == 20160202175612 AddingWhoPublishedThisDocumentToDocuments: migrated (0.0013s) 

Notice that the db/schema.rb file is updated with the new columns

$ > cat db/schema.rb

```ruby
ActiveRecord::Schema.define(version: 20160202175612) do

  create_table "documents", force: :cascade do |t|
    t.string   "name"
    t.text     "content"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
    t.string   "author"
    t.string   "publisher"
  end

end
```

Check to see if the columns have been added:

> $ bin/rails console

    irb(main):001:0> Document.all
      Document Load (1.7ms)  SELECT "documents".* FROM "documents"
    => #<ActiveRecord::Relation [#<Document id: 6, name: "Doc1", content: "Hello World!", created_at: "2016-02-02 02:01:22", updated_at: "2016-02-02 02:01:22", author: nil, publisher: nil>, #<Document id: 7, name: "Doc2", content: "Hello World in Doc2!", created_at: "2016-02-02 02:01:33", updated_at: "2016-02-02 02:01:33", author: nil, publisher: nil>, #<Document id: 8, name: "Doc3", content: "Hello World in Doc3!", created_at: "2016-02-02 02:01:41", updated_at: "2016-02-02 02:01:41", author: nil, publisher: nil>]>

<hr>

# Routes

Rails applications are RESTful by default.

RESTful resources correspond to models in Rails.

The application's routes are stored in <i>config/routes.rb</i>

$ cat config/routes.rb

```ruby
Rails.application.routes.draw do
  resources :documents
end
```
This application only has one resource <i>documents</i>.

<i>resources :documents</i> generates a set of routes for the application.

<i>List the set of routes in an application</i>

> $ bin/rake routes

    Running via Spring preloader in process 7863
           Prefix Verb   URI Pattern                   Controller#Action
        documents GET    /documents(.:format)          documents#index
                  POST   /documents(.:format)          documents#create
     new_document GET    /documents/new(.:format)      documents#new
    edit_document GET    /documents/:id/edit(.:format) documents#edit
         document GET    /documents/:id(.:format)      documents#show
                  PATCH  /documents/:id(.:format)      documents#update
                  PUT    /documents/:id(.:format)      documents#update
                  DELETE /documents/:id(.:format)      documents#destroy


The command displays 
* the route helper prefix
* HTTP verb
* URI pattern
* Controller actions for each of the seven default RESTful actions


GET \<domain-name\>/documents executes the "index" method defined in the documents controller

POST \<domain-name\>/documents executes the "create" method defined in the documents controller

<i>NOTE: Accessing a path the DOES NOT have a corresponding controller action results in an error.</i>

The controllers can be found in <i>app/controllers</i> directory. 

Controller actions are defined as methods in the controller class. 

> $ cat app/controllers/documents_controller.rb

```ruby
class DocumentsController < ApplicationController
  before_action :set_document, only: [:show, :edit, :update, :destroy]

  # GET /documents
  # GET /documents.json
  def index
    @documents = Document.all
  end

  # GET /documents/1
  # GET /documents/1.json
  def show
  end

  # GET /documents/new
  def new
    @document = Document.new
  end

  # GET /documents/1/edit
  def edit
  end

  # POST /documents
  # POST /documents.json
  def create
    @document = Document.new(document_params)

    respond_to do |format|
      if @document.save
        format.html { redirect_to @document, notice: 'Document was successfully created.' }
        format.json { render :show, status: :created, location: @document }
      else
        format.html { render :new }
        format.json { render json: @document.errors, status: :unprocessable_entity }
      end
    end
  end

  # PATCH/PUT /documents/1
  # PATCH/PUT /documents/1.json
  def update
    respond_to do |format|
      if @document.update(document_params)
        format.html { redirect_to @document, notice: 'Document was successfully updated.' }
        format.json { render :show, status: :ok, location: @document }
      else
        format.html { render :edit }
        format.json { render json: @document.errors, status: :unprocessable_entity }
      end
    end
  end

  # DELETE /documents/1
  # DELETE /documents/1.json
  def destroy
    @document.destroy
    respond_to do |format|
      format.html { redirect_to documents_url, notice: 'Document was successfully destroyed.' }
      format.json { head :no_content }
    end
  end

  private
    # Use callbacks to share common setup or constraints between actions.
    def set_document
      @document = Document.find(params[:id])
    end

    # Never trust parameters from the scary internet, only allow the white list through.
    def document_params
      params.require(:document).permit(:name, :content)
    end
end
```

<b><i>Defining Custom Routes</i></b>

Custom routes can be configured in Rails, 
* if actions other than the default actions are needed in the application
* if custom names have to be provided for default actions
* mapping old URLs to a new Rails application
* simplifying URLs for complex actions

Consider a resource "session" that provides custom route names for default actions

GET signin for executing the "new" method in the session controller, which returns a form for the users to signin

POST signin for executing the "create" method in the session controller, which gets called when the user posts their credentials and which creates a new session in response to the request.

DELETE signin for executing the "destroy" method in the session controller, which gets called when the user performs a signout action. 

Do the following changes to <i>config/routes.rb</i>

```ruby
Rails.application.routes.draw do
  resources :documents

  get 'signin' => 'session#new'
  post 'signin' => 'session#create'
  delete 'signin' => 'session#destroy'
end
```

The newly added routes would show up in the list of routes of the application

> $ bin/rake routes

    Running via Spring preloader in process 8998
           Prefix Verb   URI Pattern                   Controller#Action
        documents GET    /documents(.:format)          documents#index
                  POST   /documents(.:format)          documents#create
     new_document GET    /documents/new(.:format)      documents#new
    edit_document GET    /documents/:id/edit(.:format) documents#edit
         document GET    /documents/:id(.:format)      documents#show
                  PATCH  /documents/:id(.:format)      documents#update
                  PUT    /documents/:id(.:format)      documents#update
                  DELETE /documents/:id(.:format)      documents#destroy
           signin GET    /signin(.:format)             session#new
                  POST   /signin(.:format)             session#create
                  DELETE /signin(.:format)             session#destroy

<b>The Root Route</b>

The root route sets the application's home page. It can be set by adding <i>root    'documents#index'</i> to the application i.e. by adding it to <i>config/routes.rb</i>

```ruby
Rails.application.routes.draw do
  resources :documents

  get 'signin' => 'session#new'
  post 'signin' => 'session#create'
  delete 'signin' => 'session#destroy'

  root 'documents#index'
end
```
Look at the list of routes now:

> $ bin/rake routes

    Running via Spring preloader in process 11695
           Prefix Verb   URI Pattern                   Controller#Action
        documents GET    /documents(.:format)          documents#index
                  POST   /documents(.:format)          documents#create
     new_document GET    /documents/new(.:format)      documents#new
    edit_document GET    /documents/:id/edit(.:format) documents#edit
         document GET    /documents/:id(.:format)      documents#show
                  PATCH  /documents/:id(.:format)      documents#update
                  PUT    /documents/:id(.:format)      documents#update
                  DELETE /documents/:id(.:format)      documents#destroy
           signin GET    /signin(.:format)             session#new
                  POST   /signin(.:format)             session#create
                  DELETE /signin(.:format)             session#destroy
             root GET    /                             documents#index


<b>Nested Resources</b>

"documents" is a resource (as models in Rails are RESTful resources).

"feedback" could be considered another resource that only belongs to "documents"

A nested resource is a resource that belongs to another resource. It can be added by specifying "resource :name_of_nested_resource" in a do-end block of the main resources declaration.

<i>config/routes.rb</i>

```ruby
Rails.application.routes.draw do
  resources :documents do
    resources :feedback
  end

  get 'signin' => 'session#new'
  post 'signin' => 'session#create'
  delete 'signin' => 'session#destroy'

  root 'documents#index'
end
```

Look at the list of routes now:

> $ bin/rake routes

    Running via Spring preloader in process 11773
                     Prefix Verb   URI Pattern                                         Controller#Action
    document_feedback_index GET    /documents/:document_id/feedback(.:format)          feedback#index
                            POST   /documents/:document_id/feedback(.:format)          feedback#create
      new_document_feedback GET    /documents/:document_id/feedback/new(.:format)      feedback#new
     edit_document_feedback GET    /documents/:document_id/feedback/:id/edit(.:format) feedback#edit
          document_feedback GET    /documents/:document_id/feedback/:id(.:format)      feedback#show
                            PATCH  /documents/:document_id/feedback/:id(.:format)      feedback#update
                            PUT    /documents/:document_id/feedback/:id(.:format)      feedback#update
                            DELETE /documents/:document_id/feedback/:id(.:format)      feedback#destroy
                  documents GET    /documents(.:format)                                documents#index
                            POST   /documents(.:format)                                documents#create
               new_document GET    /documents/new(.:format)                            documents#new
              edit_document GET    /documents/:id/edit(.:format)                       documents#edit
                   document GET    /documents/:id(.:format)                            documents#show
                            PATCH  /documents/:id(.:format)                            documents#update
                            PUT    /documents/:id(.:format)                            documents#update
                            DELETE /documents/:id(.:format)                            documents#destroy
                     signin GET    /signin(.:format)                                   session#new
                            POST   /signin(.:format)                                   session#create
                            DELETE /signin(.:format)                                   session#destroy
                       root GET    /                                                   documents#index

