# commands

 - docker build -t friendlyhello .
 - docker images
 - docker run -p 4000:80 friendlyhello
 - docker run -d -p 4000:80 friendlyhello  (in background)
 - docker container ls
 - sudo docker container stop 67303d97ca0b
 - docker login
 - sudo docker tag friendlyhello huertix/get-started:test
 - sudo docker push huertix/get-started:test
 - sudo docker run -p 4000:80 huertix/get-started:test



# services

 - let's create docker-compose.yml, we will create a load balancing server
	 - docker swarm init
	 - docker stack deploy -c docker-compose.yml getstartedlab
	 - docker service ls
	 - docker service ps getstartedlab_web
	 - docker container ls -q
	 - docker stack rm getstartedlab
	 - docker swarm leave --force
	 - 



# Cheat list

- docker build -t friendlyname .  # Create image using this directory's Dockerfile
- docker run -p 4000:80 friendlyname  # Run "friendlyname" mapping port 4000 to 80
- docker run -d -p 4000:80 friendlyname         # Same thing, but in detached mode
- docker container ls                                # List all running containers
- docker container ls -a             # List all containers, even those not running
- docker container stop <hash>           # Gracefully stop the specified container
- docker container kill <hash>         # Force shutdown of the specified container
- docker container rm <hash>        # Remove specified container from this machine
- docker container rm $(docker container ls -a -q)         # Remove all containers
- docker image ls -a                             # List all images on this machine
- docker image rm <image id>            # Remove specified image from this machine
- docker image rm $(docker image ls -a -q)   # Remove all images from this machine
- docker login             # Log in this CLI session using your Docker credentials
- docker tag <image> username/repository:tag  # Tag <image> for upload to registry
- docker push username/repository:tag            # Upload tagged image to registry
- docker run username/repository:tag                   # Run image from a registry

- docker stack ls                                            # List stacks or apps
- docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
- docker service ls                 # List running services associated with an app
- docker service ps <service>                  # List tasks associated with an app
- docker inspect <task or container>                   # Inspect task or container
- docker container ls -q                                      # List container IDs
- docker stack rm <appname>                             # Tear down an application
- docker swarm leave --force      # Take down a single node swarm from the manager