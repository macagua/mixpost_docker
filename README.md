# mixpost_docker

A [Mixpost](https://github.com/inovector/mixpost) Installation with Docker Containers.

Create all the environments values for the **Mixpost** service, executing the following commands:

```
cp .env.example .env
nano .env
```

Checkout the meaning for the environments variables:

* ``MIXPOST_APP_URL``, Mixpost App Url, like ``http://127.0.0.1:80``.

* ``MIXPOST_APP_PORT``, Mixpost App Port, like ``9000``.

* ``MIXPOST_DB_DATABASE``, Mixpost db name, like ``mixpost``.

* ``MIXPOST_DB_USERNAME``, Mixpost user name.

* ``MIXPOST_DB_PASSWORD``, Mixpost user password.

* ``MIXPOST_REDIS_PASSWORD``, Redis password.

Replace the ``CHANGE_ME_HERE`` values for the real value and save the ``.env`` file.

## Run the containers

Pull the images and run the containers, executing the following command:

```
docker-compose up -d
```

An admin user will be created automatically. Check the mixpost container logs to find out the password, executing the following command:

```
docker-compose logs -f mixpost
```

You can log in to Mixpost at ``/mixpost`` using the admin user account created.

## Create new user

Once you have installed Mixpost using Docker, you can create a new user.

Log in to Mixpost container, executing the following command:

```
docker-compose exec -it mixpost bash
```

Then, executing the following command:

```
php artisan mixpost-auth:create
```

## Conclusion

Docker is a powerful tool for managing applications in containers. By following the steps outlined in this guide, you can easily install and manage Mixpost using Docker.
