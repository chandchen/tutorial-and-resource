# Testing in Django

> [Django Documentation](https://docs.djangoproject.com/en/1.11/topics/testing/)

#### 1. The test client

Simulate GET and POST requests on a URL and observe the response

```python
from django.test import Client

client = Client()
response = client.get('/any/urls/')  # Path of the URL, not whole domain
response.content

response = client.post('/any/urls/', {'user': 'test', 'pwd': 'test'})
response.status_code

# url equal to /any/urls/?user=test&pwd=test
# test code path that use django.http.HttpRequest.is_ajax() method
response = client.get('/any/urls/', {'user': 'test', 'pwd': 'test'},
                      HTTP_X_REQUESTED_WITH='XMLHttpResquest')
```

#### 2. Factory Boy

It provides a declarative syntax for how new instances should be created.

> [Documentation](http://factoryboy.readthedocs.io/en/latest/)

```
$ pip install factory_boy
```

Using factories

```python
import factory
from django.contrib.auth.models import User
from django.utils import timezone

class UserFactory(factory.DjangoModelFactory):
    
    class Meta:
        model = User

    # with random yet realistic values
    first_name = factory.Faker('first_name')
    last_name = factory.Faker('last_name')

    # generate unique values in a specific format
    email = factory.Sequence(lambda n: 'user{0}@test.com'.format(n))
    # generate using static values from other elements
    email = factory.LazyAttribute(lambda a: '{0}.{1}@test.com'.format(a.first_name, a.last_name).lower())

    # when instantiate a user from UserFactory, will create a password attribute by calling User.set_password('test')
    password = factory.PostGenerationMethodCall('set_password', 'test')

    # receive a function taking no argument and return the value
    time_joined = factory.LazyFunction(timezone.now)
    status = 'pending'

    # when many fields should be updated based on a flag
    class Params:
        shipped = factory.Trait(
            status = 'shipped',
            ...
        )
```

#### 3. Mock

> [Documentation](http://www.voidspace.org.uk/python/mock/)

#### 4. Coverage

> [Documentation](https://coverage.readthedocs.io/en/coverage-4.4.1)
