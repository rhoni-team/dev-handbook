# Useful manage.py commands


## Generate a secret key

```bash
python manage.py shell

from django.core.management.utils import get_random_secret_key
print(get_random_secret_key())
```

## Change superuser password

```bash
python manage.py changepassword <user_name>
```
