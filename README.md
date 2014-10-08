# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

rails new BunnyApp --database=postgresql -T

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command should I type in the terminal?

rails g model Bunny name:string color:string age:integer (by default evrything is string, )

rails g migration CreateBunny name color age
rails g migration CreateBunny name color age:integer
we can then edit db/migrate to add "not NULL" etc
we can add model manually --> I forgot about this one

### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

rails g model: creates a file in app/models/bunny.rb, which defines buny as ruby class. AND creates migration file in db/migrate with the columns and data types that were specified in terminal

rails g migration: creates a migration file in db/migrate with the columns and datatypes that were specified in terminal comand. db/schema is NOT created untill you actualy run the migration

it adds to schema.rb a block, which defines variable names for the table "create_bunny".
It creates model which looks like this:
class Bunny < ActiveRecord::Base
end

The database is basically empty. It is now ready for migration, it is ready to be populated by entries

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

rake db:create --> forgot this
rake db:migrate
can also do rake db:create db:migrate (all in one line!)

if you did rails g migration then your model files still do not exist
### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?

type rails db to bring up database console within rails,
type \d to see what databases have been created --> do not need at this point

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

rake routes, but I am not sure about this one

### Question 7

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

rails server and then navigate to the home page of my app
localhost:3000 --> forgot about this one
