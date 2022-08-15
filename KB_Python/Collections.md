# Collections

## namedtuple
```py
from collections import namedtuple

# creating a user for example
#first you create a namedtuple, container
#then you create a its name e.g. User  
#then you create its attributes e.g. name role occupation age etc

User = namedtuple('User','name age role cccupation')
#and then you create an instance of the class

user = User(name='Ross', age=34, profession='coder', role='teamlead')

#and now you can access its attributes by name

user.name
#Ross

user.age
#34

```

