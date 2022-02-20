# Django - docker compose templates

## Created using [this tutorial](https://testdriven.io/blog/dockerizing-django-with-postgres-gunicorn-and-nginx/#nginx)

Generic starting docker templates for django projects with development and production variants. Ready for apps to be crated.

Makes use of:
* Alpine Python
* PostgreSQL
* nginx

Requires .env and .env.db files:

```
# .env.prod
DEBUG=0
SECRET_KEY=a_secret_key
DJANGO_ALLOWED_HOSTS=localhost 127.0.0.1 [::1]
DB_ENGINE=django.db.backends.postgresql
POSTGRES_USER=new_user
POSTGRES_PASSWORD=new_password
POSTGRES_DB=new_db
POSTGRES_HOST=db
POSTGRES_PORT=5432
# This is for the entrypoint
DATABASE=postgres
```

```
# .env.db
POSTGRES_USER=new_user
POSTGRES_PASSWORD=new_password
POSTGRES_DB=new_db
```

Following this, just run `docker-compose -f docker-compose.prod.yml up -d --build`

