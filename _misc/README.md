# Commands

The following command-line programs are used when building Rails applications. 

### rails

The rails command can be used to
* Create an application
* Starting up the server
* Generate new code 
* Launch console

<i>Create an application</i>

> rails new <application name>

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


### gem

The gem command can be used to install Ruby gems, but maintaining versions of gems and their dependencies is a hassle.

Instead, use Bundler.

To check which gems are installed

> gem list --local

To check the documentation that gems have installed

> gem server

Visit the URL, usually

> http://localhost:8808

