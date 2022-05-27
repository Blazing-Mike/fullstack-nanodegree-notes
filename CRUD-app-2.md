## Implement Updating a Todo Item

An update involves setting the attributes of an existing object in the database

```python
## SQLAlchemy ORM
user = User.query.get(some_id)
user.name = 'Some new name'
db.session.commit()
```

**When using jinja templating in html make sure the percentage symbol has no space between the curly braces**
