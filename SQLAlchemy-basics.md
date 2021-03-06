 # SQLAlchemy
SQLAlchemy is the most popular open-source library for working with relational databases from Python.
It is one type of ORM library, AKA an Object-Relational Mapping library, which provides an interface for using 
object-oriented programming to interact with a database.

- when using SQLAlchemy we can forget the type of DBMS we are using, 
we can chose to use SQLITE for developement and Postgres for production

https://video.udacity-data.com/topher/2021/August/611af5f3_alchorm/alchorm.png




### Layers of SQLAlchemy
- DBAPI : Without SQLAlchemy, we'd only use a DBAPI to establish connections and execute SQL statements. Simple, but not scalable as complexity grows. SQLAlchemy generates SQL statement psycopg2 directly sends SQL statements to the database.

- The Dialect : The dialect is the system SQLAlchemy uses to communicate with various types of DBAPI implementations and databases. Dialects allow the flavor of SQL that we're using to get abstracted away from us because the dialect's layer controls the quirks and flavor of the specific database system that we're using.

- The Connection Pool : With a connection pool, the opening and closing of connections and which connection you are using when you're executing statements within a session are completely abstracted away from you. When using DBAPIs like psycopg2 to interact with database you have to manually open and close conncetions yourself

- The Engine : The enegine is the lowest level of abstraction of how we interact with the database. The Engine in SQLAlchemy refers to both itself, the Dialect and the Connection Pool, which all work together to interface with our database.

- SQL Expressions: Instead of sending raw SQL (using the Engine), we can compose python objects to compose SQL expressions, instead. SQL Expression still requires knowing and using SQL to interact with a DB

- SQLAlchemy ORM (optional) : The highest level of abstraction, it lets you compose SQL expression by mapping python classes or objects to tables in the database
- 
[SQLAlchemy Layers of Abstraction Overview (Diagram)](https://video.udacity-data.com/topher/2019/August/5d4de779_sqlalchemy-layers-of-abstraction/sqlalchemy-layers-of-abstraction.png)

## Mapping between Tables and classes
How classes in python maps to tables in SQL 

In python
<code>
 class Human:
   def __init__(self, first_name, last_name, age):
       self.first_name = first_name
       self.last_name = last_name
       self.age= age
 </code>
 
 <code>
 CREATE TABLE humans (
   id INTEGER PRIMARY KEY,
   first_name VARCHAR,
   last_name VARCHAR,
   age INTEGER
);
 </code>
 
 ## A simple Flask App
 This chapter was an exercise, install Flask and Flask-alchemy, then built a simple Hello Flask app
 
 ## Db.Model and defining models
 Given an instance of the SQLAlchemy class from Flask-SQLAlchemy,
 
 <code>db = SQLAlchemy(app) </code>
 
 - db is an interface for interacting with our database
 - db.Model lets us create and manipulate data models
 - db.session lets us create and manipulate database transactions

## Inserting records and using debug mode
We can insert records into our table using the psql terminal, something like this;
<code>
INSERT INTO persons (name) VALUES ('Amy');
SELECT * from persons;
      </code>
      
  - add the FLASK_DEBUG=true flag to turn debug mode on


## Experimenting in Interactive Mode

I had issue with ModuleErrorNotFound: error in python because i don't have those packages installed in my virtual environment, so i had to install them in my virtualenv

## SQLAlchemy Constraints
- Column constraints ensure data integrity across our database, allowing for database accuracy and consistency


## Recap
- How the components of SQL Alchemy and ORM are structured
- What are dialects
- What is a connection pool
- How does the core engine work
- How classes and tables are mapped
- How models are defined
- How data types are handled
- How to define constraints

### cheatsheet
https://github.com/crazyguitar/pysheeet/blob/master/docs/notes/python-sqlalchemy.rst#set-a-database-url
