# Install Docker

https://docs.docker.com/install/linux/docker-ce/ubuntu/

Check if the ``docker-compose`` command is available, if not - install it:
```
sudo pip install docker-compose
```

# Setup a simple webserver to host your application

Go to the project subfolder of this repository

```
docker-compose build
docker-compose up -d
```

Use browser to go to http://localhost/app

Modify the the main.py script accordingly,
after each change restart the python WSGI service:

```
docker-compose restart backend
```

If you need to add pip modules - add them to requirements.txt and rebuild:

```
docker-compose build --no-cache
docker-compose stop
docker-compose rm -f
docker-compose up -d
```
