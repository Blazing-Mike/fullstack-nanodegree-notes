In this lesson, we will learn how to make changes to your data or schema during project development.

- What are migrations
- Why we use migrations
- How to install necessary libraries
- Steps to get migrations going
- Upgrades and Downgrades


Migrations deal with how we manage modifications to our data schema, over time.
Mistakes to our database schema are very expensive to make. The entire app can go down, so we want to
  - quickly roll back changes, and
  - test changes before we make them

- Migrations stack together in order to form the latest version of our database schema
- encapsulate a set of changes to our database schema, made over time. they are uniquely named
- are usually stored as local files in our project repo, e.g. a migrations/ folder
- There should be a 1-1 mapping between the changes made to our database, and the migration files that exist in our migrations/ folder.
- Our migrations files set up the tables for our database.
- All changes made to our DB should exist physically as part of migration files in our repository.

Flask-Migrate (flask_migrate) is our migration manager for migrating SQLALchemy-based database changes
Flask-Script (flask_script) lets us run migration scripts we defined, from the terminal


### Overall Steps to Set Up & Run Migrations
- Bootstrap database migrate commands: link to the Flask app models and database, link to command-line scripts for running migrations, set up folders to store migrations (as versions of the database)
- Run initial migration to create tables for SQLAlchemy models, recording the initial schema: ala git init && first git commit. Replaces use of db.create_all()
- Migrate on changes to our data models
    - Make changes to the SQLAlchemy models
    - Allow Flask-Migrate to auto-generate a migration script based on the changes
    - Fine-tune the migration scripts
    - Run the migration, aka “upgrade” the database schema by a “version”
