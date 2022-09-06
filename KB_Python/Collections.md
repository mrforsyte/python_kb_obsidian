# Collections

A collection is data that answers yes to all further questions:
* Can I know the size of this data? YES - __SIzed__
* Can I produce elements from this data one at a time? Yes - __iterable__
* Can I check whether an element is in this data set? Yes - __Container__
Not all collection encode data in the same manner:
* Is data ordered(sequential) or unordered?
* Is the data assiciative. mapping vetween keys and values?
* is the data unique?

Depending on answers the data may be __Sequence__, __Set__, __Mapping__;



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

