# RegistrationApp

## Getting started
Pipenv install flask

pipenv install flask-sqlalchemy

Pipenv shell – starts shell. – start virtual environment

Pipenv install python-dotenv .  this allows for the reading of the .flaskenv file

Then you need you app.py file 
And the .flaskenv

Example .flaskenv
FLASK_ENV=development
FLASK_APP=app.py

Then to run flask app:
Flask run

### Creating the db
in terminal/command line run:
export SQLALCHEMY_DATABASE_URI=sqlite:///db.sqlite3

create the database:
go into python repl in terminal and then
run 
from registration_form import create_app
from registration_form.extensions import db
from registration_form.models  import member_topic_table, Member, Topic, Language
### this creates the database:
db.create_all(app=create_app())

### make inserts
when inserting data for some reason (because of use of blueprint format most likely) you have to do a :

app= create_app()
app.app_context().push()

then only can you do the inserts:
then only can you do the inserts:
(we have a multiselect for Topics so need to add them to the db)
python = Topic(name=”Python”)
js = Topic(name=”js”)
go = Topic(name=”GO”)
ruby = Topic(name=”Ruby on Rails”)

db.session.add_all([python, js, go, rugby])
