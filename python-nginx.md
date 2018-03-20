# Install Docker

https://docs.docker.com/install/linux/docker-ce/ubuntu/

# Setup a simple webserver to host your application

Go to the project subfolder of this repository

```
docker-compose build
docker-compose up -d
```

Use browser to go to http://localhost/app

Modify the requirements.txt and the main.py script accordingly,
redo the build process:

```
docker-compose build --no-cache
docker-compose stop
docker-compose rm -f
docker-compose up -d
```


