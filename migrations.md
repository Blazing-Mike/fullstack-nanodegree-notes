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
