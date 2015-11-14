# Ruby on Rails

Ruby on Rails is a web framework built with Ruby. It allows for Rapid Application Development by using 
*Convention over Configuration*.

The core features of Rails is organized into libraries called *gems*. A list of few gems are

* Active Record
* Active Support
* Action Pack
* Action Mailer
* Active Resource


### Installation

Install ruby from https://www.ruby-lang.org/en/downloads/

Check to see if RubyGems is installed

> gem -v

Install rails using RubyGems

> gem install rails (or) sudo gem install rails

Install sqlite3 using RubyGems

> gem install sqlite3

*To deal with multiple versions of ruby*

Ruby and Rails can also be installed using Ruby Version Manager (RVM)

Different versions of Ruby can be managed with rbenv


### Model-View-Controller (MVC) Paradigm

The MVC paradigm is an excellent approach for building maintainable applications. It advocates to separate logically different parts of an application while enabling data flow between them. The logic for each layer is confined to the layer. 

> Models

Models represent the domain logic (API) and the domain data structure of an application. Models define the code that interacts with the tables in a database to perform actions on the data. These actions include retrieving, validating, manipulating etc.

> Controllers 

Controllers define the code that calls methods on the models to perform actions on the data on behalf of the user. 
They ensure that the user is authenticated and authorized before acting on the data via the model classes. They provide the Views with data from the model classes. 

> Views

Views display information provided by the Controllers. Rails uses a templating language called *Embedded Ruby (ERB)* which allows to embed Ruby into any kind of file. These ERB templates are preprocessed on the server side and the output is displayed to the user. 

### Testing Frameworks

Test::Unit 

MiniTest, included in Ruby's standard library

RSpec



