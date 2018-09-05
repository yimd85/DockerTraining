Start of with creating a docker container for the node server

Tag the image by using:  ```docker build -t yimd85/visits:latest .```

When running it using ```docker run yimd85/visits```, 
we will run into errors because an instance of redis is not running.

We will needs to execute command ```docker run redis``` on the terminal