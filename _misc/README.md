# Commands

The following command-line programs are used when building Rails applications. 

### rails

The rails command can be used to
* Create an application
* Starting up the server
* Generate new code 
* Launch console

<i>Create an application</i>

> rails new \<application name\>

<i>Starting up the server</i>

> rails server (or) rails s

*NOTE: Depending on how the Rails environment is setup, the commands might have to be preceded with bundle exec*

For eg. 

> bundle exec rails

> bundle exec rake

To avoid this extra typing, try *binstubs*

The command above starts a WeBrick server. A WeBrick server supports testing applications during development and is not meant for large scale deployment. By default, it binds to localhost at 0.0.0.0 or 127.0.0.1 and is not accessible from other computers. 

An address for the server to use can be specified with -b and -p (port) options to make it accessible from other computers.

<i> Server restart </i>

In development mode, a server restart is not required for code changes.

A server restart is needed on
* configuration changes
* adding scopes
* installing gems

<i>Generate new code</i>

New code can be generated using the sub-command <i>generate</i>

> rails generate

<i>Launch console for a database</i>

> rails dbconsole

### rake

Rake is Ruby's version of make. 

Rake is an automated build tool used to run tasks of an application. 

<i> To see a list of available tasks of an application </i>

> bin/rake --tasks

<i>Origins of the tasks in an application</i>

The tasks in an application are added by some of the gems. However, custom tasks can also be added to an application by writing Ruby scripts and saving them under lib/tasks

### gem

The gem command can be used to install Ruby gems, but maintaining versions of gems and their dependencies is a hassle.

Instead, use Bundler (the bundle command).

To check which gems are installed

> gem list --local

To check the documentation that gems have installed

> gem server

Visit the URL, usually

> http://localhost:8808

### bundle

The bundle command is used to install and update the gems needed by an application. 

The bundle command reads and installs the gems listed in the <i>Gemfile</i> stored in the app's root directory. The <i>Gemfile</i> is created by the <i>rails new</i> command

It stores the version numbers of gems and their dependencies used in an application in the file Gemfile.lock

<i>Installing gems and their dependencies</i>

The <i>rails new</i> command runs the following bundle command to install the gems and their dependencies when creating an application.

> bundle install

<i> Listing the names and version of gems </i>

> bin/bundle list

<hr>

# Models

Resources in REST correspond to models in Rails. 

REST maps HTTP verbs with the CRUD operations of the database to deal with the resources

| HTTP Verb     | Database Action   |
| --------|---------|
|   GET |  read  |
|  POST |  create |
|  PATCH |  update |
|  DELETE |  delete |

# Controllers

Clients interact with a Rails application through a collection of URLs and HTTP verbs. 

Any web requests received by a Rails application is routed to an appropriate controller which determines how to handle a request based on the HTTP verb. 

The controllers in Rails connect an application's models with its views. It processes requests and returns response to the clients.  

Generally, the controllers interact with models and get data from them to render an appropriate view or just redirect to another location.

