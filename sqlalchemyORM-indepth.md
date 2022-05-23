## SQLAlchemy ORM

SQLAlchemy and SQLAlchemy ORM is one of the most popular libraries for building and interacting with models in a Python environment

- db.Model.query offers us the Query object. The Query object lets us generate SELECT statements that let us query and return slices of data from our database.
- Query allows method chaining.
- The Query object can be accessed on a model using either:
    - MyModel.query directly on the model, or
    - db.session.query(MyModel) using db.session.query instead.


### SQLAlchemy Object Lifecycle 
- Within a session, we create transactions every time we want to commit work to the database.
- The ability to undo is allowed via db.session.rollback()
- A flush takes pending changes and translates them into commands ready to be committed. It occurs
      - when you call Query. Or
      - on db.session.commit()

#### Describe why a query is not necessarily considered a transaction?
- Your reflection A query is not considered a transaction because it retrieves data from the database and do make not changes to i

- A database transaction changes (or potentially changes) data in one or more places in a database. At any point during processing, if there was a disconnect, it is possible that part of the transaction was completed, when part of it did not. This is the essence of CRUD development because data is constantly changing. A query simply reflects data as it rests in the database, so if there was a disconnect during processing, the data is still 100% fully intact
