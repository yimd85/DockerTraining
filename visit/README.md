Start of with creating a docker container for the node server

Tag the image by using:  ```docker build -t yimd85/visits:latest .```

When running it using ```docker run yimd85/visits```, 
we will run into errors because an instance of redis is not running.

We will needs to execute command ```docker run redis``` on the terminal

in order for our containers to network together, we can use docker-compose (different from docker CLI). Docker-compose allows multiple Docker CLI commands to be ran - this helps us automate the commands from the docker cli, and start multiple containers.
All the docker-compose commands will be placed on the yml file