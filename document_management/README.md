<i>Creating the application</i>

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

<i>Contents of document_management</i>

> $ cd document_management

> $ ls
  
    app  bin  config  config.ru  db  Gemfile  Gemfile.lock  lib  log  public  Rakefile  README.rdoc  test  tmp  vendor

<i>Contents of document_management/bin</i>

> $ ls bin
  
    bundle  rails  rake  setup  spring

<hr>

<i>Contents of the Gemfile</i>

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


<i>Start WEBrick server</i>

> $ bin/rails server

Visit localhost:3000 in the browser


<hr>

### Scaffold

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

Run rake to run the database migration created in the previous step. This would create a table named <i>document</i> with the fields: 
* id
* name
* content
* created_at
* updated_at

<b>id</b> is a unique and auto-incrementing integer that identifies each row uniquely.

name, content fields are to hold the name and content of <i>a document</i>

<b>created_at and updated_at</b> are fields that the framework deals with. They are used to track the creation and last updated timestamps. 

> $ bin/rake db:migrate

    Running via Spring preloader in process 2763
    == 20160129144122 CreateDocuments: migrating ==================================
    -- create_table(:documents)
       -> 0.0019s
    == 20160129144122 CreateDocuments: migrated (0.0021s) =========================



