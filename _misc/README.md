# Commands

### Gems

To check which gems are installed

> gem list --local

To check the documentation that gems have installed

> gem server

Visit the URL, usually

> http://localhost:8808

### Starting up Rails

> rails server (or) rails s

*NOTE: Depending on how the Rails environment is setup, the commands might have to be preceded with bundle exec*

For eg. 

> bundle exec rails

> bundle exec rake

To avoid this extra typing, try *binstubs*

The command above starts a WeBrick server. A WeBrick server supports testing applications during development and is not meant for large scale deployment. By default, it binds to localhost at 0.0.0.0 or 127.0.0.1 and is not accessible from other computers. 

An address for the server can be specified with -b and -p (port) options to make it accessible from other computers. 

### Server restart

In development mode, a server restart is not required for code changes.

A server restart is needed on
* configuration changes
* adding scopes
* installing gems

