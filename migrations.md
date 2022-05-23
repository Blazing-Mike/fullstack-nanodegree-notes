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
