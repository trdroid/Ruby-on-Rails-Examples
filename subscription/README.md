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

> rails generate \<what has to be generated\> 

> rails g \<what has to be generated\> 

### Scaffolding

Scaffolds can be used to quickly generate temporary structures that could be experimented with. 

The scaffold command generates a model, a controller, views and tests. 

> rails generate scaffold <name of the table> <attribute:type> <attribute:type> ..

> rails generate scaffold student name:string grade:number

>       invoke  active_record
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

