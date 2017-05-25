# Docker quick cheat sheet


#### Build an image from where the dockerfile is located:

    $ docker build -t EXAMPLE_IMAGE_NAME .

#### Run a image in a new container

    $ docker run -t -d EXAMPLE_IMAGE_NAME <command>

#### Run image in a named container and expose port 8080 from docker container to port 8080

    $ docker run -d -p 8080:8080 --name EXAMPLE_IMAGE EXAMPLE_IMAGE_NAME

#### Run image on a container, expose port 8080 and mount volume on target current location
    $ docker run -d -p 8080:8080 -v /.:/var/www/my-app EXAMPLE_IMAGE_NAME

#### List current active images

    $ docker ps

#### List all images

    $ docker ps -a

#### Get the container logs

    $ docker logs EXAMPLE_IMAGE

#### Get to a command line inside of the container

    $ docker exec -it EXAMPLE_IMAGE_NAME /bin/sh

#### Remove all images
    $ docker rmi $(docker images -a -q)


#### Stop all the containers

    $ docker stop $(docker ps -a -q)

#### Remove all the containers
    $ docker rm $(docker ps -a -q)