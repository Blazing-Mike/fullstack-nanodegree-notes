- CREATE -> INSERT -> DB.SESSION.ADD(USER1)
- READ -> SELECT -> User.query.all()
- UPDATE -> UPDATE -> user1.foo = 'new value'
- DELETE -> DELETE -> db.session.delete(user1)


### In summary, here are the skills we'll master over these next 3 lesson as we build out this application:

- Traversing across all layers of our backend stack, from our backend server in Flask to our database in Postgres, by understanding mappings between user operations, to the ORM, to the SQL executed on a database.
- Developing using the MVC Model-View-Controller pattern, for architecting out our application
- Handling changes to our data schema over time
- Modeling relationships between objects in our web application
- Implementing Search


### Model View Controller
#### Layers
  - Models manage data and business logic for us. What happens inside models and databases, capturing logical relationships and properties across the web app objects
  - Views handle display and representation logic. What the user sees (HTML, CSS, JS from the user's perspective)
  - Controllers: routes commands to the models and views, containing control logic. Control how commands are sent to models and views, and how models and views wound up interacting with each other

[Model view image]https://video.udacity-data.com/topher/2019/August/5d5dc48f_screen-shot-2019-08-21-at-3.23.56-pm/screen-shot-2019-08-21-at-3.23.56-pm.png


- How we accept and get user data in the context of a Flask app
- Send data in controllers using database sessions in a controller
- Manipulating models adding records in SQLAlchemy Models
- Direct how the view should update within the controller and views

There are 3 methods of getting user data from a view to a controller. See the image below.
URL query parameters
Forms
JSON

forms take an action (name of the route) and method (route method) to submit data to our server.
The name attribute on a form control element is the key used to retrieve data from request.get(<key>).
All forms either define a submit button, or allow the user to hit ENTER on an input to submit the form.
