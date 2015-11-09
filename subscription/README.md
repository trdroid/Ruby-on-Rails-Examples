# Commands 

### Creating an application

> rails new \<name of the application\>

> rails new subscription

NOTE: Attempting to create an application with a name that is a reserved word in Ruby or Rails would 
result in an error.

### Starting the application

Change to the application directory and start the server included in the Ruby standard library known as WEBrick

> rails server (or) rails s

### Generating specific part of an application

To generate a specific part of an application, pass generate as an argument to the rails command.

> rails generate <what has to be generated> 

> rails g <what has to be generated> 

### Scaffolding

Scaffolds can be used to quickly generate temporary structures that could be experimented with. 

The scaffold command generates a model, a controller, views and tests. 

> rails generate scaffold <name of the table> <attribute:type> <attribute:type> ..

> rails generate scaffold student name:string grade:number
