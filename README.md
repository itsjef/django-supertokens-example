Django Supertokens Example
==========================

## Start Supertokens

```shell
$ docker compose up
```

## Create first user

Open Django shell: `python manage.py shell` and type:

```python
from api.models import SupertokensUser                                     
from supertokens_python.recipe.emailpassword.syncio import sign_up         

username, password = 'test@example.com', '123456'                          
resp = sign_up(username, password)                 
u = SupertokensUser(id=resp.user.user_id, email=username)                  
u.save()                                          
```

## Start Django Server

(to-be-updated)

## Sign In

Using [httpie](https://httpie.io/)

```shell
$ http POST :8000/api/auth/signin formFields:='[{"id":"email","value":"test@example.com"},{"id":"password","value":"123456"}]'
```
