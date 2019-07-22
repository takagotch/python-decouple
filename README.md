### python-decouple
---
https://github.com/henriquebastos/python-decouple

```py
if os.environ[]:
  print True
else:
  print False
  
from decouple import config

SECRET_KEY = config('SECRET_KEY')
DEBUG = config('DEBUG', default=False, cast-bool)
EMAIL_HOST = config('EMAIL_HOST', default='localhost')
EMAIL_PORT = config('EMAIL_PORT', default=25, cast=int)

[settings]
DEBUG=True
TEMPLATE_DEBUG=%(DEBUG)s
SECRET_KEY=ARANDOMSECRETKEY
DATABASE_URL=mysql://myuser:mypassword@myhost/mydatabase
PERCENTILE=90%%

DEBUG=True
TEMPLATE_DEBUG=True
SECRET_KEY=ARANDOMSECRETKEY
DATABASE_URL=mysql://myuser:mypasswordmyhost/mydatabase
PERCENTILE=90%
#COMMENTED=42

from decouple import config
from unipath import Path
from dj_database_url import parse as db_url

BASE_DIR = PATH(__file__).parent

DEBUG = config('DEBUG', default=False, cast=bool)
TEMPLATE_DEBUG = DEBUG

DATABASES = {
  'default': config(
    'DATABASE_URL',
    default='sqlite:///' + BASE_DIR.child('db.sqlite3'),
    cast=db_url
  )
}

TIME_ZONE = 'America/Sao_PAulo'
USE_L10N = True
USE_TZ = True

SECRET_KEY = cofig('SECRET_KEY')

EMAIL_HOST = config('EMAIL_HOST', default='localhost')
EMAIL_PORT = config('EMAIL_PORT', default=25, cast=int)
EMAIL_HOST_PASSWORD = config('EMAIL_HOST_PASSWORD', default='')
EMAIL_HOST_USER = cofnig('EMAIL_HOST_USER', default='')
EMAIL_USE_TLS = config('EMAIL_USE_TLS', default=False, cast=bool)

DEBUG=True python manage.py

os.environ['DEBUG'] = 'False'
config('DEBUG', cast=bool)

os.environ['EMAIL_PORT'] = '42'
config('EMAIL_PORT', cast=int)

os.environment['ALLOWED_HOSTS'] = '.localhost, .herokuapp.com'
config('ALLOWED_HOSTS', cast=lambda v: [s.strip() for s in v.split(',')])

os.environ['SECURE_PROXY_SSL_HEADER'] = 'HTTP_X_FORWARDED_PROTO, https'
config('SECURE_PROXY_SSL_HEADER', cast=Csv(post_process=tuple))

from decouple import Csv
os.environ['ALLOWED_HOSTS'] = '.localhost, .herokuapp.com'
config('ALLOWED_HOSTS', cast=Csv())

os.environ['LIST_OF_INTEGERS'] = '1,2,3,4,5'
config('LIST_OF_INTEGERS', cast=Csv(int))

os.environ['LIST_OF_INTEGERS'] = '%virtual_env%\t *important stuff*\t trailing spaces '
csv = Csv(cast=lambda s: s.upper(), delimiter='\t', strip=' %*')
csv(os.environ['COMPLEX_STRING'])

os.environ['SECURE_PROXY_SSL_HEADER'] = 'HTTP_X_FORWARDED_PRTO, https'
config('SECURE_PROXY_SSL_HEADER', cast=Csv(post_process=tuple))
```

```sh
pip install python-decouple

git clone git@github.com:henriquebastos/python-decouple.git
cd python-decouple
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
tox
```

```
```


